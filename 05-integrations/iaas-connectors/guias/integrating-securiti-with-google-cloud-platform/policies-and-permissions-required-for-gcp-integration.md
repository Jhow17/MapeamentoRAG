---
title: "Policies and Permissions required for GCP Integration"
slug: "policies-and-permissions-required-for-gcp-integration"
updated: 2026-04-07T08:41:41Z
published: 2026-04-07T08:41:41Z
canonical: "helpcenter.securiti.ai/policies-and-permissions-required-for-gcp-integration"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Policies and Permissions required for GCP Integration

When configuring an IaaS connector, asset discovery is enabled by default, automatically deploying the required IAM permissions, policies, and roles based on the deployment type. The Service Account Key authentication in the deployed Terraform template acquires permissions necessary for asset discovery.

Meanwhile, posture scan requires specific IAM permissions listed in this document to run successfully but is not enabled by default. To activate posture scan, select the Detect Security Posture Misconfiguration option during IaaS connector configuration, which will create a dedicated service account for posture with assigned roles and permissions. The following table details roles and permissions for both asset discovery and posture scan.

| Policy/Role | Access Level | Purpose | Required for |
| --- | --- | --- | --- |
| [Security Reviewer](https://cloud.google.com/iam/docs/understanding-roles#iam.securityReviewer) | List, Read | Provides permissions to list down all resources within each GCP service. This role also allows users to view security-related configurations and settings without granting them the ability to modify these settings. | Asset Discovery |
| [Organization Role Viewer](https://cloud.google.com/iam/docs/understanding-roles#iam.organizationRoleViewer) (Optional) | Read | Gets organization wide policy. Some services have organization level policies applied to them, in order to discover their correct access/data we’ll be needing this role | Asset Discovery |
| [BigQuery Metadata Viewer](https://cloud.google.com/bigquery/docs/access-control#bigquery.metadataViewer) (Optional) | Read | Grants access to some BigQuery permissions which are not available in Security Reviewer | Asset Discovery |
| [Viewer](https://cloud.google.com/iam/docs/understanding-roles#viewer) | Read | Permissions for read-only actions that don't affect state, such as viewing (but not modifying) existing resources or data. | Posture Scan |
| [BigQuery Data Viewer](https://cloud.google.com/iam/docs/understanding-roles#bigquery.dataViewer) | List, Read | This role provides permissions to list all of the resources in the dataset (such as tables, views, snapshots, models, and routines) and to read their data and metadata with applicable APIs and in queries. | Posture Scan |
| **Custom Role - IAM** - `appengine.applications.get ` - `binaryauthorization.policy.get` - `cloudasset.assets.searchAllIamPolicies` - `compute.projects.getorg` - `orgpolicy.policy.get` | Read | Used for collecting and accessing IAM data | Asset Discovery |
| **Custom Role - Vertex AI Agent Builder** - `discoveryengine.dataStores.get` | Read | Used for creating Cloud Function relation (first-gen) | Asset Discovery |
| **Custom Role - VPC Connector** - `vpcaccess.connectors.get` | Read | Used for creating VertexAI Agent-Builder relation. | Asset Discovery |

> [!NOTE]
> **Note**
> 
> The roles marked as “optional” can be considered optional ONLY if services associated with them are not being used.

Securiti policies translate data intelligence into actions. Each policy has rules that, when matched by a file, document, or resource, trigger a response.
