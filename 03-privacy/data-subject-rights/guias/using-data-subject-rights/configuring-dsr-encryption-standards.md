---
title: "Configuring DSR encryption standards"
slug: "configuring-dsr-encryption-standards"
updated: 2026-08-12T07:49:50Z
published: 2026-08-12T07:49:50Z
canonical: "helpcenter.securiti.ai/configuring-dsr-encryption-standards"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Configuring DSR encryption standards

Securiti lets you configure encryption standards for downloading DSR reports or exporting DSR requests as per your requirements. You can also disable encryption if you lack decryption keys or tools.

> [!NOTE]
> **Note**
> 
> Only Super Admins within your Securiti tenant can make configuration changes to encryption standards.

1. In the Data Subject Rights module, choose **Settings > DSR Settings**.
2. Scroll to the Encryption Standard section, click **Edit** and choose the encryption standard from the **Encryption Standard for Downloaded Zip Files** menu and click **Save.**

![Settings for data subject rights, including encryption standards and module owner access.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-08-12 at 12.41.42 PM.png)

> [!NOTE]
> **Important**
> 
> If you choose the “No encryption” option, the system exports or downloads files without any file data protection which may lead to data theft.

Disabling encryption impacts the following cases in the DSR module:

- Exporting requests from DSR Dashboard
- Generated Report sent to Data Subject Portal
- Exporting requests from the Privacy Central Dashboard

> [!NOTE]
> **Note**
> 
> This setting is a global tenant setting and it affects all organizations. Any DSR report generated or DSR requests exported after the setting update follow the new setting. Existing reports remain unaffected by the setting change.
