---
title: "Fulfilling DSR requests for Slack Enterprise Grid"
slug: "fulfilling-dsr-requests-for-slack-enterprise-grid"
updated: 2025-10-31T06:52:10Z
published: 2025-11-03T07:34:02Z
canonical: "helpcenter.securiti.ai/fulfilling-dsr-requests-for-slack-enterprise-grid"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Fulfilling DSR requests for Slack Enterprise Grid

When Securiti accepts a DSR request, it creates a single task, with subtasks of the appropriate DSR types for each Slack Data system Instance in the Securiti platform.

The Securiti Connector for Slack Enterprise Grid supports the various DSR request types with varying degrees of automation described in the Table below.

| DSR Type | Automation |
| --- | --- |
| Access | **Automated** Securiti automatically extracts and attaches one or more Auto-generated PD reports showing all the personal data associated with the data subject. Verify that the data belongs to the data subject and that the processing record describes the processing, and if so, approve the subtask. See [Processing access request subtasks](/v1/docs/processing-access-request-subtasks) for more information. |
| Port | **Partially Automated** Securiti shows you a report or manifest that identifies the objects where it found personal data for the data subject. For each object, access the service or database to open and inspect the object that Securiti name identified. Redact any extraneous sensitive data, attach the redacted data, and approve the subtask. > [!NOTE] > **Note** > > For port requests, regulations don't require you to provide the context around which the data is processed within your organization. Therefore port subtasks do not include a process record. See [Processing port request subtasks](/v1/docs/processing-port-request-subtasks) for more information. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
