# Container Deployment Notes

## Checkpoint 3 — Confirming the Docker Environment

```bash
docker --version
```
Prints the installed Docker version, confirming the CLI is available and working.

```bash
docker info
```
Displays a detailed snapshot of the current Docker environment — number of containers and images, storage driver, and overall daemon health.

<img width="482" height="860" alt="image" src="https://github.com/user-attachments/assets/4445b178-df5b-46f9-bc2c-6475644643db" />


## Checkpoint 4 — Launching Nginx in a Container

**Step 1 — Pull the image:**
```bash
docker pull nginx
```

**Step 2 — Start the container in the background, exposing it on port 8080:**
```bash
docker run -d -p 8080:80 --name nginx-server nginx
```

**Step 3 — Test that it's actually reachable:**
```bash
curl http://localhost:8080
```
A successful response returns the default "Welcome to nginx!" HTML page.

<img width="660" height="597" alt="image" src="https://github.com/user-attachments/assets/a685e52f-a3ed-4084-855f-ce99de386434" />


## Checkpoint 5 — Managing the Container's Lifecycle

| Command | Purpose |
|---|---|
| `docker ps` | Shows every container currently running, along with its status and port mapping. |
| `docker stop nginx-server` | Sends a graceful shutdown signal to stop the container. |
| `docker ps -a` | Lists all containers, running or not, so you can confirm `nginx-server` now reads "Exited." |
| `docker rm nginx-server` | Deletes the stopped container and frees up its resources on the host. |

<img width="658" height="210" alt="image" src="https://github.com/user-attachments/assets/efdab690-719f-4c3c-930c-14442bf9d817" />
