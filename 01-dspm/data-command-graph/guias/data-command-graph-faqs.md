---
title: "Data Command Graph FAQs"
slug: "data-command-graph-faqs"
updated: 2026-09-17T08:32:17Z
published: 2026-09-17T08:32:17Z
canonical: "helpcenter.securiti.ai/data-command-graph-faqs"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Data Command Graph FAQs

This section covers frequently asked questions about using the Data Command Graph and its features.

---

### FAQ

#### How do the counts in data system metrics such as 'Data size' and 'Scanned data volume' differ from each other?

The Data System metrics represent counts pertaining to the scanning that is performed on a data system. The metrics in question can display counts for the following operations.

| Operation | Metric | Description |
| --- | --- | --- |
| Discovery scan | Scanned data volume | The metric represents the total data that is scanned during discovery scan for a data system. The count is sometimes less than the **Data Size** metric as asset discovery also scans incomplete multipart uploads. |
| Skipped data volume | Count of data which is not scoped or supported in discovery scan, such as videos are shown in this metric. |
| Scanned documents | The metric represents the count for documents scanned during a discovery scan. You may observe a discrepancy between this metric and **Object Count** as asset discovery counts each folder in a data system unlike discovery scan. |
| Asset discovery | Data size | The metric represents the total data that is scanned during asset discovery for a data system. |
| Object count | The metric represents the count for all objects scanned during asset discovery. |

#### Why do 'Data Size' and 'Data Volume' columns show null or 0 values for Amazon S3 buckets?

A possible cause for this issue may be the insufficient permissions to list objects in a bucket.

#### How is 'Skipped Data' calculated if a folder is not included in the discovery scan?

If a folder is completely excluded from the discovery scan, neither the folder's size nor the size of the files within it is considered in the 'Skipped Data' metric. Essentially, any folder not included in the scan is entirely ignored, and its contents are not counted in any data size metrics, including 'Skipped Data'.

When a folder is included in the scan but contains files that do not meet specific scan criteria (such as file type, age, or other exclusion parameters), the size of those files is added to the 'Skipped Data' metric. This means the folder is scanned, but the unprocessed files within it are reflected in the 'Skipped Data' total.
