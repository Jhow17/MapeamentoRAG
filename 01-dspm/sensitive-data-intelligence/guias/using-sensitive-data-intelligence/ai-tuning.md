---
title: "AI Tuning"
slug: "ai-tuning"
status: "update"
updated: 2026-09-24T14:09:53Z
published: 2026-09-24T14:10:06Z
canonical: "helpcenter.securiti.ai/ai-tuning"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# AI Tuning

**Scenario**

As a Data Owner, you are responsible for ensuring that sensitive fields are accurately classified across large datasets. Manually reviewing each column or file and customizing individual detectors is time-consuming and prone to error. AI Tuning provides a simple interface to simultaneously correct a large number of errors while providing feedback that Securiti can use to improve scan results. This leads to more accurate classifications and enhances the overall scan quality within Securiti.

## Overview

AI Tuning lets you correct classification results directly and improve accuracy for your data, without waiting for a new scan. When you submit feedback on a misclassified column or file, Securiti applies that feedback going forward, so future scans reflect the correction.

> [!WARNING]
> Important
> 
> This feature is available in Securiti SaaS deployments but is not currently available in Securiti Sovereign deployments. Contact your Customer Success Manager or Account Representative for updates on its availability in your tenant.

AI Tuning improves data classification accuracy and simplifies the identification of sensitive information through a feedback-driven approach. After data is synced from discovery scans, pre-built and custom classifiers detect sensitive content. AI Tuning lets users provide interactive feedback on Discovery Scan results at the data element level, using a selected reference column for context. Classification information used for tuning is synced from completed discovery scans and sourced from both private cloud and pod local storage.

Analysts can identify similar columns based on header and content similarities, determined through semantic analysis. Securiti applies this feedback across large datasets without requiring a rescan and learns from it to enhance the accuracy of future scans. This feedback fine-tunes existing classifiers or helps create custom ones to support continuous improvement in classification outcomes.

## When to use AI Tuning

Use AI Tuning when a scan consistently misclassifies a specific column or file type, and you want the correction to apply automatically going forward. AI Tuning is not a replacement for adjusting detection rules or dictionaries; it corrects classification for the specific data you provide feedback on.

You can use AI Tuning for the following:

- Correcting a large number of similar misclassifications with a single feedback session
- Applying feedback from one reference column or file to thousands of similar columns or files without rescanning
- Refining classifiers for future scans using interactive feedback
- Identifying semantic relationships across your data by combining header and content similarity
- Preserving privacy and protecting original data using vector embeddings

## Supported AI Tuning types

Use the following table to understand the supported AI Tuning types:

| AI Tuning type | Applies to | What it classifies |
| --- | --- | --- |
| Structured Data AI Tuning | Structured data systems | Securiti lets you classify data elements at the column level |
| Document Type AI Tuning | Unstructured data systems | Securiti lets you classify document types at the file level |

## User access permissions

Use the following table to understand which user roles have permission to access, configure, or submit feedback for AI Tuning:

| Role | Viewing AI Tuning feedback | Creating AI Tuning feedback | Deleting AI Tuning feedback | Viewing AI Tuning settings | Managing AI Tuning settings |
| --- | --- | --- | --- | --- | --- |
| Super Admin | ✅ | ✅ | ✅ | ✅ | ✅ |
| Organization Admin | ✅ | ✅ | ✅ | ✅ | ❌ |
| Module Owner | ✅ | ❌ | ❌ | ✅ | ❌ |
| DPO | ✅ | ❌ | ❌ | ✅ | ❌ |
| Operator | ✅ | ❌ | ❌ | ✅ | ❌ |
| SDI Classification Reviewer | ✅ | ✅ | ❌ | ✅ | ❌ |

For more information, see [Content Classification permissions with default roles](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-default-roles).

## Prerequisites

Before configuring AI Tuning, ensure the following:

- Private Cloud Storage (PCS) is configured. For more information, see [Configuring private cloud storage](/latest/docs/system-settings-configuring-private-cloud-storage).
- You must use pod **version 1.135.0** and above to use **Structured Data AI Tuning**. For more information, see [Securiti pods](https://helpcenter.securiti.ai/docs/securiti-pods-and-elastic-pods).

​​You must use pod **version 1.150.0** and above to use **Document type AI Tuning**. For more information, see [Securiti pods](https://helpcenter.securiti.ai/docs/securiti-pods-and-elastic-pods).
- A Vector database is configured to store embeddings. For more information, see [Setting up vector storage](/latest/docs/configuring-vectordb-storage).
- You must allowlist the Securiti SaaS IPs. For more information, see [Allow listing IPs or domains for PCS connection](/latest/docs/configuring-private-cloud-storage-allow-listing-domains-or-ips-for-private-cloud-storage).
- The pod is active at the time of sync to process the associated data systems.

## Accessing AI Tuning

To access AI Tuning, follow the steps below:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon to open the main menu.
2. Choose **Settings > AI Tuning > Tuning Configuration**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-01 at 11.33.46 AM.png)

## Next steps

For more information on configuring and using AI tuning, see the below resources:

- [Configuring AI Tuning](/latest/docs/configuring-ai-tuning)
- [Classifying structured data using AI Tuning](/latest/docs/classifying-structured-data-using-ai-tuning)
- [Classifying document types using AI Tuning](/latest/docs/classifying-document-types-using-ai-tuning)
- [Viewing AI Tuning history](/latest/docs/viewing-ai-tuning-history)
- [Viewing AI Tuning audit logs](/latest/docs/viewing-ai-tuning-audit-logs)
- [AI Tuning feedback scenarios](/latest/docs/ai-tuning-use-cases)
- [AI Tuning FAQs](/latest/docs/ai-tuning-faqs)
