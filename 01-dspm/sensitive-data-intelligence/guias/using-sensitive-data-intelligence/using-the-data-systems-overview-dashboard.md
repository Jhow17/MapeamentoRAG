---
title: "Using the Data Systems Overview dashboard"
slug: "using-the-data-systems-overview-dashboard"
updated: 2026-02-12T11:47:27Z
published: 2026-02-12T11:47:27Z
canonical: "helpcenter.securiti.ai/using-the-data-systems-overview-dashboard"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using the Data Systems Overview dashboard

The Data Systems Overview dashboard shows the important statistics related to IaaS Cloud and SaaS connectors that include native and non-native assets, and structured and unstructured data systems distributed across multi-cloud environments used for scanning. This dashboard also shows brief stats about connected data system instances and total and scanned data volume for structured and unstructured data systems.

This dashboard opens by default when you open the **Sensitive Data Intelligence** module. At the top of the dashboard, you can see separate sections for IaaS clouds and SaaS clouds.

## IaaS Clouds

At the top of the IaaS Clouds, there are a few tiles that give you a view of your IaaS metrics and security posture at a glance. The data is shown by clouds, regions, data systems, and violations, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NZH3M61T.png)

After the top tiles, you can see a Sankey chart that you can use to filter the dashboard view. Use the menu at the upper right side of the Sankey chart to display the following systems on the Sankey chart and also on the Cloud Regions world map below it:

- **All Systems** refer to all IaaS systems, [AWS](/v1/docs/creating-an-aws-iaas-instance-version-1111-and-later), [GCP](/v1/docs/creating-a-gcp-iaas-instance-version-1124-and-later), [Azure](/v1/docs/integrating-securiti-with-microsoft-azure), or [OCI.](/v1/docs/integrating-securiti-with-oracle-cloud-infrastructure)
- **Native assets**
- Native assets are inherently part of the organization's managed data infrastructure, including structured, unstructured, relational, and non-relational databases. These are integrated into the company's on-premise or multi-cloud environments. Securiti platform discovers and catalogs these native data assets by leveraging AI-driven tools to identify sensitive data and classify it to ensure compliance with various regulations such as GDPR and CCPA.
- **Example**
- For the AWS cloud, the native assets can be Amazon S3, Amazon Athena instances, and so on.
- **Non-native assets**
- Non-native assets, also called shadow data assets, are not inherently part of the organization's managed data infrastructure, but there are no security controls or policies in place. Securiti platform discovers and catalogs non-native or shadow data assets by leveraging AI-driven tools such as discovery scans to identify them across multi-cloud environments and integrates them into a comprehensive asset catalog.
- **Example**
- For GCP, the non-native assets can be MySQL, SQL Server, and so on.
- For information on supported data systems, see [Supported data systems in Securiti](/v1/docs/supported-data-system-connectors-in-securiti).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-PX33HWZB.png)

### Sankey chart

On the right of the Sankey chart, this dashboard shows the breakdown of security risk levels ranging from very low to very high. You can switch to view compliance with different standards that are being followed by Securiti.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XIKZM6AQ.png)

As with all Securiti dashboards, you can also use the Filter panel to filter the view and home in on specific data.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NBIV29MW.png)

### Cloud Regions

Below the Sankey chart, there is a world map that shows your cloud system regions and the traffic between them. This also shows counts for the region-wise distribution of native and non-native data systems on the right panel.

The display includes shadow assets if you have enabled flow log parsing for the IaaS systems (GCP, OCI, AWS, AZURE).

You can filter the display (and the Sankey above it) by IaaS cloud, as shown below:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-H5CX4964.png)

### Data Systems, Regions, and Accounts

Below the map, you can see the **Data Systems**, **Regions**, and **Accounts** tabs.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-JE5IDCSF.png)

#### Data Systems

The **Data Systems** tab lists the structured and unstructured data systems, as well as the tables scanned for structured data systems and files scanned for unstructured data systems.

You can resize the width of columns appearing under the **Data Systems** widget for a more personalized viewing experience. Move the cursor to the edge of the column, then click and hold the left mouse button. Further, drag the cursor to the left or right to adjust the width of the column and release the mouse button.

The following sections describe the key metrics for scan statistics of structured and unstructured data systems.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZZ99SH97.png)

