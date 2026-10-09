---
title: "Pod quick install guides cluster version v1.28"
slug: "pod-quick-install-guides-cluster-version-v128-en"
updated: 2026-08-19T13:24:00Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/pod-quick-install-guides-cluster-version-v128-en"
stale: true
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Pod quick install guides cluster version v1.28

Use one of the processes below to quickly deploy a Securiti pod in one of several common IaaS services:

- If you just want to deploy a pod, and you are going to activate data system connectors on it later, deploy the pod from the [Deployments page](/latest/docs/pod-quick-install-guides-cluster-version-v128-en#from-the-deployments-page).
- If you want to deploy a pod to scan specific resources within an IaaS account, deploy the pod from [Sensitive Data Intelligence](/latest/docs/pod-quick-install-guides-cluster-version-v128-en#from-the-sensitive-data-intelligence-data-systems-overview-page).

## Pod deployment interactive demo

### Using Install Script method

To learn how to deploy the pod in your cloud infrastructure using Install Script method, watch the video below:

## From the Deployments page

Use this process to quickly deploy a Securiti pod in one of several common IaaS services. You can either create a new compute instance for the pod or install the pod software on an existing compute instance.

1. In Securiti, open **System Settings** and choose **Deployment > Pods**.
2. Near the top of the page, click **+ New Cluster**, and from the menu choose **Quick Install**.
3. On the **Add a Compute Pod for Discovery** popup, apply the following settings:

| Setting | Description |
| --- | --- |
| Cloud Provider | Choose the IaaS service where you want to deploy the pod. |
| Region | Choose the IaaS region in which you want to deploy the pod. |
| Compute Pod Name | Enter the name for your pod that appears on the application. |
| Worker Size | When selecting Download Template in Deployment Method, it creates the number of worker node virtual machines you enter in this field automatically, along with the master node. However, you must connect the worker nodes to the master node manually. You can add a minimum of 0 and a maximum of 5 numbers in it. To create more than 5 worker nodes, you must create the virtual machines manually. |
| Deployment method | Choose one of the following: - **Install Script** - If you want to use a CURL command to deploy the new pod on an existing compute instance. For more information, see [Deploy using Install Script](/latest/docs/pod-quick-install-guides-cluster-version-v128-en#deploy-using-install-script) below. - **Download Template** - If you want to use a CloudFormation or Terraform template to create a new compute instance and deploy the new pod on it. For more information, see [Deploy using template](/latest/docs/pod-quick-install-guides-cluster-version-v128-en#deploy-using-template) below. |

## Deploy using Install Script

To deploy using Install Script:

1. On the Add a **Compute Pod for Discovery** popup, mark the **Install Script** radio button, and then click **Generate Curl Command**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CF7VJ2LM.png)

1. Copy the CURL command.
2. Create a Virtual Machine (VM) in your cloud meeting [prerequisites](/latest/docs/pod-prerequisites-cluster-version-v128).
3. Access the machine via SSH and execute the CURL command on the terminal.

It deploys the pod completely.

## Deploy using template

To deploy using the template:

1. On the **Add a Compute Pod for Discovery** popup, mark the **Download Template** radio button, and then click **Prepare Template**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ select-­template-­podVM.png)

It prepares the template.

1. Once the template is prepared, click **Download Template** to download the template into your directory.
2. Deploy the template into your cloud environment.

**AWS**

To deploy the pod in AWS using template, proceed with the following procedure.

1. Log into your AWS account using the account with deployment permissions.
2. Using the services search bar, search **CloudFormation** service.
3. On the **CloudFormation** service page, choose **Create a new stack**.
4. On the equavelent page, apply the following settings:

| Parameter | Details |
| --- | --- |
| Prepare template | Select **Choose an existing template** |
| Template source | Select **Upload a template file** |
| Upload a template file | Upload your template file that you downloaded in previous steps. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pod-quick-install-guides-cluster-version-v1.28-en-image-vefbgz64.png)

