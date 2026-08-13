# Cloud Infrastructure Components (Variant 2: Table Format)

| Component | Purpose | Why It Matters in Cloud Computing | Relation to KillerCoda Environment |
|---|---|---|---|
| **Compute** | Provides the CPU and memory that run applications and processes. | Lets providers scale processing power up/down on demand instead of buying fixed hardware. | The container's CPU cores (`lscpu`/`nproc`) and RAM (`free -h`) are its allocated compute resource. |
| **Storage** | Holds data persistently — OS files, logs, application data. | Cloud storage is durable and scalable, and decoupled from any single compute instance. | The root filesystem and mounted volumes shown by `df -h`/`mount` are the container's storage. |
| **Networking** | Connects instances to each other and the internet via IPs, routing, and firewall rules. | Determines what's reachable and secure — central to any cloud deployment. | The hostname and IP (`hostname`, `ip addr`) show how the container is addressed on its network. |
| **Operating System** | Manages hardware resources and provides the runtime for applications. | Affects compatibility, patching, and available tooling; providers offer many OS images to choose from. | The Linux distro/kernel (`os-release`, `uname -r`) running the playground is the base image, just like a cloud VM image. |
