---
title: "Uploading JDBC driver files in Securiti"
slug: "uploading-jdbc-driver-files-in-securiti"
updated: 2026-04-06T09:08:20Z
published: 2026-04-06T09:08:20Z
canonical: "helpcenter.securiti.ai/uploading-jdbc-driver-files-in-securiti"
area: integrations
modulo: drivers
tipo: guia
data_captura: 2026-10-08
---

# Uploading JDBC driver files in Securiti

You can upload JDBC Driver files for SQL Data system connectors from within Securiti. Use this feature to upload drivers for SQL connectors that use Securiti pods to connect, instead of uploading them manually.

You must downloawehookd the JDBC driver required for your Data system Connector uploading the JDBC Driver files. For more information, see [Downloading JDBC drivers for SQL connectors](/v1/docs/downloading-jdbc-drivers-for-sql-connectors).

Securiti performs antivirus checks on the drivers you upload. If the antivirus check fails, Securiti rejects the upload.

1. In Securiti, from the left navigation menu, click the **Jewel** icon and choose **Integrations.**
2. On the **Integrations** page, from the left menu, select **Drivers**. View and search for drivers from the page.

![Integration dashboard showing drivers, data systems, and options to add drivers.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/drivers_landingpage(1).png)
3. To upload a driver file, from the upper right corner of the page, click **Add Drivers**.
4. Drag and drop Connector JAR files or upload a file in the following pop-up, as shown below.

![Interface for adding a new driver with options for file upload and data system selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/adddrivers.png)

When you upload a driver file, it can take some time to complete. You can see the progress bar for the file you upload.
5. Once you've uploaded the driver files for a connector, you can view the uploaded driver for that connector at the top in the grid.

You can delete or upload a new driver version by clicking the three vertical dots menu.

![Integration dashboard displaying data systems and options to upload or delete drivers.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/drivers_settings.png)

> [!NOTE]
> **Note**
> 
> - To update and replace an old driver file, you must use the same file name as the previous file. In case of a new name, Securiti uploads the file as a new driver which can still be used as an updated version.
> - You'd see the driver(s) in the Driver files menu when activating the Connector.

For more information, see [Downloading JDBC drivers for SQL connectors](/v1/docs/downloading-jdbc-drivers-for-sql-connectors).

## Related

- [Supported data system connectors in Securiti](/supported-data-system-connectors-in-securiti.md)
- [Downloading JDBC drivers for SQL connectors](/downloading-jdbc-drivers-for-sql-connectors.md)
