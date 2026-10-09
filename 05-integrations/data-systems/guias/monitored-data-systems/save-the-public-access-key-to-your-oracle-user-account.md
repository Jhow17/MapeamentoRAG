---
title: "Save the public access key to your Oracle user account"
slug: "save-the-public-access-key-to-your-oracle-user-account"
updated: 2026-07-20T20:31:01Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/save-the-public-access-key-to-your-oracle-user-account"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Save the public access key to your Oracle user account

1. Log in to your Oracle Console at [https://console.us-ashburn-1.oraclecloud.com](https://console.us-ashburn-1.oraclecloud.com):

Oracle redirects you to your console’s homepage
2. On the left sidebar, navigate to the Governance and Administration area and click **Identity > Users**.

![OobIdentityUsers.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-26aca589-6136-8bb9-0a04-81c2bce40c6c(1).png)
3. Click on the User account you used in the initial preparation steps (in this case, eng-SaaS-signup@securiti.ai).

![OObAccountInfo.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1af9a5fa-ae02-e2f0-f996-bb138e918f0d.jpg)
4. Click on **Add Public Key**.

Mark the **Paste Public Key** radio button on the Add API Key pop-up to input the terminal’s output public key.

![add_api_key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3115803c-d980-3d02-29fb-3f5f5e07230e.png)
5. Paste the copied clipboard contents (for the public key fingerprint) into this field and click **Save**.

![OObAddPublicKey.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bb0fd05b-5b1a-1296-ec59-bff9ef0e8089.jpg)

This action assigns the key to the user account so its Credentials can be used as part of the Connector Activation process.

![OObAPIKEY.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-85852edc-6a95-0ab0-8c51-1a5348952fd6.jpg)
6. Proceed to [Connect Oracle Object Storage connector with](/latest/docs/connect-oracle-object-storage-connector-with-securiti) Securiti.
