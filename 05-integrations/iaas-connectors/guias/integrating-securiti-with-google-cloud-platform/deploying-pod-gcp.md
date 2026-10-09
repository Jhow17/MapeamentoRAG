---
title: "Deploying Pod"
slug: "deploying-pod-gcp"
updated: 2026-04-15T06:45:55Z
published: 2026-04-15T06:45:55Z
canonical: "helpcenter.securiti.ai/deploying-pod-gcp"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Deploying Pod

When a user chooses Securiti Cloud, while creating an instance, the pod is configured automatically on the Securiti Cloud. In case of My Cloud, Securiti lets you scan your data in assets on your infrastructure through automatic pod deployment. You provide Securiti with the permissions required for pod deployment to scan your data in assets on your infrastructure. This deployment process ensures seamless integration with your on-premises or private data systems to:

- Intelligently scan data systems to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account

For more information, see [pods](/v1/docs/securiti-pods-and-elastic-pods) documentation.

> [!WARNING]
> Important
> 
> Effective from release 1.137, the Data Systems Overview dashboard has been be retired for customers with Universal Data Explorer or Inventory enabled for their tenants, as its functionality is now fully covered within the Universal Data Explorer and Inventory. For more information, see [Data Systems Overview Dashboard Deprecation Summary](/latest/docs/data-systems-overview-dashboard-deprecation-summary).

### Connecting GCP Data Systems via Universal Data Explorer or Inventory

To scan data systems within your GCP environment, connect the data systems to a new or existing pod or elastic pod.

> [!NOTE]
> Note
> 
> If Universal Data Explorer or Inventory are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether these are included in your plan and whether your tenant meets the eligibility requirements for their activation.

1. To connect a data system to a pod, go to **Sensitive Data Intelligence** **> Universal Data Explorer** dashboard. Alternatively, select the jewel icon from the left panel, and choose **Inventory** from the left navigation bar.
2. On the Data Systems tab, select a subset of GCP assets in the same account or region by marking the checkboxes at their left ends.

> [!NOTE]
> Note
> 
> Currently supported GCP assets include Google Cloud Storage and GCP BigQuery.

After you mark the first checkbox, Securiti limits further selections to assets in the same hosting, asset type, account, and region.
3. From the floating modal that appears at the bottom, click **Connect Data System**.
4. On the **Add or Select a Compute Pod for Discovery** popup, apply the following settings:

| Name | Setting |
| --- | --- |
| New Pod | Mark this radio button to deploy a new pod. |
| Existing Pod | Mark this radio button to discover assets in an existing pod. |
| Cloud Provider | Choose **GCP**. |
| Deployment Types | Choose **Pod** or **Elastic Pod**. |
| Compute Pod Name | Enter a descriptive name for the pod. |
| Region | Choose the cloud service region for the pod. |
5. In case of **New Pod**, click **Sign in with Google**, then log in to Google with credentials for an account with compute create privilege in the project where the data systems are located.

Alternatively, Click **Download Template**, and use the downloaded Terraform template to deploy the pod.
6. Click **Connect**.

After Securiti deploys the pod and automatically tests connectivity with the selected GCP Assets, the assets change to the “Connected” state. You can then define scanning schedules and scopes as described in [Discovery scans](/latest/docs/discovery-scans).

### Connecting GCP Data Systems via Data Systems Overview Dashboard

To scan data systems within your GCP environment, connect the data systems to a new or existing pod or elastic pod.

1. To connect a data system to a pod, go to **Sensitive Data Intelligence** **>** **Data Systems Overview** dashboard.
2. On the **Data Systems** tab, select a subset of GCP assets in the same account or region by marking the checkboxes at their left ends.

> [!NOTE]
> **Note**
> 
> Currently supported GCP assets include Google Cloud Storage and Google BigQuery.

After you mark the first checkbox, Securiti only lets you mark additional checkboxes to select multiple assets in the same hosting, asset type, account, and region.
3. Near the upper right corner of the data assets table, click Connect Data System.
4. On the Add or Select a Compute Pod for Discovery popup, apply the following settings:

| Name | Setting |
| --- | --- |
| New Pod | Mark this radio button to deploy a new pod. |
| Existing Pod | Mark this radio button to discover assets in an existing pod. |
| Cloud Provider | Choose **GCP**. |
| Deployment Types | Choose **Pod** or **Elastic Pod**. |
| Compute Pod Name | Enter a descriptive name for the pod. |
| Region | Choose the cloud service region for the pod. |
5. In case of **New Pod**, click **Sign in with Google**, then log in to Google with credentials for an account with compute create privilege in the project where the data systems are located.

Alternatively, Click **Download Template**, and use the downloaded Terraform template to deploy the pod.
6. Click Connect.

After Securiti deploys the pod and automatically tests connectivity with the selected GCP Assets, the assets change to the “Connected” state. You can then define scanning schedules and scopes as described in [Discovery scans](/latest/docs/discovery-scans).

> [!NOTE]
> **Note**
> 
> To provide you control over pod deployment and scanning, Securiti lets you connect your data systems to existing pods without deploying new ones. You can select the data systems to scan and initiate scans whenever needed.
> 
> - On the **GCP IaaS Connector Configuration** page, you can select the **Detect for Sensitive Data** and **Discover Packages on VM Snapshots** options even if the **Deploy Pod** option is not selected.
> - The TF template will include connection details for the data systems but will not initiate scans.
> - To initiate scans, you must manually connect your data systems to pods using the **Data Systems Overview** dashboard.

## Related

- [Creating a GCP IaaS Instance (version 1.124 and later)](/creating-a-gcp-iaas-instance-version-1124-and-later.md)
- [Creating a GCP IaaS Instance (version 1.123 and earlier)](/creating-a-gcp-iaas-instance-version-1123-and-earlier.md)
