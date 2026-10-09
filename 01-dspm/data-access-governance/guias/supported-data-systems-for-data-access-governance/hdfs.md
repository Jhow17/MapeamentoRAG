---
title: "HDFS"
slug: "hdfs"
updated: 2025-11-07T06:41:46Z
published: 2025-11-07T06:41:46Z
canonical: "helpcenter.securiti.ai/hdfs"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# HDFS

This section describes the Data Access Governance features supported for HDFS and the steps to configure these functionalities.

#### Supported Data Access Governance Feature Sets

Following is the list of the features supported for HDFS:

### Access Intelligence

- Privilege Analysis - Not supported
- Activity Analysis - Not Supported

#### Access Control

- File level Permissions Management Properties

#### Cross Border Transfer Policies

- Not Supported

### Example Supported Use Cases

The supported example use cases include:

#### Access Control

- Allow or Deny the access of your users and groups to Files containing sensitive data

### Configuring HDFS Data Access Governance

To see the HDFS access intelligence data there are some prerequisite steps.

#### Configuring Data Access Control Policies for HDFS

This access control policy type lets you grant granular permissions to your Files in HDFS

#### Prerequisites

- [Set up a pod or elastic pod](/v1/docs/securiti-pods-and-elastic-pods).
- [Configure and activate the connector](/v1/docs/hdfs-connectors-1). Note that the user account you use to configure the connector must be the owner of the data resources such as Catalogs, Schemas, and Tables on which you must apply access control policies.
- Mark the checkbox for **Enable Data Access Control** in the data system’s **Permissions** tab, so that this data system is available for selection when you create the policy.
  - Select the Plugin Version from the Dropdown menu

![Apache_Ranger_Plugin_name.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-34d18cdf-3a84-f6c9-6a7c-1a68a200dab5(3).png)
  - In the plugin folder, locate the **install.properties** files.

![install_properties.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-66d75246-550d-4f75-2420-6ff249d2a407(4).png)
  - Add your **repository name** in the install.properties file.

![Reporsitry_name_install_properties.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7fc87371-3212-f9bd-0136-5861d1277abb(3).png)
- [Perform a discovery scan for your HDFS instance](/v1/docs/configure-discovery-scans-in-hdfs).

#### Creating data access control policies

1. In Securiti, open **Data Access Governance**, then click three dots icon to expand the navigation bar. Choose **Policies>Data Access Policies**.

![DAG_navbar.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d2d78989-9dd6-f337-918a-5f64aa9633c1(1).png)
2. Near the upper right corner of the page, click **+ Create Policy** button.
3. On the **Create a New Policy** popup:
  1. Choose policy type **Data Access Control**.
  2. From the **Select Data System** menu, choose **HDFS**.
  3. Click **Get Started**.
4. Enter a name for the policy.
5. (Optional) Add a description for the policy.
6. Expand the **Data Scope** area and use the tools there to configure the scope. Scope defines the boundaries and context within which the access policy's rules and privileges are enforced.
  1. From the Actions column, click on the graph icon to add the scope. Once you click the graph icon, the Graph Explorer window opens. You are presented with a blank canvas where you can begin defining your graph search criteria in the following ways:
    - By clicking the **+** sign in the upper left corner of the upper row of the dashboard.
    - By clicking the **Begin Your Search** button at the center.
    - By loading an existing filter from **Saved Views** from the upper right corner of the page
  2. Click + or the Begin Your Search button at the center of the page. The filter menu has three panels as described below:

| Panel | Description |
| --- | --- |
| Left panel (Groups) | The left panel shows the entity groups. Clicking on a group name moves the second panel to that group. |
| Center panel (Entities) | The second panel lists all available entities. |
| Right panel (Description) | Hovering over one of the entities in the center panel brings up the description for the entity in the right panel. |
  3. From the center panel, click on the **Data System** entity. Click **Add Property** to add a property. Select the **Data System Type** from the list of properties associated with the selected node. Select **HDFS - Self-Hosted** from the list.
  4. Select the instance from the data grid on which you must apply the policy.
  5. Apply the **increment (+ icon)** operator to add the entity and attribute as an include rule to the page filter. The added filter appears in the top row of the dashboard with the rest of the filters.
  6. Click options (three dots) on the right side of the **Data System** node and click **+ Add Relationship**.
  7. From the Entity Groups in the left panel, click on the **Data** group, and select the **Files** node. Click on the File entity from the left panel. Select the File for which you want to implement the privileges. Apply the **increment (+ icon)** operator.

![Dag_HDFS_Policy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-83bf9237-d9b4-aaa1-926d-d62ce4fbd7ff.png)
  8. Click **Use Query** button.
  9. In the **Access Rules** area, click **+ Add a Privilege Rule** to add a rule. **In the Add a Privilege Rule window**:
    1. Provide the Rule Name.
    2. (Optional) Add description.
    3. In the **Principals** area, click **+ Add a Principal**. Principals are the entities on which the access rule is applied.
    4. Select **Users** or **Groups**. You must select Users or Groups as a Principal to create an access rule. If you have selected the **Users** as a Principal, then you must specify the **Users**. In the Users area, select the users from the menu. You can also add the users using the menu or use Graph Query button.
    5. In the **Privileges** area, you must select the privileges that you want to grant to the **Principals**. Note that the privileges displayed are the native privileges.
    6. You can select **Allow** to Grant the selected privileges, or you can select **Deny** to revoke privileges.

![DAG_SMB_Privileges.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-63c73bfd-99e7-3554-6c01-99163c951ef9.png)
    7. Click the **Create Rule** button to add an access rule.
  10. Activate the **Enable policy after saving** toggle. When activated, the policy will be enforced as soon as the policy information is saved.
  11. Click the **Create Policy** button to create the policy.
