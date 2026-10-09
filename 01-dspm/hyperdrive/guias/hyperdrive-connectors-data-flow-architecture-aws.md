---
title: "Hyperdrive connectors data flow architecture - AWS"
slug: "hyperdrive-connectors-data-flow-architecture-aws"
updated: 2026-08-01T10:00:44Z
published: 2026-08-01T10:00:44Z
canonical: "helpcenter.securiti.ai/hyperdrive-connectors-data-flow-architecture-aws"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive connectors data flow architecture - AWS

In the Hybrid deployment with Outpost model, Securiti provisions and operates a your dedicated data plane in an isolated AWS account. It uses the SaaS control plane for orchestration, configuration, job monitoring, and results presentation, while scanning and classification workloads run inside the dedicated data plane. It temporarily processes raw content within the dedicated environment and does not export or persist it in the multi-tenant SaaS control plane. It exchanges only scan metadata, classification results, operational status, and authorized evidence access references through secured control paths.

## Key architecture components

Your dedicated Outpost data plane is made up of a handful of core AWS services and components. See the following table for what each one is and the role it plays in scanning and processing your data:

| Component | Description |
| --- | --- |
| Securiti SaaS Control plane | Manages user interactions, scan configuration and scheduling, operational state, and presentation of final scan results. |
| Dedicated Outpost EKS (Dedicated Data Plane) | A single-tenant Kubernetes cluster deployed specifically within the your dedicated account. This cluster performs data scanning and classification within an isolated private VPC. |
| Managed NAT gateway (Single Static EIP) | A consolidated egress point for outbound scanning traffic and required control-plane communications. This provides a predictable source IP that you can allowlist in your firewalls or SaaS application access policies. |
| External Data systems | Represents the target data systems. The diagram explicitly details connections for OneDrive and SharePoint. |

### Storage (dedicated account)

Your dedicated account also includes two purpose-built storage buckets that handle data at different stages of the scan. One is for temporary processing, and other one is for the results that get reported back. See the table below for details of each storage type:

| Storage type | Description |
| --- | --- |
| KMS-Encrypted Transient Storage | Securiti uses this encrypted bucket for temporary processing the content during scan execution. It stages your content only as needed for analysis and removes it after processing. |
| KMS-Encrypted Metadata Storage | A secure bucket where Securiti stages scan metadata, classification results, operational state, and result artifacts before the SaaS control plane retrieves them. It makes only metadata, classification results, and operational scan outputs available to the SaaS control plane. Raw scanned content does get exported to or persisted in the SaaS control plane. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Securiti-hosted-infrastrcture-hyperdrive-dataflow-diagram.png)

## Data movement through the Outpost architecture

Your Outpost architecture relies on a few distinct mechanisms to move and protect your data. A cross-account IAM role and a dedicated control API keep the data plane authenticated and connected to the SaaS control plane at all times. During an active scan, Securiti connects to your external data systems, temporarily processes your data, and generates evidence samples. Once a scan completes, it stages the results for retrieval by the SaaS control plane.

### Cross-account security & IAM role assumption

This is a critical security handshake between the Securiti SaaS control plane account and your managed your dedicated data plane account. Securiti governs access through a controlled AWS IAM boundary. The Securiti SaaS control plane assumes a least-privilege IAM role within the dedicated account using a unique External ID for cross-tenant protection. This lets Securiti securely and auditably access only approved orchestration, operational, and metadata retrieval actions.

### Staging & retrieval of scan results by Securiti SaaS

Once a scan finishes, its results move through two steps before you see them on your dashboard. See the table below for how staging and retrieval work:

| Step | Description |
| --- | --- |
| In-account staging | Once the scanning EKS cluster completes its analysis, it stages the final scan results and metadata (high-level insights, not the raw content itself) in the dedicated S3 Metadata Storage bucket within the processing environment. |
| Final reporting | To populate your dashboard, the Securiti SaaS control plane retrieves only this staged metadata directly from the storage bucket in the dedicated account. This ensures that only analysis results, and never raw data, cross the boundary into the Control Plane. |