It opens **Specify stack details** page and displays all the fields from the template file.
5. On the **Specify stack details** page, required parameters according to the node's requirements:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pod-quick-install-guides-cluster-version-v1.28-en-image-fky700fd.png)

> [!NOTE]
> Note
> 
> - For multi-node deployment using AWS, you must enter a number higher than zero in the Number of Worker Instances field to create the worker node VMs automatically. However, it creates empty VMs with no configurations.
> - When it creates new worker node VM instances, it also automatically connects them to your Master Node.
  - Stack name
  - Control VM Key Pair Name
  - Securiti Control VM CIDR to whitelist

### Pod template details for AWS

Expand the following accordion to see the list of all the fields present in the template file for AWS.

## Fields in AWS template file

While deploying the pod in the master node using the template, the following fields appear when you upload the template.

| Field name on AWS | Description |
| --- | --- |
| Stack name | It is the title of the pod VM that acts as the master node. Enter the convenient Stack name. |
| Stack Slug | It is a replacement for the Stack name to select an easier name. It acts the same as the actual name, but must start with Securiti. |
| Unique ID | It is the unique identifier of the stack. > [!WARNING] > Warning > > Do not modify the Unique ID value. |
| DisableLambdaCallback | It is the setting to disable the Securiti AWS Lambda Callback. Set to true only if you want to run manual commands. |
| (Optional) Owner Tag | It is the owner's information about the stack. Enter a string to identify the owner. |
| Number of Worker Instances | It is compulsory for a multi-node environment. It is the number of worker nodes in the AutoScaling Group. - For single-node deployment, set 0 for master only. - For Multinode deployment, enter a number greater than 0 to create empty VMs with no configuration for worker nodes. |
| EnvironmentType | It is the environment type of the stack. From the menu, update as per your requirement. |
| Securiti Endpoint for Pod registration | It is the Securiti endpoint URL for pod registration. Enter the correct Securiti URL as per your cloud region. |
| Securiti Control VM AMI ID | It is the Amazon Machine Image (AMI) ID for the control VM. |
| Control VM Key Pair Name | It is the EC2 key pair name for SSH access to the control VM. Select an existing key pair from the selected region. |
| Signed URL for App Install | It is the signed URL for downloading and installing the application. |
| Securiti Pod Token | It is the token for pod authentication. Do not change this value. |
| CallbackId | It is the callback ID for Securiti apps. Do not change this value. |
| (Optional) Securiti Control VM CIDR to whitelist | It is the CIDR range that needs SSH access to the pod VM. Enter the required CIDR block. You can skip it and apply your own security rule. See the example below. `142.176.32.16/32` |
| Securiti Control VM IAM Role Name Prefix | It is the IAM role name prefix used by the pod and Management Cloud during launch. |
| Pod Asset Discovery Master Role Prefix | It is the IAM role name prefix for the Asset Discovery Master Role used by Management Cloud. |
| Pod Connector Scan Master Role Prefix | It is the IAM role name prefix for the Connector Scan Master Role used by the pod. |
| Pod Connector Scan Member Role Prefix | It is the IAM role name prefix for the Connector Scan Member Role used by the pod. |
| Custom Tag Param | It is the parameter to add custom tags to the stack. Enter key–value pairs to identify or organize resources. |
| PodVPCId | It defines the network boundary where the entire Pod deployment (master VM, worker ASG, and security group if created) runs. The system scopes all resources to this VPC. |
| (Optional) PodVMSecurityGroupId | It controls inbound and outbound traffic rules for the Pod VMs. - If you leave it empty, the system automatically creates a new Security Group (CreateSecurityGroup condition). The security group allows all intra-subnet traffic (PodVMSubnetCIDR). - If you provide a value, the system reuses the existing Security Group (UseExistingSecurityGroup condition). The existing Security Group must already allow all traffic within the subnet CIDR for pod-to-pod communication. |
| PodVMSubnetID | It specifies the subnet (availability zone) where the system launches the master EC2 instance and worker Auto Scaling Group instances. |
| PodVMSubnetCIDR | The system uses this value only when it creates a new Security Group (that is, when PodVMSecurityGroupId is empty). It configures the ingress rule to allow all traffic (IpProtocol: -1) from within the subnet CIDR. This rule ensures proper communication between the master and worker nodes. |
| (Optional) PodVMKeyPairName | It assigns an SSH key pair to the VM and worker Launch Template so operators can SSH into instances for debugging or administration. |
| (Optional) PodVMSSHCIDR | It specifies the CIDR range allowed to access the Pod VMs through SSH. |

