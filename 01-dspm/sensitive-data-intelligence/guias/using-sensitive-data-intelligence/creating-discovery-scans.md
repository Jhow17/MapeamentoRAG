---
title: "Creating discovery scans"
slug: "creating-discovery-scans"
updated: 2026-09-28T05:40:08Z
published: 2026-09-29T11:16:35Z
canonical: "helpcenter.securiti.ai/creating-discovery-scans"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Creating discovery scans

Discovery scans identify and classify sensitive data across your connected data systems. You can create discovery scans for structured, unstructured, and streaming connectors.

## Prerequisites

Before running a discovery scan, ensure the following:

- Configure and [activate the data system](/latest/docs/configuring-connectors-for-monitored-data-systems).
- For self-hosted data systems, [activate a pod or an elastic pod](https://helpcenter.securiti.ai/v1/docs/securiti-pods-and-elastic-pods).
- Configure the following classification types:
  - [Data elements](/v1/docs/configuring-custom-data-element-types)
  - [Content profiles](/v1/docs/configuring-content-profiles)
  - [Data dictionaries](/v1/docs/configuring-dictionaries)
  - [Document categories](/v1/docs/configuring-document-categories-and-types)
  - [File formats](/v1/docs/configuring-file-formats)
  - [Exact data profiles](/v1/docs/using-exact-data-indexes-and-profiles)

## Accessing Scan Definitions

To access **Scan Definitions**, hover over **Sensitive Data Intelligence** and choose **Discovery Scans > Scan Definitions**, as shown below.

![Overview of discovery scans with highlighted scan definitions and completed job statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/navigatingtoscandefinitions_discoveryscans.png)

For more information, see [Discovery scans for structured connectors](/latest/docs/creating-a-discovery-scan-for-structured-connectors), [Discovery scans for unstructured connectors](/latest/docs/discovery-scans-for-unstructured-connectors), and [Discovery scans for streaming connectors](/latest/docs/discovery-scans-for-streaming-connectors).
