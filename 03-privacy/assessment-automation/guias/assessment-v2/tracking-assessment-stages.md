---
title: "Tracking Assessment Stages"
slug: "tracking-assessment-stages"
status: "new"
updated: 2025-11-03T06:15:02Z
published: 2025-11-03T06:15:02Z
canonical: "helpcenter.securiti.ai/tracking-assessment-stages"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Tracking Assessment Stages

**Scenario**

As a Data Privacy Officer, you're responsible for keeping assessments on track. Without visibility into each stage, it's hard to spot delays until it’s too late. With assessment stage monitoring, you quickly identify where progress stalls, whether it’s pending reviews or overdue tasks. This helps you take timely action, reduce bottlenecks, and ensure assessments finish on schedule.

The table provides the information about data transition through different stages and question states of the assessment lifecycle. For more information, see [Understanding Workflow Stages and assessment use cases](/v1/docs/understanding-workflow-stages-and-assessment-use-cases).

| Scenario | Unanswered (question state) | Draft (question state) | Submitted (question state) | Send Back | Approved (question state) | Stage | Result | Additional Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | The assessment has unanswered questions |  |  |  |  | Not Started |  |  |
| 2 |  | The assessment has responses that are not yet submitted |  |  |  | In Progress |  |  |
| 3 |  |  | The assessment has submitted responses |  |  | In Review |  |  |
| 4 |  |  |  | The assessment with flagged responses and requests more information |  | In Progress | Flagged | Open Flags show on the assessment that you must address before submitting back for Approval |
| 5 |  |  |  |  | The assessment has approved responses | Complete |  | Inherit Completion Date for Last Published Date If no Last Published Date, inherit from Last Modified Date |
| 6 | The assessment has unanswered questions | The assessment has responses that are not yet submitted |  |  |  | In Progress |  |  |
| 7 | The assessment has unanswered questions |  | The assessment has submitted responses |  |  | In Progress |  |  |
| 8 | The assessment has unanswered questions |  |  | The assessment with flagged responses and requests more information |  | In Progress |  |  |
| 9 | The assessment has unanswered questions |  |  |  | The assessment has responses previously approved | In Progress |  |  |
| 10 |  | The assessment has responses that are not yet submitted | The assessment has submitted responses |  |  | In Progress |  |  |
| 11 |  | The assessment has answered questions but not yet submitted |  | The assessment with flagged responses and requests more information |  | In Progress |  |  |
| 12 |  | The assessment has responses that are not yet submitted |  |  | The assessment has responses previously approved | In Progress |  |  |
| 13 |  |  | The assessment has submitted responses | The assessment with flagged responses and requests more information |  | In Progress |  |  |
| 14 |  |  | The assessment has submitted responses |  | The assessment has approved responses | Complete |  |  |
| 15 |  |  |  | The assessment with flagged responses and requests more information | The assessment has responses previously approved | In Progress |  |  |
| 16 | The assessment has unanswered questions | The assessment has responses that are not yet submitted | The assessment has submitted responses |  |  | In Progress |  |  |
| 17 | The assessment has unanswered questions | The assessment has responses that are not yet submitted |  | The assessment with flagged responses and requests more information |  | In Progress |  |  |
| 18 | The assessment has unanswered questions | The assessment has responses that are not yet submitted |  |  | The assessment has responses previously approved | In Progress |  |  |
| 19 | The assessment has unanswered questions |  | The assessment has submitted responses | The assessment with flagged responses and requests more information |  | In Progress |  |  |
| 20 | The assessment has unanswered questions |  | The assessment has submitted responses |  | The assessment has responses previously approved | In Progress |  |  |
| 21 | The assessment has unanswered questions |  |  | The assessment with flagged responses and requests more information | The assessment has responses previously approved | In Progress |  |  |
| 22 |  | The assessment has responses that are not yet submitted | The assessment has submitted responses | The assessment with flagged responses and requests more information |  | In Progress |  |  |
| 23 |  | The assessment has responses that are not yet submitted | The assessment has submitted responses |  | The assessment has responses previously approved | In Progress |  |  |
| 24 |  | The assessment has responses that are not yet submitted |  | The assessment with flagged responses and requests more information | The assessment has responses previously approved | In Progress |  |  |
| 25 |  |  | The assessment has submitted responses | The assessment with flagged responses and requests more information | The assessment has responses previously approved | In Progress |  |  |
| 26 | The assessment has unanswered questions | The assessment has responses that are not yet submitted | The assessment has submitted responses | The assessment with flagged responses and requests more information |  | In. Progress |  |  |
| 27 | The assessment has unanswered questions | The assessment has responses that are not yet submitted | The assessment has submitted responses |  | The assessment has responses previously approved | In Progress |  |  |
| 28 | The assessment has unanswered questions | The assessment has responses that are not yet submitted |  | The assessment with flagged responses and requests more information | The assessment has responses previously approved | In Progress |  |  |
| 29 | The assessment has unanswered questions |  | The assessment has submitted responses | The assessment with flagged responses and requests more information | The assessment has responses previously approved | In Progress |  |  |
| 30 |  | The assessment has responses that are not yet submitted | The assessment has submitted responses | The assessment with flagged responses and requests more information | The assessment has responses previously approved | In Progress |  |  |
| 31 | The assessment has unanswered questions | The assessment has responses that are not yet submitted | The assessment has submitted responses | The assessment with flagged responses and requests more information | The assessment has responses previously approved | In Progress |  |  |

To learn about what Securiti Assessments can help you achieve, refer to [Internal Assessments overview](/v1/docs/securiti-pods-and-elastic-pods) video.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
