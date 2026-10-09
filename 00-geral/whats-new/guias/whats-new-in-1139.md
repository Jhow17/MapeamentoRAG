---
title: "What's New in 1.139"
slug: "whats-new-in-1139"
updated: 2026-04-28T16:58:58Z
published: 2026-04-28T16:58:58Z
canonical: "helpcenter.securiti.ai/whats-new-in-1139"
area: geral
modulo: whats-new
tipo: guia
data_captura: 2026-10-08
---

# What's New in 1.139

### Discover More Cloud Assets: S3 Vector Bucket, Bedrock Models, and VertexAI

Your cloud environment isn’t just about data anymore. It’s AI too, distributed across multiple platforms. Securiti now discovers AWS S3 Vector Buckets that store vectorized data, Amazon Bedrock Models (both Imported and Prompt Router Models) used for AI workloads, and GCP VertexAI Data Store for search and generative applications. Having these assets discovered helps you monitor both your AI and data resources, check their compliance status, and keep an accurate record of your cloud landscape in one place.

[Learn more in the Asset Discovery documentation](/v1/docs/data-security-posture-management-solution#list-of-supported-cloud-native-services)

![Visual representation of data processing with icons for various technologies and a central logo.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/[IaaS]Discover More Cloud Assets_ S3 Vector Bucket, Bedrock Models, and VertexAI.jpg)

---

### Multi-PCS Is Here: One Tenant, Ten Destinations

Managing region-based data storage shouldn't mean setting up new tenants each time. With support for up to 10 Private Cloud Storage (PCS) locations in one tenant, Securiti makes it simpler. You can define a default PCS and allocate others to connectors based on region, so sample data and evidence stay aligned with where the source data resides. This gives you stronger storage control with less overhead and a more unified setup.

[Read more in docs](/v1/docs/private-cloud-storage)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-P1THHVO1.png)

---

### Know What Was Remediated, Where, and Why

Some files may have overstayed their welcome, and with policies, you know exactly which ones. Apply built-in retention policies mapped with controls to flag redundant, obsolete, or trivial files. The Data Remediation Explorer then surfaces results across these policies, so you can act fast on what’s outdated, what’s unnecessary, and where to begin. Understand the 'why' behind each result, and take cleanup actions with confidence.

[Learn more about file remediation in the docs](/v1/docs/using-the-data-systems-overview-dashboard)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8LAW5T6W.png)

---

### Redesigned UX for Unstructured Data Discovery: Coming Soon!

Want to drill into the scan results of your unstructured data like never before? You’ll get it with the new Unstructured Data Scans dashboard, coming soon to the Securiti platform!

This revamped dashboard lets you focus on individual discovery scan results and gives you deeper visibility into every scan with a top-level filter. You’ll be able to view file scan counts, skipped volumes, and detected data elements, all in one place. Stay tuned!

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8I417UUO.png)

---

### EDC Ingestion for Salesforce

Securiti now supports Salesforce metadata ingestion in the Enterprise Data Catalog. You can pull in datasets, schemas, and lineage information from your Salesforce environment for complete visibility across your data landscape. Setup is simple — use an existing Salesforce connector you already configured for discovery scans. There’s no need to create a new one. Once connected, your Salesforce data becomes part of your broader catalog for easier discovery and context. Just go to the EDC ingestion workflow to get started.

[Learn how to ingest Salesforce metadata](/v1/docs/edc-ingestion)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CH59OX3Y.png)

---

### Add Your Sitemap to Run Targeted Domain Scans

Sometimes a full domain scan picks up pages that don't matter or takes longer than you’d like. If your domain already has a sitemap, you can now put it to work. Upload it so the cookie scanner focuses cookie and tracker detection on the pages listed in your sitemap. This keeps scans quick, relevant, and complete with no more waiting for unnecessary URLs to crawl. Just make sure your sitemap file is within 5 MB, upload it, and the cookie scanner will handle the rest. It's an easy way to make each domain scan precise, targeted, and faster.

[Learn more about Sitemap Scanning](/v1/docs/scanning-your-website-for-cookies)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1SP9H3N6.png)

---

### Manage Indiana Privacy Requests with Confidence

Privacy teams in Indiana can now manage data subject requests with full compliance. Securiti’s DSR module includes support for the Indiana Consumer Data Protection Act (INCDPA). You can configure forms for this regulation and rely on ready-made notification templates that already meet INCDPA requirements. These templates and related research are available in your DSR module, making it easier to send the right notifications every time.

[See the list of supported regulations](/v1/docs/supported-jurisdictions-and-regulations-in-dsr-form)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FB7UWX4V.png)
