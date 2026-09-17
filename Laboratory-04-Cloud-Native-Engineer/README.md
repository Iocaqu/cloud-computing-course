# Mission 4: The Cloud-Native Engineer

## Overview
This activity walks through the shift from managing servers to managing services. Working in the KillerCoda Playground, I compared traditional Virtual Machines against containers, ran core Docker CLI operations, and stood up a live Nginx container to see the difference in practice.

## What I Set Out to Do
- Explain how VMs and Containers differ architecturally.
- Spin up and verify a Docker-enabled environment in KillerCoda.
- Run the essential Docker CLI commands.
- Deploy, expose, manage, and tear down an Nginx container.
- Document each step clearly in Markdown.
- Keep building out my GitHub Cloud Computing Portfolio.

## Commands Used

```bash
docker --version
docker info
docker pull nginx
docker run -d -p 8080:80 --name nginx-server nginx
curl http://localhost:8080
docker ps
docker stop nginx-server
docker ps -a
docker rm nginx-server
```

## What I Learned
- How to check the health and status of a Docker environment from the CLI.
- The difference between pulling an image and running a container from it.
- Why port mapping (`-p host:container`) is what actually makes a containerized service reachable.
- The full container lifecycle: start, inspect, stop, verify, remove.
- Where containers win over VMs on speed and resource footprint.

## Challenges I Ran Into
- *(Add your own — port conflicts, typos in flags, KillerCoda session expiring mid-task, etc., and how you got past them.)*
