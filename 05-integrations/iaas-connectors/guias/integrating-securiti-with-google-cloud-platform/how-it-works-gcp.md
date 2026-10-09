---
title: "How it Works?"
slug: "how-it-works-gcp"
status: "update"
updated: 2026-01-26T16:24:23Z
published: 2026-01-26T16:24:23Z
canonical: "helpcenter.securiti.ai/how-it-works-gcp"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# How it Works?

When you onboard a GCP project into Securiti, the platform generates specific service accounts and roles within a Securiti-managed GCP account. These key service accounts support different functions in the GCP integration:

1. **Asset Discovery Service Account:** Discovers and catalogs assets within your GCP environment.
2. **Posture Scan Service Account:** Performs security posture scans to identify vulnerabilities or configuration issues.
3. **Auto Remediation Service Account:** Triggers automated remediation actions to address detected issues or vulnerabilities.
4. **Data Scan Service Account:** Scans for data in assets.
5. **Disk Scan Service Account:** Detects and identifies sensitive data on disks.

Securiti also creates custom roles, such as Securiti_POD_VM_ROLE, Securiti_DISK_SCAN_ROLE, and Securiti_POD_ORCHESTRATOR_ROLE, each with precise permissions for tasks like VM management, disk scanning, and pod orchestration. Each service account is associated with one of these roles and secured with encrypted service account keys.

You can find these custom roles and service accounts within your GCP project and revoke them if needed. If revocation occurs, you can restore integration by re-provisioning the Google account to regenerate credentials.

After creating the service accounts, Securiti assigns them the necessary permissions to operate within your GCP project. Permissions are managed using IAM policy binding through Terraform, providing secure, role-based access control across the environment.

This setup lets Securiti execute essential functions, including asset discovery, security assessment, pod orchestration, disk and data scanning, and automated remediation, while maintaining tight, role-based permissions. This approach ensures that Securiti interacts with your resources only as needed, bolstering security and operational integrity within your GCP environment.

The following diagram illustrates Securiti’s integration with Google Cloud Platform.

![GCP_Frictionless_Onboarding_drawio.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8a941115-b2c5-3dc6-f9ed-905f5a27cfaa.png)

The sections that follow discuss the working of the above illustration in-depth, covering how each part functions and contributes to the overall process.

## Related

- [Creating a GCP IaaS Instance (version 1.124 and later)](/creating-a-gcp-iaas-instance-version-1124-and-later.md)
- [Creating a GCP IaaS Instance (version 1.123 and earlier)](/creating-a-gcp-iaas-instance-version-1123-and-earlier.md)
