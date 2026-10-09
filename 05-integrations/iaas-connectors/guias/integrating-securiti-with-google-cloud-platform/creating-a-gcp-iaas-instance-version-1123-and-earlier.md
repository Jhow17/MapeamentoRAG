---
title: "Creating a GCP IaaS Instance (version 1.123 and earlier)"
slug: "creating-a-gcp-iaas-instance-version-1123-and-earlier"
updated: 2026-02-08T12:16:50Z
published: 2026-02-08T12:16:50Z
canonical: "helpcenter.securiti.ai/creating-a-gcp-iaas-instance-version-1123-and-earlier"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Creating a GCP IaaS Instance (version 1.123 and earlier)

You integrate Securiti with GCP to accomplish a wide variety of Sensitive Data Intelligence functions, including but not limited to:

- Asset discovery, including shadow assets
- Discovery scans
- Posture management and remediation
- Integration with Security Command Center

For this integration, Securiti creates the service accounts described in [How it Works?](/v1/docs/how-it-works) in the first project it discovers.

In general, the process is:

1. Activate IaaS integration using either one-click activation or advanced mode as described in IaaS activation.
2. Activate Securiti pods in GCP to scan specific data systems as described in [pods](/latest/docs/securiti-pods-and-elastic-pods) documentation.
3. Perform discovery scans as described in [Discovery Scans](/v1/docs/discovery-scans).

### Prerequisites

- You must have Terraform 1.6.6 or later. We strongly recommend using 1.7.0 or later, because it addresses several vulnerabilities.
- You must have the following GCP roles:
  - Organization Administrator
  - Owner
- All projects that you want to be discovered and scanned must have the compute.googleapis.com APIs and billing enabled on them as a minimum requirement. Otherwise, those projects and associated assets may not be discovered. You may have to enable additional APIs depending on the types of assets in the projects.

### IaaS activation

There are three methods of integrating Securiti with GCP:

- **One-click activation--**Securiti connects to all projects within a GCP organization. If you want to only connect to a subset of Projects in your org, use the advanced activation instead.
- **Advanced activation--**You download Terraform activation scripts and specify an explicit list of GCP projects that Securiti service accounts are authorized to perform discovery, scanning, and remediation against. The API account used to execute the activation scripts to complete activation requires an Owner role for the projects being activated. It may also require an Organization Admin role if you have enabled certain SDI features.
- **Activation from GCP Security Command Center (SCC) Marketplace--**Lets you generate findings to GCP Security Command Center and create and tag entries in GCP Data Catalog. You can also trigger GCP data catalog functionality via the Securiti Workflow module.

#### One-click activation

With one-click activation, Securiti connects to all projects within a GCP organization. If you want to only connect to a subset of Projects in your org, use the advanced activation instead.

1. In Securiti, open **Settings**. Choose **Integrations** > **IaaS Cloud**, and click **Create Instance** on the **Google Cloud Platform** card.
2. On the **Add a Cloud Account** popup, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Account Provider | Choose **Google Cloud**. |
| Initiate asset discovery | Mark to discover assets. The asset discovery is enabled by default when configuring a particular IaaS connector. For detailed IAM permissions, policies, and roles see [Policies and Permissions required for GCP Integration](/v1/docs/policies-and-permissions-required-for-gcp-integration) |
| Notify all owners by email when asset discovery is complete | Enabled by default to send emails to owners and co-owners after an asset discovery scan completes. The notification includes key insights and a direct link to the Graph for deeper analysis. > [!NOTE] > **Note** > > - Email notifications are sent only when asset discovery identifies new assets. > - To trigger the email notifications, it is necessary to reschedule and run asset discovery again. > - To enable this feature for existing instances, navigate to the **Instance Setup tab > Advanced Settings > Notify all owners by email when asset discovery is complete**. > - If the feature was enabled during the connector onboarding, you can disable it from the same tab if you no longer wish to receive email notifications. |
| Initiate security posture scan | Enable to have Securiti scan Google Cloud for security vulnerabilities and display them on the [Findings](/latest/docs/configuring-security-posture-policies). |
| Auto-remediate security posture violations | Enable to have Securiti automatically remediates any security vulnerabilities it finds. |
| Integrate with GCP SCC & Data Catalog | If you are activating via the SCC marketplace as described in Activation from GCP Security Command Center (SCC) Marketplace section, mark the checkbox to Enable to generate findings in the GCP Security Command Center and create and tag entries in the GCP data catalog. Then enter the following information you recorded during that procedure: - Source ID - Organization ID - Service account key |
3. Click **Sign in with Google**.
4. On the Choose an account popup, choose a Google account for which you have GCP Organization Admin role permissions.

