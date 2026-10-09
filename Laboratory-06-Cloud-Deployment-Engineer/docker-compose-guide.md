# Docker Compose Guide

## The docker-compose.yml File
```yaml
version: '3'

services:
  database:
    image: mariadb:10.6
    environment:
      - MYSQL_ROOT_PASSWORD=cloudnova_root
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user

  app:
    image: nextcloud
    ports:
      - 8080:80
    environment:
      - MYSQL_PASSWORD=cloudnova_pass
      - MYSQL_DATABASE=nextcloud_db
      - MYSQL_USER=nextcloud_user
      - MYSQL_HOST=database
```

## Code Explanation
| Line | Purpose |
|------|---------|
| `version: '3'` | Compose file format version (newer Compose releases treat this as obsolete and ignore it). |
| `services:` | Defines every container that makes up the application. |
| `database:` / `app:` | Names of the two services. These names also act as hostnames on the network. |
| `image:` | The Docker image used to create the container. |
| `ports: - 8080:80` | Maps port 8080 on the host to port 80 in the Nextcloud container. |
| `environment:` | Passes configuration (database name, user, passwords) into the container. |

## What does the `services:` block do?
The `services:` block defines each container that is part of the application. Every entry under it (`database` and `app`) is one service with its own image, ports and environment variables. Docker Compose creates, networks and manages all of these services together as one stack.

## How did the Nextcloud container find the database container?
Docker Compose places all services in the same default network and registers each service name as a DNS hostname. The line `MYSQL_HOST=database` tells Nextcloud to connect to the host named `database`, which is the name of the MariaDB service. Docker resolves that name to the database container's IP address, so no IP address has to be written manually.

## Difference between `docker run` and `docker-compose up -d`
| `docker run` | `docker-compose up -d` |
|--------------|------------------------|
| Starts a single container | Starts all containers defined in the YAML file |
| All options are typed manually each time | Options are saved in a reusable file |
| Networking between containers must be set up by hand | A shared network is created automatically |
| Harder to repeat and share | Repeatable and can be version-controlled (Infrastructure as Code) |

The `-d` flag runs the containers in the background (detached mode).
