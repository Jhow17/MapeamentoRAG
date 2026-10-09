---
title: "Roles & Permissions Required for OCI Integration"
slug: "roles-permissions-required-for-oci-integration"
updated: 2026-07-16T10:21:40Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/roles-permissions-required-for-oci-integration"
stale: true
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Roles & Permissions Required for OCI Integration

For this integration, Securiti creates the service account described in the table below:

### OCI Service Accounts

| Service Account Name | Group Created | Policy Created | Access Level | Required for |
| --- | --- | --- | --- | --- |
| Securiti user- <16-HEX-CHAR> | Securiti-user-grp-<16-HEX-CHAR> | Securiti-user-policy-<16-HEX-CHAR> | Allow group Securiti-user-grp-<16-HEX-CHAR> to read all-resources in compartment id <OCID> | - Asset Discovery - Posture Scan |

### OCI Resources

Securiti creates the following OCI resources in your cloud environment. You can view these resources from the Resource Explorer screen in your OCI tenancy.

| OCI Resource | Resource Name Format | Purpose |
| --- | --- | --- |
| OCI Identity Group | `securiti-user-grp-[random-id]` | Groups the service account |
| OCI Identity User | `securiti-user-[random-id]` | Represents the service account user |
| OCI User Capabilities | N/A | Disables auth tokens, console password, and SMTP credentials. Only allows API key auth. |
| OCI API Key | N/A | Uses public key from Securiti |
| OCI Group Membership | N/A | Associates the user with the group |
| OCI Policy | `securiti-user-policy-[random-id]` | Grants read-only access to all resources in the relevant compartment |

### OCI Policy

Securiti creates the following policy during onboarding, covering compartment discovery, resource discovery across all subscribed regions, and asset discovery collection.

| Policy | Access Level | Purpose |
| --- | --- | --- |
| Allow group `&lt;group&gt;` to read all-resources in compartment id `&lt;tenancy_ocid&gt;` | List, Read | Provides read-only access to all OCI services within the tenancy. This does not grant any permissions to create, modify, or delete resources. |

## Related

- [Creating an OCI Instance](/creating-an-oci-instance.md)
