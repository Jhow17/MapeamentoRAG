---
title: "Using Credentials File authentication"
slug: "using-credentials-file-authentication"
updated: 2026-04-28T04:36:48Z
published: 2026-04-28T04:36:48Z
canonical: "helpcenter.securiti.ai/using-credentials-file-authentication"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Using Credentials File authentication

The **Credentials File** Authentication method lets you authenticate your Google Cloud Storage (GCS) Connector using a service account key file. This method uses a JSON Credentials file that contains the Authentication details required for the Connector to interact with your Google Cloud Storage buckets.

Follow the steps below to create a **Credentials File**:

1. Create a service account and assign the relevant roles and Permissions to it as described in [Prerequisites for Google Cloud Storage connector](/latest/docs/prerequisites-for-google-cloud-storage-connector).
2. Click **Add key** and select **Create new key** from the menu.

![gcs_addkey.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4fc7a4a8-8236-17e3-fdb4-2d99a2fc113c.png)
3. On the popup, select **JSON** and click **Create**. This creates and downloads the JSON file, save it to use later.

![gcs_createJSON.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5546a9b7-fe41-6107-3ad2-b570228f284d.png)
4. Proceed to [(New UI) Connecting Google Cloud Storage with Securiti](/latest/docs/new-ui-connecting-google-cloud-storage-with-securiti) or [Activate the Google Cloud Storage connector in Securiti](/latest/docs/activate-the-google-cloud-storage-connector-in-securiti).
