---
title: "Data Subject Rights prerequisites"
slug: "data-subject-rights-prerequisites"
updated: 2026-06-12T08:38:00Z
published: 2026-06-12T08:38:00Z
canonical: "helpcenter.securiti.ai/data-subject-rights-prerequisites"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Data Subject Rights prerequisites

Observe the following prerequisites when you use the Data Subject Rights module:

- For DSR robotic automation, you must have the following pre-requisites depending upon the type of Data system:
  - You must deploy pods to connect your self-hosted data systems. For more information, see [pods documentation](/v1/docs/securiti-pods-and-elastic-pods).
  - You must configure connectors for the data systems that you want to include in DSR workflow. Additionally, while configuring the Data System, simply mark Include this **instance in the DSR workflow** option under **Permissions** tab. For more information, see [configuring connectors for data systems](/v1/docs/configuring-connectors-for-monitored-data-systems).
  - For unstructured self-hosted data systems, you must have a subscription for the Sensitive Data Intelligence module to perform discovery scans on those data systems containing personal data of the Data Subject. While initiating a discovery scan, you must enable the “Enable Data Subject Requests (DSR) Automation on this Data” option. For more information, see [Discovery scans for unstructured data systems.](/v1/docs/discovery-scans)
- If you are manually processing a DSR request, you must create new or add existing unmonitored data systems in the Data Mapping module and include them in the DSR workflow. For this purpose, you need to subscribe to the Data Mapping module. For more information on creating assets in Data Mapping, see [Creating and editing processes](/v1/docs/creating-and-editing-processes).

**Prerequisites for specific use cases**

- If you want to automate DSR processing, you can create workflows and execute them. For that, you must have a subscription for the **Workflow Orchestration** module. For more information on DSR Automation using workflows, see [Workflow Automation in DSR](/v1/docs/workflow-automation-in-dsr).

To see how you can create workflows, see see [Workflow Orchestration](/v1/docs/building-and-using-securiti-workflows) documentation.

A collection of organized data or repositories and their corresponding management software, which could be IaaS, SaaS, or SQL. Data systems are configured in Securiti so that it can help you protect sensitive data and also locate personal data for data subjects who submit DSR requests. Data systems can be monitored, un-monitored, or user-defined. For each monitored or user-defined data system, you configure a connector that Securiti uses to interact with the data system.
