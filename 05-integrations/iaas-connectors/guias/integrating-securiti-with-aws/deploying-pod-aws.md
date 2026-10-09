---
title: "Deploying Pod"
slug: "deploying-pod-aws"
updated: 2026-04-08T06:05:08Z
published: 2026-04-08T06:05:08Z
canonical: "helpcenter.securiti.ai/deploying-pod-aws"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Deploying Pod

When a user chooses Securiti Cloud, while creating an instance, the pod is configured automatically on the **Securiti Cloud**. In case of **My Cloud**, Securiti lets you scan your data in assets on your infrastructure through automatic pod deployment. You provide Securiti with the permissions required for pod deployment to scan your data on your infrastructure. This deployment process ensures seamless integration with your on-premises or private data systems to:

- Intelligently scan data systems to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account

For more information, see [pods](/v1/docs/securiti-pods-and-elastic-pods) documentation.

> [!WARNING]
> Important
> 
> Effective from release 1.137, the Data Systems Overview dashboard has been be retired for customers with Universal Data Explorer or Inventory enabled for their tenants, as its functionality is now fully covered within the Universal Data Explorer and Inventory. For more information, see [Data Systems Overview Dashboard Deprecation Summary](/latest/docs/data-systems-overview-dashboard-deprecation-summary).

### Connecting AWS Data Systems via Universal Data Explorer or Inventory

To scan data systems within your AWS environment, connect the data systems to a new or existing pod or elastic pod.

> [!NOTE]
> Note
> 
> If this feature Universal Data Explorer or Inventory are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether these are included in your plan and whether your tenant meets the eligibility requirements for their activation.

1. To connect a data system to a pod, go to **Sensitive Data Intelligence** **> Universal Data Explorer** dashboard. Alternatively, select the jewel icon from the left panel, and choose **Inventory** from the left navigation bar.
2. On the **Data Systems** tab, select a subset of AWS assets in the same account or region by marking the checkboxes at their left ends.

> [!NOTE]
> **Note**
> 
> Currently supported AWS assets include Amazon S3.

After you mark the first checkbox, Securiti limits further selections to assets in the same hosting, asset type, account, and region.
3. From the floating modal that appears at the bottom, click Connect Data System.
4. On the Add or Select a Compute Pod for Discovery popup, apply the following settings:

| Name | Settings |
| --- | --- |
| New Pod | Mark this radio button to deploy a new pod. |
| Existing Pod | Mark this radio button to discover assets in an existing pod. |
| Cloud Provider | Choose **AWS**. |
| Deployment Types | Choose **Pod** or **Elastic Pod**. |
| Compute Pod Name | Enter a descriptive name for the pod. |
| Region | Choose the cloud service region for the pod. |
| Worker Size | Specify the number of member nodes to launch to deploy a pod. The minimum limit is 0, and the maximum limit is 5. > [!NOTE] > Note > > When you execute the CloudFormation (CF) template the worker nodes automatically connect to the master node. You do not require to manually configure each worker node. |
5. Click **Connect**.

Alternatively, in case of **New Pod**, click **Download Template**, and use the downloaded CloudFormation template to create roles and trigger discovery.

After Securiti deploys the pod and automatically tests connectivity with the selected AWS assets, the assets change to the “Connected” state. You can then define scanning schedules and scopes as described in [Discovery Scans](/v1/docs/discovery-scans).

### Connecting AWS Data Systems via Data Systems Overview Dashboard

To scan data systems within your AWS environment, connect the data systems to a new or existing pod or elastic pod.

1. To connect a data system to a pod, go to **Sensitive Data Intelligence** **>** **Data Systems Overview** dashboard. Alternatively, select the jewel icon from the left panel, and choose **Inventory** from the left navigation bar.
2. On the **Data Systems** tab, select a subset of AWS assets in the same account or region by marking the checkboxes at their left ends.

> [!NOTE]
> **Note**
> 
> Currently supported AWS assets include Amazon S3.

After you mark the first checkbox, Securiti limits further selections to assets in the same hosting, asset type, account, and region.
3. Near the upper right corner of the data assets table, click **Connect Data System**.
4. On the **Add or Select a Compute Pod for Discovery** popup, apply the following settings:

| Name | Settings |
| --- | --- |
| New Pod | Mark this radio button to deploy a new pod. |
| Existing Pod | Mark this radio button to discover assets in an existing pod. |
| Cloud Provider | Choose **AWS**. |
| Deployment Types | Choose **Pod** or **Elastic Pod**. |
| Compute Pod Name | Enter a descriptive name for the pod. |
| Region | Choose the cloud service region for the pod. |
| Worker Size | Specify the number of member nodes to launch to deploy a pod. The minimum limit is 0, and the maximum limit is 5. > [!NOTE] > Note > > When you execute the CloudFormation (CF) template the worker nodes automatically connect to the master node. You do not require to manually configure each worker node. |
5. Click **Connect**.

Alternatively, in case of **New Pod**, click **Download Template**, and use the downloaded CloudFormation template to create roles and trigger discovery.

After Securiti deploys the pod and automatically tests connectivity with the selected AWS assets, the assets change to the “Connected” state. You can then define scanning schedules and scopes as described in [Discovery Scans](/v1/docs/discovery-scans).

> [!NOTE]
> **Note**
> 
> To provide you control over pod deployment and scanning, Securiti lets you connect your data systems to existing pods without deploying new ones. You can select the data systems to scan and initiate scans whenever needed.
> 
> - On the **AWS IaaS Connector** **Configuration page**, you can select the **Detect for Sensitive Data** and **Discover Packages on VM Snapshots** options even if the **Deploy Pod** option is not selected.
> - The CF template will include connection details for the data systems but will not initiate scans.
> - To initiate scans, you must manually connect your data systems to pods using the **Data Systems** **Overview** dashboard.

## Related

- [Creating an AWS IaaS instance (version 1.111 and later)](/creating-an-aws-iaas-instance-version-1111-and-later.md)
- [Creating an AWS IaaS instance (version 1.110 and earlier)](/creating-an-aws-iaas-instance-version-1110-and-earlier.md)
