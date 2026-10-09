---
title: "Configuring workflow allow-listing"
slug: "configuring-workflow-allow-listing"
updated: 2025-10-30T18:37:14Z
published: 2025-11-03T07:41:36Z
canonical: "helpcenter.securiti.ai/configuring-workflow-allow-listing"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Configuring workflow allow-listing

If your firewalls or WAFs are configured to block the entire AWS or Azure address ranges, you must allow-list the following IP addresses to permit Workflow Nodes to reach your internal services (for example, SMTP servers) behind the firewalls:

| Production instance | Endpoint | IP address |
| --- | --- | --- |
| US Cloud | `wf-mt.app.securiti.ai` | - `99.83.154.190` - `13.248.185.49` |

| Production instance | Endpoint | NATIP address |
| --- | --- | --- |
| U.S. Cloud | `app.securiti.ai` | - `54.68.117.210` - `44.232.248.202` - `35.155.217.93` |
| EU Cloud | `app.eu.securiti.ai` | - `54.73.208.151` - `52.18.221.170` - `52.215.125.10` |
| U.S. GCP Cloud | `app1.securiti.ai` | - `34.105.10.226` - `34.105.44.52` |
| Indonesia Cloud (Jakarta) | `app2.securiti.ai` | - `108.136.119.196` - `108.137.87.223` - `108.136.196.30` |
| Canada Cloud (Montreal) | `app3.securiti.ai` | - `3.97.59.2` - `15.222.204.203 ` - `3.97.187.88` |
| Australia Cloud (Sydney) | `app4.securiti.ai` | - `13.239.141.172` - `3.104.48.164` - `54.252.203.75` |
| United Arab Emirates (UAE) Cloud | `app5.securiti.ai` | - `3.29.154.64` - `3.29.228.59` - `3.29.219.172` |
| India Cloud (Mumbai) | `app6.securiti.ai` | - `52.66.187.150` - `3.7.77.210` - `13.127.253.194` |
| Kingdom of Saudi Arabia (KSA) Cloud | `app7.securiti.ai` | - `34.166.62.175` - `34.166.60.3` |
| State of Qatar Cloud | `app8.securiti.ai` | - `34.18.56.161` - `34.18.83.173` |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.

## Related

- [Building and using Securiti workflows](/building-and-using-securiti-workflows.md)
- [Build your first Securiti workflow](/build-your-first-securiti-workflow.md)
