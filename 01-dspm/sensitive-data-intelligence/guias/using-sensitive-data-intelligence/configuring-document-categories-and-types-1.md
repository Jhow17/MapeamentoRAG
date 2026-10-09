---
title: "Configuring document categories and types"
slug: "configuring-document-categories-and-types-1"
updated: 2026-06-12T05:09:43Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/configuring-document-categories-and-types-1"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Configuring document categories and types

Document categories are used to define how Securiti classifies documents by grouping them into relevant categories and types using a combination of machine learning and pattern matching. To improve scanning performance, it's recommended to disable any document categories that are not relevant to your data.

To view the available document categories and types, open **Sensitive Data Intelligence** and choose **Data Classification > Document Categories**.

![Overview of document categories including Academia, Biometric, and Financial sections.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.20.29 PM.png)

When you are done configuring document categories, near the upper right corner of the page, click **Save**.

### Supported data systems for custom document types

The following data system connectors are supported for creating custom document types:

- Alibaba Cloud OSS
- Amazon S3
- Azure Blob Storage
- Azure Files
- Google Cloud Storage
- HDFS
- Microsoft 365 SharePoint Online
- NFS
- Oracle Object Storage
- SFTP
- SMB

### Adding custom document types

You can create custom document types that train the Securiti data classification system to recognize new document types. You upload examples of the documents that you want to detect, and also documents that are similar, but that you don’t want Securiti to tag with any of our system document types. Doing so trains the Securiti data classification system to recognize the documents and tag them accordingly. The document classification applies to all our data system connectors.

> [!NOTE]
> **Note**
> 
> To ensure reliable performance for the data classification system, Securiti enforces the following limits for both the positive and negative match document sets:
> 
> - Maximum number of files: 50
> - Maximum size per file: 50 MB

1. From the main menu, choose Sensitive Data Intelligence > **Data Classification** > **Document Categories****.**

![Securiti interface displaying sensitive data intelligence and document categories for data classification.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.20.52 PM.png)
2. On the **Document Categories** page, near the upper right corner of the page, click **Add Custom Document Type**.
3. In the **Details** area, give the new document type a name and description. and choose a category for it.

> [!CAUTION]
> Warning
> 
> The character limit for naming classification resources and their categories is 50 characters. If a name exceeds this limit,​ Securiti shows an error message. Existing names remain unchanged.
4. To add a new custom document category or to move it to another category, click **Add New**. Enter the name of the custom category and press **ENTER** or **RETURN** key. To move it to a new category, choose the one you added.

> [!NOTE]
> **Note**
> 
> The custom document category that you create belongs to the specific organization in which you create it.
5. In the Details area, choose a language for the document type.
6. In the **Matches** area, mark the **Near Exact** radio button to train nearly similar documents or mark the Similar radio button to train exactly similar documents. To view the documents that are nearly or exactly similar, click the Download sample files links provided on the right side of each radio button, as shown below. **![sdiDocumentCategoriesDocTypes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3b982c17-d702-1916-052f-20287aa14568.png)**
7. In the **Matches** area, for Mode choose **Data Connector** (the only mode currently available).
8. For Data System, choose your relevant data system, then choose its instance.
9. In **Positive Document Path and Filename**, enter the path and filename available your relevant data system that contains documents that are positive matches of the document type that you want to identify. For multiple documents, place them together in a zip file and enter the path and filename for the zip file.
10. (Optional) In the **Negative Document Path and Filename** box, enter the path and filename for a file containing the negative document that you want to train the system not to make mistakes for the intended document type.

**![posNegativeDocTypes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-efcdfe4c-3be6-5daf-3691-2063c9e3c7fd.png)**

> [!NOTE]
> **Note**
> 
> A negative document is not required for data classification.
11. Click **Upload**. This button is available for uploading both positive and negative documents.
12. Use the **Set Confidence Level Threshold for Matching** slider to configure how confident the system must be before identifying a document as being of the intended type.
13. In the Document Training area, click **Train Document Type** to start the system training. When the document training is complete, you may see the following.

![complete_doc_training.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-47f34bc3-8155-50f9-763e-e0fb2f4f589b.png)

### Disabling document types

- To disable an entire category, unmark the checkbox at its left edge.
- To disable a specific document category, select the entire category and disable the **Active** toggle. When you disable an entire document category or a specific document category, Securiti shows a modal of affected content profiles, before you proceed to save. The modal only appears if there are affected content profiles related to the data classification of an entire category or a specific document category. You can cancel it or proceed to click the **Confirm and Disable** button to disable a document category.
- To enable an entire document category, mark the checkbox on its left edge.
- To enable a specific document type, enable the **Active** toggle on its details page.

### Enabling document types

- To enable an entire document category, mark the checkbox on its left edge.
- To enable a specific document type, enable the **Active** toggle on its details page.

### Renaming a custom document category

Once you add a custom document category, you can see a pencil icon on the category. Click that pencil icon to rename that category and press **ENTER** or **RETURN** key. The changes to these custom categories are reflected under the discovery scan results, structured, unstructured, and streaming data dashboards.

> [!NOTE]
> **Note**
> 
> You can only rename the title of the custom document category; you cannot rename the system categories.
