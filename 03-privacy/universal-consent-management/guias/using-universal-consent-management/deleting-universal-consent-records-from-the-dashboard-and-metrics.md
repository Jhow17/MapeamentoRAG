---
title: "Deleting universal consent records from the Dashboard and Metrics"
slug: "deleting-universal-consent-records-from-the-dashboard-and-metrics"
updated: 2026-07-09T10:36:54Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/deleting-universal-consent-records-from-the-dashboard-and-metrics"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Deleting universal consent records from the Dashboard and Metrics

You can delete consent records from the **Universal Consents** records table. The **Delete Records** button only appears when there are records available in the dashboard. Securiti maintains audit logs for both successful and aborted consent records deletions. The respective admin of the tenant receives an email when records are deleted from the dashboard. Only the following roles have the permission to delete the consent records:

- Super Admin
- Organization Admin
- Module Owner

To delete consent records:

1. Open Universal Consent Management and choose **Explorers > Dashboards & Metrics**.
2. On the **Universal Consent Dashboard**, from the upper right side of the consent records table, click **Delete Records**, as shown below.

![Universal Consent Dashboard displaying consent records and options for managing data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/delete_consent_records_1.png)

To delete specific consent records, you can apply a filter. For more information, see [Filtering universal consent records in the Dashboard and Metrics](/latest/docs/filtering-universal-consent-records-in-dashboard-and-metrics).
3. On the **Delete Consent Records** popup, write the appropriate reason to delete the consent records in the text field, then click Delete to delete the consent records from the dashboard as shown below.

![Confirmation dialog for deleting 49 consent records with reason input field.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/delete_consent_records_2.png)
4. Near the bottom of the popup, click **Cancel** to abort the deletion of consent records, as shown below.

![Confirmation dialog for deleting 49 consent records with options to cancel or delete.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/delete_consent_records_3.png)
5. Securiti queues the consent record deletion request for processing, as shown below.

![Dashboard displaying consent management metrics and processing notifications for user consent requests.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/delete_consent_records_4.png)
6. Securiti also notifies you by email upon completion of the consent record deletion request, as shown below.

![Notification of successful deletion of universal consent records with relevant details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/delete_consent_records_5.png)

## Best practices for deleting consent records

For stable and reliable performance, follow these guidelines:

1. Filter and delete a limited number of UUIDs at a time.
2. Break large deletion requests into smaller batches.
3. Run deletion queries sequentially to ensure stable processing.
4. Use shorter deletion timeframes (1-2 months) for substantial data volumes.