**Azure**

To deploy the pod in Azure using template, proceed with the following procedure.

### Prerequisites

Before deploying the pod in Azure, make sure you have the following:

- Terraform CLI installation on your machine
- An Azure account with an Azure Active Directory (Azure AD) tenant
- An Azure subscription without tight quota caps
- Azure portal access with permissions to create an application and service principal
- Client credentials

> [!NOTE]
> Note
> 
> If you do not already have client credentials, see **Generate a client secret** heading below.

### Set up a service principal

A service principal is a security principal within Azure Active Directory that lets you grant permissions to manage Azure resources. To authenticate with a service principal, you must create an application object within Azure Active Directory.

To create the application and service principal, proceed with the following steps:

1. In the Azure portal, log in with an administrative privileged account.
2. From **Azure Services** section, select **Azure Active Directory**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-3WRC2E78.png)

1. From the left sidebar, under **Manage**, click **App registrations**.
2. On the **App registration** page, at the top of the page, click **+ New registration**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KGGKIQET.png)

1. On the **Register an application** page, apply the following settings:

| Settings | Description |
| --- | --- |
| Name | Enter an identifier for the application, for example, "Securiti Terraform". |
| Supported account types | From the options, choose **Accounts in this organizational directory only (Default directory only - single tenant)**. |
| (Optional) Redirect URI | Choose **Web** as the URI type. It returns an authentication response to this URI after successfully authenticating the user. At this point, you could leave the web URI field as empty. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-LL82EUKJ.png)

### Generate a client secret

To generate a client secret for the application:

1. On the **App** page, under **Manage**, click **Certificates & secrets**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XJA5PR0Z.png)
2. On the **App | Certificates & secrets** page, click **+ New client secret**.
3. On the **Add a client secret** popup, add the following details:

| Parameters | Description |
| --- | --- |
| Description | Add the description for the client secret |
| Expires | Add the expiry days when this secret expires |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/final_pod_azure_deployment_guide-image-vyx6sf7s.png)
4. Copy the **client_secret** value and save it as Azure displays it only once.

## Assign a role to the application

To assign a role to the application from Subscription Access Control (IAM):

1. In the Azure Portal, open **Subscriptions** and select the subscription where you are creating the resources.
2. From the left sidebar, click **Access Control (IAM)**.
3. Near the top of the page, click **+ Add** and choose **Add role assignment**.
4. Choose a role with read/write permissions, such as **Owner** or **Contributor**. Securiti recommends that you create a custom role with the minimum permissions listed below.
5. On the **Members** tab, search for and select your application.
6. Click **Review + assign**.

## Minimum permissions for a custom role

While deploying the pod using the template, the following fields appear when you apply the minimum permissions for the custom role.

