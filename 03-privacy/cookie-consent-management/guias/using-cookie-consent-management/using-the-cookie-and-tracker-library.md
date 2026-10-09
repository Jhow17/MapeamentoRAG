---
title: "Using the Cookie and Tracker Library"
slug: "using-the-cookie-and-tracker-library"
status: "update"
updated: 2026-09-22T05:14:39Z
published: 2026-09-22T05:14:40Z
canonical: "helpcenter.securiti.ai/using-the-cookie-and-tracker-library"
area: privacy
modulo: cookie-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Cookie and Tracker Library

**Scenario**

As a Data Security Officer, you need a centralized way to manage trackers across your web properties. For instance, when a new tracker appears on a domain, you must quickly review and control it to ensure it aligns with your consent setup. Without a unified system, monitoring and managing trackers across domains becomes difficult. With Securiti’s Cookie & Tracker Library, you can manage cookies, trackers, beacons, and storage items from a single hub. This centralized view helps you maintain better control and ensure accurate consent tracking across your domains.

The Cookie and Tracker Library functionality streamlines and simplifies your cookie consent management by providing a comprehensive and centralized catalog of all cookies across your domains in one place. This library acts as a centralized hub for cookie and tracker management, and lets you streamline and simplify your consent management process. It serves as a comprehensive catalog of all tracking technologies such as **Cookies**, **Trackers**, **Image beacons**, **Local storage items** and **Session storage items** across all your domains, providing you with a single point of control.

> [!NOTE]
> **Note**
> 
> - If this functionality is not available in your Securiti tenant, contact your **Customer Success Manager** or **Account Representative** to confirm whether it is included in your plan.
> - Once the Cookie and Tracker Library is enabled on your Securiti tenant, **you must re-scan your domain** to establish a link between the library and the cookies detected during the scan. This ensures that the most recent cookies are reflected in the Cookie and Tracker Library.
> 
> If some cookies remain in the **Unapplied Trackers** tab after the domain re-scan, it indicates they were not detected during the scan and will remain there.

![main_dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ddb41f23-eb62-20fe-9ea1-f625a254675c.png)

With the Cookie and Tracker Library, you can:

- Build queries by combining the following properties to filter out cookies and trackers that exist across all the domains present in your Securiti tenant:

![filter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-62c516aa-eb65-90af-5636-cca9cf63ca9a.png)
  - Tracker Name
  - Category
  - Tracker Domain
  - Service
  - Tracker Type such as **Cookie**, **Image Beacon**, **Local storage item**, and **Session storage item**
  - First/Third Party
  - Domain
  - Status such as **Draft** or **Published**
  - Cookie Last Found Date
  - Source such as **Online Scan**, **Offline Scan**, and **Manual**
- View detailed metadata of any cookie or tracker, as shown below

![metadata_view.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6585105a-79c5-255b-d9b2-ff761e6fc2ca.png)
- Save built queries as **Saved Views** for later use. For instance, once you save a query, it gets saved as a Saved View with the filters you applied and the results that were filtered out. This ensures you can access commonly used searches from the Saved View section, instead of repeatedly searching for cookies and trackers with specific and occasionally used properties.
- Add cookies and trackers to the library.
- Edit and delete cookies and trackers individually or in bulk.
- Apply trackers to one or multiple domains at once.
- Quickly filter trackers by their application status from the **Applied Trackers** and **Unapplied Trackers** tabs.
- Export the selected search results in `CSV`, `JSON`, and `Excel` formats.
- Share information with internal or external users via email with a custom email message.

![tracker_selection_sharing.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4e5cb276-5b6d-c6de-b2a1-bda77fafbd7d.png)

## Using the top-level filter

With the top-level filter, you can combine different properties of cookies and trackers and then filter them out. The top-level filter takes precedence and dictates the behavior of other filters below it, filtering all data from the top down, affecting the result values of both metric tiles and the grid view.

To use the top-level filter:

1. From the upper left corner of the Cookie & Tracker Library dashboard, click **+**, as shown below.

![tracker_top_level_filter_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-26ec45f4-32d4-651b-48aa-52f30a15fa60.png)
2. On the popup, either search by cookie or tracker property name or use the out-of-the-box listed properties.

For instance, if you want to filter out cookies and trackers based on cookie category (property), click **Category**, and from the list of values on the right side, mark the checkbox next to cookie categories which you filter the cookies and trackers from. Once selected, near the bottom of the popup, click **Apply**, as shown below.

