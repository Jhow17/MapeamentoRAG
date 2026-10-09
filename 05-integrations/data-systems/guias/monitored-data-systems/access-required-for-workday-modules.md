---
title: "Access required for Workday modules"
slug: "access-required-for-workday-modules"
updated: 2025-10-31T06:37:37Z
published: 2025-11-03T07:38:02Z
canonical: "helpcenter.securiti.ai/access-required-for-workday-modules"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Access required for Workday modules

Workday supports web service operations associated with different modules. The following web services apply to Securiti.

| Module name | Web services |
| --- | --- |
| Human Resource | > [!NOTE] > **Note** > > For Workday Posture scan to run successfully, you must verify that your user group has all the necessary Permissions for the Human Resource module, even if the Connector is activated for another module e.g. Staffing or Recruiting. - Get Workers - Get Employee - Get Employee Personal Info - Get Employee Related Persons - Get Employee Employement Info - Get Employee Image - Get Worker Profile - Get Organization - Get Worker Event History - Get Worker Photos - Get Workday Account - Get Contingent Worker - Get Contingent Worker Contract Info - Get Contingent Worker Personal Info - Get Change Passport And Visas - Get Change Personal Information - Get Change Government IDs - Get Business Site - Get Change Home Contact Information - Get Change Preferred Name - Get Change Legal Name - Get Previous System Job History - Get Academic Appointee - Get Provisioning Group Assignments - Get Preferred Communication Language - Get Locations - Get Work Shifts - Get External Form I-9 |
| Staffing | - Get workers - Get Applicants - Get Probation period for workers - Get Notice Period for workers - Get Organization - Get worker Documents - Get Positions. - Get Change government IDs - Get Change legal Name - Get Change Licenses - Get Change Other IDs - Get Change passport and visas - Get Change Personal information - Get Change preferred name |
| Recruiting | - Get workers (For Test Connection only) - Get Candidates - Get Applicants - Get Assess Candidates - Get Candidate Attachments - Get Interviews - Get Interview feedbacks - Get Job application additional data - Get background check - Get recruiting agency additional data - Get Job Requisitions - Get job postings - Get job site postings - Get recruiting agencies - Get assign recruiting self-schedule calendars - Get recruiting agency users > [!NOTE] > **Note** > > You cannot use last two web services **Get assign recruiting self-schedule calendars** and **Get recruiting agency users** with Integration System Security Group (Constrained). You must create Unconstrained Security Group to use these two web services. To create Unconstrained Security Group, see [](/v1/docs/integration-details-required-for-workday-authentication). |

See [Activate the Workday (Self-hosted) connector in Securiti](/v1/docs/activate-the-workday-self-hosted-connector-in-securiti) for information on how to activate a module.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
