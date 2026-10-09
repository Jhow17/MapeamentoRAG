---
title: "Configure discovery scans in Amazon MSK"
slug: "configure-discovery-scans-in-amazon-msk"
updated: 2026-07-14T10:13:59Z
published: 2026-07-14T10:13:59Z
canonical: "helpcenter.securiti.ai/configure-discovery-scans-in-amazon-msk"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure discovery scans in Amazon MSK

This section describes creating a discovery scan for Amazon MSK. See [Understanding discovery scans](/latest/docs/discovery-scans) for more information about Securiti discovery scans.

1. Near the bottom of the Connector tab, click **Create Discovery Scan**.
2. On the Create Discovery Scan page Scan details area, enter a convenient name and description for the scan job.
3. In the Scope area, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Target | Choose **Amazon MSK**. |
| Select Data Systems | Choose the specific Amazon MSK data system instances to scan. |
| Data System Scope | (Optional) Expand the Data System Scope area, and for each selected data system, choose which topics to include or exclude in the scan. The default is all topics of all selected data system instances. You can also configure the scope of scanning by specifying a regex pattern. |
4. In the Advanced Settings area, use the following settings for your streaming data systems.

  - In the For field classification section, configure the following field classification settings:

| Setting | Description |
| --- | --- |
| Sample first ‘x’ rows | This setting collects the sample of the table and views with a sample "LIMIT" query and classifies the first ‘x’ rows discovered. |
| Sample random ‘x’ rows | This setting enables the random sampling process, which collects the data column-wise and in a random manner. > [!WARNING] > **Important** > > - Random sampling is a resource-intensive operation, depending on the table size and the data source's access latency. > - Securiti does not support random sampling on views. The process applies to tables only. > - If the actual number of table rows is less than the specified random sampling limit, regular sampling takes place using a "LIMIT" query. The default LIMIT is 1000, unless a different value is set in the regular Sampling Limit. |
| Sampling Limit | This defines the size of the table sample (i.e, the number of rows) that is collected for classification, either by selecting the first rows or by fetching them randomly. - For first 'x' rows , you can set a minimum of 1 row and a maximum of 10,000 rows for sampling. - For random 'x' rows , you can set a minimum of 1 row and a maximum of 500 rows for sampling. |
| Store Sample Data | The option is enabled by default and stores your sample files at your desired location configured during the connector activation process. When disabled, Securiti does not store any sample files on the appliance or cloud to preview on the [Table Training](/latest/docs/new-ui-table-training-for-structured-and-hybrid-data-systems) page. |
| Include empty database tables | Mark the checkbox to include tables with 0 or empty rows. > [!NOTE] > **Note** > > When disabled, discovery scan does not include empty tables for classification if the table headers are being classified. For more information, see Customizing system data element types. |
| Skip empty fields and the fields below | Mark this checkbox to skip the rows that have empty values in all the CLOB columns fetched during the sampling. Enabling this option lets Securiti skip the fields containing certain values such as Unknown, NA, Null, or Not Applicable, and so on. This saves time and the cost of scanning by not performing any additional scans. |
| Include newly discovered tables and schemas into the scan scope | Considers all new tables and schemas automatically for scanning while maintaining the configurations done in the scope section. Selecting this option lets Securiti automatically include newly discovered tables and schemas in the scope of the scan. |
5. (Optional) In the Responses area, choose what responses Securiti takes when the scan completes. You can specify one or more emails with a relevant email template.
6. (Optional) In the Responses area, trigger a specified workflow. To do this, configure a [Discovery scan trigger node](/latest/docs/discovery-scan-regular-node).
7. Near the top right side of the page, click **Finish and Activate**. To view discovery scan results, see [Viewing discovery scan results](/latest/docs/viewing-discovery-scan-results).

## Related

- [Obtain credentials in Amazon MSK](/obtain-credentials-in-amazon-msk.md)
- [(Optional) Grant permissions for Amazon MSK cluster running ACL](/optional-grant-permissions-for-amazon-msk-cluster-running-acl.md)
- [Discovery scans](/discovery-scans.md)
- [Viewing scan results in Data Command Graph](/viewing-scan-results-for-data-system-connectors.md)
- [Using the Streaming Data Discovery dashboard](/using-the-streaming-data-discovery-dashboard.md)