| **Permission** | **Description** |
| --- | --- |
| Microsoft.Authorization/*/read | Reads authorization resources. |
| Microsoft.ClassicCompute/domainNames/* | Manages classic compute domain names. |
| Microsoft.ClassicCompute/virtualMachines/* | Manages classic virtual machines. |
| Microsoft.ClassicNetwork/reservedIps/link/action | Links reserved IPs. |
| Microsoft.ClassicNetwork/reservedIps/read | Reads reserved IPs. |
| Microsoft.ClassicNetwork/virtualNetworks/join/action | Joins classic virtual networks. |
| Microsoft.ClassicNetwork/virtualNetworks/read | Reads classic virtual networks. |
| Microsoft.ClassicStorage/storageAccounts/disks/read | Reads classic storage account disks. |
| Microsoft.ClassicStorage/storageAccounts/images/read | Reads classic storage account images. |
| Microsoft.ClassicStorage/storageAccounts/listKeys/action | Lists classic storage account keys. |
| Microsoft.ClassicStorage/storageAccounts/read | Reads classic storage accounts. |
| Microsoft.Insights/alertRules/* | Manages alert rules. |
| Microsoft.ResourceHealth/availabilityStatuses/read | Reads resource health availability statuses. |
| Microsoft.Resources/deployments/* | Manages resource deployments. |
| Microsoft.Resources/subscriptions/resourceGroups/read | Reads resource groups. |
| Microsoft.Resources/subscriptions/resourceGroups/write | Creates and updates resource groups. |
| Microsoft.Resources/subscriptions/resourceGroups/delete | Deletes resource groups. |
| Microsoft.Support/* | Manages support tickets. |
| Microsoft.Network/virtualNetworks/read | Reads virtual networks. |
| Microsoft.Network/virtualNetworks/write | Creates and updates virtual networks. |
| Microsoft.Network/virtualNetworks/delete | Deletes virtual networks. |
| Microsoft.Network/virtualNetworks/subnets/read | Reads subnets. |
| Microsoft.Network/virtualNetworks/subnets/write | Creates and updates subnets. |
| Microsoft.Network/virtualNetworks/subnets/delete | Deletes subnets. |
| Microsoft.Network/virtualNetworks/subnets/join/action | Joins subnets. |
| Microsoft.Network/publicIPAddresses/read | Reads public IP addresses. |
| Microsoft.Network/publicIPAddresses/write | Creates and updates public IP addresses. |
| Microsoft.Network/publicIPAddresses/delete | Deletes public IP addresses. |
| Microsoft.Network/publicIPAddresses/join/action | Joins public IP addresses. |
| Microsoft.Network/networkInterfaces/read | Reads network interfaces. |
| Microsoft.Network/networkInterfaces/write | Creates and updates network interfaces. |
| Microsoft.Network/networkInterfaces/delete | Deletes network interfaces. |
| Microsoft.Network/networkInterfaces/join/action | Joins network interfaces. |
| Microsoft.Network/networkSecurityGroups/* | Manages network security groups. |
| Microsoft.Compute/virtualMachines/read | Reads virtual machines. |
| Microsoft.Compute/virtualMachines/write | Creates and updates virtual machines. |
| Microsoft.Compute/virtualMachines/delete | Deletes virtual machines. |
| Microsoft.Compute/virtualMachines/powerOff/action | Powers off virtual machines. |
| Microsoft.Compute/disks/read | Reads managed disks. |
| Microsoft.Compute/disks/write | Creates and updates managed disks. |
| Microsoft.Compute/disks/delete | Deletes managed disks. |

### Update Terraform file

Before applying the Terraform file, proceed with the following steps:

1. Update the following values in your Terraform template:

| Variable | Description |
| --- | --- |
| subscription_id | Find the ID from the Subscriptions blade in the Azure Portal. |
| tenant_id | Find the ID from the Azure Active Directory blade. |
| client_id | Find the ID from the App registrations page for the application you created. |
| client_secret | Find the secret from the Certificates & secrets tab of your application. |
| create_custom_resource_group / custom_resource_group_name | If set to true, you must specify the name of the resource group. |
| pod_name | Enter a prefix for the pod resources. |
| vm_size | Enter the size of the virtual machine. The default value is Standard_D8s_v3. |

1. In your **hybrid-cloud-vm-user-data.yaml** file, update **ssh-authorized-keys** with your virtual machine's public SSH key to access the virtual machine through SSH where you are deploying the pod.
2. On your virtual machine, run the following commands:

```shell
terraform init
terraform plan
terraform apply
```
3. Once you finalize the details, it deploys the template. During deployment, it creates the following Azure resources in the pod resource group:

- Network interface
- Network security group
- OS disk
- Public IP address
- Virtual machine
- Virtual network

## Verify the deployment

Once Terraform finishes, the terminal displays **Apply complete!** message along with the VM’s IP addresses. This indicates that the infrastructure is successfully deployed.

To verify the pod application running inside the virtual machine:

1. Connect to the VM via SSH:
2. View the pod installation logs:

```bash
cat /mnt/appliance.log
```

1. Wait 30-40 minutes for the pod installation to complete, then confirm the pods are running:

```bash
sudo kubectl get pods -A
```
2. Verify the deployment from the Azure portal by viewing events for more information.

Once the pod connects to the Securiti application, it appears green on the interface.

When you deploy the pod, it performs the following actions:

- In the case of a single node:
  - It deploys the pod and connects it to Securiti application.
  - Once the pod is connected to Securiti application, it appears green on the interface.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-WCJZ2DG8.png)
- In the case of a multi-node cluster:

You must configure the worker nodes after the master node is active on the UI. For more information, see [Adding secondary nodes](/latest/docs/pods-adding-secondary-nodes-cluster-version-v128).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/pod-quick-install-guides-cluster-version-v1.28-en-image-v2443j98.png)
  - It deploys the Securiti pod as the master node.
  - In addition, it creates the same number of empty worker node VMs defined in the **Number of Worker Instances** field for the AWS template.

If the pod you created does not meet the hardware resources baseline, it displays a warning banner at the following locations at **Pods** page:

1. A warning banner in red color above the pod name, if master node or any of the worker node is under-provisioned.
2. A yellow alert icon with the node is that specific node is under-provisioned. Hovering over the yellow alert icon displays the specific hardware that is under-provisioned.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-DI2TTVPC.png)

## From the Sensitive Data Intelligence data systems overview page

Use this process to quickly deploy a Securiti pod in one of several common IaaS services to connect with and scan resources within the IaaS service.

1. In Securiti, open **Sensitive Data Intelligence** to the **Data Systems Overview** page.
2. On the Data Systems tab, mark the checkboxes for one or more data systems of the same Cloud / Type and within the same region. Once you mark the first checkbox, Securiti only lets you choose additional data systems of the same Cloud / Type and within the same region.
3. Near the upper right corner of the table of data systems, click **Connect Data System**.
4. On the **Add or Select a Compute Pod for Discovery** popup, apply the following settings:

| Setting | Description |
| --- | --- |
| New Pod | Mark this checkbox to deploy a new pod, instead of connecting to the data systems with an existing pod. |
| Cloud Provider | Choose the IaaS service where you want to deploy the pod. This setting defaults to the IaaS services of the selected data systems. |
| Deployment Types | Choose **Pod**. If you want to deploy an elastic pod, see [Elastic Pod V2](/latest/docs/elastic-pods-v2). |
| Compute pod name | Leave as-is, or edit to suit with a convenient name for the pod. |
| Region | Choose the IaaS region in which you want to deploy the pod. |

1. Do one of the following:
  - To quickly deploy a pod using default clickthrough settings, click one of the following, depending on the IaaS service, and follow the prompts to deploy the pod.

| For this IaaS service: | Click this: |
| --- | --- |
| AWS | **Connect** |
| Azure | **Connect** |
| GCP | **Sign in with Google** |
| OCI | **Connect** |
  - To use a CloudFormation or Terraform template to create a new compute instance and deploy the new pod on it:
    1. In the **Advanced Mode** area, click **Prepare Template** and then **Download Template** to download the template to your downloads folder.
    2. In the IaaS console, use the CloudFormation or Terraform tools to create a new stack from the template, specify any necessary stack details, and then proceed to deploy the stack.

##

## Related

- [Pod custom installation guides (cluster version v1.28+)](/podcustom-installation-guides.md)
- [Backing up and restoring pods](/backing-up-and-restoring-pod.md)
- [Upgrading pods cluster version](/upgrading-pods-cluster-version.md)
- [Updating pod software (cluster version v1.28+)](/pod-updating-pod-software.md)
