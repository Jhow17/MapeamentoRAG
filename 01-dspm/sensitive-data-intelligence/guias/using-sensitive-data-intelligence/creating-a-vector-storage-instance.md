---
title: "Creating a vector storage instance"
slug: "creating-a-vector-storage-instance"
updated: 2026-08-31T18:02:18Z
published: 2026-08-31T18:02:18Z
canonical: "helpcenter.securiti.ai/creating-a-vector-storage-instance"
stale: true
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Creating a vector storage instance

AI Tuning stores the embeddings it generates from your data in a vector storage instance. Securiti supports two vector storage engines, OpenSearch Service and Elasticsearch. This article covers creating and configuring an instance of each.

## Creating instance using AWS OpenSearch Service

You provision this instance as an Amazon OpenSearch Service domain in your own AWS account.

### Prerequisites

- You have an AWS account with permissions to create an OpenSearch Service domain.
- You have allowlisted the Securiti SaaS IPs.

> [!NOTE]
> Note
> 
> If allowlisting is not configured, AI Tuning cannot write embeddings to the database.

### Procedure

When you create a new domain, Amazon OpenSearch Service selects the latest available engine version by default. Securiti supports OpenSearch versions 2.17.0 and 2.19.0 for AI Tuning. You must select one of these two versions instead of the default. To create the domain:

1. In the AWS Management Console, open **Amazon OpenSearch Service**, then click **Create domain**.
2. Under **Use case**, select **Vector search**.

> [!WARNING]
> Important
> 
> AWS asks you to choose a use case before you configure the domain, and this choice determines the domain's storage engine. You cannot change it after the domain is created. Selecting **Observability** provisions Analytics-optimized instances, which are append-only, and AI Tuning updates and deletes embeddings. If your use case is not listed, select **Custom** and configure equivalent settings to Vector search.
3. Under the **Engine options**, set the version to OpenSearch `2.17.0` or `2.19.0`.
4. Under **Network**, choose how the domain is reached. If you use a VPC, allow network access from the pod that runs AI Tuning to the domain. If you use public access, allowlist Securiti’s SaaS IP addresses.
5. Under **Fine-grained access control**, enable it and create a master user with a username and password.

> [!NOTE]
> Note
> 
> Securiti authenticates to OpenSearch with a username and password, not IAM roles or SAML. Use this master user when you configure AI Tuning in Securiti. For the generic Amazon OpenSearch Service domain-creation flow, see AWS's [OpenSearch Service getting-started guide](https://docs.aws.amazon.com/opensearch-service/latest/developerguide/gsg.html).
6. Complete the remaining domain settings and click **Create**. For more information, see Vector storage sizing guidance before finalizing instance type, data node count, and storage size.

## Elasticsearch

Securiti supports Elasticsearch versions `8.17.0`, `8.17.1`, and `9.3.0` as a vector storage engine for AI Tuning. Securiti authenticates to Elasticsearch using API key authentication.

To create and configure your Elasticsearch cluster, see [Elastic search's official documentation](https://www.elastic.co/guide/index.html).
