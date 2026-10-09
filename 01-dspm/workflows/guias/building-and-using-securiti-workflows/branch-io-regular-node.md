---
title: "Branch.io"
slug: "branch-io-regular-node"
updated: 2026-01-09T08:52:21Z
published: 2026-01-09T08:52:21Z
canonical: "helpcenter.securiti.ai/branch-io-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Branch.io

Branch.io is a deep linking and mobile attribution platform that helps businesses create links that can lead users to specific content within a mobile app. These deep links are often used to track and attribute app installations and user actions back to the original source or campaign.

Securiti provides a Branch.io node in the Workflow Automation module that can delete a user data using details such as user ID, mobile ID or browser ID.

Refer to the [Node configurations section](/v1/docs/branchio) to understand the node configuration and properties.

#### Example use case

In this example use case, the business is implementing a workflow automation to handle Data Subject Rights (DSR) erasure requests, specifically focusing on the deletion of user data associated with Branch.io. This scenario ensures compliance with data privacy regulations, such as GDPR, where individuals have the right to request the erasure of their personal data.

The workflow is triggered by DSR trigger node that is triggered on a data erasure request by the user. The workflow then leads to the Branch.io node that deletes the data using the user ID from the DSR trigger response.

The following nodes are used in this workflow:

1. [DSR Trigger Node](/v1/docs/dsr)
2. Branch.io Node

#### Handling DSR requests with Branch.io for automatic data erasure

1. Add the DSR trigger node and set the trigger type to Erasure, so that the workflow is triggered every time there is an erasure request.
2. Using the Branch.io node, delete the user data by user ID using the ID from the response of the DSR trigger node.

![Screenshot_2024-01-30_at_7_19_51_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3307d97f-a5e4-09c3-29aa-f4daa5af839b.png)
3. Connect the nodes and execute the workflow.

![Screenshot_2024-01-30_at_7_12_16_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0418ea18-15ae-7d4f-02c5-9f688bca225c.png)
4. Once the workflow is successfully executed, you can view both table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| DataSource Name | Select the dataSource name for Branch.io. To understand the data system configuration for Branch.io, see the Branch.io connector documentation. |
| Operation | Delete User’s Data | Select this option to delete the data of the user from the data source |
| Identity Types | Select the identity type to trigger the deletion request against - User ID (Developer ID) - Browser ID - Device ID |
| Identity Value | Specify the value against the selected **Identity Type** |
| For User ID (Developer ID) | The value set in the .setIdentity method from the SDKs (Android, iOS, Web) |
| For Browser ID | The browser user identifier such as browser_fingerprint_id |
| For Device ID | The device user identifier such as IDFA, IDFV, Google_advertising_id |