![tracker_top_level_filter_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-08f0884a-faaa-904d-9ee5-9e074095bb52.png)
3. Repeat the same step for other properties according to your search needs. Once you apply all required properties, press **Enter**. Securiti builds a query based on your selected properties, and displays the filtered results, as shown below.

![tracker_top_level_filter_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a3c874f2-f808-aad3-298d-ae8c47bd0e89.png)

> [!NOTE]
> **Note**
> 
> The top-level filter takes precedence over all other filters, and if there's an overlap of similar filters, Securiti disables the same filter other than the top-level filter. For instance, in the following screenshot, the overlap of **First/Third Party** filters occur, as shown below.
> 
> ![tracker_top_level_filter_4_note.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9a433057-0fe9-c0c5-0699-0e11d2daf610.png)
4. To clear the top-level filter, from the upper right corner, click **Clear Search**, as shown below. ![tracker_top_level_filter_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b3f0c0bc-9432-095b-6d61-990317a5f6f8.png)

## Saving searched views

Securiti lets you save your built queries as **Saved Views** for later use. For instance, once you save a query, it gets saved as a Saved View with the filters you applied and the results that were filtered out. This ensures you can access commonly used searches from the **Saved View** section, instead of repeatedly searching for cookies and trackers with specific and occasionally used properties.

To save a built query as a saved view:

1. After filtering the cookies and trackers from the top-level filter, from the upper right corner, click **Save View**, as shown below.

![save_view_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-401df1ff-876c-7c90-289a-a3f11e76c6cf.png)
2. On the Save View side panel:
  1. Select the Group Name or click **Add New** to create a new group name. Type the group name, and press **Enter**, as shown below.

![save_view_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-114872c3-f682-22cd-f0c7-deea68ef16b3.png)

![save_view_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e4bc62a8-e912-6489-1a13-aabd196e7613.png)
  2. Enter a name for the view that you want to save.
  3. Enter the description for the view you want to save.
  4. Near the bottom of the side panel, click **Save View**, as shown below.

![save_view_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-61af2da4-703f-b350-89d8-aef3c61fb241.png)

Once done, s shows you a success message near the upper right side, as shown below.

![save_view_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b1200840-0641-9910-fc56-010b5f9ce739.png)
3. To view your saved view, from the upper right corner, click **Saved Views**, as shown below. ![save_view_6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-87ad3d41-c431-51cc-8def-86c00bb88b3d.png)

## Adding a new tracker

Securiti lets you easily add new trackers to the Cookie and Tracker Library. You can add as many trackers as needed to ensure accurate tracking and categorization across your domains. This functionality provides full control over the management of cookies and trackers.

Use the table below to understand potential use cases for adding new trackers to the Cookie and Tracker Library.

| Use Case | Description |
| --- | --- |
| Missed Trackers from Domain Scan | If certain trackers were not detected during the domain scan, Securiti lets you add them manually to the library. Instead of raising a support request, this functionality lets you take immediate action, saving time and ensuring your tracking setup is always accurate and up-to-date. |
| New Trackers for Third-Party Services | When you integrate new third-party services or tools into your domain, they might come with their own trackers that need to be categorized for privacy and compliance purposes. Adding them directly to the library ensures these trackers are properly managed alongside existing ones. |
| Changes to Tracking Requirements | If your domain experiences changes to its tracking requirements such as switching to a different analytics platform, you may need to add new trackers to reflect the updated configuration. This ensures that your privacy preferences are aligned with your current tracking setup. |
| Custom Tracker for Marketing Campaigns | If you are running a specific marketing campaign and need to add custom trackers, such as tracking pixels for email marketing, retargeting ads, or affiliate tracking, you can easily add them to the library. This lets you effectively monitor your campaign's performance and helps ensure you are in control of your tracking and aligns with your marketing efforts. |
| Third-Party Tracker Not Detected by Domain Scan | If you are using a third-party tool or service that is not detected during the domain scan, you can add the corresponding tracker manually to the library. This ensures you maintain accurate tracking and compliance even if the system doesn't automatically detect every tracker in use. |

To add a new tracker to the library:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent Configurations > Cookie & Tracker Library**.
2. On the **Cookie & Tracker Library** page, from the upper right corner, click **More Options**, and choose, **Add a Tracker**.

![add_tracker_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f68b378d-c9e1-3173-1051-410b7c1f2d3f.png)
3. On the **Add Tracker to Library** popup, fill out the details for:

