---
title: "Deploying Pod and Managing GCP Permissions"
slug: "deploying-pod-and-managing-gcp-permissions"
updated: 2026-06-22T12:40:48Z
published: 2026-06-22T12:40:48Z
canonical: "helpcenter.securiti.ai/deploying-pod-and-managing-gcp-permissions"
stale: true
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Deploying Pod and Managing GCP Permissions

This section provides a comprehensive overview of setting up and managing the GCP integration process. It includes details on VPC setup, IAM role assignment, creation of service accounts, and deployment of pods for data and disk scanning. Each step explains how the pod interacts with various GCP resources (e.g., Compute Engine, Cloud Storage, Secret Manager), and which GCP IAM roles (e.g., Disk Scan Role, Data Scan Role) are applied to ensure the correct permissions are in place throughout the process.

### VPC and Network Setup

- A **Virtual Private Cloud (VPC)** is created to provide a secure, isolated network environment within GCP.
- Subnetworks are configured for distinct IP ranges across specified regions, enabling regional segmentation and private IP access to Google services.
- A firewall rule restricts inbound SSH access exclusively from **Google Identity-Aware Proxy (IAP)**, applying strict access control for enhanced security.

### Secrets Management Configuration

- Network, subnetwork, firewall, and VM settings are securely stored in Google Secret Manager, ensuring sensitive information remains protected.
- These settings are combined into a JSON format and saved as a versioned secret, which is automatically replicated across regions, providing secure, organized, and easily accessible configuration management.

### Scanning Pod Permission Configuration

Defines necessary resources, permissions, and IAM roles for a scanning pod VM within a GCP project to perform data and disk scans securely.

- **Storage Bucket Creation:** A storage bucket is created in the specified region for the scanning pod VM to store and access essential files (e.g., drivers).
- **Service Accounts for Scanning Operations:** Three service accounts are created to manage access for various scanning tasks:
  - **Asset Discovery Service Account:** Discovers and catalogs assets within your GCP environment.
  - **Posture Scan Service Account:** Performs security posture scans to identify vulnerabilities or configuration issues.
  - **Pod Orchestrator Service Account:** Authenticates the scanning pod VM to interact with GCP resources.
  - **Auto Remediation Service Account:** Triggers automated remediation actions to address detected issues or vulnerabilities.
  - **Data Scan Service Account:** Manages permissions for accessing Google Cloud Storage.
  - **Disk Scan Service Account:** Manages permissions for accessing target disks.
- **Custom IAM Roles:** Custom IAM roles with specific permissions are defined for:
  - **Scanning Pod VM Operations:** Lets the pod VM to perform network and compute tasks.
  - **Disk Access:** Performs necessary disk operations for data and disk scanning tasks.
- **IAM Bindings for Additional Permissions:**
  - **Metric Writer and Log Writer Roles:** Permit the pod VM service account to write metrics and logs to Cloud Monitoring and Logging.
  - **Storage Object Viewer Role:** Grants read-only access to the bucket where driver files are stored, restricted by a condition to limit access to the specific bucket.
- **Custom Role Assignments:** Custom roles are assigned to the relevant service accounts, enabling necessary operations for the scanning pod VM and associated tasks.
- **Service Account Policies:** Policy bindings let the pod VM service account to impersonate the data scan and disk scan service accounts, ensuring secure, delegated access as needed for scanning activities.

### Pod Orchestration IAM Role Configuration

Defines a custom IAM role and binds it to a service account to support scanning pod orchestration in GCP.

- **Custom IAM Role:** A role specific to pod orchestration and data scans is created, granting necessary permissions in the GCP project.
- **IAM Binding:** The role is assigned to the specified service account, letting it to perform required pod orchestration tasks securely.

### GCP Project Configuration Variables

Defines key settings and permissions needed to deploy resources, manage IAM roles, and activate essential services in a GCP project.

- **General Settings:** Specifies basic project details, including region, resource naming conventions, project ID, project number, and the path to GCP credentials.
- **Network Configuration:** Sets up custom subnetworks, IAP access, and VM specifications such as zone labels, machine type, source image, and disk size.
- **IAM Roles for Pod Orchestration and Scanning:**
  - **Pod Orchestration:** Defines the role and service account needed to coordinate scanning pods.
  - **Scanning Pods:** Includes service accounts and roles for accessing disks, and performing data scans with specific permissions.
- **Enabled Services:** Lists required GCP APIs (e.g., IAM, Compute, Secret Manager) that support project operations.

### VPC Network and Subnetwork Outputs

These outputs provide essential details about the created VPC network and its subnetworks:

- Displays the VPC network name for easy identification.
- Lists the names of all subnetworks within the VPC for quick reference.
- Shows the regions where each subnetwork is deployed, helping locate resources across regions.
- Provides a JSON summary of the network configuration, ensuring secure storage and accessible network details.

The cloud term typically refers to cloud computing. Cloud computing is a technology that allows users to access and use computing resources and services over the internet, often from remote data centers.
