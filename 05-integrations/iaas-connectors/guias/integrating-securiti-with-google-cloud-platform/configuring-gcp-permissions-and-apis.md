---
title: "Configuring Permissions and APIs"
slug: "configuring-gcp-permissions-and-apis"
updated: 2026-03-06T07:13:39Z
published: 2026-03-09T21:35:07Z
canonical: "helpcenter.securiti.ai/configuring-gcp-permissions-and-apis"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Configuring Permissions and APIs

Following the creation of service accounts, appropriate permissions are granted to these accounts to enable the necessary activities within each customers’ project. This is achieved through IAM policy binding through terraform.

The APIs listed below are enabled in Securiti’s GCP project when **Securiti Cloud** option is selected. If **My Cloud** option is chosen, they are enabled in the customer’s project via Terraform.

| Purpose | APIs/Services |
| --- | --- |
| GCP Integration (Mandatory) | - `cloudresourcemanager.googleapis.com ` - `iam.googleapis.com` - `admin.googleapis.com` - `appengine.googleapis.com` - `bigquery.googleapis.com` - `servicemanagement.googleapis.com` - `serviceusage.googleapis.com` - `cloudasset.googleapis.com` - `storage-api.googleapis.com` - `groupssettings.googleapis.com` - `bigtableadmin.googleapis.com` - `spanner.googleapis.com` - `osconfig.googleapis.com` |
| Pod Deployment | - `iam.googleapis.com` - `compute.googleapis.com` - `deploymentmanager.googleapis.com` - `secretmanager.googleapis.com` |
| GCP SCC Integration | - `securitycenter.googleapis.com` - `datacatalog.googleapis.com` |
| Asset Discovery | - `accesscontextmanager.googleapis.com ` - `aiplatform.googleapis.com` - `alloydb.googleapis.com` - `apigateway.googleapis.com` - `appengine.googleapis.com` - `backupdr.googleapis.com` - `bigquery.googleapis.com` - `bigtable.googleapis.com` - `bigtableadmin.googleapis.com` - `binaryauthorization.googleapis.com` - `cloudasset.googleapis.com` - `cloudbilling.googleapis.com` - `cloudbuild.googleapis.com` - `cloudfunctions.googleapis.com` - `cloudkms.googleapis.com ` - `cloudresourcemanager.googleapis.com` - `cloudscheduler.googleapis.com` - `compute.googleapis.com` - `container.googleapis.com` - `datacatalog.googleapis.com` - `datastore.googleapis.com` - `dataproc.googleapis.com` - `dataprocrm.googleapis.com` - `dns.googleapis.com` - `file.googleapis.com` - `firestore.googleapis.com&nbsp;` - `iam.googleapis.com` - `logging.googleapis.com` - `memcache.googleapis.com` - `monitoring.googleapis.com` - `metastore.googleapis.com` - `notebooks.googleapis.com` - `orgpolicy.googleapis.com ` - `osconfig.googleapis.com` - `privateca.googleapis.com` - `pubsub.googleapis.com` - `redis.googleapis.com` - `run.googleapis.com` - `securitycenter.googleapis.com` - `servicemanagement.googleapis.com` - `serviceusage.googleapis.com` - `secretmanager.googleapis.com` - `source.googleapis.com` - `spanner.googleapis.com` - `sqladmin.googleapis.com` - `storage.googleapis.com` - `storage-api.googleapis.com` - `websecurityscanner.googleapis.com` |

> [!NOTE]
> **Note**
> 
> If any of the above Service APIs are not enabled or permissions are not provided, that raises a 403 error and that particular service is skipped.
> 
> If you want to skip a certain service, you can keep its service api disabled, this way you don’t have to go to the granular level of permissions
