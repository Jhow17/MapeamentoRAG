---
title: "Troubleshooting for Google Cloud Storage connector (Hyperdrive)"
slug: "troubleshooting-for-google-cloud-storage-connector-1"
updated: 2026-05-25T21:17:19Z
published: 2026-05-25T21:17:19Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-google-cloud-storage-connector-1"
stale: true
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for Google Cloud Storage connector (Hyperdrive)

This topic covers a troubleshooting guide for common errors and issues for the Google Cloud Storage Connector.

### Common errors during IAM Service Account authentication

When using IAM service account Authentication for impersonation, we recommend you follow the best practices below to avoid errors.

- Grant the minimum required Permissions.
- Regularly rotate and audit service account keys to reduce security risks.
- Use service account impersonation instead of sharing service account keys directly. Impersonation provides a secure and controlled method for delegating access.
- Monitor service account activity through Cloud Audit Logs to ensure that service accounts are being used as intended.
- Use short-lived tokens instead of persistent keys to enhance security.

Below are some common errors and their solutions for IAM Service Account Authentication:

| Error | Solution |
| --- | --- |
| "Request had insufficient Authentication scopes" | Update the VM's OAuth scopes to include the below scope: `https://www.googleapis.com/auth/cloud-platform` |
| "Permission 'iam.serviceAccounts.getAccessToken' denied on resource" | Ensure the source service account has been granted the **Service Account Token Creator** role on the target service account |
| "Service account not found" or "Resource does not exist" | Verify that the service account email addresses are correct and that the accounts exist in the specified project. |
