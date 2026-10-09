---
title: "Using Validation Workbench to review and validate classifications"
slug: "using-validation-workbench-to-review-and-validate-classifications"
updated: 2026-03-19T18:28:53Z
published: 2026-03-19T18:28:53Z
canonical: "helpcenter.securiti.ai/using-validation-workbench-to-review-and-validate-classifications"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using Validation Workbench to review and validate classifications

**Scenario**

As a Data Owner, you are responsible for ensuring that sensitive data is accurately classified across your organization’s databases. Manually reviewing every data element is prone to errors. With the Validation Workbench, you can quickly review and validate a random sample of classified data, confirm or correct labels, and monitor classification accuracy through analytics dashboards. This streamlines your validation process and boosts confidence in automated classifications.

## Overview

The Validation Workbench lets you review and validate the data classifications. Based on your feedback, it provides insights into the precision of detected classifications.

Once data is available from a discovery scan, you can create a validation workbench session. Within a session, you can review detections across files, inspect the detected evidence, and see related details such as the data element, file name, file location, and data system instance. You can then confirm the classification, reject it, or update it manually when the detected data element is incorrect.

This process reduces the need to review every detection, helping you focus on targeted improvements and saving time.

You can use the Validation Workbench for:

- Structured data: Review, validate, and update classifications when needed, and classifying similar columns in bulk with AI Tuning.
- Unstructured data**:** Review detections across files, inspect evidence, and update or reject classifications as needed.

> [!NOTE]
> Note
> 
> When creating a **Validation Workbench** session, consider the following:
> 
> - You must have one or more discovery scans completed for your data system. For more information, see [Discovery scans](/latest/docs/discovery-scans).
> - You must store sample data in Private Cloud Storage (PCS) to use Validation Workbench features. Enabling PCS ensures that sample data is available for analysis. For more information, see [Configure Private Cloud Storage](/latest/docs/system-settings-configuring-private-cloud-storage).
> - You can configure multiple PCS instances in Securiti. Each data system is linked to its own PCS instance, and Securiti automatically uses the correct PCS instance when processing cases.
> - The multi-org feature is supported by the Validation Workbench. Sessions and their analytics are organization-sensitive. For more information, see [Changing your Organization](/latest/docs/system-settings).

## Understanding roles and permissions for Validation Workbench sessions

You can create a validation session to review, edit, and validate classifications for the data. These sessions let you add users as co-owners so they can review and edit classifications based on their assigned permissions.

Securiti lets you create new sessions, resume existing ones to review additional classifications, and view previously validated classifications. The ability to create a new Validation Workbench session depends on the user role. The table below outlines the role-specific permissions.

| User Role | Permission to create a new session | Description |
| --- | --- | --- |
| Super Admin | Yes | **Super Admins** and **Organization Admins** have full control over session management. Using the **Edit Session Details** option, they can add themselves as owners of any session and delete it if needed. |
| Organization Admin | Yes |
| Module Owner | Yes | - |
| Data Protection Officer | No | Users with the **DPO** role cannot create or delete sessions, even if they are assigned as session owners by another user. |
| Operator | Yes | - |
| User | No | - Users with the **User** role must be explicitly added as **Session Owners** by an authorized user. - Users with the **User** role cannot create or delete sessions. |

> [!NOTE]
> Note
> 
> - By default, the creator of a session in the Validation Workbench is designated as the **Session Owner**.
> - Users with permission to edit session details can assign themselves as **Session Owners** during session editing, which gives them full access to session options. This capability does not apply to users with the **User** role.