You can resize the width of columns appearing under the **Data Systems** widget for a more personalized viewing experience. Move the cursor to the edge of the column, then click and hold the left mouse button. Further, drag the cursor to the left or right to adjust the width of the column and release the mouse button.

**Unstructured data systems**

For unstructured data systems, scan statistics are generated using the following information:

- The size of the data system
- The volume of data system
- The capacity of the data system

This measurement lets Securiti monitor the quantity of data housed within the data system and the proportion of data scanned by the connector. The scan statistics generated using this volume information from the connectors help in evaluating the coverage of any discovery scan.

**Note**

The total size of the data system refers to the overall size of the files scanned by the connector.

**Structured data systems**

For structured data systems, the scan statistics are generated using the following information:

- Number of databases, schemas, views, and tables
- Total count of columns across all tables

**Note**

For structured data systems, the scan by default examines the first 1,000 rows of data. This behavior can be customized based on your specific work environment needs. For further details, see the [Discovery Scans](/v1/docs/discovery-scans) section.

The list below describes the metrics displayed on the dashboard for structured data systems:

| Total number of databases | The total number of databases in a data system represents the number of databases scanned by the connector |
| --- | --- |
| Total number of schemas | The total number of schemas in a data system represents the number of schemas scanned by the connector |
| Total number of views | The total number of views in a data system represents the number of views scanned by the connector |
| Total number of tables | The total number of tables in a data system represents the number of tables scanned by the connector |
| Total number of columns | The total number of columns in the data system represents the number of overall columns scanned by the connector |

**Connecting a new or existing Pod for Data Discovery**

This section provides instructions on how to connect to a Pod for data discovery or classification.

1. Select the checkbox from the **Data Systems** list to connect to the relevant data system.
2. On the **Add** or **Select a Compute Pod for Discovery** modal, configure your existing or new pod.
3. Select the cloud provider, deployment type (Pod or Elastic pod), pod name, region, and number of maximum nodes in the case of the elastic pod.
4. Click **Connect**.

For more information, see [Pods](/v1/docs/securiti-pods-and-elastic-pods) documentation.

#### Regions

**Integrating an IaaS Cloud account (AWS, Azure, GCP, and OCI)**

To integrate your IaaS cloud accounts, click the plus sign (+). For more information, see the [Cloud Systems](/v1/docs/data-security-posture-management-solution) documentation.

#### Accounts

The **Accounts** tab provides an overview of cloud instances connected with the count for resources and data systems.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-20CVO6YH.png)

## SaaS Clouds

The **SaaS Clouds** section shows the important statistics related to SaaS Cloud connectors, such as connected applications or instances, scanned instances, and counts for data element categories, content profiles, as well as document categories.

This section also redirects you to configure SaaS cloud connectors' permissions to configure data scans for Securiti cloud connectors as well as to set up connector activation configuration.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-875DXATS.png)

This section also redirects you to configure SaaS cloud connectors' permissions to configure data scans for Securiti cloud connectors, as well as to set up the connector activation configuration.

| Widget | Description |
| --- | --- |
| Application / Instances | In the first widget, you can see counts for applications/instances, scanned instances, and connected instances associated with your SaaS cloud accounts. |
| Data Element Categories | In the Data **Element Categories** widget, you can see counts for data element categories identified during the scan process and the level of data sensitivity ranging from very high to very low. |
| Sensitive Documents | In the **Sensitive Documents** widget, you can see the counts for content profiles and document categories falling in different areas. |
| App Instance | The last widget is **App Instances**, where Securiti platform lists the app instances that you can connect to your SaaS cloud accounts. The list also shows the status of each app instance, which can be active or inactive. |

### Connecting app instances to SaaS clouds

From the **App Instances** list, click **Connect**. It takes you to the Data Systems page, where you can add fields to connect your apps to SaaS cloud data systems.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5G0OPJY7.png)

For more information, see [Configuring data system connectors](/v1/docs/configuring-connectors-for-monitored-data-systems).

### Connecting SaaS clouds for data discovery

From the **App Instances** list, click **Discovery**. It takes you to the relevant Data Systems page, where you can add fields to connect your SaaS cloud data systems with Securiti.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-LD12WGK2.png)

## Related

- [Discovery scans](/discovery-scans.md)
- [Pods deployment](/pods-deployment.md)