### Transient data handling during scan

During a scan, Securiti fetches your data from your SaaS applications into the private processing VPC. Securiti temporarily stores this data in the KMS-encrypted transient storage bucket only as needed for scan processing and removes it after processing. Raw and un-redacted content remains within the dedicated data plane and is not exported to or persisted in the SaaS control plane.

### Scanning workflow

This is the main data pipeline for discovery. The scanning EKS cluster in the dedicated account initiates secure egress connections (via the managed NAT gateway) to the external data systems. Securiti analyzes data in a single, high-throughput pass from services like OneDrive and SharePoint. It uses Reactive Rate Handling logic to maximize safe throughput while respecting SaaS vendor throttling behavior, including retry-after responses and platform-specific rate limits.

### Configuration and control APIs

The data plane processing cluster uses a dedicated API path to send configuration reports, state updates, and resource requests (such as signed URLs) to the Securiti SaaS control plane. This path ensures the data plane is configured correctly and gives you continuous operational visibility over a secure egress path.

### Evidence review path

To protect sensitive evidence samples, the architecture uses a direct user-to-storage access model. The dedicated data plane generates evidence and writes it directly to the private storage location using temporary, scoped access. When you or another authorized Securiti platform user or auditor reviews evidence through the SaaS portal, the SaaS control plane provides a temporarily signed URL, and your browser retrieves the evidence sample directly from the private storage location. Securiti does not proxy or persist evidence content through the SaaS control plane.

### Evidence generation

During scan execution, the scanning cluster in the dedicated data plane identifies and generates evidence samples based on the applicable scan configuration and classification results. The scanning cluster calls Securiti Control Plane APIs to obtain a scoped, temporary signed URL that provides write access to the dedicated Private Cloud Storage bucket, as shown in the diagram above. The dedicated data plane then writes the evidence file directly to the Private Cloud Storage bucket. Evidence content does not flow through or get stored in the multi-tenant SaaS control plane.

### Auditor access

When you or another authorized Securiti platform user needs to review evidence, you initiate the request from the SaaS portal. The SaaS control plane brokers a temporary signed URL that lets your browser retrieve the evidence sample directly from the secure Private Cloud Storage bucket. Securiti delivers the evidence content directly from private storage to your browser and does not proxy or persist it through the multi-tenant SaaS portal.

## On-premises connectors data flow architecture

The diagram illustrates a representative hybrid connectivity pattern. Your final network design may vary based on your approved AWS, Direct Connect, VPN, routing, firewall, and inspection architecture.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-F1J2Y6P9.png)

### Hybrid Connectivity for On-Premises Systems

To reach on-premises systems such as SMB or NFS shares, the Securiti-hosted dedicated data plane requires a private network path from your managed dedicated AWS account to your on premises network. You can establish this connectivity using one of the following approved network patterns, depending on your network architecture and security requirements:

| Connectivity pattern | Description |
| --- | --- |
| AWS Transit Gateway-based connectivity | Securiti establishes a private routing path using AWS Transit Gateway attachments between the dedicated data plane VPC and your approved network connectivity layer. Your Transit Gateway, Direct Connect, or VPN architecture routes traffic onward to the required on-premises systems, subject to your routing, firewall, and security controls. |
| Direct VPN or private tunnel connectivity | Where you approve it, Securiti can establish a dedicated site-to-site VPN or private tunnel between the dedicated data plane and your network edge. Your internal network then routes traffic to the target on-premises SMB or NFS shares. |
| Customer-managed network appliance pattern | Where you require inspection, routing enforcement, or segmentation through a network virtual appliance, Securiti can route traffic through your approved appliance. In this model, you must explicitly design the appliance to support the required routing path between the data plane and your on-premises network. |
