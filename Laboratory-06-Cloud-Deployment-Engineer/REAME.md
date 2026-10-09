# Laboratory 06 – The Cloud Deployment Engineer

## Mission Overview
In this mission I acted as a Cloud Deployment Engineer at CloudNova Technologies. Instead of deploying single containers by hand, I used **Docker Compose** to define and deploy a two-tier private cloud storage system, made up of a **Nextcloud** web container and a **MariaDB** database container, from one YAML file. This is an example of Infrastructure as Code (IaC).

## Objectives
- Explain the concept of a multi-tier application architecture
- Understand the purpose and structure of a `docker-compose.yml` file
- Use the `nano` text editor to create configuration files
- Deploy a multi-container application (Nextcloud + MariaDB) using Docker Compose
- Document the deployment and IaC principles using Markdown
- Continue expanding my GitHub Cloud Computing Portfolio

## Commands Executed
```bash
mkdir nextcloud-deployment        # create project directory
cd nextcloud-deployment           # move into it
nano docker-compose.yml           # write the Compose file
docker-compose up -d              # deploy both containers in the background
docker-compose ps                 # verify the containers are running
docker-compose down               # stop and remove the whole stack
```
Nextcloud was accessed through the KillerCoda Traffic/Ports tab on port **8080**.

## Screenshots
| Evidence | File |
|----------|------|
| Successful deployment and running containers | <img width="779" height="734" alt="image" src="https://github.com/user-attachments/assets/0d2efd33-2a8e-4c7f-8bc8-605ba6058921" />
 |
| Nextcloud installation page in the browser | <img width="970" height="511" alt="image" src="https://github.com/user-attachments/assets/bce6d19c-2b11-4695-b7b0-3711c794e2f4" />
 |
| Containers stopped and removed | <img width="771" height="732" alt="image" src="https://github.com/user-attachments/assets/283f4ca0-7226-4e2b-8e92-169f1e9334b7" />
 |

## Repository Contents
- `multi-tier-architecture.md` – two-tier architecture research
- `docker-compose-guide.md` – explanation of the Compose file
- `reflection.md` – mission reflection
- `screenshots/` – evidence screenshots

## Skills Learned
- Writing a valid, indentation-sensitive YAML Compose file
- Deploying and tearing down a multi-container stack with one command each
- Connecting containers using service names as hostnames
- Passing configuration to containers with environment variables
- Mapping host ports to container ports to reach an app from the browser
- Documenting infrastructure with Markdown and Git
