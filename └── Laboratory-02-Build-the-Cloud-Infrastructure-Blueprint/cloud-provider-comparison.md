# Cloud Provider Comparison (Variant 2: Expanded Table)

| Infrastructure Component | AWS | Microsoft Azure | Google Cloud Platform |
|---|---|---|---|
| Compute (VMs) | EC2 | Virtual Machines | Compute Engine |
| Serverless Compute | Lambda | Azure Functions | Cloud Functions |
| Object Storage | S3 | Blob Storage | Cloud Storage |
| Networking (Virtual Network) | VPC (per-region) | Virtual Network / VNet (per-region) | VPC (global) |
| Identity & Access Management | AWS IAM | Microsoft Entra ID (formerly Azure AD) | Cloud IAM |
| Managed Kubernetes | EKS | AKS | GKE |

*Note: this variant adds Serverless Compute and Managed Kubernetes rows beyond the minimum required, to show the pattern extends across more service categories.*

## Guide Questions

**1. Broadest range of services?**
AWS, with 200+ managed services. Being the first major cloud provider gave it the longest runway to build out specialized and niche offerings that the other two are still catching up on.

**2. Best for a Microsoft-centric organization?**
Azure. Its native integration with Active Directory/Entra ID, Office 365, and .NET tooling gives Microsoft-heavy organizations a single, familiar management experience across on-prem and cloud.

**3. Best known for AI/ML and Kubernetes?**
GCP. It originated Kubernetes and its managed GKE remains best-in-class for orchestration; BigQuery ML and TPUs are also strong AI/ML differentiators (though Azure's OpenAI integration and AWS's SageMaker are strong competitors in AI specifically).

**4. Similarities across the three?**
All three offer the same core building blocks — VM compute, object storage, virtual networking, and IAM — under pay-as-you-go pricing, meaning the underlying concepts and skills transfer between them even when service names differ.