| Field | Description |
| --- | --- |
| Tracker Name | Add the name of the tracker you are adding to the library. |
| Purpose | Add some description to clearly specify the purpose of the tracker. |
| Category | From the menu, select one cookie category to organize the tracker. |
| Tracker Type | From the menu, choose the type of tracker, such as **Cookie**, **Image beacon**, **Local storage item**, or **Session storage item**. |
| Service | Identify and enter the service associated with the tracker, such as **Google Analytics**, **Facebook Pixel**, or **Marketo**, etc. |
4. Near the bottom of the popup, click **Add**, as shown below.

![add_tracker_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f29cab92-ebb8-b92d-830e-933116b9a43c.png)

Securiti adds this tracker to the Cookie and Tracker Library, and you can locate it using the **Unapplied Trackers** tab.
5. (Optional) To apply the newly added tracker to your domain(s) immediately, near the bottom of the **Tracker Added to the Library** popup, click **Apply to Domain(s)**, as shown below.

![add_tracker_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a8050ef4-9ff9-eb37-72ec-b32c2f7c7d5f.png)
6. On the **Apply to Domain(s)** popup, fill out details for:

| Field | Description |
| --- | --- |
| Tracker Name | You already added a value for this field previously. |
| Domain | From the menu, select the domain where you want to apply this tracker. |
| First/Third Party | Select the radio button for **First Party** or **Third Party** based on the ownership of the tracker you added. |
| Category | Select a different value for this field if changes are needed. |
| Tracker Domain | Add the domain of the tracker such as `sp.auth.example.com`. |
| Resource | Provide the URL or file path to the resource related to the tracker, such as the tracker's script or the resource that hosts it. For instance, `www.example-resource.com`. |
| Privacy Policy link | Provide the URL of the privacy policy that governs the use of the tracker. For instance, `https://www.yourprivacypolicy.com`. |
| Initiator Type | Specify the type of entity or action that initiates the tracker such as **Network**, **Click**, etc. |
| Initiator URL | Enter the URL of the webpage or service that triggers the tracker such as `https://www.example.com/0:00/`. |
| Duration | Define the expiration period for the tracker by selecting one of the following options from the menu: - **Session**: Tracker expires at the end of the browser session. - **Less than a day**: Tracker expires within less than a day. - **Day**: Tracker expires after one day. - **Year**: Tracker expires after one year. |

![Apply-to-domains-filled-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a3cc37d3-64bb-008f-d277-b700a9f1d8f0.png)

![Apply-to-domains-filled-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-061cec4f-0487-70b5-b38b-49f3d3e170b7.png)
7. (Optional) Once done, near the bottom of the popup, click **Apply tracker to another domain** if you wish to add this tracker to more domains, as shown below.

![Apply-to-another-domain.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3b5f2f8f-16d5-f991-9c32-549347d2603d.png)
8. From the **Domain** menu, select another domain and enter values in the fields again. Repeat this step as many times as needed to apply this tracker to additional domains based on your requirements.

![Multiple-domains-selected.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-527ba47a-914d-361d-64b8-10ee5536ccee.png)
9. After adding the tracker to the required domains, near the bottom of the popup click **Apply to Domain(s)**. Securiti applies the tracker to all selected domains.

> [!WARNING]
> **Important**
> 
> The newly added tracker remains in draft state even after being applied to domains. You must redeploy the cookie configuration for each domain individually for this change to take effect in the domains.

## Editing trackers individually

Securiti lets you edit trackers in both **Published** and **Draft** states. From the organization you are currently using, you can locate the following:

- Published trackers in the **Applied Trackers** tab, as shown below.

![editing_tracker_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2cb8c2db-4f48-1fd0-051a-7e172d62e6b7.png)
- Draft trackers in the **Unapplied Trackers** tab, as shown below. This tab displays all trackers across all organizations within your Securiti tenant. ![editing_tracker_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-30f5d717-704d-20ec-39d7-f45ad8770bbd.png)

### Key considerations

You must consider the following points when editing a tracker:

- You can edit trackers in both Published and Draft states only from the **Applied Trackers** tab.
- Securiti does not let you edit multiple trackers or bulk edit trackers from the **Unapplied Trackers** tab.
- Published trackers are applied to domains and are actively being used by the domains.

