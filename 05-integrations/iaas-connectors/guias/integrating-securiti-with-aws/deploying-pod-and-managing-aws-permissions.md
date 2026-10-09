---
title: "Deploying pod and managing AWS permissions"
slug: "deploying-pod-and-managing-aws-permissions"
updated: 2026-06-22T11:37:16Z
published: 2026-06-22T11:37:16Z
canonical: "helpcenter.securiti.ai/deploying-pod-and-managing-aws-permissions"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Deploying pod and managing AWS permissions

This section provides a detailed breakdown of the pod's deployment process and operations within the AWS environment. It covers VPC setup, IAM role configuration, snapshot creation, and data and disk scanning. Each step explains how the pod interacts with various AWS services (e.g., S3, EC2, Glacier) and which AWS policies (e.g., SecurityAudit, AmazonGlacierReadOnlyAccess) are used to ensure the correct permissions are applied throughout the process.

### VPC and Network Setup

- A **Virtual Private Cloud (VPC)** is created to isolate network resources within the customer’s AWS environment.
- The VPC includes configuration of subnets, internet gateways, route tables, and security groups, enabling the pod to communicate securely both within the VPC and with external services (e.g., Securiti services or external AWS services).
- **Security Groups** are set up to define inbound and outbound traffic rules, ensuring the pod can communicate securely with necessary AWS services like S3, EC2, and KMS while keeping it isolated from unnecessary network access.

### Pod Launch in Customer Environment

- The pod is launched in the **member account** using a CloudFormation template initiated by the **master account**. This automates the creation of necessary roles, policies, and permissions required for the pod to perform its operations.

### IAM Role Setup

The pod is assigned an IAM role that grants it the required permissions to operate within the member account. These include:

- Accessing snapshots and decrypting them.
- Reading and writing to S3 buckets.
- Interacting with **EC2** instances for scanning and data operations.

### Snapshot Creation and Access

The pod creates snapshots of the member account’s resources (e.g., EC2) using permissions from the assigned IAM role. These snapshots are encrypted and securely stored, with the pod decrypting them for scanning.

### Data Scanning Operations

Once the snapshots are decrypted, the pod initiates data scans to discover sensitive information, compliance issues, and other metadata across multiple data sources.

### Disk Scan

The pod performs disk scans on EC2 instances to gather insights into sensitive data, configuration issues, and malware.

### Access to S3 bucket

The pod accesses an S3 bucket where necessary artifacts (e.g., database drivers or scanning tools) are stored. Permissions to access the S3 bucket are granted by the IAM role, ensuring the pod has the resources needed for scanning.

> [!NOTE]
> Note
> 
> If you plan to run Discovery Scans on Amazon S3, ensure that the IAM role includes the additional permissions required for data scanning. For more information, see [Use cases and permissions for Amazon S3](https://helpcenter.securiti.ai/docs/amazon-s3-connectors-1#5-use-cases-and-permissions-for-amazon-s3)

### Access to EC2 Snapshots

The pod also interacts with EC2 volume for scanning data on volumes.

- **Deletion Process:**
  - After scanning, the temporary EC2 volume are deleted, while the original EC2 volumes and backups remain unaffected.
