---
title: "Opening the appeal request in DSR Workbench"
slug: "opening-the-appeal-request-in-dsr-workbench"
updated: 2025-12-09T16:09:56Z
published: 2025-12-09T16:09:56Z
canonical: "helpcenter.securiti.ai/opening-the-appeal-request-in-dsr-workbench"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Opening the appeal request in DSR Workbench

**Scenario**

As a Data Privacy Officer, you are responsible for ensuring that individuals’ rights are respected and that responses to DSR requests are fair and thorough. Sometimes, a data subject may disagree with the outcome of their request. By enabling the appeal mechanism in the Data Subject Rights module, you allow them to challenge decisions directly. This ensures transparency, builds trust, and helps your organization demonstrate accountability.

Securiti lets you configure the appeal mechanism within the Data Subject Rights module.This means that data subjects who submit DSR requests to your organizations now have the ability to challenge decisions made in response to their requests. If a data subject is dissatisfied with a DSR report shared as a result of a submitted DSR request, they may initiate an appeal to seek a reconsideration or resolution. To configure an appeal mechanism, see **Enable Appeals** details in [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms).

> [!NOTE]
> **Note**
> 
> If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.

Once the data subject submits an appeal, it lands in the DSR Dashboard , and Securiti sends an email to DSR owners, notifying them about the creation of a new appeal ticket.

![appeal_notification_to_DSR_owner.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b6b1ca6a-e187-d0e7-cef1-a9abf725487a.png)

From the **DSR Dashboard**, you can also track the original DSR for which the data subject has submitted an appeal.

![DSR_Dasboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-23b7692e-7058-885f-d54f-77a18baab140.png)

To process the appeal request:

1. In the DSR Dashboard, click on the appeal card to open it in DSR Workbench.
2. In the **Appeal** tab, review the appeal request information provided by the data subject. You can also view or download the evidence files provided as part of the appeal request.
3. From **Review Appeal** menu, choose **Approve** or **Decline**, add **Internal Notes** and click **Submit**.

![Appeal_tab.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-281d1562-e58a-fc8c-28e0-13604374dfc3.png)
  - If you approve the appeal request, Securiti rescans the data systems containing personal data of the data subject, creates Tasks and subtasks and assigns them to respective data system owners. The subsequent steps in the process remain the same as those for processing a standard DSR request. For more information, see [DSR Workbench Overview](/v1/docs/dsr-workbench-overview).

> [!NOTE]
> **Note**
> 
> When you approve an appeal for a custom DSR request, Securiti checks the latest configuration for that request type. It creates tasks and subtasks in the **Worklist** based on the [current settings](/v1/docs/configuring-dsr-request-types). For instance, if DSR Automation is enabled when the DSR request is submitted but later disabled when the appeal is submitted, Securiti follows the updated configuration. At the time of approval, it creates tasks and subtasks as per the disabled automation setup.
  - If you decline the appeal request, use the **Reason for decline** menu to choose a template category, then choose one of the available templates and click its **Preview** and **Edit**. Further either edit the existing template or clone it and make changes to the cloned one. See [Creating and editing messaging templates](/v1/docs/creating-and-editing-messaging-templates) for more information about customer messaging templates.

![Decline_appeal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4886ae66-f84f-7c9c-927c-a72f60e2e820.png)

Securiti notifies the data subject about the decision of the DSR Owner regarding the appeal request, whether it is approved or declined. For more information on notification templates, see [Configuring DSR email notification templates.](/v1/docs/configuring-dsr-email-notification-templates)