> [!NOTE]
> **Note**
> 
> When you edit a published tracker, Securiti clones it and creates a draft. You can make edits to the draft to suit, and then select an acknowledgment to update it. The draft tracker is then published in the library, but stays in draft in your domain's cookie configuration. You must redeploy the cookie configuration for each domain individually for this change to take effect in the domains.
- Trackers in the Draft state are not applied to any domain(s) and are not actively used by any domain.

> [!NOTE]
> **Note**
> 
> If a draft exists for a tracker but the tracker is in a published state, Securiti recommends editing the draft version, not the published one.

### Editing a published tracker

To edit a single published tracker:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent Configurations > Cookie & Tracker Library**.
2. On the **Cookie & Tracker Library** page, from the upper right corner, click **Applied Trackers** tab.
3. From the right side of the tracker you want to edit, click **Options** (three dots) and select **Edit**, as shown below.

![editing_published_tracker_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d53c0d1-33e3-429a-a540-39d5565d0c1f.png)
4. On the **Edit Published Tracker** confirmation popup, click **Edit Anyway**, as shown below.

![editing_published_tracker_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fbeeff76-4985-8da6-0e84-852cf1266f5d.png)
5. On the **Edit Tracker** popup, modify the values you want to update. Once you are satisfied with the changes, near the bottom of the popup, mark the acknowledgment checkbox. The Update button becomes active. Click **Update** to save your changes, as shown below.

![Edit-Published-Tracker-Acnknowledgement.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e25b7c33-0530-7159-05ce-19f465ee27d2.png)
6. On the **Tracker Updated Successfully** popup, click **Visit Domain Page**, as shown below.

![editing_published_tracker_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-99baa6a1-f90d-5888-c639-1a4b216523ea.png)

Securiti redirects you to your domain’s cookie configuration in a new tab. You must redeploy the cookie configuration for the changes to take effect on your live domain.

### Editing a draft tracker

To edit a draft tracker from either applied or unapplied tab:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent Configurations > Cookie & Tracker Library**.
2. On the **Cookie & Tracker Library** page, from the upper right corner, click **Unapplied Trackers** or **Applied Trackers** tab.
3. From the right side of the tracker you want to edit, click **Options** (three dots) and select **Edit**.
  1. For an **unapplied** tracker, on the **Edit Tracker** popup, modify the values you want to update. Once you are satisfied with the changes, near the bottom of the popup, click **Edit Tracker** to save your changes, as shown below.

![edit_draft_tracker_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-14a84fde-8c09-4e06-0df9-9d05c9d72d27.png)

Securiti updates the tracker in the library, and shows you a success message near the upper right corner of the screen.
  2. For an **applied** tacker, on the **Edit Draft Tracker** popup, click **Edit Anyway**, as shown below.

![edit_draft_tracker_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b26bc7a2-73fe-f9f8-f664-0e2dcd2af17f.png)
  3. From the **Edit Tracker** popup, modify the values you want to update. Once you are satisfied with the changes, near the bottom of the popup, mark the acknowledgment checkbox. The Update button becomes active. Click **Update** to save your changes, as shown below.

![edit_draft_tracker_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-26f48746-c09d-9768-416c-9ed457f35e5c.png)
  4. On the **Tracker Updated Successfully** popup, click **Visit Domain Page**, as shown below.

![edit_draft_tracker_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a34f9e71-0360-094c-a78e-00ee49f64273.png)

Securiti redirects you to your domain’s cookie configuration in a new tab. You must redeploy the cookie configuration for the changes to take effect on your live domain.

## Editing trackers in bulk

To edit the trackers in bulk:

> [!NOTE]
> Note
> 
> You can bulk edit up to 100 trackers at a time in the Cookie & Tracker Library. Securiti recommends reviewing the changes before publishing them.

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent Configurations > Cookie & Tracker Library**.
2. On the Cookie & Tracker Library page, from the upper right corner, click **Applied Trackers** tab, as shown below.

> [!WARNING]
> **Important**
> 
> You can bulk edit trackers in both Published and Draft states only from the **Applied Trackers** tab.

From the left side, mark the checkboxes next to the trackers you want to edit in bulk. Then, near the bottom of the page, from the floating tab, click **Edit**, as shown below.

![editing_bulk_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07ea4c1d-aa72-1037-a7c7-f7b875875b6f.png)
3. On the **Bulk Edit Trackers** popup, click **Edit Anyway**, as shown below.

![editing_bulk_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf184506-81e3-5a20-7c0d-03fd34c53f6f.png)
4. On the **Bulk Edit Trackers** popup, from the right side of the field(s) you want to update, click **Update**, and modify the values.

