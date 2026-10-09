---
title: "Understanding connector status"
slug: "understanding-connector-status"
updated: 2025-10-30T19:55:34Z
published: 2025-11-03T06:13:35Z
canonical: "helpcenter.securiti.ai/understanding-connector-status"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Understanding connector status

The **Connector** tab for a monitored Data system Instance has a status indicator for the Connector, as shown below.

![connectorstatus.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-50a4d7df-01a2-855f-586a-08133240eff1.png)

The **Connector Status** section displays indicators for the Data system Connector's status, Authentication status, and scoping metadata sync status. For more information, see [Scoping Metadata Syncs for connectors](/v1/docs/scoping-metadata-syncs-for-connectors)

The following Table describes all possible Connector statuses:

| Connector Status | Description |
| --- | --- |
| Active | Connector activated |
| Auth | Authentication in progress |
| Auth-complete | Authentication was successful |
| Auth-failed | Authentication has failed |
| Deleting | Deletion in progress |
| Inactive | No Connector connected |
| Learn | Learning in progress |
| Learn-complete | Learning has been successfully completed |
| Learn-failed | Learning has failed |
| Learn-scheduled | Learning has been initiated but not started |
| Paused | Scan or Learning has been paused |
| Scan | Scanning in progress |
| Scan-complete | Scanning has completed successfully |
| Scan-failed | Scanning has failed |
| Scan-scheduled | Scanning has been initiated but not started |
| Training | Schema changes have been detected. You should review the training data on the Table Training tab |

## Related

- [Configuring connectors for monitored data systems](/configuring-connectors-for-monitored-data-systems.md)
- [Scoping Inventory Syncs for connectors](/scoping-metadata-syncs-for-connectors.md)
