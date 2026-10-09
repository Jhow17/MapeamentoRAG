---
title: "Configure Data Inventory Sync for GitHub"
slug: "configure-data-inventory-sync-for-github"
updated: 2026-08-31T09:04:01Z
published: 2026-08-31T09:04:01Z
canonical: "helpcenter.securiti.ai/configure-data-inventory-sync-for-github"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Configure Data Inventory Sync for GitHub

Securiti supports Data Inventory Sync and entitlement scanning for GitHub (Self-hosted) Data system Connector. This sync collects an inventory of all of the files and their associated metadata within the configured scope of the sync. For Gencore AI use cases, the scan builds an index of Entitlements to files for populating Gencore AI Pipelines.

For more information, see [Data Inventory Sync for data systems](/latest/docs/data-inventory-sync-for-self-hosted-connectors).

You can configure Data Inventory Sync and entitlement scanning for your Data system Instance from the **Connector** tab, after the Connector Activation. Prior to the Connector Activation process, fulfill any required prerequisites as highlighted in the [section below](/latest/docs/configuring-data-inventory-sync-for-zendesk-support-self-hosted), for successful scanning.

### Prerequisites for running Data Inventory Sync for GitHub

#### Allowlisting APIs for Data Inventory Sync

You must allowlist the following APIs between your deployed Securiti Pod and the GitHub APIs to successfully run the Data Inventory Sync.

Default URL is *https://api.github.com*

| Sr. No | Method | URL | Purpose |
| --- | --- | --- | --- |
| 1 | GET | https://api.github.com/user/orgs | Get user’s organizations |
| 2 | GET | https://api.github.com/orgs/{{org_name}}/repos | Get organizational repositories |
| 3 | GET | https://api.github.com/user/repos | Get user repositories |
| 4 | GET | https://api.github.com/repos/{{org_name}}/{{repo_name}} | Get repository details |
| 5 | GET | https://api.github.com/repos/{{org_name}}/{{repo_name}}/branches | Get repository branches |
| 6 | GET | https://api.github.com/repos/{{org_name}}/{{repo_name}}/contents/{{path}} | Get repository content by branch |
| 7 | GET | https://api.github.com/repos/{{org_name}}/{{repo_name}}/pulls | Get pull requests by branch |
| 8 | GET | https://api.github.com/repos/{{org_name}}/{{repo_name}}/pulls/{{pull_no}} | Get a single pull request |
| 9 | GET | https://api.github.com/repos/{{organization}}/{{repo}}/commits | Get commits by branch |
| 10 | GET | https://api.github.com/repos/{{organization}}/{{repo}}/commits/{{commit_id}}/comments | Get commit comments |
| 11 | GET | https://api.github.com/repos/{{organization}}/{{repo}}/pulls/{{pull_request}}/reviews | Get pull request reviews |
| 12 | GET | https://api.github.com/repos/{{organization}}/{{repo}}/pulls/{{pull_request}}/reviews/{{review_id}}/comments | Get review comments |
| 13 | GET | https://api.github.com/repos/{{organization}}/{{repo}}/issues | Get repository issues |
| 14 | GET | https://api.github.com/repos/{{organization}}/{{repo}}/issues/{{issue}}/comments | Get Issue comments |
| 15 | GET | https://api.github.com/repos/{{organization}}/{{repo}}/branches/{{branch}} | Get a single branch |
| 16 | GET | https://api.github.com/repos/{{owner}}/{{repo}}/contents?ref={{branch}} | Get repository content |
| 17 | GET | https://api.github.com/repos/{{owner}}/{{repo}}/collaborators | Get collaborators for a repository |
| 18 | GET | https://api.github.com/users/{{user}} | Get collaborator details |

### Configure Data Inventory Sync for GitHub

After activating the GitHub (Self-hosted) Connector, wait until the Discovery scan meta is synced. Perform the following steps to run the Data Inventory Sync and Entitlement Scan for GitHub.

1. On the **Connector** tab, in the **Inventory Sync Options** section, enable the following settings to suit.

| Scan setting | Description | Type of data scanned |
| --- | --- | --- |
| Run Data Inventory Sync | Enable the toggle to sync the metadata for your Data system. The scan builds an inventory for all the discovered resources. | - Scoping inventory: Organizations, repositories and branches - Data inventory: Description of all repositories, files and folders in all branches, issues, commits, and pull requests. |
| Entitlement Scan | Enable the toggle to sync the entitlement metadata for the discovered resources. This is used in Gencore AI pipelines | View Permissions on GitHub files that are used to restrict prompt responses in our Gencore AI product. |
2. (Optional) In the **Data Inventory and Entitlement Sync Scope** section on the same **Connector** tab, select the collections of data resources to be included in your inventory.

![Data inventory settings for GitHub permissions, including organizations and repositories selected.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/githubscopes.png)
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
