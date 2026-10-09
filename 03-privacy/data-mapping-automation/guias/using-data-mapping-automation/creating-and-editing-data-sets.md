---
title: "Creating and editing data sets"
slug: "creating-and-editing-data-sets"
updated: 2025-10-30T19:47:24Z
published: 2025-11-03T06:12:21Z
canonical: "helpcenter.securiti.ai/creating-and-editing-data-sets"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Creating and editing data sets

You use data sets to identify groups of data elements and/or data element types along with their properties. Data sets are unique to each asset, vendor, and institution.

To create a new data set:

1. If you haven't already done so, open the asset, vendor, or institution for which you want to create a data set. See one of the following topics if you need help:
  - [Creating and editing data assets](/v1/docs/creating-and-editing-data-assets)
  - [Creating and editing vendors](/v1/docs/creating-and-editing-vendors)
  - [Creating and editing institutions](/v1/docs/creating-and-editing-institutions)
2. If you haven't already, near the upper right corner of the page click **Edit**.
3. Expand the Data Sets area and click **Add Data Sets**.

To edit a new or existing data set:

1. If you haven't already, open the catalog element, click **Edit**, and expand the Data Sets area.
2. Next to the data set name, click **Edit** (pencil icon) and edit the data set name so that it indicates the function of the data set. The default name is a set of random characters. Click the checkmark when you are done.
3. Click the data set name to expand the data set.
4. Apply the following settings:

| Taxonomy | The data type from the menu. |
| --- | --- |
| Classification | The classification level (public, confidential, etc) for the data. |
| Is Structured | Whether the asset represents a structured data system such as an SQL database. |
| Is PII | Whether the data represents Personal Identifying Information. |
| Data Source Type | Type the data source type |
| Data Source Name | Type the data source name |
| Tags | Build a list of convenient tags for the data set. |
5. Click **Add Data Elements or Types** and choose from among the data elements and types on the data system those that belong to the data set.

The types and elements available are limited to those you configured for the data system when you added it to the catalog.
6. (Optional) Configure data element attribute properties as described in [Configuring attribute properties for data elements](/v1/docs/configuring-attribute-properties-for-data-elements).
7. When you are done adding data elements and types, click **Update**.
8. When you are done, check to make sure the **Save** button near the upper right corner of the page is disabled, showing you that Securiti has already autosaved your changes. If the button is active, click it to manually save your changes.
