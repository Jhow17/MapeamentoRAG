---
title: "Amazon Services"
slug: "amazon-services"
updated: 2026-06-24T10:52:17Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/amazon-services"
stale: true
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Amazon Services

This section describes the Data Access Governance features supported for Amazon Services and the steps to configure these functionalities. The following is a list of Amazon Services that are supported for Data Access Governance features:

- Amazon S3
- Amazon Bedrock
- Amazon DynamoDb
- Amazon Redshift Cluster
- Amazon MSK (Amazon Managed Streaming for Apache Kafka)
- Amazon RDS Instance

### Supported Data Access Governance Feature Sets for Amazon S3

Following is the list of the features supported for Amazon S3:

### Access Intelligence

- Privilege Analysis
  - Bucket level Permissions Granularity
- Activity Analysis - Not Supported

#### Access Control

- Not supported

#### Cross Border Transfer Policies

- Supported (Based on Data Location)

#### Example Supported Use Cases

The supported example use cases include:

#### Access Intelligence

- Identify and report on which AWS Users have access to S3 Buckets and what their permissions are on those buckets.
- Identify and report on which AWS Users have access to S3 Buckets that contain files with sensitive data in them.

#### Prerequisites

To see the Amazon S3 access intelligence data on the dashboard you must:

- [Configure and Activate the connector.](/v1/docs/creating-an-aws-iaas-instance-version-1111-and-later)
- Mark the **Discover Access Entitlements** checkbox to gain intelligence into users and roles with access to resources and sensitive data.
- Perform asset discovery. The asset discovery is enabled by default when you configure an Amazon IaaS connector. All these IAM permissions, policies & roles described here will be deployed automatically along with the IaaS connector based on the deployment type. For Amazon Cloud Formation template deployment, the following policies will be attached to the role or user depending on the authentication type:
  - SecurityAudit
  - AmazonInspector2ReadOnlyAccess
  - AmazonGlacierReadOnlyAccess
  - AmazonDocDBElasticReadOnlyAccess
  - AmazonBedrockReadOnly

#### Using Access Intelligence with Amazon S3

Below are example use cases to familiarize you with how to leverage our Data Command Graph to identify access and risk in your Amazon's tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

#### Identifying AWS Users have access to S3 Buckets and what their permissions are on those buckets using Identity Graph Explorer

To identify the users with Access to Amazon S3 Buckets:

1. In Securiti, open **Data Access Governance** and choose **Access Intelligence** to access the dashboard.
2. Near the upper right corner of the page, click the **Identity Graph Explorer** button.
3. Navigate to the **Saved Views** panel on the left side of the page.
4. On the **Popular Views** tab, navigate to the **S3 Queries** area. You can see the queries that help you perform privilege analysis for your Amazon S3 Buckets.
5. Click on the query **AWS IAM Users with any access to S3 Buckets**. Click on the User Principal node to see the users in the data grid.

#### Identifying AWS Users have access to S3 Buckets that contain files with sensitive data in them using Identity Graph Explorer

To identify the users with Access to Amazon S3 Buckets containing files with sensitive data elements:

1. In Securiti, open **Data Access Governance** and choose **Access Intelligence** to access the dashboard.
2. Near the upper right corner of the page, click the **Identity Graph Explorer** button.
3. Click + button on the top left corner.
4. Select **User Principal** node. Click three dot buttons on the node in the query area, and select **+ Add Property**.
5. Click **Provider Type**. Select **Amazon Web Services**.
6. Click three dots available with the User Principal node. Select **Add Relationship**.
7. Select **Policy Element** node from the list of Entities. Add relationship with the **Resource Scope** Node.
8. Click three dots available with the Resource Scope node. Select **Add Relationship**.
9. Select **Data System** node. Add relationship of the Data System node with **Files** node.
10. Add relationship of the **Files** node with the **Data Element** node.
11. Click three dots available on the **Data Element** node in the query area. Click **+ Add Property**. Select **Non Personal Sensitive Data** from the list of properties. Select the **Equals** operator. Select the **True** option.

![Dag_AWS_S3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1e210115-7c43-bae4-929f-31eb54c81d93.png)
12. Click on the **User Principal** node to see the list of users.

#### Reporting

#### The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/v1/docs/using-graph-reporting-dashboards). Interactive Demo

