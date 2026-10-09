---
title: "Obtain authentication credentials for Oracle Object Storage connector"
slug: "obtain-authentication-credentials-oracle-object-storage"
updated: 2026-07-20T20:24:01Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/obtain-authentication-credentials-oracle-object-storage"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain authentication credentials for Oracle Object Storage connector

1. Log in to your Oracle Object Storage account at [https://cloud.oracle.com/en_US/sign-in](https://cloud.oracle.com/en_US/sign-in).

Oracle redirects you to your Oracle Dashboard screen.

![OObSignIn.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e1dd4478-6abd-ee79-8e4c-1880e4dfb9bb.jpg)
2. On the left sidebar, scroll down to the “Governance and Administration” section.

![OObDashboard.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5ff3a3be-a213-9ef4-ab19-88e9fff57231.jpg)

![OObDashboardSidebar.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ccdfde23-f3b3-99dd-8d42-48a9d9b60274.jpg)
3. Click **Identity & Security**, then click **Users**.

![OobIdentityUsers.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-26aca589-6136-8bb9-0a04-81c2bce40c6c.png)
4. On the Identity & Security page, click on your account that is listed under the Users subsection.

After clicking on your user account, your OCID (also known as the user ID) is displayed.

![OObAccountInfo.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d9a92609-f806-2bd1-5042-ec89594c57aa.jpg)
5. Record the OCID to use later.
6. To obtain Compartment ID:
  1. Select **Identity > Compartments** from the Oracle Object Storage left-hand menu.
  2. On the following page, click on any compartment, as shown below.

![Compartments.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ad154bfd-cadc-d980-ec0e-30b2bfb65188.png)
  3. Record the OCID (aka Compartment ID) to use later, as shown below.

![Compartment_ID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-688d0036-b592-19c4-c3fd-03535b03f9f4.png)
7. Return to the main Oracle Object Storage homepage and find the **Administration** menu on the left sidebar.

![OObTenancyDetails.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1878dcbc-0771-6662-6d2b-cbb56b8d5513.jpg)
8. Click **Tenancy Details**.

The Tenancy Details page shows you the Tenant ID and Region (in the form of a OCID and Home Region respectively).

![OObTenancyInfo.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e6ef11bb-5640-845f-f34f-b009b4e09dc9.jpg)
9. Record the Tenant ID and Region to use later.
10. Proceed to [Generate Oracle API signing keys](/latest/docs/generate-oracle-api-signing-keys).