Securiti starts asset discovery and populates the Overview dashboard with them.

#### Advanced activation

For Advanced activation you download Terraform activation scripts and specify various parameters, optionally including an explicit list of GCP projects that Securiti service accounts are authorized to perform discovery, scanning and remediation against. The API account used to execute the activation scripts to complete activation requires Admin role for the projects being activated. You must have Organization Admin role if you have enabled SCC integration feature.

1. In Securiti, open **Sensitive Data Intelligence**.
2. On the Overview dashboard that opens by default, near the upper right corner of the page click **+ Add Cloud Account**.
3. On the Add a Cloud Account popup, apply the following settings:

| Parameter | Description |
| --- | --- |
| Select Account Provider | Choose **Google Cloud** |
| Initiate asset discovery | Mark to discover assets The asset discovery is enabled by default when configuring a particular IaaS connector. For detailed IAM permissions, policies, and roles see [Policies and Permissions required for GCP Integration](/v1/docs/policies-and-permissions-required-for-gcp-integration) |
| Initiate security posture scan | Enable to have Securiti scan Google Cloud for security misconfigurations |
| Auto-remediate security posture violations | Enable to have Securiti automatically remediate any security misconfigurations it finds |
| Integrate with GCP SCC & Data Catalog | Enable to generate findings in the GCP Security Command Center and create and tag entries in the GCP data catalog |
4. Expand the **Advanced Mode** area, then click **Download Template**.

Securiti downloads a .zip file containing the Terraform templates to your Downloads folder.
5. Open the README.md file and study it for guidance on customizing the Terraform templates.
6. Customize the Terraform templates to suit per the guidelines in README.md.

> [!NOTE]
> **Note**
> 
> General guidance on using Terraform is beyond the scope of the Securiti documentation.
7. Open a command prompt in the directory where you extracted the Terraform configuration files and execute the following commands:

```plaintext
terraform init
terraform apply
```
8. Confirm creation by entering **yes** when prompted.