> [!NOTE]
> **Tip**
> 
> To revert to the previous value, click **Reset**.
  1. Once you are satisfied with the changes, near the bottom of the popup, mark the checkbox for the acknowledgment.
  2. The Update button becomes active. Click **Update** to save your updated changes, as shown below.

![editing_bulk_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e4787faf-fc39-b70c-3aaf-a82577cc884f.png)
5. On the **Confirm Bulk Changes** popup, review the updated values carefully. If everything looks correct, click **Confirm Changes** to save your updates, as shown below.

![editing_bulk_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-207442f1-f265-ce95-796a-32e50c60b960.png)
6. Once done, the trackers are updated in the library and on the domains using them. On the **Trackers Updated Successfully** popup, click **Dismiss**, as shown below.

![editing_bulk_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0bd6705d-e966-14ad-d602-ce2502cb1be1.png)

> [!WARNING]
> **Important**
> 
> After editing trackers in bulk, you must redeploy the cookie configuration for each affected domain for the changes to take effect.

## Deleting trackers individually

Securiti lets you delete tracker(s) from the Cookie and Tracker Library to manage outdated or unnecessary trackers effectively. Follow the considerations outlined below to ensure proper deletion and avoid potential conflicts with the cookie configurations of your domains.

### Key considerations

You must consider the following points when deleting a single or multiple trackers:

| Unapplied Trackers | Applied Trackers |
| --- | --- |
| You can only delete manually added trackers that are not assigned to any domain in any organization within your Securiti tenant. The "Source" of the tracker must be **Manual**, not **Online Scan**. | You can only delete trackers in **draft** state. |
| If you try to delete a manually added, unapplied tracker linked to domains in a draft state or included in a previously published cookie policy of another organization, Securiti displays an error message. To delete the tracker, navigate to the Cookie and Tracker Library in the other organization and remove it from the associated domain(s): - If the tracker is linked to a draft cookie policy in that domain, you can delete it. - If the tracker is part of a previously published cookie policy, you cannot delete it. | If you select both draft and published trackers, the **Delete** button remains disabled. Hovering over it shows the message: "Bulk delete is disabled because one or more published trackers are selected. Unselect the published trackers to enable the bulk delete option." ![key_considerations.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-860a6446-5f53-6b26-b150-5a2934bc970d.png) |
| Securiti does not let you delete multiple trackers or bulk delete trackers from the **Unapplied Trackers** tab. | Bulk deletion is only available for trackers in **draft** state. |

### Procedure

To delete a single unapplied or applied tracker:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent Configurations > Cookie & Tracker Library**.
2. On the **Cookie & Tracker Library** page, from the upper right corner, click **Unapplied Trackers** or **Applied Trackers** tab, as shown below.

![delete_procedure_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d0906e21-be54-f0a4-800f-cba1c02dbd40.png)
3. From the right side of the tracker you want to delete, click **Options** (three dots) and select **Delete**, as shown below.

![delete_procedure_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fd9f72ed-93cf-7ce1-1e59-356520a737d6.png)
4. On the **Delete Tracker** confirmation popup, click **Delete** to delete it from the library, as shown below.

## Deleting trackers in bulk

> [!NOTE]
> **Note**
> 
> Securiti only lets you bulk delete trackers that are in draft state from the **Applied Trackers** tab. You cannot bulk delete trackers from the **Unapplied Trackers** tab.

To delete applied trackers in bulk:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent Configurations > Cookie & Tracker Library**.
2. On the **Cookie & Tracker Library** page, from the upper right corner, click **Applied Trackers** tab, as shown below.

![delete_in_bulk_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-31d7c048-e03e-5831-7cc1-41d50df53dc4.png)
3. From the left side, mark the checkboxes next to the trackers in draft state you want to delete. Then, near the bottom of the page, from the floating tab, click **Delete**, as shown below.

> [!NOTE]
> **Note**
> 
> The trackers must be in **draft state** to be deleted.

![delete_in_bulk_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ab3aa558-ffcf-2bba-63ab-254adb8b47e6.png)
4. On the **Delete Tracker** confirmation popup, click **Delete** to delete the selected trackers from the library, as shown below. ![delete_in_bulk_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a54647a5-e473-823d-669c-528a92f6dff2.png)

## Sharing and exporting cookie and tracker information

You can also share the information of cookies and trackers with internal or external users via email with a custom email message, and you can also export the selected search results in `CSV`, `JSON`, and `Excel` file formats.

