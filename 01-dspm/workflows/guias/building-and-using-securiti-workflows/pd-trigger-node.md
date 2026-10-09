---
title: "PD Trigger Node"
slug: "pd-trigger-node"
updated: 2025-10-30T19:13:13Z
published: 2025-11-03T07:39:28Z
canonical: "helpcenter.securiti.ai/pd-trigger-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# PD Trigger Node

Data classification is a process of organizing and categorizing data for its improved understanding and efficient use. Securiti has a comprehensive tool developed for data classification that delivers a complete understanding and categorization of all the data across the organization, including shadow and dark data. Hence, data classification effectively sifts through data assets to identify and discover data, groups it by shared attributes, and classifies it at the data element level.

A Personal Data (PD) trigger node is triggered when any of the following conditions are met:

- the overall PD volume for the complete tenant, specific data asset, or specific process exceeds a certain threshold during a specified period of time (for example 10% change in data elements volume is found in a scan)
- a specific PD Type is discovered for the complete tenant, specific data asset, or process during a specified period of time (for example SSN is found in a scan)

#### Prerequisites

To fetch the results of your PD detection, you must run the discovery scan to find the classification results to get the PD trigger node triggered.

#### Example Use Case

As an example, let’s create a Workflow where the PD node is triggered whenever any change in data elements or any new data element is discovered. It then identifies if there is a change in data elements. Here is a breakdown of the Workflow:

1. The PD Trigger node gets the results of classification whenever there is any change in data element volume.
2. The results are then used to create an assessment using the Assessment node.

#### Generating the classification results and creating an assessment

1. Add a PD trigger node linked to the specific data system for any specific tenant, asset, or process.

![pdtrigger_node.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-87eea436-8911-dc84-1068-1728a057cdd6.png)
2. Add an Assessment node for the data elements identified through PD trigger node.
3. Create the pipeline and activate the Workflow.

![pdtrigger_assessment_nodes.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-274058ae-c5fe-ca25-a864-4a89e46c96f7.png)
4. Once you execute the Workflow successfully, it gets the assessment that you can use to evaluate you data elements identified after classification. This is what the success response looks like.

![pdtrigger_results.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-42532da8-83d2-99d4-73bd-e2850c37ea9f.png)

#### Node Configuration

| Parameter | Description |
| --- | --- |
| Monitoring Level | The monitoring level is based on the following levels: - **Tenant** (specific data element(s) is(are) discovered for the complete tenant.) - **Asset** (specific data element(s) is(are) discovered for specific data system(s). For example SSN is found in a particular scan job.) - **Process** (specific data element(s) is(are) discovered for specific data system(s).)Specify one of the Monitoring Level options from Tenant, Asset, or Process. |
| Operate On | The Operate On is based on: - Specify **PD Volume** if you want to set a threshold of data element classification or percent change in the data elements. Configure the relevant parameters relevant to **PD Volume**. - Specify **PD Type** if you want to do an exact match of data elements found in the classification. Configure the relevant parameters relevant to **PD Type**. |
| Comparison | - Specify **Absolute** if you want the exact matching of data elements. Configure the relevant parameters relevant to Absolute comparison. - Specify **Relative** if you want a close match. Configure the relevant parameters relevant to Relative comparison. |
| Threshold | Specify a threshold if a specific process may exceed a certain threshold during a specified period (for example 1000 detections/data elements are found in a scan). It is based on the Absolute match of the data elements. |
| % Change | For a relative comparison, specify % change in the data elements. |
| Polling Interval | Specify the interval on which the trigger works, for example, 2 minutes, 5 hours, etc. |
| Unit | Specify the unit of the polling interval: - Specify 2 minutes for PD trigger to be triggered every 2 minutes - Specify 3 hours for PD trigger to be triggered every 3 hours |
| Throttling | Throttle trigger events for a specified time window. To initiate the Trottling, enable the **Throttling** toggle. |
| Throttling Interval | When throttling is enabled, choose **Throttling Interval** and **Unit**. - Minutes (for example every 2 minutes) - Hours (for example every 3 hours it should throttle) |
| Unit | When throttling is enabled, the type of unit: - Specify **Minutes** (for example every 2 minutes as a unit of throttle) - Specify **Hours** (for example every 2 hours as a unit of throttle) |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
