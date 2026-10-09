---
title: "Using exact data indexes and profiles"
slug: "using-exact-data-indexes-and-profiles"
status: "update"
updated: 2026-08-10T21:00:09Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/using-exact-data-indexes-and-profiles"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using exact data indexes and profiles

Exact data indexes and Exact data profiles help discover and secure sensitive data to match it with the detected classifications for your structured and unstructured data systems. This eliminates false positives and lets you focus on accurate detections, making it a highly effective tool for sensitive data discovery.

> [!WARNING]
> **Important**
> 
> Exact data profiles run on tables and files that contain all data element types defined in the profile. For example, a profile with Email and SSN scans only tables that include both data elements selected in the discovery scan.
> 
> Exact Data Matching starts with the creation of an Exact Data Index. This is created using a hash function (SHA256) that is performed locally on the pod to ensure that your actual data does not leave your environment. When a discovery scan is initiated with an Exact Data Profile using the Exact Data Index generated, it needs to be accessible by the pod that is running the scan job.

The Exact Data Index is stored in Private Cloud Storage (PCS) if configured; otherwise, it's saved within your tenant in the Securiti Cloud. For more information, see [Private Cloud Storage](/v1/docs/system-settings-configuring-private-cloud-storage) documentation. Securiti stores multiple PCS configurations on its platform.

You can configure multiple PCS instances in Securiti. Each data system is linked with its own PCS instance, and Securiti automatically uses the correct PCS instance when processing cases.

| Feature | Description | Example use case |
| --- | --- | --- |
| Exact Data Index | With Exact Data Indexes, you can define the sensitive data you want to scan, choose which columns to include, and set primary identifiers for both structured and unstructured data. | If you have an exact data index with Email and SSN, and an exact data profile where SSN is the primary field and Email is the secondary, you can use this profile in a discovery scan. The scan looks through your data and finds tables and files matching Email and SSN pairs. This helps accurately identify sensitive records by matching them exactly in both structured and unstructured data. ![ediSchema.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d86a4ee2-4855-bf0e-cffa-098616c588dc.png) |
| Exact Data Profile | In the Exact Data Profile, you can use the exact data index to find the exact match of data elements configured in discovery scans. |

> [!WARNING]
> Important
> 
> We recommend that you consider the number of records when setting an indexing approach. Use the table below to understand the recommended indexing.
> 
> | Number of Records | Indexing Approach |
> | --- | --- |
> | Less than 90 million records | Create a single index |
> | 90 million to approximately 500 million records | Create multiple indexes. |
> | More than 500 million records or 2 GB of memory usage | Create multiple indexes and contact [support@securiti.ai](mailto:support@securiti.ai) to enable an extended memory limit. |

### **​Example use cases for Exact Data Matching​​**

The following diagram shows the steps to use an exact data profile in discovery scans for exact data matching.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/EDMFlow.svg)

1. Creating an exact data index
  1. Using an exact data index in a custom data element
2. Creating an exact data profile
3. Configuring a discovery scan
4. Viewing the scan results

### 1. Creating an exact data index

#### Exact data index interactive demo

To learn how to create an exact data index, watch the video below:

[Embedded content](https://app.storylane.io/demo/az26r3tgi4r9?embed=popup)

Exact data index helps you detect and secure your most sensitive content, particularly data such as SSN and bank account numbers, with zero false positives. To create an exact data index:

1. For self-hosted data systems only, [activate the pod](/v1/docs/securiti-pods-and-elastic-pods).
2. [Activate and authenticate data systems (structured or unstructured)](/v1/docs/configuring-connectors-for-monitored-data-systems). To view supported data systems, see [Supported data systems for exact data index creation](/v1/docs/supported-data-systems-for-exact-data-indexes).
3. In Securiti, open **Sensitive Data Intelligence**, and choose **Data Classification** > **Exact Data Indexes**.

![sdiEDIMenu.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5a74f3ab-3af5-8881-61f4-6d3e0f8ef777.png)

It displays the **Exact Data Index** page.
4. On the Exact Data Index page, near the upper right corner, click **+ Add Exact Data Index** as shown below:

![List of exact data indexes with descriptions and fields in a system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 9.57.33 PM.png)
5. From the **Organization** menu, choose an organization for which you want to create the exact data index.

![Dropdown menu for selecting organizations in the Exact Data Indexes section.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 9.57.49 PM.png)

> [!NOTE]
> **Note**
> 
> You can subscribe to the **Multiple Org Unit Selection** feature only if you are also subscribed to the **Manage Org Units** feature, which is a premium feature that is available by subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable these features for your Securiti tenant.
6. In the **Details** area, enter the data index name and description.

> [!CAUTION]
> Warning
> 
> The character limit for naming classification resources and their categories is 50 characters. If a name exceeds this limit,​ Securiti shows an error message. Existing names remain unchanged.
  1. Choose **Data Connector**, a data system name, and the related instance. For example, you can choose Amazon S3.

> [!WARNING]
> **Important**
> 
> EDM indexing may take longer for some data systems, including **GCP MySQL**, **GCP PostgreSQL**, and **Teradata**. The following table enlists the minimum indexing durations based on the record volume.
> 
> | Data System | Record Volume | Estimated Time |
> | --- | --- | --- |
> | GCP MySQL / GCP PostgreSQL | 1 million records | 1 hour and 41 minutes |
> | 10 million records | 16 hours and 50 minutes |
> | 100 million records | 7 days |
> | Teradata | 100 million records | 9 hours |
  2. Next, enter the path where your CSV file containing the sensitive data is stored in the data system, then click **Scan Data System Instance** to perform the field classification on the CSV file.

For a structured data system such as Snowflake, choose the relevant database tables and schema.

![ediCSVPath.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7e0cc852-b272-625b-ce1f-a80bf2df8038.png)

> [!NOTE]
> **Note**
> 
> - For structured data, it's recommended to know the tables in the database schema, and they must be scanned before creating an exact data index.
> - For unstructured data, ensure you have the CSV file path ready when creating an Exact Data Index. The file size limit is up to 5GB.
> 
> After Securiti scans the data system instance, it populates the **Schema** details with the schema found in the input file or table.
7. In the **Schema** area, for each field, you want to include in the index:
  1. Use its **Data Element Type** menu to identify its respective data element type, and mark its **Include Field in Index** checkbox as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image4(1).png)
  2. To make any of your data element types a primary field, mark the **Primary Field** checkbox.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image3.png)

> [!NOTE]
> **Note**
> 
> Make sure to select at least one primary field. On marking a **Primary Field**, the **Include Field in Index** is automatically marked.
  3. To make any field case-insensitive, uncheck the **Case Sensitive** checkbox.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image1.png)

> [!NOTE]
> Note
> 
> - By default, case sensitivity is enabled for all fields. Case-insensitive fields are supported only on pod version 1.138.0 and above.
> - If you change the case sensitivity for fields that are already indexed, you must reindex the affected templates.
  4. To disable text normalization for any field, unmark the **Text Normalization** checkbox. **Text Normalization** removes special characters from strings and standardizes the text to improve matching accuracy.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image2.png)

> [!NOTE]
> Note
> 
> - By default, **Text Normalization** is enabled for all fields.
> - If you change the text normalization for fields that are already indexed, you must reindex the affected templates.
8. In the Index area, click **Initiate Indexing**.

Once indexing is complete, you can proceed to associate the exact data index with exact data profiles.

> [!NOTE]
> Note
> 
> Securiti supports multipart uploads for large files during indexing, which improves indexing efficiency. This support is available for the following data systems:
> 
> - Google Cloud Storage (GCS)
> - Azure Storage
> - AWS S3
9. Scroll up and from the upper right side of the page, click **Create Index**.

