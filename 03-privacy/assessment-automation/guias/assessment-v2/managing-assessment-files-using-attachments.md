---
title: "Managing assessment files using Attachments"
slug: "managing-assessment-files-using-attachments"
updated: 2026-07-20T10:29:51Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/managing-assessment-files-using-attachments"
area: privacy
modulo: assessment-automation
tipo: guia
data_captura: 2026-10-08
---

# Managing assessment files using Attachments

As you conduct an assessment, you can use file attachments to deliver in-depth information to the partners with whom you share the assessment, and also to your team members inside your organization. You can attach files to the assessment as a whole, and also to the external and internal responses to individual questions.

Securiti only allows you to upload these file formats:

```plaintext
Text and Configuration Files: .txt, .json, .xml, .rtf

Document Files: .csv, .pdf, .doc, .docx, .xls, .xlsx, .ppt, .pptx

Media Files: .mp3, .wav, .ogg, .jpg, .jpeg, .png, .webp, .gif, .bmp, .mp4, .avi, .mov, .mkv

Compressed Files: .rar, .zip
```

## Prerequisites

### 

You must have the respondent or reviewer role depending on what section of the assessment you're accessing and where you're in the [assessment lifecycle](/v1/docs/tracking-assessment-stages). The table below shows assessment area, user permission, and workflow stage when uploading files.

| Assessment Area | Logged in as (User) | Stage |
| --- | --- | --- |
| Question | Reviewer or Respondent | Not Started or In Progress |
| Notes | Reviewer or Respondent | Not Started or In Progress |
| Set a Flag or Flag for Review | Reviewer | In Review |
| Attachments panel | All participants | All stages |

## Adding attachments to different assessment areas

### 

> [!NOTE]
> **Note**
> 
> See information on *file formats above* before proceeding.

- To insert attachment in a question:
  1. Click **Add Attachment** near the response area.
  2. On the Upload popup, choose the file to upload or drag and drop it.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot%202026-07-20%20at%201.38.18%E2%80%AFPM.png)
  3. (Optional) Click **Notes** icon below the response area, and repeat step 2.
- To insert attachment when setting or resolving a flag:
  1. Click the **Flag Question** icon below the response area.
  2. In Flag Description, enter your comments and click **Add Attachment**.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot%202026-07-20%20at%201.41.24%E2%80%AFPM.png)
  3. (Optional) When resolving a flag, enter your comments in the Explanation box then click **Add Attachment** and upload the file as usual.

Adding risk attachment is done via the Risk Detail page. Securiti shows you the attachment option when performing the risk remediation workflow. For more information, see [Risk details](/latest/docs/navigating-the-risk-details-page#pending-actions).

> [!NOTE]
> Note
> 
> For risk, only risk users can download attachments.

## Navigating the Attachments panel

### 

To access the attachments panel:

1. In the assessment header click **Attachments**.
2. Use the search bar to find attachments. Use the panel options to manage attached files:

> [!NOTE]
> **Note**
> 
> You cannot remove files attached to responses or internal responses unless you are the question editor. If you are the assessment owner and you do need to remove such an attachment, you can reassign the question to yourself, then remove the attachment.
> 
> You can also search for attachments using the 'file search' on the panel.
  - Click **Assessment** tab to view attachments. The **+ Add Attachments** is only visible if your user is assigned to the assessment.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-20 at 2.08.43 PM.png)
  - Click **Question** tab to view one or more attachments at a question(s) level. Securiti differentiates using color graded “pills” for Response, Notes, Flag, and Risk.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-20 at 12.39.42 PM(1).png)

Click **Move to Question** to jump to that question.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-20 at 12.41.05 PM.png)
  - To archive a file, click **Options** (three vertical dots) **>** **Archive**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-20 at 12.40.19 PM.png)
  - Toggle **Show archived files** to show file(s). You can choose to permanently delete or unarchive it.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-07-20 at 12.38.58 PM.png)
3. Near the upper right corner, click **Download All** to send a zip file containing all attachments at your email address.

## Private Cloud Storage support for Assessment Automation

### 

You can configure Private Cloud Storage or PCS to securely store assessment file attachments, including sensitive data related to completed assessments. When private cloud storage is enabled, all assessment-related files, such as attachments or evidence, are stored in the organization's designated storage account (e.g., AWS S3, Azure Files, or Google Cloud Storage).

Private Cloud Storage salient features:

- Supports saving assessments
- Offered as an On-premises service.
- Supports AWS PrivateLink–based connectivity (not covered under default PCS license and billed separately). This enables private communication between the customer’s AWS storage (for example, S3) and the SaaS tenant without traversing the public internet.
- By default, PCS communicates over the public internet. When AWS PrivateLink is configured, traffic is routed privately within AWS and does not traverse the public internet.

For more information, see the following topics:

- [Creating questions in Assessment Template Builder](/v1/docs/creating-questions-in-assessment-template-builder)
- [Answering assessment questions in Securiti](/v1/docs/answering-assessment-questions-in-securiti)
- [Understanding Workflow Stages and assessment use cases](/v1/docs/understanding-workflow-stages-and-assessment-use-cases)
- [Configuring Private Cloud Storage](/v1/docs/system-settings-configuring-private-cloud-storage)

## Related

- [Answering assessment questions in Securiti](/answering-assessment-questions-in-securiti.md)
