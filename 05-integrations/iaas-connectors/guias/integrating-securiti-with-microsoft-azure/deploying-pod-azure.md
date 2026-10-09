---
title: "Deploying Pod"
slug: "deploying-pod-azure"
updated: 2026-02-20T07:52:52Z
published: 2026-02-20T07:52:52Z
canonical: "helpcenter.securiti.ai/deploying-pod-azure"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Deploying Pod

After integrating the Azure IaaS connector with Securiti and once asset discovery is complete, you can deploy Securiti pods or elastic pods to scan specific data systems for sensitive or personal data.

For more information, see [pods](/latest/docs/securiti-pods-and-elastic-pods) documentation.

> [!WARNING]
> Important
> 
> Effective from release 1.137, the Data Systems Overview dashboard has been be retired for customers with Universal Data Explorer or Inventory enabled for their tenants, as its functionality is now fully covered within the Universal Data Explorer and Inventory. For more information, see [Data Systems Overview Dashboard Deprecation Summary](/latest/docs/data-systems-overview-dashboard-deprecation-summary).

### Connecting Azure Data Systems via Universal Data Explorer or Inventory

To scan data systems within your Azure environment, connect the data systems to a new or existing pod or elastic pod.

1. To connect a data system to a pod, go to **Sensitive Data Intelligence** **>** **Universal Data Explorer** dashboard. Alternatively, select the jewel icon from the left panel, and choose **Inventory** from the left navigation bar.

> [!NOTE]
> Note
> 
> If Universal Data Explorer or Inventory are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether these are included in your plan and whether your tenant meets the eligibility requirements for their activation.
2. On the Data Systems tab, select a subset of Azure assets in the same account or region by marking the checkboxes at their left ends.

> [!NOTE]
> **Note**
> 
> Currently supported Azure assets include Azure Blob Storage and Azure Files.

After you mark the first checkbox, Securiti limits further selections to assets in the same hosting, asset type, account, and region.
3. From the floating modal that appears at the bottom, click **Connect Data System**.
4. On the **Add** or **Select a Compute Pod for Discovery popup**, apply the following settings:

| Name | Settings |
| --- | --- |
| New Pod | Mark this radio button to deploy a new pod. |
| Existing Pod | Mark this radio button to discover assets in an existing pod. |
| Cloud Provider | Choose **Azure**. |
| Deployment Types | Choose **Pod** or **Elastic Pod**. |
| Compute Pod Name | Enter a descriptive name for the pod. |
| Region | Choose the cloud service region for the pod. |
5. Click **Connect**.

Alternatively, in case of **New Pod**, click **Download Template**, and use the downloaded Terraform template to create roles and trigger discovery.

After Securiti deploys the pod and automatically tests connectivity with the selected Azure assets, the assets change to the “Connected” state. You can then define scanning schedules and scopes as described in [Discovery Scans](/latest/docs/discovery-scans).

### Connecting Azure Data Systems via Data Systems Overview Dashboard

To scan data systems within your Azure environment, connect the data systems to a new or existing pod or elastic pod.

1. To connect a data system to a pod, go to **Sensitive Data Intelligence** **>** **Data Systems Overview** dashboard.
2. On the **Data Systems** tab, select a subset of Azure assets in the same account or region by marking the checkboxes at their left ends.

> [!NOTE]
> **Note**
> 
> Currently supported Azure assets include Azure Blob Storage and Azure Files.

After you mark the first checkbox, Securiti only lets you mark additional checkboxes to select multiple assets in the same hosting, asset type, account, and region.

1. Near the upper right corner of the data assets table, click **Connect Data System**.
2. On the **Add** or **Select a Compute Pod for Discovery** popup, apply the following settings:

| Name | Settings |
| --- | --- |
| New Pod | Mark this radio button to deploy a new pod. |
| Existing Pod | Mark this radio button to discover assets in an existing pod. |
| Cloud Provider | Choose **Azure**. |
| Deployment Types | Choose **Pod** or **Elastic Pod**. |
| Compute Pod Name | Enter a descriptive name for the pod. |
| Region | Choose the cloud service region for the pod. |
3. Click **Connect**. Alternatively, in case of **New Pod**, click **Download Template**, and use the downloaded Terraform template to create roles and trigger discovery.

After Securiti deploys the pod and automatically tests connectivity with the selected Azure assets, the assets change to the “Connected” state. You can then define scanning schedules and scopes as described in [Discovery Scans](/latest/docs/discovery-scans).

> [!NOTE]
> **Note**
> 
> Securiti deploys Redis as part of the elastic pod deployment. However, Redis is not supported by Azure in the US West region. Customers should verify that Redis is available in the region of their choice before deployment, as Redis support for regions may change over time.

## Related

- [Creating a Microsoft Azure Instance](/creating-a-microsoft-azure-instance.md)
