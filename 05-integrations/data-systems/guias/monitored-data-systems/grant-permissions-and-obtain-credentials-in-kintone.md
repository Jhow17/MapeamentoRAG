---
title: "Grant permissions and obtain credentials in Kintone"
slug: "grant-permissions-and-obtain-credentials-in-kintone"
updated: 2026-07-10T07:08:23Z
published: 2026-07-10T07:08:23Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-kintone"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Kintone

Kintone data systems use the username, password, and URL of your Kintone subdomain to establish a successful Connection in Securiti.

Use the matching procedure below.

1. > [!NOTE]
> **Note**
> 
> We assume you have a Kintone Instance running or you're the admin of your Kitone account, so you have read all Permissions for private and public spaces, apps, and records.

Log in to your Kintone account.

(Optional) If you haven't, you can create a trial account for Kintone at [https://www.kintone.com/en-us/trial/](/v1/docs/securiti-pods-and-elastic-pods) and click **NPO free trial here**.
2. At the top of the dashboard, record your Kintone **URL** from the address bar for later use. See the following example.

<https://**{instance_id}**.kintone.com/admin/>

The placeholder *{instance_id}* before ".kintone.com" is your URL parameter.
3. In the left sidebar, select **User Administration > Groups or (Roles)**.

![image__1_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a70440a3-2a19-7782-e229-3669e0165937.png)

![image__2_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-74573fdb-93d8-149a-44aa-b399903fc3e3.png)
4. On the following page, next to Administrators, click **Settings** (cog icon) and select **Change Members**.

![unnamed.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e04c7626-67d1-43c3-01ce-13a1951ffe1e.png)
5. Choose the user account you want to use for Connector Activation (we recommend using the admin account or the account with admin privileges).

![image_1_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5d69bb9d-8a45-6b7c-8eed-3e072e317f1d.png)

Click **Add** and then **Save**.
6. Proceed to [Connecting Kintone with Securiti](/latest/docs/activate-the-kintone-connector-in-securiti).
