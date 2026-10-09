---
title: "Google Bigtable"
slug: "google-bigtable-connectors-1"
status: "new"
updated: 2026-04-28T04:33:12Z
published: 2026-04-28T04:33:12Z
canonical: "helpcenter.securiti.ai/google-bigtable-connectors-1"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Google Bigtable

Bigtable is a sparsely populated, highly scalable table capable of handling billions of rows and thousands of columns, allowing you to store terabytes to petabytes of data. Each row contains a single indexed value, known as the row key. Bigtable is optimized for storing large volumes of single-keyed data with low latency, and it supports high read and write throughput. It also serves as an excellent data source for MapReduce operations.

### Supported connector types and modules

| Connector type | Modules supported |
| --- | --- |
| Google Bigtable (Self-hosted) | It supports: - Sensitive Data Intelligence - DSR Automation |

### Supported pod type

- Standard Securiti Pods.

### Supported authentication methods

- Service account credential file authentication.

For more information, see [Google documentation](https://cloud.google.com/docs/authentication#:~:text=Service%20account%20keys%20identify%20a%20principal%20(the%20service%20account)) on authentication methods.

#### Keyring support

Keyring is not supported is not available for Google Bigtable.

### Supported items for Classification Scans

For more information about Classification Scans, see [Understanding Discovery Scans](/v1/docs/discovery-scans).

For Google Bigtable, tables entity is scanned.

### Prerequisites for configuring Google Bigtable connectors

#### 1. Pod deployment

You must deploy a Securiti pod in your environment to connect your Google Bigtable with a self-hosted connector. Make sure the pod deployment is with appropriate reachability through firewalls and network routing to reach the appropriate Securiti.ai endpoints, and Google Bigtable endpoints. See Allow-listed URLs section in [Elastic pod manual deployment guide (private cloud)](/v1/docs/elastic-pods-1) for more information.

For more information on configuring pods, see [Securiti variables: Platform name pods and elastic pods](/v1/docs/securiti-pods-and-elastic-pods).

#### 2. Bigtable instance

You must have a running Bigtable instance in your environment.

#### 3. Admin access

You must be an admin to Google console to create new user and service accounts.

#### 4. Permissions and use cases for Google Bigtable

| Modules use case | Constraint | Permissions/ Roles | Explanation of use case |
| --- | --- | --- | --- |
| - Discovery Scan (Sensitive Data Intelligence) - DSR Automation (Data Subject Rights) | SDI Discovery Scans and DSR Automation Indexing is only available on the self- hosted connector | **Roles to service account** - Bigtable Reader - Bigtable Viewer **(Optional) Roles to assigned user** - Service account users role - Service account admin role | These permissions let Securiti to read the tables for classification purposes and to build the Personal Data Index for DSR Automation. |

### Connect Google Bigtable connectors with Securiti

**New UI**

1. Configure and deploy Pod. For more information, see the prerequisites section above in this article.
2. [Acquire authentication credentials in Google Bigtable](/latest/docs/acquire-authentication-credentials-in-google-bigtable)
3. [(New UI) Connecting Google Bigtable with Securiti](/latest/docs/new-ui-connecting-google-bigtable-with-securiti)
4. [Configure discovery scans in Google Bigtable](/latest/docs/configure-discovery-scans-in-google-bigtable).
5. [Do Table Training for Google Bigtable.](/latest/docs/table-training-for-structured-and-hybrid-data-systems)

For more information on how Securiti uses the Google Bigtable data to respond to DSR requests, see [Fulfilling DSR requests for Google Bigtable](/latest/docs/fulfilling-dsr-requests-for-google-bigtable)

**Classic UI**

1. Configure and deploy Pod. For more information, see the prerequisites section above in this article.
2. [Acquire authentication credentials in Google Bigtable](/latest/docs/acquire-authentication-credentials-in-google-bigtable)
3. [Activate the Google Bigtable connector in Securiti](/v1/docs/activate-the-google-bigtable-connector-in-securiti)
4. [Configure discovery scans in Google Bigtable](/latest/docs/configure-discovery-scans-in-google-bigtable).
5. [Do Table Training for Google Bigtable.](/latest/docs/table-training-for-structured-and-hybrid-data-systems)

For more information on how Securiti uses the Google Bigtable data to respond to DSR requests, see [Fulfilling DSR requests for Google Bigtable](/latest/docs/fulfilling-dsr-requests-for-google-bigtable)
