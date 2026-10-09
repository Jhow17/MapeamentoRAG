---
title: "Registering an app in Starburst Enterprise"
slug: "registering-an-app-in-starburst-enterprise"
updated: 2025-10-31T06:46:17Z
published: 2025-11-03T07:38:02Z
canonical: "helpcenter.securiti.ai/registering-an-app-in-starburst-enterprise"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Registering an app in Starburst Enterprise

This document shows steps on how to register a connecting app in Starburst.

1. Visit the following link to create a new account.

[https://www.starburst.io/platform/starburst-galaxy/start/](/v1/docs/securiti-pods-and-elastic-pods)
2. Now log in to Starburst using the username and password you created in step 1.

![login_starburst.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b5a817bc-f9aa-9cbd-6317-a97ffcd1b7f9.png)
3. On the Starburst dashboard, in the left-hand menu, select **Catalogs**. Then on the right side, in View catalogs, click **Create catalog**.

![catalogs_starburst.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1739034f-1661-cbb4-e59a-e95d51677a98.png)
4. On the following page, select a datasource, for example, "Snowflake."

![select_datastore.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a6344d3e-41a7-ee9e-d287-32560fbb7ba7.png)
5. Now, do the following to create your Database Connection.
  1. Select your Cloud provider.
  2. Enter catalog name, description, and details of the datasource you want the catalog to connect with.
  3. Click **Test Connection**, then click **Connect catalog**.

![test_connection_connect_catalog.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c9f1fdc8-8ad8-826d-4a44-23347253305c.png)
6. On the dashboard, in the left-hand menu, select **Clusters** and on the right side click **Create cluster**.

![select_clusters.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6946312e-28b6-f0c7-0a54-1f2eaa02c9d7.png)
7. Enter cluster name, catalog(s) you want to connect with the cluster and other required information.

![cluster_information.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-83bf495c-70c4-c23a-22a3-492a8c5f8f60.png)

Click **Create cluster**.
8. After the cluster is created, on the Cluster page under Quick actions Column, click **Resume**.

![click_resume.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5868e35c-1973-9bad-4f9e-4a875f0bd906.png)
9. On the Connection information popup, record the cluster host, port, and username for later use.

Password is "password" by default for the account.

![connection_information.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-94586422-0d4d-f287-b218-0a5c2bb6bc04.png)
10. Proceed to [Grant permissions and obtain credentials in Starburst](/v1/docs/grant-permissions-and-obtain-credentials-in-starburst).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
