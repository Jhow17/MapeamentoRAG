---
title: "Acquire authentication credentials in Google Bigtable"
slug: "acquire-authentication-credentials-in-google-bigtable"
updated: 2026-04-28T04:33:39Z
published: 2026-04-28T04:33:39Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-google-bigtable"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Google Bigtable

> [!NOTE]
> **Note**
> 
> This procedure assumes you have a Google Bigtable instance before enabling the following prerequisites or Permissions for connector activation.

Perform the following steps to acquire authentication in Google Bigtable:

### Step 1- Create a Service account in Google Cloud Platform

1. Log in to [Google Cloud Platform](/v1/docs/securiti-pods-and-elastic-pods).
2. On the left sidebar, choose **IAM & Admin** > **Service Accounts**.

![IAM-ADmin.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0d63aacf-4b42-da9b-5920-172cb95c65d1.png)
3. On top of the **Service accounts** page, click **+ Create service account**.

![__service_ac.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3673b4ba-13da-e1d8-2a9d-56e7030078eb.png)
4. On the **Create service account** page, add the following information.

| Parameter | Description |
| --- | --- |
| Service account name | Enter a convenient name for the service account. See the example. *Google-Bigtable-Test-Account* |
| Service account ID | Service account ID is automatically generated based on the Service account name. See the example below. *google-bigtable-test-account* > [!NOTE] > **Note** > > This Service account ID is added to the email for your service account. |
| Service account description | Enter a description to add important details for your service account. |

![service-ac-form.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6e4553ea-fe20-2133-acfc-5e9eee802a36.png)
5. Under the **Grant this service account access to project** section, select the following roles from the **Role** menu by clicking **+ ADD ANOTHER ROLE**.

Click **Continue**.
  - Bigtable Reader
  - Bigtable Viewer

![bigtable-reader-viewer.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2b147dc5-fd1f-00af-da9c-b98b9aa3b5ab.png)
6. (Optional step) Under the **Grant users access to this service account** section, assign the following roles by entering the email of the user to whom you want to share the access.

> [!NOTE]
> **Note**
> 
> You can skip this step if you do not want to share access with the other users.
  - In the **Service account users role** field, add the email of user to whom you want to share access.
  - In the **Service account admin role** field, add the email of user to whom you want to share access..

![Grant-user-access.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d596fa1d-a231-f1d1-17c2-f232bce6adff.png)
  - On bottom of the **Create service account** page, Click **Done**

It creates a service account with the assigned roles.

### Step 2 - Create a key for your service account.

1. On the left sidebar, choose **Service Accounts**.
2. On the **Service accounts** page under the **Email** Column, choose the newly created service account by clicking on the link.

![new-service-ac.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-283e6a30-e488-8c4f-d637-127de311bc21.png)
3. On the **Service account details** page under the **KEYS** tab, select the **Create new key** from the **ADD KEY** menu.

![add-key-btn.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-501ed8a1-66c9-4c74-fa7d-f6cf6e53c236.png)
4. On the **Create private key for “your service account”** popup, perform the following steps:
  1. Select the **JSON** radio button for the **Key type**.
  2. Click **CREATE**. ![pvt-key-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-080cd3c6-28e2-6fe2-3575-ecb593807623.png)

> [!NOTE]
> **Note**
> 
> It downloads the JSON file into your device. Save the file to use it for Connector Activation.
5. It shows the JSON success message popup as shown below. Click **Close**.

![saves-pvt-key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3fb81181-dbd7-0ead-e76c-e1da9cb15b01.png)

### Step 4 - Obtain credentials for Google Bigtable

1. In the top search bar, search and choose **Bigtable**.

![Bigtable_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3be4dbcf-ee6f-a92c-bc65-11a6dfdb0aaf.png)
2. On the **Bigtable Instances** page, record the **Instance ID**.

![bigtable-instances.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1554fc3b-2352-c190-6a2a-eb0eaf1f67c6.png)
3. On the top left, next to **Google Cloud** logo, click Project **(IaaS)**.
4. On **Select a project** popup, record the **Project ID** to use it later for Connector Activation.

![Select-project-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-42375cc2-b079-1cbd-1958-694e71888522.png)
5. Proceed to [Activate the Google Bigtable connector in Securiti](/latest/docs/activate-the-google-bigtable-connector-in-securiti) or [(New UI) Connecting Google Bigtable with Securiti](/latest/docs/new-ui-connecting-google-bigtable-with-securiti).
