---
title: "Performing Actions Post OCI Instance Creation"
slug: "performing-actions-post-oci-instance-creation"
updated: 2026-08-10T07:46:54Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/performing-actions-post-oci-instance-creation"
area: integrations
modulo: iaas-connectors
tipo: guia
data_captura: 2026-10-06
---

# Performing Actions Post OCI Instance Creation

Once an OCI IaaS instance is created on the Securiti platform, users gain access to a variety of post-instance creation actions designed to help manage and secure their cloud environment. These actions enable users to edit configurations, discover accounts, reinitiate asset discovery and posture scan, and delete instances.

For detailed guidance on creating an OCI IaaS instance, refer to the [Creating an OCI Instance](/v1/docs/creating-an-oci-instance) section, which outlines the step-by-step process for setting up your instance on the Securiti platform.

To perform these post-activation actions:

1. In Securiti, select the jewel icon and choose **Integrations** from the left navigation bar.
2. On the **Integrations** page, navigate to **IaaS Connectors**.
3. On the **IaaS Connectors** page, you will see a list of existing instances. Click the **More actions** icon next to an instance, or click the instance directly. A menu appears, letting you perform the following actions.

### Editing an OCI Instance

**Scenario**

As a Data Governance Officer, you need to align co-ownership and scan settings for your OCI instance when responsibilities shift. Manually updating owner lists and juggling scheduled scans in spreadsheets risks overlooking new compartments and hidden misconfigurations. With Securiti’s post-instance editing, you add co-owners and refresh asset discovery and posture scans in seconds, ensuring accurate oversight and continuous security monitoring.

In the **Basic Information** tab, under the **Owners** section you can add co-owners by clicking the **+Add co-owner** button.

In the **Instance Setup** tab, you can view all accounts along with their asset discovery and posture scan status. You can also configure scan settings, schedule and define exclusion periods for automatic scans.

You can modify the following details in an existing instance:

- To discover data system assets in monitored IaaS accounts, mark the **Initiate asset discovery** checkbox.
- To monitor and remediate misconfigurations across your IaaS data systems, mark the **Initiate security posture scan** checkbox.
- To schedule automatic scans to discover data systems and security posture, mark the checkbox. Moreover, to define time periods when scans should be paused, click **+Add Exclusion**.
- In the **View Compartments** section, you can selectively reinitiate asset discovery and posture scan for specific accounts. After the instance is created and the initial scan is complete, select the desired compartments and click **Initiate**. This action triggers asset discovery and posture scan for all selected compartments.

> [!NOTE]
> Note
> 
> - Securiti supports this feature under the following conditions:
>   - Only for asset discovery and posture scan.
>   - Only for on-demand reinitiation. Scheduled asset discovery and posture scan continue to run automatically for all compartments.
>   - Only for compartments where both the asset discovery and posture scan are in a **Completed** or **Failed** state. Securiti disables this option if either scan is in **In Progress** or **Scheduled** state.
> - To support this feature, Securiti has added checkboxes for selecting compartments when reinitiating scans and now manages compartment linking through toggle buttons. Disabling a compartment excludes it from future checks and scans.

### Deleting an OCI Instance

**Scenario**

As a Data Security Officer, you must decommission inactive OCI instances to minimize vulnerabilities. Manually identifying stale instances and coordinating removals via email and spreadsheets risks leaving orphaned resources exposed. With Securiti’s post-instance deletion, you remove inactive instances and purge their discovered assets in seconds. You reduce your attack surface quickly and maintain a streamlined, secure cloud environment.

Select **Delete** to remove the instance. A warning message will confirm whether you're sure about the deletion.

> [!NOTE]
> **Note**
> 
> Only inactive instances can be deleted.

You can choose to deactivate your instance by selecting **More options** in the upper-right corner of the **Instance Setup** tab.

### Reinitiating DSPM

**Scenario**

As a Data Compliance Officer, you must validate your OCI security posture right after policy updates. Waiting for scheduled DSPM cycles delays compliance checks and leaves gaps. With Securiti’s on-demand DSPM action, you rerun asset discovery and posture scans together instantly, linking findings to each resource. You close compliance gaps in minutes and sustain continuous regulatory adherence.

Select **Reinitiate DSPM** to reinitiate both asset discovery and the detection of data security posture misconfigurations.

> [!NOTE]
> **Note**
> 
> If the **Initiate Security Posture Scan** checkbox wasn't selected when configuring your OCI instance, only asset discovery runs on your activated instance.

## Related

- [Creating an OCI Instance](/creating-an-oci-instance.md)
