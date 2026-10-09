---
title: "Merge"
slug: "merge-regular-node"
updated: 2025-10-30T19:06:11Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/merge-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Merge

In Securiti, Merge node combines the data from multiple data streams once the data is available in both the data streams. The merge mode defines how the data can be merged. The primary function of a merge node is to bring together disparate data sources, process outputs, or tasks from various branches of a Workflow. This consolidation allows for centralized decision-making or further processing. You can merge the data as per your requirement using various merging modes such as appending data, keeping the key matches etc.

Jump to the [Node Configuration](/v1/docs/merge) section to understand the node parameters and descriptions.

#### Example use case

As an example use case, let’s create a Workflow that involves merging data from two different data streams, specifically from the risks assessments API and the user API. The goal is to replace the owner ID from the risks assessments API with the user API's email address. Below is a breakdown of the steps:

- The risk Assessments API is the data source that has details about risks, including an owner's ID.
- The User API is the data source that has information about users, such as their email addresses.
- The goal is to combine data from these two sources using a "merge node." The reason to merge the data from the two Nodes is that when the owner ID is picked from the Risks API and the managing organization, it returns only the numeric ID. However, the user needs the name of the user and the name of the managing organization, not just the ID.

This Workflow uses the following Nodes:

1. Cron Trigger node
2. HTTP Request Node
3. Set
4. Function
5. Merge

#### Creating a workflow to merge the results from two data streams

1. Set the tenant configuration values by providing the authentication header details in the Set Node. Refer to Set Node reference for details.
2. Add two HTTP request Nodes to perform the following actions:
  - Fetch the user details
  - Fetch the vendor risk details
3. From the API results, set the values of user details such as name, ID and role and assessment details such as Assessment ID, risk level, status etc.
4. Merge the values from the outputs of both the APIs using the merge node.

![merge-node-prop.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8eb41918-2541-fdda-57d0-6c5ddb0434b0.png)
5. Connect the Nodes and execute the Workflow.

![merge-node-wf.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c12d35d0-7327-bb1d-a5b3-8e9655f93d8e.png)
6. Upon successful execution, the Workflow Node will provide a successful response. After the Workflow runs successfully, you can access the results in two formats i.e. table view and JSON response.

#### Node configurations

| Parameters |
| --- |
| Mode | Specify how the data branches are merged. |
| Append | Specify this mode to append the data from one stream to another stream. The output contains items from Input stream 1, followed by all items from Input stream 2. |
| Keep Key Matches | Specify this mode if you want to only merge the matched values in both the streams, for example if the data in Input stream is 100, 101 and 102 and the data in input stream 2 is 103, 101 and 100, then the merged output will be 100, 101. |
| Merge By Index | Specify this mode to merge the data from both inputs. The output contains items of input 1 merged with data of input 2. Merge happens depending on the indexes of the items. First item of input 1 is merged with first item of input 2, and so on. |
| Merge By Key | Specify this mode to merge the data from both inputs. The output contains items of input 1 merged with data of input 2. Merge happens depending on a defined key. |
| Multiplex | Specify this mode to merge each value of one input with each value of the other input. The output contains (m*n) items where (m) and (n) are the lengths of the inputs. |
| Pass-through | Specify this mode to pass through data of one input. The output contains only items of the defined input. |
| Remove Key Matches | Specify this mode to keep data of input 1 if it does not find a match with data of input 2. For example if a value X is present in both input streams, the merged data will have the value only once. |
| Wait | Specify this mode for the node to wait until data of both inputs is available and then outputs a single empty item. If supposed to wait for multiple Nodes, they have to get attached to input 2. Node does not output any data. |
| Property input 1 | Specify the name of the property that decides which items to merge of input 1 i.e. first data stream. |
| Property input 2 | Specify the name of the property that decides which items to merge of input 2 i.e. second data stream. |
| Join | Specify the type of join if the mode selected is *Merge by Index*. |
| Inner Join | Merges as many items as both inputs contains |
| Left Join | Merges as many items as the first input contains |
| Outer Join | Merges as many items as the input with the greatest number of items contains |
| Overwrite | Specify when to overwrite values from input 1 with those of input 2 if the mode selected is *Merge by Key*. |
| Always | Always overwrites everything. |
| If Blank | Overwrites only values of "null", "undefined", or empty strings. |
| If Missing | Only adds values that are absent. |
| Output Data | Specify which input is used as the output data if the mode selected is *Pass-Through*. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
