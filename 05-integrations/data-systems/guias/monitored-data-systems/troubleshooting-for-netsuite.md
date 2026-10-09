---
title: "Troubleshooting for NetSuite"
slug: "troubleshooting-for-netsuite"
updated: 2026-07-20T08:18:53Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-netsuite"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for NetSuite

This article provides troubleshooting guidance for common issues encountered when configuring and using the NetSuite connector.

## 1. NetSuite connector activation fail

Connector activation fails with an **Invalid Login Attempt** error when connecting to NetSuite.

### Troubleshooting

1. Review the appropriate NetSuite documentation based on the authentication method being used:
  - **Basic / Token-Based Authentication:** For more information, see [Track TBA Tokens and Users](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_1534941538.html#subsect_1534941869).
  - **OAuth 2.0:** [OAuth 2.0 and the Login Audit Trail](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_158323851171.html).
2. Retry activating the NetSuite connector.
3. In NetSuite, navigate to **Setup → Users/Roles → View Login Audit Trail**.
4. Select **Use Advanced Search**.
5. On the **Criteria** subtab, add the following filters:
  - Status = *Failure*
  - Date = *Today* (or the date the activation was retried)
6. On the **Results** subtab, add the below mentioned columns and click **Submit**.
  - **Detail**
  - **Authentication** (if available)
  - **Token** (if available)
  - **OAuth Application Name** (if available)
  - **Role** (if available)
7. Locate the entry corresponding to the activation attempt and review the **Detail** column.

> [!WARNING]
> Important
> 
> The **Detail** column is not displayed by default and must be added through **Advanced Search**. The value in this column contains the specific reason NetSuite rejected the authentication request (for example, `EntityOrRoleDisabled`, `ScopeMismatched`, or `AuthorizationCodeGrantRequired`).

For more information on advanced login audit trail, see [Defining an Advanced Login Audit Trail Search](https://docs.oracle.com/en/cloud/saas/netsuite/ns-online-help/section_1548084729.html#bridgehead_N324640).

## 2. NetSuite connector activation fail

Connector activation fails with `java.sql.SQLException: No such file or directory` error when connecting to NetSuite.

### Troubleshooting

This issue may occur if the default **OAuthSettingsLocation** path is inaccessible.

1. Edit the connector configuration.
2. Add the following value to the **Additional Connection String** field:

```plaintext
OAuthSettingsLocation=memory://net_suite_oauth
```
3. Save the configuration and retry activating the connector.

## 3. NetSuite Learn scan fail

NetSuite scan fails with `Permission Violation: You need the (Any Record or Tables) permission to access this page. Please contact your account administrator` error during initiate learning scan in NetSuite.

### Troubleshooting

> [!NOTE]
> Note
> 
> This troubleshooting guide applies only to NetSuite connectors using Basic Authentication.

1. Grant **View** access for the missing **standard permissions,** in NetSuite:
  - Navigate to **Setup → Manage Roles → *[Integration Role]* → Permissions**.
  - Under the appropriate tab (**Transactions**, **Reports**, **Lists**, or **Setup**), add the required permission with **View** access.
2. Grant **View** access for the missing **custom record types** using either of the following methods:

> [!WARNING]
> Important
> 
> If using Option B, you can temporarily set Access Type = No Permission Required only for the duration of the Learn scan. After the scan completes successfully, restore the original access setting.
  1. Option A – Role-level access (recommended)
    - Navigate to **Setup → Manage Roles → *[Integration Role]* → Permissions → Custom Record**.
    - Add the required custom record types with **View** access.
  2. Option B – Record-level access (temporary)
    - Navigate to **Customization → Lists, Records & Fields → Record Types**.
    - Open the required custom record type and select **Edit**.
    - Set **Access Type** to **No Permission Required**.
    - Save the changes.
3. After assigning the required permissions, allow 30–60 minutes for NetSuite permission changes to propagate before rerunning the Learn scan.
