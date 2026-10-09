---
title: "Prerequisites for Braze (self-hosted) connector"
slug: "prerequisites-for-braze-self-hosted-connector"
updated: 2026-02-13T06:38:13Z
published: 2026-02-13T06:38:13Z
canonical: "helpcenter.securiti.ai/prerequisites-for-braze-self-hosted-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Prerequisites for Braze (self-hosted) connector

Braze supports integration with several cloud storage platforms including AWS Cloud Storage (Amazon S3), Google Cloud Storage, and Microsoft Cloud Storage (Microsoft Azure Blob Storage). However, Securiti currently supports integration with Amazon S3 only.

Following prerequisites must be met prior to connector activation.

- Verify if your Braze account has any cloud storage integrated by following these steps on the Braze Portal:
  1. Navigate to **Integrations**.
  2. Select **Technology Partners**.
  3. Choose the appropriate cloud storage platform (AWS S3, Google Cloud Storage, or Microsoft Azure Blob Storage).
- During connector activation, select **AWS S3** in the **Target Data System** field if the Braze data system instance is integrated with Amazon S3. Select **Default**. if no cloud storage is integrated with your account.

![braze_targetds.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-485f5fca-0ae8-9d63-81b3-727d795ee4a3.png)

If your Braze instance is integrated with any of the above platforms, the data exported through APIs will be uploaded to one of the integrated cloud storage platforms as a default behavior.

> [!WARNING]
> **Important**
> 
> Only Amazon S3 integration is supported for Braze instances currently. Securiti does not scan data in case your Braze instance is connected to a cloud storage other than Amazon S3.

See [Braze's official documentation](https://www.braze.com/docs/partners/data_and_infrastructure_agility/cloud_storage) to integrate cloud storage with your Braze instance.

## Related

- [Obtain permissions and authentication credentials in Braze](/obtain-permissions-and-authentication-credentials-in-braze.md)
