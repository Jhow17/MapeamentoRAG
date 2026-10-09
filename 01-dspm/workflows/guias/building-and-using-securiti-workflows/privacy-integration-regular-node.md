---
title: "Privacy Integration"
slug: "privacy-integration-regular-node"
updated: 2025-10-31T14:22:27Z
published: 2025-11-03T06:21:18Z
canonical: "helpcenter.securiti.ai/privacy-integration-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Privacy Integration

The Privacy Integration node lets you retrieve and display information from an active privacy integration with external platforms or data systems such as **Salesforce**, **Pardot**, etc. You can choose to display the data in either tabular or `JSON` format.

![PI-node-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3e79124d-9d17-2702-8cd8-3b7337739ab6.png)

This node displays the following runtime details:

- id
- name
- operation
- data_flow
- module
- object_name
- ds_name
- ds_id
- batch_size
- sync_from_ts
- optional_criteria
- field_mappings
- module_config
- wf_metdata

This Workflow node is specifically introduced for the Privacy Platform Integrations functionality, as explained in the [Privacy Platform Integrations - Implementation Guide](/v1/docs/configuring-salesforce-integration-in-securiti).

![1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4e63cd2e-144c-5139-f664-c9937d6d33a9.png)![2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7cd82326-619d-cb11-a376-1bc09567c374.png)

#### Node Configurations

| Parameters |
| --- |
| Operation | Get | Get Privacy Integration by ID |
| Integration Id | Enter the numeric ID of the Privacy Integration |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.
