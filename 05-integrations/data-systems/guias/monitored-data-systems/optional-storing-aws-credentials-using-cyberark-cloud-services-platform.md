---
title: "(Optional) Storing AWS Credentials using CyberArk Cloud Services platform"
slug: "optional-storing-aws-credentials-using-cyberark-cloud-services-platform"
updated: 2026-06-15T05:24:42Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/optional-storing-aws-credentials-using-cyberark-cloud-services-platform"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# (Optional) Storing AWS Credentials using CyberArk Cloud Services platform

When using CyberArk Credential Vault for credential management, Securiti recommends registering AWS credentials through the **CyberArk Cloud Services** account platform. This approach enables organizations to securely store AWS credentials within CyberArk while allowing Securiti to retrieve the required authentication details during connector configuration.

## Prerequisites

Before registering AWS credentials in CyberArk Cloud Services platform, ensure the following:

- An appropriate CyberArk Safe has been created for storing cloud credentials.
- Valid AWS Access Key ID and AWS Secret Access Key values are available.
- The user performing the configuration has permissions to create accounts within the target Safe.

## Registering AWS credentials through CyberArk Cloud Services

To register AWS credentials through CyberArk Cloud Services, perform the following steps:

1. In the CyberArk application, navigate to **Accounts** and select **Add Account**.
2. In the **Select system type** step, select **Cloud Service** as the account category, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-15 at 9.53.55 AM.png)
3. In the **Assign to Platform** step, select **Amazon Web Services-AWS-Access Keys** as assigned platform, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-15 at 9.55.38 AM.png)
4. In the **Store in Safe** step, select the appropriate Safe in which the credentials will be stored.
5. In the **Define properties** step, define account properties using the following AWS credential values, as shown Below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-06-15 at 10.00.24 AM.png)

Complete any additional mandatory CyberArk fields as required by your environment. Placeholder values may be used for fields that are not consumed by the integration.
  - **Access Key ID** – Enter the AWS Access Key ID.
  - **Secret Access Key** – Enter the AWS Access Key Secret.
6. Click **Add** to create the account.
