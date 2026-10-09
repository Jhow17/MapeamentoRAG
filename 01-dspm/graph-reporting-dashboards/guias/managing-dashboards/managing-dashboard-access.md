---
title: "Managing dashboard access"
slug: "managing-dashboard-access"
updated: 2026-09-16T08:58:37Z
published: 2026-09-16T08:58:37Z
canonical: "helpcenter.securiti.ai/managing-dashboard-access"
area: dspm
modulo: graph-reporting-dashboards
tipo: guia
data_captura: 2026-10-06
---

# Managing dashboard access

Securiti lets you control the visibility of your dashboard data and insights, letting you choose whether to keep your dashboard private or share it with users across a tenant. By default, all custom dashboards are marked as Restricted, which means that the dashboard and its widgets are visible only to the dashboard owner. However, you can share your custom dashboards by making them **Public** and available to all the users in your tenant or share them with specific users.

## Sharing dashboards with users

> [!WARNING]
> Important
> 
> You can share dashboards only with users in your tenant. You cannot share a dashboard with users in another tenant.

To share your dashboard.

1. From the left navigation panel, click the Jewel icon and select **Dashboard** from the menu, as shown below.

![dashboard_nav.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-733737cd-b840-569c-4f9c-3cf484077aed.png)
2. In the Default dashboard page, select your custom dashboard or, from the left menu, select **Manage Dashboards** and select your custom dashboard to share.
3. Click options (three dots) and **Share** from the menu, as shown below

![Overview of security findings with risk severity and asset posture scores displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sharereportingdashboard_dropdown.png)

![Dashboard interface displaying security findings and options for sharing and editing data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sharereportingdashboard_managingdashboard.png)
4. Alternatively, in the **Default Dashboard** page, you can open your dashboard and, near the upper right corner of the page, click **Share**.

![Dashboard displaying security findings, asset posture score, and data posture score metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/sharefromdashboardpage.png)
5. In the pop-up, in the **General access** section, select one of the following options:
  - **Public**: Select **Public** as shown below, to make the dashboard publicly visible to all users in a tenant.

![Sharing settings for a dashboard with options for restricted and public access.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/userpermissions_reportingdashboardshare.png)

Once you select this option, you can choose to give **Editor** or **Viewer** access to the users, as shown below.

![Sharing dashboard access options for users, including roles like Viewer and Editor.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewandeditrights_sharingreportingdashboards.png)
  - **Restricted**: Select **Restricted** to make the dashboard visible to selective users only. By default, the dashboard is only visible to you.

In **Restricted** access, you can perform the following actions for users in the **Users with access** section:
    - **Add users**: You can search and add users to selectively share your dashboard with.
    - **Assign a role to users with access**: You can choose who can view your dashboard and who can make changes to it. Click options (three dots) for a user and select **Viewer** or **Editor** roles, as shown below.

> [!NOTE]
> Note
> 
> Securiti lets you add new widgets and copy existing widgets to your dashboard if you have write access to a shared dashboard.

![Sharing access settings for a dashboard with user roles and permissions options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewandeditpermissions_newuser.png)
    - **Transfer ownership**: You can transfer ownership of your dashboard to another user. Click options (three dots) for a user and select **Transfer Ownership**, as shown below.

![Sharing options for a dashboard with user access and permissions settings displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/transferownership_reportingdashboard.png)

On the pop-up, select **Yes** to confirm making the user a new owner for the dashboard.

![Sharing settings for a dashboard, allowing user ownership and access permissions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/transferownership_reportingdashboardconfirmation.png)
    - **Remove access**: You can choose to remove dashboard access from a user. Click options (three dots) for a user and select **Remove access**, as shown below.

![Sharing options for a dashboard, including user access and permissions settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/removeaccess_reportingdashboard.png)

On the pop-up, select **Remove access** to confirm, as shown below.

![Prompt to remove access for user Amad Asif from a security dashboard.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/removeaccess_reportingdashboardconfirmation.png)
6. Click **Save Preferences & Share**, as shown below.

![Sharing settings for a dashboard with user access options and public visibility.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/saveaccesspreferences_reportingdashboards.png)
7. Near the upper right corner of the page, click on the users count to see the list of users the dashboard is shared with.

![Dashboard displaying security findings, asset posture scores, and data posture metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewsharedrights_reportingdashboard.png)
8. You can view the dashboard's sharing status by hovering your cursor over the icon displayed in the **Visibility** column, as shown in the screenshot below.

![Dashboard displaying various security findings and their visibility status for data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/viewreportingdashboardvisibility.png)

## Managing privately shared dashboards

For privately shared dashboards in the **Shared with me** tab, users with access to the dashboard can perform the following actions.

- Viewing dashboards: Users who do not own the dashboard can still view it by selecting **View** from options (three dots).
- Cloning dashboards: Private dashboards can be cloned by other users across the same tenant by selecting **Clone** from the options (three dots).
- Marking dashboard as default: Users who do not own the dashboard can mark the private dashboards as default by selecting **Mark as Default** from the options (three dots).
- Re-ordering: Users across the tenant can re-order private dashboards according to their preferences. The order of dashboards is maintained individually for each user and does not affect the order for the dashboard owner or other users with whom the dashboard is shared.

The default dashboard appears on the module’s page automatically as you access the Reporting Dashboard. You can set a dashboard of your choice as the default to make its widgets automatically visible to all users.
