---
title: "Workflow automation in DSR"
slug: "workflow-automation-in-dsr"
updated: 2025-11-04T13:15:41Z
published: 2025-11-04T13:15:41Z
canonical: "helpcenter.securiti.ai/workflow-automation-in-dsr"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Workflow automation in DSR

**Scenario**

As a Data Privacy Officer, you handle multiple DSR requests daily, including access and erasure tasks. Manual approval and assignment often slow down your response time. By using automated workflows in the DSR Workbench, you set rules for privacy officer approvals and auto-completion of specific tasks. This reduces delays, ensures accuracy, and helps you close requests faster with confidence.

Automating DSR subtasks is a key feature of Securiti’s **DSR Workbench**. You can perform automation within the DSR fulfillment process to improve efficiency. In many cases, you may want to execute a particular workflow through a DSR intake form. In other cases, you may want to trigger a specific workflow before accepting the DSR requests.

You can use workflows in DSR for various purposes, such as:

- If you want subtasks generated for a specific DSR type(such as Access or Erasure) to be approved by the privacy officers before automatically assigning them to data system owners.
- If you want to auto-complete and close some specific requests, create a workflow that automatically handles and finishes them. Further, associate that workflow with the DSR form where that request will be raised.
- If there is a use case where a summary of emails from some information management application such as O365 Outlook needs to be returned as part of a DSR access request, you can create a workflow to execute it.
- The use case is to validate the data subject’s identity with a third-party service before accepting the request.

For more information on how you create workflows, see [Workflows](/v1/docs/building-and-using-securiti-workflows) documentation.

> [!NOTE]
> **Note**
> 
> Securiti does not support DSR robotic automation during the creation of DSR tasks or subtasks via workflow nodes or APIs. However, automation is supported after creation through a rescan or partial scan. This means tasks or subtasks created via workflows or APIs can be automated only after their creation, not by default.

To associate a workflow within the DSR form:

1. In the **Data Subject Rights** choose **Settings > Form Builder** and select the form with which you like to associate the workflow.
2. To perform some action before accepting the DSR like verifying the data subject’s identity, in the External Workflow Trigger section, mark **Enable External Workflow** and choose workflow from the menu. For more information, refer to the **External Workflow Trigger** section in [Creating and Publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms)

> [!WARNING]
> **Important**
> 
> - Only saved workflows will be shown in the list
> - The workflows must have DSP trigger nodes.
3. Similarly, to automate DSR after accepting the request, in the Automation section, mark **Associate with Workflows** and select Workflows you want to associate with the DSR form. For more information, refer to the **Associate with Workflows** section in [Creating and Publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms)

![Screenshot_2024-01-06_at_11_30_36_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a7fb06c1-fe43-b22e-faca-635fab0fcff9.png)

> [!WARNING]
> **Important**
> 
> - Only active workflows are shown in the list.
> - The workflows must have DSR trigger nodes.

Securiti executes all the workflows associated with the form receiving the DSR requests.
