---
title: "Managing Hybrid deployments with Outpost"
slug: "managing-securiti-outpost-deployments-1"
updated: 2026-08-01T08:54:37Z
published: 2026-08-03T21:00:00Z
canonical: "helpcenter.securiti.ai/managing-securiti-outpost-deployments-1"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Managing Hybrid deployments with Outpost

To access the **Securiti Outpost** page, proceed with the following steps.

1. At the top left corner of the platform, click the **Jewel** icon.
2. From the Platform Services section in the new navigation, click **Settings**.
3. From the **Settings** menu, choose **Deployment** > **Securiti Outpost**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti-outpost-deployment-image-e2235xmo.png)

It shows all the relevant information about the deployments created in **Securiti Outpost** page.

## Creating a new hybrid deployment with Outpost

Use this option to create and deploy a new Securiti Outpost in your cloud environment.

1. On the top right of the **Securiti Outpost** page, click **+ New Outpost**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti-outpost-deployment-image-8aca36ui.png)For more information on creating a new Outpost deployment, see [Hybrid deployment with Outpost - AWS](/latest/docs/full-saas-hyperdrive-deployment).

## Using the search option

Use this search bar to search across created deployments using the supported Outpost columns.

1. At the top of the **Securiti Outposts** page, click in the search bar to begin searching. Search options support the following columns:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti-outpost-deployment-image-8qkk5pl2.png)
  - Name
  - Region
  - Status

## Using the Outpost deployment list

This section shows all hybrid Outpost deployments, their associated details across multiple columns, and the overall deployment count.

#### Deployments count

This section shows the total number of Outposts created, including both active and inactive deployments. It also includes deployments for which you have downloaded the CloudFormation template but have not yet deployed it.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-QNKC0XX9.png)

#### 

#### Hybrid Outpost deployments list

The list of deployments contains the table showing all the deployments and relevant information. It contains the following columns to display the deployments' details.

| Column name | Description |
| --- | --- |
| Name | Displays the name of the Outpost instance added to your tenant. |
| Status | Displays whether the Outpost is currently Active or Offline. |
| Version | Displays the software version running on the Outpost, if the deployment is active. |
| Nodes | Displays the total number of nodes of the EKS cluster. |
| Last Update | Displays the date and time when the Outpost last synced with the platform. |
| Owner | Displays the primary owner's profile who was selected as Primary Owner while creating the Outpost deployment in Securiti. |
| Account ID | Displays the account ID, which is unique to your deployment, and is also in your account. It is also a part of the CloudFormation template. |
| External ID | Displays the external ID, which is auto-generated when you configure for Outpost deployment in Securiti. |
| Suffix | Displays the unique identifier automatically assigned to the Outpost. |
| Metadata Bucket Name | Displays the name of the AWS S3 metadata bucket that stores Outpost-related metadata. |
| Created At | Displays the date and time at which the owner created the deployment. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti-outpost-deployment-image-nuh58nqd.png)

#### 

#### Column Selector

The column selector lets you list only specific columns.

1. On the right side of the column titles, click the **Column Selector** icon.
2. In the popup, mark the columns you want to display.
3. Click **Apply** to show the selected columns.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti-outpost-deployment-image-wmyam4yy.png)

#### 

#### 

## Using the More actions option

Use the More actions option to access additional controls, including viewing details, editing, and deleting an Outpost deployment.

#### Editing the hybrid Outpost deployment

To edit your hybrid Outpost deployment, proceed with the following steps:

1. Open the **Securiti Outpost** page, where all the deployments are listed in the table, and select a deployment to edit.
2. At the right side of the deployment row, click the **Options** button (three dots).
3. From the menu, select **Edit**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti-outpost-deployment-image-wlv40jvb.png)

It opens the **Edit Outpost** popup.

1. Update the name, as you can only update the **Instance Name** field here.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti-outpost-deployment-image-kqaqqy70.png)

1. To redownload the CloudFormation template you applied to deploy your Hybrid Outpost, under **Deployment Method**, click **Download Template**. It downloads the CloudFormation template in your local storage. You can use this template to upgrade your existing Outpost deployment. For more information on upgrading hybrid Outpost, see [Upgrading Hybrid deployment with Outpost](/latest/docs/upgrading-hybrid-deployment-with-outpost).
2. Once you modify the name, click **Save**.

#### 

#### Deleting the hybrid Outpost deployment

To delete an existing hybrid Outpost deployment, proceed with the following steps:

> [!WARNING]
> Important
> 
> You must delete the associated data system instance before deleting the Outpost deployment.

1. Open the **Securiti Outpost** page, where all the deployments are listed in the table, and select a deployment to edit.
2. At the right side of the deployment row, click the **Options** button (three dots).
3. From the menu, select **Delete**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti-outpost-deployment-image-p9m14hs4.png)

It opens up a confirmation popup.

1. On the appeared popup for a confirmation, click **Yes, continue**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti-outpost-deployment-image-eijf3evq.png)

It deletes the Outpost deployment.

####
