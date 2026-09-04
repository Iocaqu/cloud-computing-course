# Client Recommendations

## Checkpoint 4 — Recommendations

**Client A (Startup, limited budget, fast growth) → AWS**
Pay-as-you-go pricing and a free tier keep early costs low, while AWS's scale means the startup never has to migrate providers as it grows. Services: EC2, S3, Lambda.

**Client B (University, Windows Server/M365/AD) → Azure**
Extends their existing Active Directory into the cloud via Entra ID instead of replacing it, minimizing retraining and risk. Services: Azure Virtual Machines, Microsoft Entra ID, Azure Virtual Desktop.

**Client C (AI research, needs HPC) → GCP**
Purpose-built ML infrastructure (TPUs) and tooling (Vertex AI, BigQuery ML) matches the client's exact workflow needs. Services: Compute Engine with TPUs/GPUs, Vertex AI, BigQuery.

**Client D (Global e-commerce, high availability, auto-scaling) → AWS**
Largest global region/AZ footprint plus mature, battle-tested auto-scaling and CDN services for worldwide low-latency delivery. Services: EC2 Auto Scaling, CloudFront, RDS Multi-AZ.

## Checkpoint 6 — Decision Matrix

| Requirement | Platform | Why |
|---|---|---|
| Startup | AWS | Pay-as-you-go + widest service range to grow into |
| Enterprise | AWS / Azure | AWS for breadth; Azure if Microsoft-invested |
| Microsoft Environment | Azure | Native AD/M365/Windows Server integration |
| AI/ML | GCP | TPUs, Vertex AI, strong analytics tooling |
| Kubernetes | GCP | Created K8s; GKE is most mature managed offering |
| Global Web App | AWS | Largest region/AZ footprint, mature auto-scaling/CDN |
