---
title: "Synchronizing assets from AWS"
slug: "synchronizing-assets-from-aws"
updated: 2025-12-09T08:30:56Z
published: 2025-12-09T08:30:56Z
canonical: "helpcenter.securiti.ai/synchronizing-assets-from-aws"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Synchronizing assets from AWS

You can synchronize Securiti with an AWS instance to import the following assets from multiple AWS member accounts into your Securiti Data Mapping Automation module:

- S3 buckets
- Relational databases
- Non-native data systems on virtual machines

> [!NOTE]
> **Note**
> 
> To import non-native data systems, AWS Systems Manager Inventory must be set up and the virtual machines must have the AWS SSM agent running on them.

This feature is not available to all accounts; contact your Securiti representative to activate this feature for your Securiti account.

Once we have activated this feature for your account, use this procedure to configure asset sync from AWS:

1. In Securiti open **Sensitive Data Intelligence**, then choose **Settings > CMDB Systems Connectors**.
2. On the card for AWS, near the upper right corner click **+** to create a new instance.
3. On the Basic Information tab, apply the following settings:

| Instance Name | Enter a convenient name for the instance. |
| --- | --- |
| Instance Location | Choose the country and state, and enter the city where the instance is located. |
| Owner | Choose additional co-owners for the instance if you want. By default you are the instance owner. |

![AWS_asset_sync_basic_info.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eca0c508-6b45-90ba-f588-ead47d51257f.png)
4. Click **Create Instance and continue**.

Securiti advances you to the Connector Setup tab.
5. On the Instance Setup tab, click **Advanced** and apply the following settings:

| AWS Master Account ID | Enter the ID of the AWS master account for which Securiti assumes the AWS Discovery Master IAM Role via External AWS Cross Account Access. |
| --- | --- |
| AWS Discovery Master IAM Role | Enter the name for the AWS discovery master IAM role that Securiti assumes via External AWS Cross Account to further assume the AWS Discovery Member IAM Role in AWS Member Account Ids. This role name must begin with one of the following: - SECURITI - Securiti - securiti |
| AWS Member Account Ids | Enter the member account ID(s) where Securiti scans for AWS S3 assets. If you enter multiple member account IDs, separate them with commas. |
| AWS Discovery Member IAM Role | Enter the name for the AWS discovery member IAM role that Securiti assumes in each AWS Member Account to scan available S3 Buckets. |
| Securiti Account ID | Leave as-is. |
| External ID | (Optional) click **Regenerate** to generate a new External ID for the discovery roles. |
| Select Region(s) | Choose one or more regions to scan for assets. |
| Include Data Scan Role | Leave unmarked. |
6. Near the bottom of the Instance Setup tab, click **Save**, then on the popup click **OK**.
7. Near the bottom of the Instance Setup tab, click the links to download the master account CloudFormation template and the member account CloudFormation template.
8. In the AWS console, use the templates to launch a CloudFormation stack for the master and each member account to authenticate access for Securiti as shown below.

![image__6_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b44ec13b-26e9-07af-9378-5e62d10e1057.png)
9. In Securiti, near the bottom of the Connector Setup tab, click **Activate Connector**.

Securiti tests the credentials and information you provided to check whether they give it access necessary to scan AWS for assets, and whether you correctly applied the CloudFormation templates. When the test succeeds, Securiti adds Scan Policies tools to the bottom of the Connector Setup tab.
10. Use the Scan Policies to configure regular scans, and click **Initiate Data Scan** to manually start a scan.
11. (Optional) Click the **Scheduling** tab and use the tools there to schedule periodic re-scans. Click **Add Exclusion** to create one or more exclusion periods during which Securiti does not perform re-scans.
12. In Securiti, open **Data Mapping Automation** and then open the Assets catalog.

The AWS S3 assets that Securiti discovered are listed in Assets. If necessary, Filter the page by Technology Type (if specified) to find the AWS assets more easily.

A Technology Type defines what type of asset or vendor an entity belongs to. These may include 101Data, ServiceNow, MySQL, and the likes thereof.
