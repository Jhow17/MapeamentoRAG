---
title: "Using the Data Risk Explorer"
slug: "using-the-data-risk-explorer"
updated: 2026-04-27T10:42:56Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/using-the-data-risk-explorer"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using the Data Risk Explorer

#### Using the Data Risk Explorer

The Data Risk Explorer gives you detailed information about all personal data records in your environment. It gives you visibility into identities, residences, and other data. The data risk explorer shows you the aggregated risk for your entire organization. It tells the risk associated with business units (BUs), data systems, and locations at a micro level.

The Data Risk Explorer gives you an analytical display of:

- Data systems with the highest risk.
- Data system owners with the highest risk.
- Whether risk has declined (for example, if data has been retired), or increased (for example, if more data has been added).

#### Prerequisites

Follow the steps below to view the stats on this dashboard:

1. Configure data risk profiles if required; otherwise, default settings will be used for the data risk explorer dashboard.
2. The risk score can be viewed only after scanning, and you can also see the sensitive data associated with the risk.
3. The Risk Dashboard is a premium feature available by subscription. To enable it for your Securiti tenant, contact [support@securiti.ai](mailto:support@securiti.ai). Note that once enabled, the feature cannot be disabled.

> [!NOTE]
> **Note**
> 
> The risk score is calculated based on your environment's schedule after the risk scheduler is executed.

#### Summary of Data Risk Explorer dashboard

The summary of important elements, Securiti identified after completing the discovery scan jobs, is:

- Risk scores are calculated automatically after running the scheduler job, based on the latest available data in your environment.
- View counts for data elements, data systems, and relevant data locations to gain a clear overview of your data landscape and sensitive data distribution.
- View data risk trends on a daily, weekly, and monthly basis to monitor changes over time and identify emerging risks in your data environment.
- The score tree is organized in the hierarchy of locations > data elements > data systems, helping you trace and understand risk contributions at each level of your data environment.
- View a geographical map of unstructured data centers across various global locations, along with counts for key statistics such as data volume, sensitive data detections, and risk levels.
- Access a tile view of risks categorized by data systems, data system owners, and data types, making it easy to identify and prioritize high-risk areas across your data landscape.

#### Using the Data Risk Explorer dashboard

This section explains how you can use the Data Risk Explorer dashboard.

1. In Securiti open **Sensitive Data Intelligence**, then choose **Data Explorers > Data Risk**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/drDataRiskMenu.png)
2. Use the Data Risk Explorer's main parts to view the amount of inherent risk in the data your organization processes.
  - **Widgets** provide you with a bird's-eye view of the data risk exposure. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dataRisktopTiles.png)
  - **Data Risk Trend** provides a chart view of daily data risk trends.

The line graph displays the progress and trends of the overall risk score over time. The stack graph shows the relative contributions of data type sensitivity and data location sensitivity to the total risk score. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dataRisktopTrends.png)
  - **Data Risk Score Tree**, a dynamic tree structure showing factors that go into an overall risk score and displays the highest risk path.

Click a tree node to expand it, and from the View menu (near the upper right corner of the area), change the order. The tree structure uses a proprietary algorithm to aggregate risk scores from the various nodes from right to left to arrive at your overall data risk score. ![data_risk_score_tree.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e039d55c-8955-441a-d919-c26ca7bce794.png)
  - **Distribution by Data Locations** uses a world map that shows your data locations and their risk scores. ![DRE-Data-Locations_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-123d5910-e5df-7538-5ab1-e2cd760f0b4e.png)
  - **Risk Distribution Panels** employ three panels that show you the risk distribution by data system, data system owner, and data type in graphical and list form. ![DRE-Distribution-Panels_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-36ac3b79-93df-45c2-1817-767a0b7ef021.png)

#### Viewing risks associated with your data systems

You can view data risks linked to your specific data systems and discovery scans to support regulatory compliance and maintain trust with your customers and partners.

This section outlines the steps to view risks associated with your data systems and discovery scans, enabling you to monitor data exposure and take informed actions to reduce potential threats.

> [!NOTE]
> **Note**
> 
> You can view the risks associated with your data systems only for the completed discovery scans.

1. In Securiti, open the **Sensitice Data Intelligence** module, choose **Data Explorers** > **Data Risk**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/drDataRiskMenu(1).png)

This opens the Data Risk Explorer as shown below: ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dataRiskExp.png)
2. In the filter panel on the top right side of the page, in the **Data System** filter, enter the data system instance for which you created the discovery scan and click **Apply**. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/dataRiskFilters.png)

You can view the specific risks associated with this specific data element, with the data risk score and discovered data elements for a specific location. ![data_risk_score_tree.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e039d55c-8955-441a-d919-c26ca7bce794.png)

Additionally, there are some other widgets that show you the percentage of each risk related to the data system, owner, and data element types. ![otherWidgersRisk.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7a4e5546-55ac-7d17-fca3-a77782e0e873.png)

#### Configuring data risk profiles

You can configure risk profiles for your environment to identify risks related to your data systems and data elements detected through discovery scans. This section explains how to set up and manage data risk profiles effectively.

1. In the **Sensitive Data Intelligence** module, choose **Discovery Scans > Data Risk Profile** to adjust the variables that determine your risk score. ![Dashboard displaying sensitive data intelligence and data risk profile options for analysis.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 6.13.56 PM(1).png)
2. From the **Organization** menu, choose the organization for which you want to configure the data risk profile.

> [!NOTE]
> **Note**
> 
> You can subscribe to the **Multiple Org Unit Selection** feature only if you are also subscribed to the **Manage Org Units** feature, which is a premium feature that is available by subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable these features for your Securiti tenant.
  - Use the **Data Type** and **Data Location** tabs to set the importance level for that risk factor and each value's sensitivity level for that risk factor.

![Data Risk Profile settings showing data types and sensitivity levels for various categories.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-17 at 3.20.43 PM(3).png)
  - Use the **Data Concentration** tab to calibrate your risk score to suit your environment by specifying the **Number of Data Elements** needed to reach a score of 10 and 90.

![Data Risk Profile settings with highlighted Data Concentration and Data Score options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-17 at 3.21.00 PM.png)

> [!NOTE]
> **Note**
> 
> Securiti's calculation of the Data Risk score considers a global aggregate value for all data element records across your organization. It also includes scores for specific data systems, locations, owners, and residencies, allowing for targeted risk analysis at various levels.
3. When you are done adjusting the settings, click **Save** in the upper right corner of the page.

## Related

- [Viewing scan results](/viewing-discovery-scan-results.md)
