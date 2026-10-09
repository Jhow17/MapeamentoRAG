---
title: "Configuring Data Inventory Sync for GitLab"
slug: "gitlab-connectors-configuring-data-inventory-sync-for-gitlab"
updated: 2026-08-31T09:05:47Z
published: 2026-08-31T09:05:47Z
canonical: "helpcenter.securiti.ai/gitlab-connectors-configuring-data-inventory-sync-for-gitlab"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configuring Data Inventory Sync for GitLab

Securiti supports Data Inventory Sync and entitlement scanning for GitLab (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync. For Gencore AI use cases, the scan builds an index of Entitlements to files for populating Gencore AI Pipelines.

For more information, see [Data Inventory Sync for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure Data Inventory Sync and entitlement scanning for your Data system Instance from the **Connector** tab, after the Connector Activation. Prior to the Connector Activation process, fulfill any required prerequisites as highlighted in the [section below](/latest/docs/configuring-data-inventory-sync-for-zendesk-support-self-hosted), for successful scanning.

### Prerequisites for running Data Inventory Sync for GitLab

#### Allowlisting APIs for Data Inventory Sync

You must allowlist the following APIs between your deployed Securiti Pod and the GitLab APIs to successfully run the Data Inventory Sync.

Default URL is *https://gitlab.com/*

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://gitlab.com/api/v4/groups | Get Groups |
| 2 | GET | https://gitlab.com/api/v4/groups/{{group_id}}/members/all | Get Group members |
| 3 | GET | https://gitlab.com/api/v4/groups/{{group_id}}/members/all | Get group projects |
| 4 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/members/all | Get project members |
| 5 | GET | https://gitlab.com/api/v4/users/{{user_id}} | Get member email |
| 6 | GET | https://gitlab.com/api/v4/user | Get current user |
| 7 | GET | https://gitlab.com/api/v4/users/{{user_id}}/projects | Get user projects |
| 8 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/repository/branches | Get project branches |
| 9 | GET | https://gitlab.com/api/v4/groups/{{group_id}} | Get group details |
| 10 | GET | https://gitlab.com/api/v4/projects/{{project_id}} | Get project details |
| 11 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/repository/commits | Get branch commits |
| 12 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/repository/tree | Get commit tree |
| 13 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/merge_requests | Get merge requests by project branch |
| 14 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/snippets | Get project snippets |
| 15 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/snippets/{{snippet_id}}/files/main/{{file_download_path}}/raw | Download the project snippet file |
| 16 | GET | https://gitlab.com/api/v4/snippets | Get user snippets |
| 17 | GET | https://gitlab.com/api/v4/snippets/{{snippet_id}}/files/main/{{file_download_path}}/raw | Download the user snippet file |
| 18 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/repository/blobs/{{file_sha}} | Get file content |
| 19 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/snippets/{{snippet_id}} | Get project snippet details |
| 20 | GET | https://gitlab.com/api/v4/snippets/{{snippet_id}} | Get user snippet details |
| 21 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/merge_requests/{{merge_request_iid}} | Get merge request details |
| 22 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/repository/commits/{{commit_id}} | Get branch commit details |
| 23 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/repository/branches/{{branch_name}} | Get branch details |
| 24 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/repository/files/{{file_path}}?ref={{branch_name}} | Get commit file details |
| 25 | GET | https://gitlab.com/api/v4/groups/{{group_id}}/wikis | Get Group Wikis |
| 26 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/wikis | Get Project Wikis |
| 27 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/repository/commits/{{commit_id}}/comments | Get Commit comments |
| 28 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/merge_requests/{{merge_req_id}}/notes | Get Merge Request comments |
| 29 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/snippets/{{snippet_id}}/notes | Get project snippet comments |
| 30 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/issues | Get Project Issues |
| 31 | GET | https://gitlab.com/api/v4/projects/{{project_id}}/issues/{{issue_id}}/notes | Get project issue comments |

### Configuring Data Inventory Sync

After activating the GitLab (Self-hosted) Connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for GitLab.

1. On the **Connector** tab, in the **Inventory Sync Options** section, enable the following settings to suit.

> [!NOTE]
> **Note**
> 
> Individual projects cannot be scanned unless they are part of a group. Ensure that projects are within a group for scanning.

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: GitLab Projects, branches, and Groups. - Data inventory: All wikis, snippets, issues, commits, and files and folders for each commit. |
| Run Gencore AI Entitlement Scan | Enable the toggle to sync the entitlement metadata for the discovered resources. This is used in Gencore AI pipelines | View Permissions on GitLab Projects that are used to restrict prompt responses in our Gencore AI product. |
2. (Optional) In the **Data Inventory and Entitlement Sync Scope** section on the same **Connector** tab, select the collections of data resources to be included in your inventory.

![Data inventory and entitlement sync scope with selected groups, projects, and branches.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/gitlabscopes.png)
3. Click **Save**
4. Click **Execute** after the update is saved successfully.

It takes time to complete the Data Inventory Sync. You can check the state of your Data Inventory Sync in the **Status** and **Ingestion Status** message in the **Inventory Sync** section.

If you want to cancel or pause the Data Inventory Sync, perform the following steps:

  1. Under the **Inventory Sync** section beside **View Stats**, open the Action (**v**) menu.
  2. From the Action menu, choose one of the following:
    - Use **Cancel** to permanently stop the running scan
    - Use **Pause** to temporarily stop the running scan
    - Use **Restart** to start the Data Inventory Sync again from the beginning. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/inventory_pasuse-resume.png)
5. To view the Scan statistics for Inventory and Entitlement scans, see [Viewing data inventory sync statistics](/latest/docs/viewing-data-inventory-sync-statistics).

> [!NOTE]
> **Important**
> 
> Scan statistics are available only after the scan is successfully completed.
