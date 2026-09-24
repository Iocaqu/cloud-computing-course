# Storage Types Research

## Comparison of Cloud Storage Types

| Storage Type | Description | Primary Use Case | Cloud Provider Example |
|---|---|---|---|
| **Block Storage** | Splits data into fixed-size blocks, each with a unique address, and manages them independently of the file system. Behaves like a raw hard drive attached to a server. | High-performance workloads that need low-latency, structured read/write — databases, virtual machine disks, transactional systems. | AWS EBS (Elastic Block Store) |
| **File Storage** | Organizes data in a hierarchical folder/file structure, accessed through standard file-system protocols (e.g., NFS, SMB), often shared across multiple servers at once. | Shared file access for multiple users or applications — home directories, content management systems, shared application data. | AWS EFS (Elastic File System) |
| **Object Storage** | Stores data as discrete objects (data + metadata + a unique identifier) in a flat namespace, accessed over HTTP APIs rather than a file-system path. Scales essentially without limit. | Massive amounts of unstructured data — images, videos, backups, static website assets, big-data archives. | AWS S3 (Simple Storage Service) |

## Why Object Storage for the Client's Photos

Object Storage is the best fit for a photo-sharing application because it can scale to millions (or billions) of files without the performance and management overhead that Block or File storage would hit at that scale. Each photo is stored as an independent object with rich metadata and is accessible directly over HTTP, which makes it simple to serve images straight to a web or mobile app without routing traffic through the application server. It's also far more cost-effective and durable for this kind of unstructured, rarely-modified data than provisioning and managing raw block volumes.
