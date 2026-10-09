---
title: "AWS Permissioning Architecture"
slug: "aws-permissioning-architecture"
updated: 2026-06-22T08:52:14Z
published: 2026-06-22T08:52:14Z
canonical: "helpcenter.securiti.ai/aws-permissioning-architecture"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# AWS Permissioning Architecture

The diagram shows two distinct paths for assuming roles, depending on the scan type.

![Diagram illustrating AWS account roles and scanning processes for Securiti SaaS Cloud.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/AWS-Permission-Architecture.drawio.png)

## Key Components

1. Securiti **SaaS AWS Account**

- This is Securiti’s own cloud environment. The Securiti Platform makes the initial, authenticated requests to begin a scan. It does this by using a dedicated Securiti IAM Role which is the only entity permitted to connect to your environment.

1. **Customer's AWS Organization - Management Account**

- This is the central control point of your AWS Organization. It houses a set of Master Roles.
- **Purpose:** This account acts as a secure entry and delegation point. Securiti is granted permission to assume roles here, and these Master Roles are then authorized to assume more specific roles in your other accounts. This centralizes control and simplifies auditing.

1. **Customer's Outpost AWS Account**

- This is a separate, dedicated AWS account that you own. Its purpose is to host the temporary infrastructure for Data Plane scans.
- **Orchestrator Role:** A role that Securiti assumes to manage the lifecycle of the scanning infrastructure. It provisions pods to allow data scanning.
- Securiti **POD:** The Securiti pod is launched on-demand by the Orchestrator. This instance performs the actual data processing.
- **POD Instance Role:** This role is attached to the EC2 instance and gives it the permissions needed to assume roles in the Management Account to begin its scanning task.

1. **Customer's Member Accounts**

- These are the AWS accounts that contain your actual applications and data resources (e.g., S3 buckets, and EKS clusters).
- **Member Roles:** Each member account contains a set of granular roles that grant the final, specific permissions required to perform a scan (e.g., `s3:GetObject` , and `eks:DescribeCluster`).

### Path A: Control Plane Scans (Discovery & Posture)

This is a direct, two-step process for lightweight metadata scanning.

- **Step 1:** The Securiti IAM Role assumes the Asset Discovery or Posture Scan Master Role in your Management Account. This initial handshake is secured by a unique **External Id**, ensuring only the legitimate Securiti platform can assume the role.
- **Step 2:** The Master Role then assumes the corresponding Member Role (e.g., `S_ASSET_DISCOVERY_MEMBER_ROLE`) in the target Member Account.
- **Step 3:** With the permissions of the Member Role, Securiti can now perform its Asset Discovery and Posture Scans, listing resources and checking their configurations.

### Path B: Data Plane Scans (Data, Disk & Kubernetes)

- **Step 1:** The Securiti IAM Role assumes the Orchestrator Role in your Outpost Account, again secured by an External Id.
- **Step 2:** The Orchestrator Role launches the Securiti POD (EC2 Instance), attaching the POD Instance Role to it. The POD is now active inside your cloud environment.
- **Step 3:** The POD Instance Role (from within your Outpost Account) assumes the appropriate Data/Disk Scan or Kubernetes Scan Master Role in your Management Account.
- **Step 4:** The Master Role then delegates access by assuming the specific Member Role (e.g., S_CONNECTOR_SCAN_MEMBER_ROLE) in the target Member Account.
- **Step 5:** The POD EC2 instance now has the necessary permissions to perform its task.
