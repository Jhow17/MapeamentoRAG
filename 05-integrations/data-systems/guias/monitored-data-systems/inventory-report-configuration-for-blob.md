---
title: "Inventory report configuration for Google Cloud Storage"
slug: "inventory-report-configuration-for-blob"
updated: 2026-04-28T04:36:29Z
published: 2026-04-28T04:36:29Z
canonical: "helpcenter.securiti.ai/inventory-report-configuration-for-blob"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Inventory report configuration for Google Cloud Storage

> [!NOTE]
> **Important**
> 
> This process is required when using **Native Inventory** method for Data Inventory Sync. Skip this topic if you are using the default Listing method.

You must create an inventory report Configuration to use the **Native Inventory** method for running Data Inventory Syncs for GCS.

### Creating inventory report configuration

To create inventory report Configuration:

1. In the Google Cloud console, select the **Cloud Storage Buckets** page.
2. Click **Buckets**.

![gcs_buckets_page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-acda4b93-36d6-0ac7-a941-058404b45456.png)
3. From the list of buckets, click the name of the bucket you want to use as the source bucket.

![gcs_sourcebucket.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c5383c09-3f6b-10cd-9b5a-08736cacac82.png)
4. On the **Bucket details** page under the **INVENTORY REPORT** tab, click **CREATE REPORT Configuration**.

![gcs_inventoryreports_tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-82e18c9d-92a7-391e-6cf6-edab0fa2a15a.png)
5. In the **Identify your report Configuration** section, apply the following settings:

| Setting | Description |
| --- | --- |
| Report Configuration display name | Add a display name for the inventory report Configuration. The display name can contain up to 256 characters |
| Choose metadata fields | In the **Choose metadata fields** section, select the metadata fields you want to include in your inventory reports. > [!NOTE] > **Note** > > If you enable **Process All Versions** in Data Inventory Sync, you must also select the following metadata fields to ensure proper functionality: > > - *timeDeleted* under Time > - *generation* under Content > > For more information, see [Configuring Data Inventory Sync for Google Cloud Storage](/v1/docs/securiti-pods-and-elastic-pods). |

![gcs_reportconfig_create.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-edadfc62-dbd8-ebb8-2396-0b0d02fbf62e.png)
  - Click **Continue**.
6. In the **Choose a file format** section, select the file format to generate inventory reports, in.

![gcs_report_format.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9bffcb0d-ab80-40e5-23da-1aa8b3d4fb7b.png)
7. In the **Choose a destination bucket** section, select the bucket to use as a destination bucket.

![gcs_destination_bucket.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-365fa443-847c-1e8e-e4d3-fb4e53dddc00.png)
8. (Optional) In the **Enter destination path** section, you can specify a destination path where the generated inventory reports are stored.
9. In the **Scheduling options** section, specify the frequency, start date, and end date for generating reports.

![gcs_scheduling_options.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-22aa6f0a-f7b1-7848-6fcc-2dfe9e12396c.png)
10. Click **Create**.

The Report Configuration details page is displayed. The metadata of generated inventory reports appear on this page.

### Acquiring inventory report configuration name

To acquire the **Inventory Report Configuration** name to use in the GCS Connector Configuration:

1. In Google Cloud Console, from the left navigation bar, select **Buckets**.
2. Click **Inventory Reports** tab to list all the configurations.
3. Click on the required inventory report Configuration to see its details.
4. Copy and save the **Report Configuration name**, as shown below.

![gcs_reportconfig_details.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a66e4ca8-da4f-9e22-c483-3e5c0c334eeb.png)

Proceed to [(New UI) Connecting Google Cloud Storage with Securiti](/latest/docs/new-ui-connecting-google-cloud-storage-with-securiti) or [Activate the Google Cloud Storage connector in Securiti](/latest/docs/activate-the-google-cloud-storage-connector-in-securiti).
