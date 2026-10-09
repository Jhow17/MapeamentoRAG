---
title: "Data Systems Overview Dashboard Deprecation Summary"
slug: "data-systems-overview-dashboard-deprecation-summary"
updated: 2026-07-20T10:31:08Z
published: 2026-07-20T10:31:08Z
canonical: "helpcenter.securiti.ai/data-systems-overview-dashboard-deprecation-summary"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Data Systems Overview Dashboard Deprecation Summary

To ensure a consistent and powerful experience, we are consolidating all data visualizations into our graph-powered tools.

Effective from release 1.137, the Data Systems Overview dashboard will be retired for customers with Universal Data Explorer or Inventory enabled for their tenants, as its functionality is now fully covered within the Universal Data Explorer and Inventory.

> [!NOTE]
> Note
> 
> - If **Universal Data Explorer** and **Inventory** are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether these are included in your plan and whether your tenant meets the eligibility requirements for their activation.

You can find all previous dashboard information and more, including advanced querying and interactive graphing within these familiar tools. This move completes our transition to a single, streamlined hub for data intelligence. The detailed comparison of the current and new behaviour has been provided below.

## Connect Data Systems

| Current Behaviour | New Behaviour |
| --- | --- |
| - There are two ways to connect a data system to a pod: - **From Universal Data Explorer or Inventory:** To connect your data systems to a pod, under the **Data Systems** tab, select your desired assets, then click the **Connect Data Systems** button on the floating modal at the bottom of the **Universal Data Explorer** or **Inventory** dashboards. > [!NOTE] > Note > > You can connect your data systems to a pod from **Universal Data Explorer** or **Inventory** from Securiti release 1.135 onwards. ![Overview of data systems with selected assets and connection options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/connect-data-systems-1.png) - **From Data Systems Overview Dashboard:** To connect your data systems to a pod, under the **Data Systems** tab, select your desired assets, then click the **Connect Data Systems** button located in the upper-right corner of the data assets table. ![List of data systems with details on cloud type, accounts, and violations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/connect-data-systems-2.png) | - From release 1.137 onwards, you can connect your data systems to a pod only from the **Universal Data Explorer** or **Inventory** dashboards. |

## Add Discovery Scan

| Current Behaviour | New Behaviour |
| --- | --- |
| - There are two ways to run discovery scans today: - **From Sensitive Data Intelligence:** To run a discovery scan on your data systems, navigate to **Sensitive Data Intelligence > Discovery Scans > Scan Definitions**, then click Create **Discovery Scan** located in the upper-right corner on the Discovery Scans page. ![Overview of Discovery Scans interface with options to create and filter scans.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/add-discovery-scan-1.png) - **From Data Systems Overview Dashboard:** To run a discovery scan on your data systems, under the **Data Systems** tab, select your desired assets, then click the **Add Discovery Scan** button located in the upper-right corner of the data assets table. ![List of cloud data systems with options to connect and add discovery scans.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/add-discovery-scan-2.png) | - From release 1.137 onwards, you can run discovery scans only from the **Sensitive Data Intelligence > Scan Definitions** page. |

## Regions

| Current Behaviour | New Behaviour |
| --- | --- |
| - You can visualize an overview of the regions, including the count of associated resources and data systems and data elements under the **IaaS Clouds > Regions** tab. ![List of AWS regions with corresponding resources and data systems information displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/regions-1.png) | - You can visualize an overview of the regions, including the associated clouds and data system count, and security posture findings under the **Management > Regions** tab. ![Overview of cloud regions with hosting details and security posture findings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/regions-2.png) |

## Accounts

| Current Behaviour | New Behaviour |
| --- | --- |
| - You can visualize an overview of connected accounts, including the associated regions, resources, data systems and their owners under the **IaaS Cloud > Accounts** tab. ![Overview of AWS accounts with details on regions, resources, and data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/accounts-1.png) | - You can visualize an overview of connected accounts, including the associated clouds, data system count, and security posture findings under the **Management > Accounts** tab. ![Overview of cloud accounts with details on hosting and security posture findings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/accounts-2.png) |

## Related

- [Deploying Pod](/deploying-pod-aws.md)
- [Deploying Pod](/deploying-pod-gcp.md)
- [Deploying Pod](/deploying-pod-azure.md)
