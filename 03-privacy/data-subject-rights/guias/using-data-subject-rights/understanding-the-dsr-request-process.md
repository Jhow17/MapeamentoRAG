---
title: "Understanding the DSR request process"
slug: "understanding-the-dsr-request-process"
status: "update"
updated: 2025-11-05T10:41:03Z
published: 2025-11-05T10:41:03Z
canonical: "helpcenter.securiti.ai/understanding-the-dsr-request-process"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Understanding the DSR request process

This topic describes the overall process that Securiti uses to respond to a DSR request from a Data Subject.

In most cases, the process starts with a request from the data subject submitted using a form that you publish on your website as described in [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms). Once the subject verifies their email address, Securiti automatically assigns the request a number and lists it in the DSR workspace. However, Securiti admins and DPOs can also manually create a DSR request in the DSR workspace in response to a request submitted through email or over the phone or through other channels as described in [Opening DSR requests on behalf of data subjects](/v1/docs/opening-dsr-requests-on-behalf-of-data-subjects).

The owner of a DSR request is responsible for ensuring that the request is fulfilled before its deadline. In the case of a request submitted by a data subject through a Securiti DSR request form, the DSR request is co-owned by the Securiti users who own the form. Manually created DSR requests are co-owned by the Securiti user who created the request, and by the users who own the internal DSR request form. For more information, see [Creating and publishing DSR request forms](/v1/docs/creating-and-publishing-dsr-request-forms).

Once a DSR request has been created in the DSR workspace, Securiti uses the information in the request to locate matching personal data in your data systems corresponding to the data subject. Securiti then produces a set of subtasks relating to that data that data system owners must accomplish in order to fulfill the subject’s request.

Securiti assigns each subtask to the owner of the data system in which Securiti found the personal data. Data system owners can perform these tasks themselves, or they can delegate them to other Securiti users. For more information, see [Manually assigning DSR request subtasks](/v1/docs/manually-assigning-dsr-request-subtasks).

For some requests, the subtasks are almost entirely automated, requiring its owner only to verify that the automation correctly handled it. Other subtasks require more intervention for the owner to locate the data and handle it as needed. For more information, see [Processing DSR subtasks](/v1/docs/processing-dsr-subtasks) .

Once an owner completes their subtask, they mark it as successfully completed and submit it. When all of the subtasks created for the request have been completed, the request is marked for review by its owner. For more information, see [Approving and publishing reports](/v1/docs/approving-and-publishing-reports) .

When the DSR request owner approves the report, Securiti closes the DSR request, publishes the report to the secure customer-facing DSR request center, and sends the data subject an email with a link to the report. For more information, see [Understanding the DSR request center](/v1/docs/understanding-the-dsr-request-center).

The report remains available on the DSR request center for the DSR report archive duration you configured on the **Settings > Data Subject Rights** page. The closed DSR request remains available in the DSR workspace for the DSR archive duration you configured on the **Settings > Data Subject Rights** page. For more information, see [Configuring DSR retention policy](/v1/docs/configuring-dsr-retention-policy).

A **Data Protection Officer (DPO)** ensures the safety and security of personal data. In the Data Subject Rights module, DPOs are responsible for configuring DSR forms and responding to different types of data subject requests.