To see similar steps in action through Access Graph Explorer or Data Command Graph , watch the videos below: **With Access Graph Explorer**

[Embedded content](https://app.storylane.io/demo/e4uagldkle6a?embed=inline)

**With Data Command Graph**

[Embedded content](https://app.storylane.io/demo/va1b2bfdmdpd?embed=inline)

### Supported Data Access Governance Feature Sets for Amazon Bedrock

Following is the list of the features supported for Amazon Bedrock:

### Access Intelligence

- Privilege Analysis - Private Preview
- Activity Analysis - Not Supported

#### Access Control

- Not supported

#### Cross Border Transfer Policies

- Not Supported

#### Example Supported Use Cases

The supported example use cases include:

#### Access Intelligence

- Identify and report on which AWS Users have access to AWS Bedrock AI models and what their privileges are on those models.
- Identify and report on which Roles have access to AWS Bedrock Agents and their associated privileges.

#### Prerequisites

To see the Amazon Bedrock access intelligence data on the dashboard you must:

- [Configure and Activate the connector.](/v1/docs/creating-an-aws-iaas-instance-version-1111-and-later)
- Mark the **Discover Access Entitlements** checkbox to gain intelligence into users and roles with access to resources and sensitive data.

![Access_Entitlements.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bf678800-b2ce-2c8d-5468-0d06cf1507a2.png)
- Perform asset discovery. The asset discovery is enabled by default when you configure an Amazon IaaS connector. All these IAM permissions, policies & roles described here will be deployed automatically along with the IaaS connector based on the deployment type. For Amazon Cloud Formation template deployment, the following policies will be attached to the role or user depending on the authentication type:
  - SecurityAudit
  - AmazonInspector2ReadOnlyAccess
  - AmazonGlacierReadOnlyAccess
  - AmazonDocDBElasticReadOnlyAccess
  - AmazonBedrockReadOnly

#### Using Access Intelligence with Amazon Bedrock

Below are example use cases to familiarize you with how to leverage our Data Command Graph to identify access and risk in your Amazon's tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

#### Identify and report on which AWS Users have access to AWS Bedrock AI models and what their privileges are on those models.

To identify the users with Access to AWS Bedrock AI models:

1. In Securiti, open **Data Access Governance** and choose **Access Intelligence** to access the dashboard.
2. Near the upper right corner of the page, click the **Identity Graph Explorer** button.
3. Near the upper left corner of the page, click **+** to open the filter. From the list of Entities, select **User Principal** in the Access Intelligence category. Click three dots with the **User Principal** Entity, and select **+ Add Property**. From the list of Properties, choose **Provider Type**. Select **Amazon Web Services**. Click **Apply**.
4. Click three dots with the query, and select **Add Relationship**. Select **Policy Element**. Click three dots with the Policy Element Entity, and select **Add Relationship**. Choose the **Resource Scope** Entity.
5. Add the relationship of the **Resource Scope** Entity with the **AI Model**. Click three dots with the **AI Model** entity, and select **+ Add Property**. Choose **Asset Type** property. Enter **Bedrock Titan Model**. You can add the name of the Model for which you must identify the access. Click **Apply**.

![Bedrock_Titan_Model.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ce0b2dc1-a2e9-6152-d6a5-edcfa8d66383.png)
6. Click on the User Principal Node to see the list of AWS Users that have access to the Bedrock Titan Model.

![Users_access_to_Titan_Model.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3865ae6e-e192-c9e1-0d9a-7139fcf4c503.png)

#### Identify and report on which Roles have access to AWS Bedrock Agents and their associated privileges.

To identify the Roles with Access to AWS Bedrock Agents:

1. In Securiti, open **Data Access Governance** and choose **Access Intelligence** to access the dashboard.
2. Near the upper right corner of the page, click the **Identity Graph Explorer** button.
3. Near the upper left corner of the page, click **+** to open the filter. From the list of Entities, select **Role** in the Access Intelligence category. Click three dots with the **Role** Entity.
4. Click three dots with the Role Entity in the query area, and select **Add Relationship**. Select **Policy Element**. Click three dots with the Policy Element Entity, and select **Add Relationship**. Choose the **Resource Scope** Entity.
5. Add the relationship of the **Resource Scope** Entity with the **AI Agent**. Click three dots with the **AI Agent** entity, and select **+ Add Property**. Choose **Asset Type** property. Enter **AWS Bedrock Agent**. Click **Apply**.

![Bedrock_Titan_Model.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ce0b2dc1-a2e9-6152-d6a5-edcfa8d66383.png)

![AWS_Bedrock_Agent_Access.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-67cef26c-b770-d203-2699-5beeab40ce3b.png)
6. Click on the User Principal Node to see the list of AWS Users that have access to the AWS Bedrock Agents.
7. Click on the Policy Element Node to see the privileges

#### Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/v1/docs/using-graph-reporting-dashboards).

### Supported Data Access Governance Feature Sets for Amazon DynamoDb

Following is the list of the features supported for Amazon DynamoDb:

### Access Intelligence

- Privilege Analysis - Private Preview
- Activity Analysis - Not Supported

#### Access Control

- Not supported

#### Cross Border Transfer Policies

- Not Supported

#### Example Supported Use Cases

The supported example use cases include:

#### Access Intelligence

- Identify and report on which AWS Users have access to Amazon DynamoDb resources and what their permissions are on those resources.
- Identify and report on which AWS Roles have access to Amazon DynamoDb resources and what their permissions are on those resources.

#### Prerequisites

To see the Amazon DynamoDb access intelligence data on the dashboard you must:

- [Configure and Activate the connector.](/v1/docs/creating-an-aws-iaas-instance-version-1111-and-later)
- Mark the **Discover Access Entitlements** checkbox to gain intelligence into users and roles with access to resources and sensitive data.
- Perform asset discovery. The asset discovery is enabled by default when you configure an Amazon IaaS connector. All these IAM permissions, policies & roles described here will be deployed automatically along with the IaaS connector based on the deployment type. For Amazon Cloud Formation template deployment, the following policies will be attached to the role or user depending on the authentication type:
  - SecurityAudit
  - AmazonInspector2ReadOnlyAccess
  - AmazonGlacierReadOnlyAccess
  - AmazonDocDBElasticReadOnlyAccess
  - AmazonBedrockReadOnly

#### Using Access Intelligence with Amazon DynamoDb

Below are example use cases to familiarize you with how to leverage our Data Command Graph to identify access and risk in your Amazon's tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

#### Identify and report on which AWS Users have access to Amazon DynamoDb resources and what their permissions are on those resources.

To identify the users with access to Amazon DynamoDb:

1. In Securiti, open **Data Access Governance** and choose **Access Intelligence** to access the dashboard.
2. Near the upper right corner of the page, click the **Identity Graph Explorer** button.
3. Near the upper left corner of the page, click **+** to open the filter. From the list of Entities, select **User Principal** in the Access Intelligence category.
4. Click three dots with the query, and select **Add Relationship**. Select **Policy Element**. Click three dots with the Policy Element Entity, and select **Add Relationship**. Choose the **Policy Object** Entity.
5. Click three dots with the **Policy Element** node, and select **Add Relationship**. Select **Resource Scope**.
6. Add relationship of **Resource Scope** node with **Data System** node. Click three dots with the **Data System** entity, and select **+ Add Property**. Choose **Asset Type** property. Select **Amazon DynamoDb - Self-Hosted**. Click **Apply**.

![DAG_DynsmoDB.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-48873674-c33e-2ddd-f01a-b85a2a9fb83a.png)
7. Click on the User Principal Node to see the list of AWS Users that have access to the DynamoDb resources.

#### Identify and report on which AWS Roles have access to Amazon DynamoDb resources and what their permissions are on those resources.

To identify the roles with access to Amazon DynamoDb resources:

1. In Securiti, open **Data Access Governance** and choose **Access Intelligence** to access the dashboard.
2. Near the upper right corner of the page, click the **Identity Graph Explorer** button.
3. Near the upper left corner of the page, click **+** to open the filter. From the list of Entities, select **Role** in the Access Intelligence category.
4. Click three dots with the query, and select **Add Relationship**. Select **Policy Element**. Click three dots with the Policy Element Entity, and select **Add Relationship**. Choose the **Policy Object** Entity.
5. Click three dots with the **Policy Element** node, and select **Add Relationship**. Select **Resource Scope**.
6. Add relationship of **Resource Scope** node with **Data System** node. Click three dots with the **Data System** entity, and select **+ Add Property**. Choose **Asset Type** property. Select **Amazon DynamoDb - Self-Hosted**. Click **Apply**.

![DAG_DynamoDB_Role.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e58f0bf0-7a75-353a-1fc4-155abdd0e357.png)
7. Click on the Role Node to see the list of AWS Users that have access to the DynamoDb resources.

#### Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/v1/docs/using-graph-reporting-dashboards).

### Supported Data Access Governance Feature Sets for Amazon Redshift Cluster

Following is the list of the features supported for Amazon RedShift Cluster:

### Access Intelligence

- Privilege Analysis - Private Preview
- Activity Analysis - Not Supported

#### Access Control

- Not supported

#### Cross Border Transfer Policies

- Not Supported

#### Example Supported Use Cases

The supported example use cases include:

#### Access Intelligence

- Identify and report on which AWS Users have access to Amazon Redshift Cluster resources and what their permissions are on those resources.
- Identify and report on which AWS Roles have access to Amazon Redshift Cluster resources and what their permissions are on those resources.

#### Prerequisites

To see the Amazon Redshift Cluster access intelligence data on the dashboard you must:

- [Configure and Activate the connector.](/v1/docs/creating-an-aws-iaas-instance-version-1111-and-later)
- Mark the **Discover Access Entitlements** checkbox to gain intelligence into users and roles with access to resources and sensitive data.
- Perform asset discovery. The asset discovery is enabled by default when you configure an Amazon IaaS connector. All these IAM permissions, policies & roles described here will be deployed automatically along with the IaaS connector based on the deployment type. For Amazon Cloud Formation template deployment, the following policies will be attached to the role or user depending on the authentication type:
  - SecurityAudit
  - AmazonInspector2ReadOnlyAccess
  - AmazonGlacierReadOnlyAccess
  - AmazonDocDBElasticReadOnlyAccess
  - AmazonBedrockReadOnly

#### Using Access Intelligence with Amazon Redshift Cluster

Below are example use cases to familiarize you with how to leverage our Data Command Graph to identify access and risk in your Amazon's tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

#### Identify and report on which AWS Users have access to Amazon Redshift Cluster resources and what their permissions are on those resources.

To identify the users with access to Amazon Redshift Cluster:

1. In Securiti, open **Data Access Governance** and choose **Access Intelligence** to access the dashboard.
2. Near the upper right corner of the page, click the **Identity Graph Explorer** button.
3. Near the upper left corner of the page, click **+** to open the filter. From the list of Entities, select **User Principal** in the Access Intelligence category.
4. Click three dots with the query, and select **Add Relationship**. Select **Policy Element**. Click three dots with the Policy Element Entity, and select **Add Relationship**. Choose the **Policy Object** Entity.
5. Click three dots with the **Policy Element** node, and select **Add Relationship**. Select **Resource Scope**. Add the **Resource Scope ID** Property, and specify the Resource Scope ID Redshift Cluster.
6. Add relationship of **Resource Scope** node with **Data System** node. Click three dots with the **Data System** entity.
7. Click on the User Principal Node to see the list of AWS Users that have access to the Redshift resources.

#### Identify and report on which AWS Roles have access to Amazon Redshift Cluster resources and what their permissions are on those resources.

To identify the roles with access to Amazon Redshift Cluster resources:

1. In Securiti, open **Data Access Governance** and choose **Access Intelligence** to access the dashboard.
2. Near the upper right corner of the page, click the **Identity Graph Explorer** button.
3. Near the upper left corner of the page, click **+** to open the filter. From the list of Entities, select **User Principal** in the Access Intelligence category.
4. Click three dots with the query, and select **Add Relationship**. Select **Policy Element**. Click three dots with the Policy Element Entity, and select **Add Relationship**. Choose the **Policy Object** Entity.
5. Click three dots with the **Policy Element** node, and select **Add Relationship**. Select **Resource Scope**. Add the **Resource Scope ID** Property, and specify the Resource Scope ID Redshift Cluster.
6. Add relationship of **Resource Scope** node with **Data System** node. Click three dots with the **Data System** entity.
7. Click on the Role Node to see the list of AWS Roles that have access to the Redshift resources.

#### Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/v1/docs/using-graph-reporting-dashboards).

### Supported Data Access Governance Feature Sets for Amazon MSK (Amazon Managed Streaming for Apache Kafka) Cluster

Following is the list of the features supported for Amazon MSK Cluster:

### Access Intelligence

- Privilege Analysis - Private Preview
- Activity Analysis - Not Supported

#### Access Control

- Not supported

#### Cross Border Transfer Policies

- Not Supported

#### Example Supported Use Cases

The supported example use cases include:

#### Access Intelligence

- Identify and report on which AWS Users have access to Amazon MSK Cluster resources and what their permissions are on those resources.
- Identify and report on which AWS Roles have access to Amazon MSK Cluster resources and what their permissions are on those resources.

#### Prerequisites

To see the Amazon MSK Cluster access intelligence data on the dashboard you must:

- [Configure and Activate the connector.](/v1/docs/creating-an-aws-iaas-instance-version-1111-and-later)
- Mark the **Discover Access Entitlements** checkbox to gain intelligence into users and roles with access to resources and sensitive data.
- Perform asset discovery. The asset discovery is enabled by default when you configure an Amazon IaaS connector. All these IAM permissions, policies & roles described here will be deployed automatically along with the IaaS connector based on the deployment type. For Amazon Cloud Formation template deployment, the following policies will be attached to the role or user depending on the authentication type:
  - SecurityAudit
  - AmazonInspector2ReadOnlyAccess
  - AmazonGlacierReadOnlyAccess
  - AmazonDocDBElasticReadOnlyAccess
  - AmazonBedrockReadOnly

#### Using Access Intelligence with Amazon MSK Cluster

Below are example use cases to familiarize you with how to leverage our Data Command Graph to identify access and risk in your Amazon's tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

#### Identify and report on which AWS Users have access to Amazon MSK Cluster resources and what their permissions are on those resources.

To identify the users with access to Amazon MSK Cluster:

1. In Securiti, open **Data Access Governance** and choose **Access Intelligence** to access the dashboard.
2. Near the upper right corner of the page, click the **Identity Graph Explorer** button.
3. Near the upper left corner of the page, click **+** to open the filter. From the list of Entities, select **User Principal** in the Access Intelligence category.
4. Click three dots with the query, and select **Add Relationship**. Select **Policy Element**. Click three dots with the Policy Element Entity, and select **Add Relationship**. Choose the **Policy Object** Entity.
5. Click three dots with the **Policy Element** node, and select **Add Relationship**. Select **Resource Scope**.
6. Add relationship of **Resource Scope** node with **Data System** node. Click three dots with the **Data System** entity. Select **+ Add Property**. Choose **Asset Type** property. Select **Amazon MSK - Self-Hosted**. Click **Apply**.
7. Click on the User Principal Node to see the list of AWS Users that have access to the MSK Cluster resources.

#### Identify and report on which AWS Roles have access to Amazon MSK Cluster resources and what their permissions are on those resources.

To identify the roles with access to Amazon MSK Cluster resources:

1. In Securiti, open **Data Access Governance** and choose **Access Intelligence** to access the dashboard.
2. Near the upper right corner of the page, click the **Identity Graph Explorer** button.
3. Near the upper left corner of the page, click **+** to open the filter. From the list of Entities, select **Role** in the Access Intelligence category.
4. Click three dots with the query, and select **Add Relationship**. Select **Policy Element**. Click three dots with the Policy Element Entity, and select **Add Relationship**. Choose the **Policy Object** Entity.
5. Click three dots with the **Policy Element** node, and select **Add Relationship**. Select **Resource Scope**.
6. Add relationship of **Resource Scope** node with **Data System** node. Click three dots with the **Data System** entity. Select **+ Add Property**. Choose **Asset Type** property. Select **Amazon MSK - Self-Hosted**. Click **Apply**.

![MSK_Roles.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-49a08c45-3db7-9102-c77d-8bc72113003f.png)
7. Click on the Role Node to see the list of AWS Roles that have access to the MSK Cluster resources.

![MSK_Role_Node.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2d7e5feb-5d3c-93fe-eeda-a086c5333a33.png)

#### Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/v1/docs/using-graph-reporting-dashboards).

### Supported Data Access Governance Feature Sets for Amazon RDS Instance

Following is the list of the features supported for Amazon RDS Instance:

### Access Intelligence

- Privilege Analysis - Private Preview
- Activity Analysis - Not Supported

#### Access Control

- Not supported

#### Cross Border Transfer Policies

- Supported (Based on Data Location)

#### Example Supported Use Cases

The supported example use cases include:

#### Access Intelligence

- Identify and report on which AWS policies have been applied on the RDS Instance that was a part of Cluster.
- Identify and report on which AWS Roles have access to Standalone RDS Instance resource.

> [!NOTE]
> **Note**
> 
> - An RDS cluster appears under **Database Cluster** and **Data System**, while its RDS instances appear under **DB Cluster nodes.**
> - A standalone RDS instance appears directly under **Database Cluster** and **Data System** nodes.

#### Prerequisites

To see the Amazon RDS Instance access intelligence data on the dashboard you must:

- [Configure and Activate the connector.](/v1/docs/creating-an-aws-iaas-instance-version-1111-and-later)
- Mark the **Discover Access Entitlements** checkbox to gain intelligence into users and roles with access to resources and sensitive data.
- Perform asset discovery. The asset discovery is enabled by default when you configure an Amazon IaaS connector. All these IAM permissions, policies & roles described here will be deployed automatically along with the IaaS connector based on the deployment type. For Amazon Cloud Formation template deployment, the following policies will be attached to the role or user depending on the authentication type:
  - SecurityAudit
  - AmazonInspector2ReadOnlyAccess
  - AmazonGlacierReadOnlyAccess
  - AmazonDocDBElasticReadOnlyAccess
  - AmazonBedrockReadOnly

#### Using Access Intelligence with Amazon RDS Instance

Below are example use cases to familiarize you with how to leverage our Data Command Graph to identify access and risk in your Amazon's tenant using Securiti’s Privilege Analysis feature set. When you filter in the Data Command Graph, all of the associated tables on the graph update with your filtered results.

#### Identify and report on which AWS policies have been applied on the RDS Instance that was a part of Cluster.

To identify the users with access to Amazon RDS Instance:

1. In Securiti, open **Data Access Governance** and choose **Access Intelligence** to access the dashboard.
2. Near the upper right corner of the page, click the **Identity Graph Explorer** button.
3. Near the upper left corner of the page, click **+** to open the filter. From the list of Entities, select **DB Cluster Nodes**. A standalone RDS instance appears directly under **Database Cluster** and **Data System**.
4. Click three dots with the query, and select **Add Relationship**. Select **Resource Scope**. Click three dots with the Resource Scope Node, and select **Add Relationship**. Choose the **Policy Element** Entity.
5. Click three dots with the **Policy Element** node, and select **Add Relationship**. Select **Policy Object**.

![DAG_RDS_Instance_Query.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fcab8382-61ed-6d3b-d5e7-94c7a645e6e0.png)
6. Click on the Policy Element Node to see the list of AWS Policies that have been applied to the RDS Instance resources.

![DAG_RDS_Instance_Policy_Element_nodes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-454a9255-0f00-4f8c-1df0-d8e9193a3834.png)

#### Identify and report on which AWS Roles have access to Standalone RDS Instance resource.

To identify the users with access to Amazon RDS Instance:

1. In Securiti, open **Data Access Governance** and choose **Access Intelligence** to access the dashboard.
2. Near the upper right corner of the page, click the **Identity Graph Explorer** button.
3. Near the upper left corner of the page, click **+** to open the filter. From the list of Entities, select **Role** in the Access Intelligence category.
4. Click three dots with the Role node, and select **Add Relationship**. Select **Policy Element**. Click three dots with the Policy Element Node, and select **Add Relationship**. Choose the **Policy Object** Entity. You can add additional properties for Policy Object.
5. Click three dots with the Policy Element Node, and select **Add Relationship**. Choose the **Resource Scope** Entity.
6. Click three dots with the **Resource Scope** node, and select **Add Relationship**. Select **Database Cluster**.
7. Click on the Policy Element Node to see the list of AWS Policies that have been applied to the RDS Instance resources.

#### Reporting

The results of all of the above graph queries can be used to create dashboards using our reporting widget functionality. For more details on creating dashboards and reporting widgets, see [reporting dashboard documentation](/v1/docs/using-graph-reporting-dashboards).
