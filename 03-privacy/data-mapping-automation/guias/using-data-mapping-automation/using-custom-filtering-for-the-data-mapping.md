---
title: "Using custom filtering for the data mapping"
slug: "using-custom-filtering-for-the-data-mapping"
updated: 2025-10-30T19:47:07Z
published: 2025-11-03T06:12:21Z
canonical: "helpcenter.securiti.ai/using-custom-filtering-for-the-data-mapping"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Using custom filtering for the data mapping

As with most Securiti apps, you can filter the pages for the different catalog item types on various criteria. See [Filtering Securiti pages and dashboards](/v1/docs/filtering-securiti-pages-and-dashboards) for general information about filtering.

One filtering feature that is specific to the data mapping pages is custom filtering. This feature lets you filter elements in your data mapping based on fields specific to the element’s definition template, including custom fields that you have defined. For example, if your template has fields for data retention and disposal, you could drill down and find assets for which there is no data disposal plan.

When you use custom filters to match on a text field, they match on partial matches in which the text in the filter is a subset of the text in the field for the catalog item. For example, if a catalog item has the name “John Jacob Jingleheimer Schmidt” as the External Contact, you can find this item with a custom filter that matches the item’s template definition plus the External contact “Jacob”.

You can also apply multiple filters, joined with logical OR. For example, you can apply two filters to find both the data systems and the SaaS applications for which the data disposal method is “Degaussing.”

1. If you haven't already done so, in Securiti open **Data Mapping Automation** and from the **Catalog** menu choose one of the four catalog types (assets, processes, vendors, or institutions).
2. Near the upper right corner of the page click the **Filter** icon, and near the bottom of the filter panel click **Apply Custom Filter**.
3. On the Custom Filters popup, configure the criteria for the first filter.
4. If you want to apply multiple filters, in the filters list on the left, click **Add New Filter**, then configure the criteria for the next filter. If you want, repeat as necessary to create additional filters.

![RN_DMA_multi_filters1a.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e85ca5cf-8f7d-1500-3f01-674ad3728314.png)
5. When you are done configuring the filters, click **Apply Filters** to filter the catalog item types on the filters you configured.
