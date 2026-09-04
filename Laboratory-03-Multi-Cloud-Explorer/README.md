# Laboratory 3: Multi-Cloud Explorer

## Mission Overview

As part of CloudNova Technologies' Cloud Evaluation Team, this lab explored AWS, Microsoft Azure, and Google Cloud Platform, compared their core services, and produced platform recommendations for four different client scenarios — thinking like a Cloud Solutions Architect rather than simply picking the most popular provider.

## Objectives

- Explore the major public cloud platforms
- Identify the core services offered by AWS, Azure, and GCP
- Compare cloud services across providers
- Analyze business requirements and recommend appropriate cloud solutions
- Create professional technical documentation in Markdown
- Continue developing the GitHub Cloud Computing Portfolio

## Checkpoint 7 — Linux Investigation

> Run these commands in your KillerCoda terminal, screenshot the output, and paste your real findings below. Save the screenshot(s) as `screenshots/server-information.png` etc.

**Operating System** — `cat /etc/os-release`
```
<img width="663" height="223" alt="server-information" src="https://github.com/user-attachments/assets/e39e718a-5c87-43bf-ba80-9895b7e2f432" />

```

**CPU Information** — `lscpu`
```
<img width="665" height="810" alt="lscpu" src="https://github.com/user-attachments/assets/7cd89dc3-7742-40ea-a2d4-4033af3f94e1" />

```

**Memory** — `free -h`
```
<img width="662" height="65" alt="network-information" src="https://github.com/user-attachments/assets/772425f0-5466-4464-b55e-5303aac3bee5" />

```

**Disk Space** — `df -h`
```
<img width="663" height="130" alt="storage-information" src="https://github.com/user-attachments/assets/fd3c321b-1334-4876-b31e-022145592494" />

```

### If this Linux server were migrated to the cloud, which AWS, Azure, and GCP services could host it?

This server is a general-purpose Linux virtual machine, so it maps directly onto each provider's core compute service:

- **AWS** — Amazon EC2, using an Ubuntu AMI matching the OS version found above, sized to an instance type matching the observed CPU core count and RAM.
- **Microsoft Azure** — Azure Virtual Machines, using an Ubuntu Server image, sized to a matching VM tier (e.g., a B-series or D-series VM depending on the workload).
- **Google Cloud Platform** — Compute Engine, using an Ubuntu image from Google's public image family, sized to a matching machine type (e.g., e2-medium or similar, based on observed CPU/RAM).

In all three cases, the disk space observed via `df -h` would map to an attached block storage volume — an EBS volume on AWS, a Managed Disk on Azure, or a Persistent Disk on GCP — sized to match or exceed what was found on the KillerCoda server.

## Tools Used

KillerCoda Playground · Git/GitHub · Markdown · Official AWS/Azure/GCP documentation

## Skills Learned

- Researching and comparing core services across three major cloud providers
- Mapping business requirements to specific cloud platform strengths
- Matching equivalent services across AWS, Azure, and GCP
- Relating a Linux VM's specs to real cloud compute/storage offerings
- Producing structured multi-document Markdown technical reports

## Challenges Encountered

One challenge was keeping track of service names across three providers that describe the same underlying concept differently — for example, remembering that Azure's identity service was recently rebranded from Azure Active Directory to Microsoft Entra ID took extra double-checking against official documentation to avoid citing outdated naming. Another challenge was writing the client recommendations objectively: it was tempting to default to the most well-known provider (AWS) for every scenario, but matching each client's actual constraints — like the university's existing Active Directory setup or the AI research company's need for TPUs — required looking past general popularity and focusing on what each specific business actually needed.