Securiti starts asset discovery and populates the Overview dashboard with them.
9. To scan specific data systems within GCP for sensitive or personal data, proceed to [Pod activation](/v1/docs/creating-a-gcp-iaas-instance#pod-activation) to activate Securiti pods.

#### Activation from GCP Security Command Center (SCC) Marketplace

If you are activating the GCP integration starting from the SCC marketplace, follow these steps to create the service account/key in order to reference them later during Single Click activation steps.

1. Navigate to the SCC dashboard in your GCP tenant and click on the **Explore** tab.
2. Locate the tile for **Securiti for cloud SCC** and click it.

![explore_for_organization.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-78f4a9a2-8293-8ab7-0af6-b3209d8a5fe7.png)
3. On the page for Securiti for cloud SCC, click **Sign up with partner**.

![overview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-baabb33e-b302-e381-41f5-f328e77179c7.png)
4. Select the organization where you would like to integrate into.

![SCC_select_an_organization.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a516f996-01fa-8ccb-6065-6e3abbb23f39.png)
5. Select the project you would like to create the service account in, define a name for the service account, and click **Submit**.

![create_service_account___enable_securiti_for_cloud_scc.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-af5f7c6f-9c10-550f-27e5-04f4046617d1.png)

After GCP creates the service account, it automatically redirects you to the list of current integrations in your environment.
6. Locate the entry for “Securiti for cloud SCC” and record the information in the following fields:

![source_ID_and_service_account.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a8115e25-1cff-6ea6-4930-56091c23476b.png)
  - Source ID
  - Service Account
7. Navigate to the IAM & Admin module in the project where you created the service account.
8. Navigate to Service Accounts and locate the service account that you created.
9. Click the **Keys** tab, then click **Add Key > Create New Key**.

![create_new_key.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-85281767-c3f1-b88b-463b-faa1b4514fae.png)
10. Select **JSON** for the type, then click **Create**.

![create_private_key_1920.jpg](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2b4c8f23-4b68-23e7-a44a-1338503356f0.jpg)
11. Store the downloaded key in a secure location to use later.
12. If you don't already have it available, record your GCP organization ID [as described in this article](https://cloud.google.com/resource-manager/docs/creating-managing-organization).
13. Proceed to One-click activation.

### Pod activation

After you integrate Securiti with GCP and do asset discovery as described in IaaS activation, activate Securiti pods in GCP to scan specific data systems for sensitive or personal data. Use one of these methods:

- **One-click pod activation--**Quickly sets up a new Securiti pod to monitor a set of assets in GCP. Your Google account must have compute create privilege in the project where the data systems are located.
- **Manual pod activation--**Uses an existing Securiti pod that you have already set up.

> [!NOTE]
> **Note**
> 
> We recommend that you deploy pods in the same IaaS region as the target assets you want to scan.

### One-click pod activation

> [!NOTE]
> **Note**
> 
> When you create a pod using one-click activation, it is configured with security groups such that inbound connection attempts are rejected but all outbound connection attempts are allowed. The outbound access is not restricted to allow the pods to communicate with Securiti’s SaaS cloud, to download images for installation and upgrade and to scan any SaaS data systems that are outside the IaaS. If you want to add additional restrictions, see [Pod Prerequisites](/v1/docs/securiti-pods-and-elastic-pods) for more information about the URLs the pod must be able to reach in order to function.

1. If you haven't already done so, Open **Sensitive Data Intelligence** to the Overview dashboard.
2. On the Data Systems tab, select a subset of GCP assets (Cloud Storage, Bigtable, etc.) in the same account or region by marking the checkboxes at their left ends.

After you mark the first checkbox, Securiti only lets you mark additional checkboxes for assets in the same account or region.
3. Near the upper right corner of the data assets table, click **Connect Data System**.
4. On the Add or Select a Compute Pod for Discovery popup, apply the following settings:

| Parameter | Description |
| --- | --- |
| New Pod | Mark this radio button to use one-click pod activation |
| Cloud Provider | Choose GCP. |
| Deployment Types | Choose **Pod**. |
| Compute Pod Name | Enter a descriptive name for the pod. |
| Region | Choose the cloud service region for the pod. |
5. Click **Sign in with Google**, then log in to Google with credentials for an account with compute create privilege in the project where the data systems are located.

After Securiti deploys the pod and automatically tests connectivity with the selected GCP Assets, the Assets change to the "Connected" state. You can then define scanning schedules and scopes as described in [Discovery Scans.](/v1/docs/discovery-scans)

### Manual pod activation

1. If you haven't already done so, set up a Securiti pod as described in [pods](/v1/docs/securiti-pods-and-elastic-pods) documentation.
2. On the Data Systems tab, select a subset of GCP assets (Cloud Storage, Bigtable, etc.) in the same account or region by marking the checkboxes at their left ends.

After you mark the first checkbox, Securiti only lets you mark additional checkboxes for assets in the same account or region.
3. Near the upper right corner of the data assets table, click **Connect Data System**.
4. On the Add or Select a Compute Pod for Discovery popup, apply the following settings:

| Parameter | Description |
| --- | --- |
| Existing Pod | Mark this radio button to use manual pod activation. |
| Compute Pod Name | Choose the pod you want to use to connect with the selected data systems. |
| Compute Pod Name | Choose an existing pod from the menu. |
5. (Optional) Click **Download Template**, and use the downloaded Terraform templates to to create roles and trigger discovery
6. Click **Connect**.

After Securiti deploys the pod and automatically tests connectivity with the selected GCP Assets, the Assets change to the “Connected” state. You can then define scanning schedules and scopes as described in [Discovery Scans](/v1/docs/discovery-scans).

### Elastic pod activation

Elastic Pods are similar to regular pods, but because they run in a Kubernetes cluster, you can easily increase or decrease their capacity to match your processing needs. The GCP elastic pod activation procedures below create the following artifacts required for the operation of an elastic pod:

| Artifact | Resources | Description |
| --- | --- | --- |
| Service Account | google_project_iam_member | Service account with least privileges for deploying resources for elastic-pod |
| VPC | module.vpc.google_compute_address.nat_ips[0] module.vpc.google_compute_address.nat_ips[1] module.vpc.google_compute_firewall.internal module.vpc.google_compute_network.network module.vpc.google_compute_router.router module.vpc.google_compute_router_nat.nat module.vpc.google_compute_subnetwork.private module.vpc.google_compute_subnetwork.public | Internal Subnets (Customer configurable)Firewall and routes configured to allow cluster-local communication. Allow connections from bastion (control VM) |
| Control VM | google_compute_address.static google_compute_firewall.securiti-firewall google_compute_instance.deployment-server | Used to bootstrap the kubernetes cluster and bastion host for subsequent communication for upgrades and configuration changes. Terraform state of GKE is stored on control VM. |
| Elastic Pod Cluster | module.gke.google_container_cluster.primary module.gke.google_container_node_pool.primary | GKE Cluster to run Securiti jobsVersion: 1.21.12One node pool - precreated3 Nodes deployed initially, one per zone.User-configurable max number of nodes.Auto scale up and down within the pool.No auto provisioning of pools. |
| Artifact Registry | module.gar.google_artifact_registry_repository.edss-repo | To store images for GKE |
| Operational Access via Bastion (Control VM) | module.bastion.data.google_compute_image.ubuntu module.bastion.google_compute_firewall.ssh module.bastion.google_compute_instance_template.primary (e2-medium) module.bastion.google_compute_region_instance_group_manager.primary module.bastion.google_compute_target_pool.primary | e2-medium sized VM used for Bastion (Control VM). Single instance in single instance group |
| Redis In-Memory DB | module.redis.google_monitoring_alert_policy.redis-alerts module.redis.google_monitoring_notification_channel.email | GCP Managed service, Version 5.0 No replicas Capacity 8 GB |

### One-click elastic pod activation

1. If you haven't already done so, open **Sensitive Data Intelligence** to the Overview dashboard.
2. On the Data Systems tab, select a subset of GCP assets (Cloud Storage, Bigtable, etc.) in the same account or region by marking the checkboxes at their left ends.

After you mark the first checkbox, Securiti only lets you mark additional checkboxes for assets in the same account or region.
3. Near the upper right corner of the data assets table, click **Connect Data System**.
4. On the Add or Select a Compute Pod for Discovery popup, apply the following settings:

| Name | Setting |
| --- | --- |
| New Pod | Mark this radio button to use one-click pod activation |
| Cloud Provider | Choose **GCP**. |
| Deployment Types | Choose **Elastic Pod**. |
| Compute Pod Name | Enter a descriptive name for the pod. |
| Region | Choose the cloud service region for the pod. |
| Max Nodes | Enter the maximum number of nodes the auto-scaling elastic pod group is allowed to utilize. |
5. Click **Sign in with Google**, then log in to Google with credentials for an account with owner privilege in the project where the data systems are located.
6. Wait an hour, then check the **Settings > Deployments > Elastic Pods** page and the new elastic pod should be registered.

After Securiti deploys the pod and automatically tests connectivity with the selected GCP Assets, the Assets change to the "Connected" state. You can then define scanning schedules and scopes as described in [Discovery Scans](/v1/docs/discovery-scans).

### Manual elastic pod activation

1. In GCP, determine the project to be used for the elastic pod deployment.
2. Create a service account with Owner role, only for the specific project.
3. Create a service account key and download JSON formatted key file.

The key file name is something like "gcpproject-123456-db482a9ec234.json".
4. If you haven't already done so, log in to Securiti and open **Sensitive Data Intelligence** to the Overview dashboard.
5. On the Data Systems tab, select a subset of GCP assets (Cloud Storage, Bigtable, etc.) in the same account or region by marking the checkboxes at their left ends.

After you mark the first checkbox, Securiti only lets you mark additional checkboxes for assets in the same account or region.
6. Near the upper right corner of the data assets table, click **Connect Data System**.
7. On the Add or Select a Compute Pod for Discovery popup, apply the following settings:

| Parameter | Description |
| --- | --- |
| New Pod | Mark this radio button to use one-click pod activation |
| Cloud Provider | Choose **GCP**. |
| Deployment Types | Choose **Elastic Pod**. |
| Compute Pod Name | Enter a descriptive name for the pod. |
| Region | Choose the cloud service region for the pod. |
| Max Nodes | Enter the maximum number of nodes the auto-scaling elastic pod group is allowed to use. |
8. In the Advanced Mode area, click **Prepare Template**.

Securiti uses the information you provided to prepare a Terraform template to deploy the elastic pod in your GCP environment. Once it finishes, the button changes to Download Template.
9. Click **Download Template** to download a zip file containing the Terraform template, then unzip the file.

Open the readme file for more information how to run in order to create the elastic pod in your GCP environment.
10. Edit the terraform.tfvars file to update the GCP Project ID, Region and the Credentials JSON file location using the values you downloaded from the GCP Console.
11. Run the following commands to start the deployment:

```bash
terraform init;
terraform plan;
terraform apply
```

These commands deploy the control VM, the elastic pod infrastructure, and the application code. They also register back with Securiti.
12. Wait an hour, then check the **Settings > Deployments > Elastic Pods** page and the new elastic pod should be registered.

### Deleting an elastic pod

To completely remove an elastic pod and all resources linked to it:

1. If you haven't already done so, log into Securiti and open **Sensitive Data Intelligence** to the Overview dashboard.
2. Record the region and project that the elastic pod is deployed to.
3. Disconnect all data systems from the elastic pod.
4. Open **System Settings > Deployment > Elastic pods**, and delete the elastic pod.
5. On the GCP Console where the elastic pod was deployed, find the control VM for the pod.
6. Install your ssh key on the control VM and ssh to the VM.
7. Execute the following commands:

```bash
sudo su 
cd /opt/securiti
terraform show  (to ensure it is the correct VM and EDSS instance)
terraform destroy  (or terraform destroy -auto-approve) to destroy the EDSS infra
```

> [!NOTE]
> **Note**
> 
> - Ensure your laptop does not suspend or go on standby, since it takes time to destroy the instance.
> - When deleting a GCP elastic pod, ensure that any event-based hold enabled on the associated bucket is disabled before proceeding with the elastic pod destruction. If the event-based hold remains enabled, the cluster will be deleted, but the bucket will not be removed, and you will need to manually delete it. Disabling the hold in advance ensures a complete and seamless deletion process.
8. After the destroy is successful, exit the ssh session.
9. Go to the GCP console record the <random_id> that is assigned to the control VM name (for example "securiti-terraform-<random_id>-deployment-server".
10. After recording the random_id, delete the control VM:
  1. In IAM, disable the Service account and then delete it (searching by <random_id>).
  2. Go to the VPC network Console page and navigate to the Firewall section and delete the Firewall policy (again searching by <random_id>).
  3. In the VPC network Console page, navigate to the External IP addresses section and delete the External IP that was assigned to the Control VM.

Infrastructure as a Service is one of the three primary service models in cloud computing, alongside Platform as a Service (PaaS) and Software as a Service (SaaS). IaaS provides a virtualized computing infrastructure over the Internet, allowing organizations to rent and manage fundamental computing resources such as virtual machines, storage, and networking components on a pay-as-you-go basis.

An application running on a server or compute instance that connects with your on-premises or private data systems to:

- Intelligently scan them to classify content
- Identify personal data
- Upload hashed values of the personal data to your Securiti account
- Act as a hop-off point for DSR requests for your on-premises and user-defined data systems

The cloud term typically refers to cloud computing. Cloud computing is a technology that allows users to access and use computing resources and services over the internet, often from remote data centers.

## Related

- [Performing Actions Post GCP Instance Creation](/performing-actions-post-gcp-instance-creation.md)
- [Visualizing Results of Asset Discovery](/visualizing-results-of-gcp-asset-discovery.md)
- [Deploying Pod](/deploying-pod-gcp.md)
- [How it Works?](/how-it-works-gcp.md)
