---
title: "Impact of AI Tuning on Structured Data Insights policies"
slug: "impact-of-ai-tuning-on-structured-data-insights-policies"
updated: 2026-08-18T16:14:17Z
published: 2026-08-18T16:14:17Z
canonical: "helpcenter.securiti.ai/impact-of-ai-tuning-on-structured-data-insights-policies"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Impact of AI Tuning on Structured Data Insights policies

AI Tuning bulk-updates similar columns based on your classification feedback on a reference column. This feedback also applies to future discovery scans. If AI-tuned columns are part of any policy findings, they're updated accordingly as well.

When an AI Tuning session is completed, all Structured Data Insights policies are re-triggered so that policy findings reflect the updated classifications. For more information, see [Classifying columns using AI Tuning](/latest/docs/classifying-columns-using-ai-tuning).

The following image shows a completed AI Tuning feedback entry on the **AI Tuning History** page. For more information, see [Viewing AI Tuning History](/latest/docs/using-ai-tuning-for-classifying-columns).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(547).png)

> [!NOTE]
> Note
> 
> - If no policy findings are classified after AI Tuning feedback, no changes appear, even if the policy is re-triggered.
> - Changes from AI Tuning feedback are only reflected in findings that contain the Data Scope column, since the feature bulk-classifies and updates columns. Tables and other data scopes aren't included in AI Tuning.
> - Changes from AI Tuning feedback are only reflected in findings that contain the Data Scope column. Tables and other data scopes are not included in AI Tuning.
> - If AI Tuning feedback is deleted, all updated findings revert to their original form and Open state.

To view classifications updated by AI Tuning on Structured Data Insights Findings page:

1. To view AI-tuned findings, expand a Structured Data Insights policy, as shown below. A finding is marked **Resolved** if it is updated by AI Tuning and no longer falls within the policy scope, and **Open** if it's updated by AI Tuning but still falls within the policy scope.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(548).png)
2. To view AI-tuned findings in **Graph Explorer**, click **Column** under the **Data Scope** column, as shown below. For more information, see [Data Command Graph](/latest/docs/using-graph-explorer).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(549).png)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(550).png)
