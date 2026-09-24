# MinIO Deployment Documentation

## Docker Command Used

> **Note:** The lab's original command uses `minio/minio`, but MinIO discontinued free Docker Hub images in October 2025, so that image is no longer pullable. This deployment uses `tobi312/minio`, a community-maintained image with an identical command-line interface and environment variables, as a drop-in replacement.

```bash
docker run -d -p 9000:9000 -p 9001:9001 --name minio-server \
  -e "MINIO_ROOT_USER=cloudadmin" \
  -e "MINIO_ROOT_PASSWORD=CloudNova2026!" \
  tobi312/minio:latest server --console-address ":9001" /data
```

## Access Details

- **Web Console Port:** 9001 (accessed via the KillerCoda "Traffic / Ports" tab)
- **API Port:** 9000 (used by S3-compatible clients/SDKs to talk to the server)
- **Bucket Created:** `client-photos`

## Explanation of the `-e` (Environment Variable) Flags

- `-e "MINIO_ROOT_USER=cloudadmin"` sets the administrator username used to log in to the MinIO console. Environment variables let you configure the container at startup without baking credentials into the image itself.
- `-e "MINIO_ROOT_PASSWORD=CloudNova2026!"` sets the administrator password paired with that username. Together, these two variables are how MinIO knows what credentials to require for console and API access — the same pattern most containerized services use to inject configuration/secrets at runtime instead of hardcoding them.

## Screenshots

<img width="1917" height="1015" alt="image" src="https://github.com/user-attachments/assets/0f90330c-c8db-4ff2-9a13-51d7870447b7" />
 — terminal showing the container running.
<img width="1917" height="1015" alt="image" src="https://github.com/user-attachments/assets/9c1683fa-29b1-49b0-b35a-598cc6cddf5d" />
 — MinIO console showing the `client-photos` bucket and uploaded file.
