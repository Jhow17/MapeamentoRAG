---
title: "Upgrading hybrid deployment with Outpost"
slug: "upgrading-hybrid-deployment-with-outpost"
updated: 2026-08-28T08:12:14Z
published: 2026-08-28T08:12:14Z
canonical: "helpcenter.securiti.ai/upgrading-hybrid-deployment-with-outpost"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Upgrading hybrid deployment with Outpost

This document guides you through the process you need for updating your hybrid Outpost version. It includes:

- [Updating hybrid deployment with Outpost manually](/latest/docs/upgrading-hybrid-deployment-with-outpost#upgrade)
- [Upgrading hybrid Outpost deployment](/latest/docs/upgrading-hybrid-deployment-with-outpost#upgrading-hybrid-outpost-deployment)

## Updating hybrid deployment with Outpost manually

When there is an update available for your hybrid Outpost deployment, a version update warning sign appears on your **Securiti Outposts** page in the **Version** column. This sign indicates that there is an update available. When this sign appears, it indicates that you did not mark **Enable Auto-update** field during installation.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-2ABDVLF5.png)

You must update it manually using the following steps:

1. On the **Securiti Outpost** page, select the Outpost you wish to update.
2. Under the Version column, hover over the version update warning sign.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-OH9HRAY8.png)
3. On the appearing popup, click **Update Now**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VSQ0ZFF4.png)

It starts updating your Outpost version to the latest.

## Upgrading hybrid Outpost deployment

Upgrading the hybrid Outpost lets you upgrade some or all of your AWS cloud infrastructure. When there is a new addition or deprecation of any AWS service, configurations, or any other major change, you must upgrade your hybrid Outpost.

To upgrade your hybrid Outpost, proceed with the following steps:

1. At the top left corner of the platform, click the **Jewel** icon.
2. From the Platform Services section in the new navigation, click **Settings**.
3. From the **Settings** menu, choose **Deployment** > **Securiti Outpost**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti-outpost-deployment-image-e2235xmo.png)

It displays all your hybrid Outpost deployments.
4. Select any deployment you wish to upgrade. At the right side of your deployment row, click **Options** (three dots) and select **Edit**.
5. On the **Edit Outpost** popup, click **Prepare & Download Template**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4Q2T0K4J.png)

It downloads your hybrid Outpost’s CloudFormation template to your local storage.

Once you download the CloudFormation template for your hybrid Outpost, apply it to your existing CloudFormation stack on your AWS and update it. It applies any changes reflected in the latest template. It lets you upgrade your hybrid Outpost to the latest infrastructure that Securiti supports.