> [!WARNING]
> Important
> 
> Ensure that the uploaded file is correctly formatted for EDM indexing, including consistent columns and non-duplicate headers. If the format is incorrect, indexing fails and an error is displayed.

#### a. Using an exact data index in a custom data element

You can optionally use exact data indexes with a custom data element, and then select that custom element in the **Sensitive Data** section when configuring your discovery scans. This lets you target specific, known sensitive values more accurately during the scan.

1. [Configure a custom data element type](/v1/docs/configuring-custom-data-element-types).
2. [Create an exact data index](https://helpcenter.securiti.ai/v1/docs/using-exact-data-indexes-and-profiles).
3. Edit the exact data index you created above and choose the above custom data element name for the **First Name** field from the **Data Element Type** column.

![firstname_dataelement.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aa01a2b4-0f4e-b47b-d0b5-322ab933487f.png)
4. Edit a custom data element and choose an exact data index in the **Limit to Exact Data Matches** option.
5. Select the match percentage threshold to be used when performing table classification using this custom data element.

![editCustomDEMatchPercentage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f90e2953-7380-45da-0d40-3ac043974079.png)
6. Save your changes.
7. Configure a discovery scan and in the **Sensitive Data** section, choose the relevant custom data element that you configured, and save your changes as well as the relevant exact data profile.

![customDataElementwithIndex.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fe9020f9-3458-44b9-2096-615adfc4a654.png)
8. To view results, see [Viewing the scan results for the exact data index and profile](/v1/docs/using-exact-data-indexes-and-profiles).

### 2. Creating an exact data profile

#### Exact data profile interactive demo

To learn how to create an exact data profile, watch the video below:

[Embedded content](https://app.storylane.io/demo/l9ixa2hjyjbf?embed=popup)

Exact data profiles help you use them in the discovery scans for structured or unstructured data for exact data matching of data elements such as SSNs and bank account numbers, with zero false positives. To create an exact data profile:

1. [Create an exact data index](https://helpcenter.securiti.ai/v1/docs/using-exact-data-indexes-and-profiles) and mark the relevant primary and secondary fields that you want to use in the exact data profiles.
2. In Securiti, open **Sensitive Data Intelligence**, and choose **Data Classification** > **Exact Data Profiles**.

![sdiEDPMenu.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3ef89576-361c-b104-c90d-a0e283f842a5.png)

It displays the **Exact Data Profiles** page as shown below:

![List of active data profiles with descriptions and languages in system settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.00.25 PM.png)
3. Near the upper right corner of the page, click **+ Add Exact Data Profile**.

![List of active data profiles with options to add new profiles and manage settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.01.32 PM.png)
4. From the **Organization** menu, choose the organization in which you want to create the exact data profile.

![Dropdown menu for selecting organization in Exact Data Profiles settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.00.37 PM.png)

> [!NOTE]
> **Note**
> 
> You can subscribe to the **Multiple Org Unit Selection** feature only if you are also subscribed to the **Manage Org Units** feature, which is a premium feature that is available by subscription. Contact [support@securiti.ai](mailto:support@securiti.ai) to enable these features for your Securiti tenant.
5. In the **General Information** section, the **Status** toggle is already marked. We recommend that you disable the profile until you have finished configuring it.

![edpActivate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6eeffb45-4fa5-dbbf-3fa6-b51744d3dbf5.png)
6. In the **Details** area, enter the profile name and description.
7. In the **Scope** section, choose a specific language from the **Select Languages** menu as shown below:

![edpSelectLangauge.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fdf83be-678b-6b77-20f6-9985d467aa67.png)
8. In the **Exact Data Profile Definition** section, choose a specific Exact Data Index from the **Exact Data Index Name** menu that you created in the previous section.

> [!NOTE]
> **Note**
> 
> To use an exact data index in a profile, ensure the index has been created and initiated from the Index section while configuring the exact data index.

![edpEDISelection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2091fda0-ac1c-bd60-8465-bbff32f19823.png)

> [!NOTE]
> **Note**
> 
> Once you create an exact data index, you can use it in one or more exact data profiles to define exact data definitions, which help you define the criteria for your exact data classifications.
9. Expand the **Exact Data Profile Definition** field and choose a primary field, for example, email. There can be multiple fields as well that you marked as primary while creating the exact data index.

> [!NOTE]
> **Note**
> 
> Each exact data profile requires at least one primary field. The primary field is a unique key that your exact data profile is based on. It is a required field that must be unique based on your data records.
  - (Optional) Choose a secondary field. There can be multiple fields that you can use to create an expression, which is a combination of primary and secondary fields.

Use it to evaluate your exact data profile definition to make sure it embodies the logic you intend.

![edpPrimarySecondaryFields.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3aecc660-185f-310b-3138-275df1608cfa.png)
  - In the **Exact Data Profile Expression** field Securiti shows an expression combined with the primary and secondary fields.

![edpExpression.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7a6b1b68-6c66-c1b4-fe8b-05e821ea5cdb.png)
10. Scroll up and from the upper right side of the page, click **Create Profile**.

#### Enabling or disabling an exact data profile

- To enable the profile, scroll back to the top of the page and enable the **Status** toggle.

![List of active data profiles with toggle switches for enabling or disabling features.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.00.55 PM.png)
- To disable the profile, turn the **Status** toggle off. Securiti shows the affected content profiles in a popup before you proceed to save. You can cancel it or proceed to click the **Confirm and Disable** button to disable an exact data profile.

### 3. Run a discovery scan

#### Discovery scan for unstructured data

1. Create a discovery scan for an unstructured data system such as Amazon S3 and choose its relevant instance, define the scope, and scan conditions according to your requirements.
2. In the **Sensitive Data** section, under the **Exact Data Profile** area, mark the relevant exact data profile checkbox.

![EDP_Unstru.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-be9c710d-c276-36ba-0574-b33b150d6d0b.png)
3. Save your changes. When the discovery scan is complete, you can see the scan results in the Unstructured Data Discovery and Graph Explorer.

#### Discovery scan for structured data

1. Create a discovery scan for a structured data system such as Snowflake, choose its relevant instance, and define the scope according to your requirements.
2. In the **Advanced Settings**, mark the **Allow Exact Data Profiles** checkbox and enter the scan depth value for exact data scanning.

![discovery_scan_allow_edp.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3cdb1c6e-c217-d4a5-94a6-f62908366aac.png)
3. In the **Sensitive Data** section, under the **Exact Data Profile** area, mark the relevant exact data profile checkbox.

![edp_snowflake.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d226a05e-a8ef-ad9c-42d7-552728cdf004.png)
4. Save your changes. When the discovery scan is complete, you can see the scan results in the Structured Data Discovery and Graph Explorer.

### 4. Viewing the scan results for the exact data index and profile

#### Viewing exact data profiles in the Structured Data Discovery dashboard.

To view exact data profiles in the Structured Data Discovery Classic View:

1. In Sensitive Date Intelligence, from the left panel, choose **Data Explorers** > **Structured Data Discovery**.
2. Scroll down and choose the **Tables** tab. You can see the **Exact Data Profile** column as shown below:

![mariaDBExactDataIndexSDEv1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3341251d-4a93-92ee-7d5d-7faf0778a873.png)

To view exact data profiles in the Structured Data Discovery New Experience:

1. In Sensitive Date Intelligence, from the left panel, choose **Data Explorers** > **Structured Data Discovery**.
2. Switch to **New Experience**.
3. From the left panel, choose the **Tables** tab. You can see the **Exact Data Profile** column as shown below:

![mariaDBEDBsdeV2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ac6ad5f5-5b6b-6646-1056-8957960a7eb3.png)

#### Viewing exact data profiles in the Unstructured Data Discovery dashboard

To view exact data profiles in Unstructured Data Discovery:

1. In Sensitive Date Intelligence, from the left panel, choose **Data Explorers** > **Unstructured Data Discovery**.
2. From the upper left side of the page, click the plus sign **(+)**, the **Exact Data Profile** filter, choose a relevant profile, and click **Apply**.

![udeMariaDBEDP.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9d7f1e9f-0aed-78f4-d79c-3f37ce63d9ab.png)
3. Expand the second row of tiles to see **Exact Data Profiles** as shown below:

![udeedpFilterandTile.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7217772b-d650-07e8-cafd-be6ba96916bf.png)
4. Additionally, scroll down to the **Documents** grid, and expand an entry to the Exact Data Profile with counts.

![mariaDBDocumentsEDP.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1eb6e88b-6709-aad8-40e4-b88f6d79d3bc.png)

#### Viewing exact data profiles in the Graph Explorer

To view exact data profiles in Graph Explorer:

- In **Graph Explorer**, from the upper left side of the page, click the plus signs **(+)**, use the **Exact Data Profile** filter, and select a relevant data system as shown below:

![ge_EDP.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-db00a4f7-05a4-ccc6-4475-8d19c41d1232.png)

Additionally, you can view exact data profiles in the following properties:
  - Table
  - Data System
  - Files

#### Use Case: Securing Sensitive Consumer Data

Sensitive information types help identify and govern data to prevent inappropriate sharing and aid in discovery. If you need to match exact values instead of generic patterns, Exact Data Match classification lets you create custom sensitive types that are dynamic, scalable, accurate, secure, and optimized for structured data.

#### Scenario

Here, we have an example of a large enterprise in retail, finance, or healthcare that may need to locate and secure sensitive consumer data—like personal identifiers and payment details—spread across hundreds of data environments, including cloud warehouses, SaaS platforms, and on-prem databases.

To ensure the precise discovery of sensitive information and minimize false positives, the organization uses our [Exact Data Match (EDM) Classification tool](/v1/docs/securiti-pods-and-elastic-pods).

#### Implementation Details

1. Create an exact data index and
  - Include SSN in indexed fields
  - Choose First Name and Last Name as primary fields

![ediExampleIndexFields.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-27cb000d-fbb7-505f-f200-acdd2098ce66.png)
2. Create an exact data profile and
  - Choose SSN as a primary field
  - (Optionally) Choose First Name and Last Name as the secondary field

![edpExample.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1af282bb-883d-1d12-a067-93770df45c33.png)
3. Define a scanning policy
  - Configure a discovery scan and in the Sensitive Data area, choose SSN, First Name, and Last Name

![dsSSN.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8ca6a273-11c4-42c4-633b-d9eae28767ea.png)

![dsName.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-92520c0e-16e9-d500-c336-67da8cead075.png)
4. Choose the relevant exact data profile from the **Sensitive Data** section of discovery scans:

![chooseEDP.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0536f58c-8b32-d1dc-3666-b8e9975e76f0.png)

> [!NOTE]
> **Note**
> 
> A match is confirmed only when the primary field appears alongside the defined secondary fields:
> 
> - SSN (Primary) and First Name or Last Name (Secondary)

Once matched records are identified, our exact data matching automatically classifies them as sensitive and lets you view the classified data elements in the dashboards.

![udeEDP.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-83933432-fecb-641d-878f-75decbeefbb7.png)

#### Conclusion

Securiti’s Exact Data Match Classification provides a high-precision solution for identifying and securing sensitive consumer data across the enterprise. It empowers security and privacy teams to implement robust data protection strategies, reduce compliance risk, and maintain control over sensitive assets, provided the right planning, data preparation, and logic design are in place.

---

### FAQ

#### 1. Exact data index supported for pod deployments?

Ans: Yes, exact data profile functionality is available for all our pod deployments.

## Related

- [Using the Unstructured Data Scans dashboard](/using-the-unstructured-data-discovery.md)
- [Structured Data Discovery New Experience dashboard](/structured-data-discovery-new-experience.md)
