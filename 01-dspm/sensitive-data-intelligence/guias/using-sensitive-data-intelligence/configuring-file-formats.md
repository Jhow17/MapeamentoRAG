---
title: "Configuring file formats"
slug: "configuring-file-formats"
updated: 2026-04-27T21:00:23Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/configuring-file-formats"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Configuring file formats

Use the File Format Categories page to enable or disable the scanning of file formats in the unstructured data systems. These file formats also include AI models, archives, audio, video, CAD, word processing, spreadsheets, and so on. Securiti's content classification determines the file format using a combination of magic bytes, header information, and the file extension. As with other data element settings, you should disable the scanning of irrelevant file formats to improve scanning performance.

### Accessing the file types

To access the file types:

1. From the main menu, choose Sensitive Data Intelligence > Data Classification > **File Formats**.

![Securiti dashboard displaying sensitive data intelligence and file formats overview.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.12.22 PM.png)

This opens the **File Formats** page as shown below:

![Overview of file formats categorized under data classification settings in a system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.12.43 PM.png)
2. Expand a file format category to view the supported file types.

![Overview of AI model file formats and categories in system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-14 at 1.02.50 PM.png)

### Enabling or disabling a file format category

To enable or disable a file format category:

1. In Securiti, open **Sensitive Data Intelligence**, and from the left panel, choose **Data Classification > File Formats**.
2. For each category on the **File Formats** page, click the category to expand it and see a full list of the file types in the category, as shown below.

![Overview of AI model file formats and categories for machine learning applications.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.13.10 PM.png)
3. To disable the scanning of a category, unmark the checkbox at its left edge as shown below.

![Overview of file formats including AI models, archives, audio, and biometric files.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.13.25 PM.png)

When you disable a file format, Securiti shows the affected content profiles in a modal with a disabled state, before you proceed to save. The modal only appears if there are affected content profiles related to the data classification of file formats. You can cancel it or proceed to click the **Confirm and Disable** button to disable a file format.
4. When you are done enabling or disabling categories, near the upper right corner of the page, click **Save**.
