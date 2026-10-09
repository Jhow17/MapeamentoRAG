---
title: "Pausing and resuming DSR deadline"
slug: "pausing-and-resuming-dsr-deadline"
updated: 2026-01-13T02:35:52Z
published: 2026-01-13T02:35:52Z
canonical: "helpcenter.securiti.ai/pausing-and-resuming-dsr-deadline"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Pausing and resuming DSR deadline

Once you configure the pause DSR deadline settings at the tenant level, you can pause the request directly from the workbench.

1. Open the request in the DSR Workbench and from the upper right corner, choose **More Actions (3 dots) > Pause DSR Deadline**.

![Dashboard displaying DSR request details for John Brown, including tasks and deadlines.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-08 at 1.40.25 PM.png)
2. On the Pause DSR Deadline popup, review the warning and click **Yes Proceed**.

![Pause DSR deadline warning for data subject request regarding John Brown's information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-08 at 1.42.51 PM.png)
3. Choose the reason for pausing the deadline, mark Send email notification to Data Subject checkbox to notify the data subject.

(Optionally) You can make changes to the subject of the email, choose variables to incorporate in the email content or update email content as per your requirement.

![Form to pause DSR deadline with email notification and reason for pause options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-08 at 1.58.26 PM.png)

> [!NOTE]
> Note
> 
> This email template adapts the content from the DSR Pause Deadline notification template which means any change in that template automatically influences the content here.
4. Once done, click **Proceed**.

This sends an email notification to the data subject. Securiti also records pausing of deadline in the request audit logs along with the email sent to the data subject. For more information, see Auditing DSR requests.

  

For non-digital or internal requests where the Privacy Central account is not linked to the data subject, you must select a reason for pausing the deadline. Then notify data subjects through their preferred communication channel.

![Request to pause DSR deadline for clarification on Jim John's access request.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-08 at 3.53.53 PM.png)

> [!NOTE]
> Note
> 
> When a request is paused, you cannot publish the DSR report or manually extend the request. The auto extension is also not applicable in this case.

To resume a deadline:

1. Open the request in the DSR Workbench and from the upper right corner, choose **More Actions (3 dots) > ResumeDSR Deadline**.

![DSR Workbench showing a request for personal information sale restrictions and task updates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-09 at 11.52.59 AM.png)
2. On the Resume DSR Deadline popup, mark Send email notification to Data Subject checkbox and click Proceed.

![Form to resume DSR deadline for a data subject request with email notification options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-01-09 at 11.52.13 AM.png)

This sends an email notification to the data subject. Securiti also re-calculates the DSR deadline and records the resuming of the deadline in the audit logs.