![share_export_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4e4d756c-612b-a2c9-7ccc-d2ea53d1acac.png)

To share the cookie and tracker information with other admin users:

1. Mark the checkboxes next to the cookies and trackers that you want to share with other internal or external users.
2. On the bar that appears near the bottom of the page, click **Share**, as shown below.

![share_export_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-43d8b6e4-26e9-2a19-c751-3845e2b144ab.png)
3. On the Share popup:

Securiti sends out emails to your selected recipients, and shows you a success message near the upper right corner of the screen.
  1. From the **File Format** menu, select the format such as CSV, JSON, or Excel.
  2. From the **Add Recipients** field, select the users with which you to share the cookie and tracker information. Securiti also lets you add the email address of the users.
  3. In the **Message** field, type your custom email message for the selected recipients.
  4. Once done, near the bottom of the popup, click **Share**, as shown below.

![share_export_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3a58e03d-d234-9acb-5745-ac13c4c310da.png)

To export the cookie and tracker information:

1. Mark the checkboxes next to the cookies and trackers that you want to export.
2. On the bar that appears near the bottom of the page, click **Export**, as shown below.

![share_export_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2f050165-d5f2-a193-1891-132a14978647.png)
3. On the Export popup:

Securiti schedules your export, and shows you a success message near the upper right corner of the screen, as shown below. ![save_view_7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f8eb6ffd-7699-93e9-4587-4dd7b05c54ff.png)
  1. From the **Export as** menu, select the file format in which you want to export the cookie and tracker information such as `CSV`, `JSON`, or `Excel`.
  2. Once done, near the bottom of the popup, click **Export**, as shown below.

![share_export_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ef827ee6-d483-d2ca-b0af-2d7bbdcef3cf.png)

## Associating assigned or unassigned trackers with domains

Securiti lets you easily manage and reuse cookies and trackers across multiple domains to avoid redundant work and ensure consistent classification. Whether you are onboarding new domains or restructuring existing ones, Securiti lets you associate cookies and trackers with one or more domains, whether they are already assigned or still unassigned in your Securiti tenant.

> [!NOTE]
> **Note**
> 
> Securiti logs all actions related to associating or disassociating cookies and trackers with domains in the Audit Log. Clicking **Audit Log** from **More Options** redirects you to the module-level audit log, with a filter for Cookie & Tracker Library pre-applied, as shown below.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Tracker-Library-filter.png)
> 
> To view the comprehensive audit log record details for cookie consent activities, see [Using the Cookie Consent Management Audit Log](/latest/docs/using-the-cookie-consent-management-audit-log).

To manage this, you can use the **Applied Trackers and Unapplied Trackers** tabs in the Cookie & Tracker Library.

- The **Applied Trackers** tab shows cookies and trackers that are already linked to at least one domain.
- The **Unapplied Trackers** tab lists all cookies and trackers that are not yet associated with any domain(s).

> [!NOTE]
> **Note**
> 
> Securiti shows applied trackers that are associated with one organization as **unapplied trackers** in other organizations. You must review existing tracker associations before applying them across organizations to ensure accurate configuration.

![Assign-Cookie-to-Domains.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4c309a90-23e3-45b1-3fc8-f4c21a9f5b4b.png)

To associate a cookie or tracker (applied or unapplied) with one or more domains:

1. In Securiti, open **Cookie Consent Management**, and choose **Cookie Consent Configurations > Cookie & Tracker Library**.
2. On the **Cookie & Tracker Library** page, from the upper right corner, select the appropriate **Applied Trackers** or **Unapplied Trackers** tab based on the tracker's current state.
3. Locate the cookie or tracker you want to associate with a domain.
4. From the right side of the cookie or tracker, click **Options** (three dots), and select **Apply to Domain(s)**.
5. On the **Apply to Domain(s)** popup, from the **Domain-Specific Data** section, fill out the required details for the domain.
6. (Optional) To associate this same cookie or tracker with a different domain, near the bottom of the popup, click **Apply Tracker to Another Domain**.
7. Repeat steps 3 to 5 for each additional domain.
8. Once done, near the bottom of the popup, click **Apply to Domain(s)**.
9. On the **Trackers Applied Successfully** popup, click **Visit Domain Page** to open the domains list. From there, redeploy the cookie configuration for each domain where the cookie or tracker was assigned to ensure the changes take effect.

This process helps you streamline tracker setup across domains and maintain a unified view of cookie and tracker usage in your Securiti tenant.
