---
title: "Obtain permission and authentication credentials in Oracle HCM"
slug: "obtain-permission-and-authentication-credentials-in-oracle-hcm"
updated: 2026-07-20T20:35:49Z
published: 2026-07-20T21:00:00Z
canonical: "helpcenter.securiti.ai/obtain-permission-and-authentication-credentials-in-oracle-hcm"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Obtain permission and authentication credentials in Oracle HCM

Oracle Fusion Cloud (HCM) uses minimum API Permissions based on the module of your choice and Activation Credentials for successful Connector Authentication in Securiti.

## Steps to authenticate credentials in Oracle HCM

Oracle HCM currently supports these modules via the Basic Authentication method:

- Absence Management
- Common
- Compensation
- Global Human Resources
- Global Payroll
- Health and Safety
- Performance Management
- Learning Cloud
- Recruiting
- Talent Management
- Time and Labor
- Wellness

Use the matching procedure below:

> [!WARNING]
> **Important**
> 
> You must add all Permissions for the module you want to use for activating the Connector. Otherwise, Securiti only scans some tables (data) for that module instead of all.
> 
> 
> 
> Furthermore, add the following roles (in the Available in Roles Column) to a new or existing user account you would use for Connector Activation.

1. Select API Permissions for your opted module below. For more information on how to add these Permissions, see [Create Authorized User](https://www.oracle.com/webfolder/technetwork/tutorials/obe/fusionapps/HCM/WorkerRestAPI_OBE_AUTH/html/index.html).

| Module | Table Name | Privilege | Available in Roles |
| --- | --- | --- | --- |
| Absences | Absences &amp; Plan Balances | Use REST Service - Absences Read Only (ORA_ANC_REST_SERVICE_ACCESS_ABSENCES_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Absences | Availability Patterns | Use REST Service - Availability Patterns Read Only (ORA_ANC_REST_SERVICE_ACCESS_AVAILABILITY_PATTERNS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Common | User Accounts | Use REST Service - User Accounts Read Only (ORA_PER_REST_SERVICE_ACCESS_USER_ACCOUNTS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Common | Public Workers | Use REST Service - Public Workers Read Only (ORA_PER_REST_SERVICE_ACCESS_PUBLIC_WORKERS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Common | Tasks | Use REST Service - Tasks Read Only (PER_REST_SERVICE_ACCESS_TASKS_RO_PRIV) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Talent Management | Person Notes | Use REST Service - Person Notes Read Only (ORA_HRT_REST_SERVICE_ACCESS_PERSON_NOTES_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Talent Management | Check-In Documents | Use REST Service - Check-In Documents Read Only (ORA_HRA_REST_SERVICE_ACCESS_CHECK_IN_DOCUMENTS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Talent Management | Questions | Use REST Service - Questions Read Only (HRQ_REST_SERVICE_ACCESS_QUESTIONS_RO_PRIV) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Talent Management | Questionnaires | Use REST Service - Questionnaires Read Only (HRQ_REST_SERVICE_ACCESS_QUESTIONNAIRES_RO_PRIV) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Talent Management | Talent Person Profiles | Use REST Service - Talent Person Profiles Read Only (ORA_HRT_REST_SERVICE_ACCESS_TALENT_PERSON_PROFILES_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Talent Management | Questionnaire Participants | Use REST Service - Questionnaire Participants Read Only (ORA_HRQ_REST_SERVICE_ACCESS_QUESTIONNAIRE_PARTICIPANTS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Wellness | Tracking Services | Use REST Service - Wellness Connector Push (EHW_REST_SERVICE_ACCESS_WELLNESS_CONNECTOR_PUSH_PRIV) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Learning Cloud | Learner Learning Records | Use REST Service - Learner Learning Record Read Only (ORA_WLF_REST_SERVICE_ACCESS_LEARNER_LEARNING_RECORD_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Time and Labor | Time Attributes | Use REST Service - Time Record Groups Read Only (ORA_HWM_REST_SERVICE_ACCESS_TIME_RECORD_GROUPS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Time and Labor | Time Record Groups | Use REST Service - Time Record Groups Read Only (ORA_HWM_REST_SERVICE_ACCESS_TIME_RECORD_GROUPS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Time and Labor | Time Records | Use REST Service - Time Records Read Only (ORA_HWM_REST_SERVICE_ACCESS_TIME_RECORDS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Health and Safety | Incident Kiosks | Use REST Service - Incident Kiosks (PER_REST_SERVICE_ACCESS_INCIDENT_KIOSKS_PRIV) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Health and Safety | Health Surveys | Create Self-Serve Environment Health and Safety Incident (HNS_CREATE_SELF_SERVICE_ENVIRONMENT_HEALTH_AND_SAFETY_INCIDENT_PRIV) | Environment, Health and Safety Manager (ORA_HNS_ENVIRONMENT_HEALTH_AND_SAFETY_MANAGER_JOB) |
| Recruiting | Recruiting Candidates | Use REST Service - Candidates Read Only (IRC_REST_SERVICE_ACCESS_CANDIDATES_RO_PRIV) | Use REST Service - Candidates Read Only (ORA_IRC_REST_SERVICE_ACCESS_CANDIDATES_RO) |
| Compensation | Salaries | Use REST Service - Salaries Read Only (ORA_CMP_REST_SERVICE_ACCESS_SALARIES_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Performance Management | Performance Evaluations | Use REST Service - Performance Evaluations Read Only (ORA_HRA_REST_SERVICE_ACCESS_PERFORMANCE_EVALUATIONS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Performance Management | Performance Goals | Use REST Service - Performance Goals Read Only (ORA_HRG_REST_SERVICE_ACCESS_PERFORMANCE_GOALS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Global Payroll | Payroll Relationships | Use REST Service - Payroll Relationships Read Only (ORA_PAY_REST_SERVICE_ACCESS_PAYROLL_RELATIONSHIPS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Global Payroll | Flow Patterns | Use REST Service - Payroll Flow Patterns Read Only (ORA_PAY_REST_SERVICE_ACCESS_PAYROLL_FLOW_PATTERNS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Global Payroll | Element Entries | Use REST Service - Element Entries Read Only (ORA_PAY_REST_SERVICE_ACCESS_ELEMENT_ENTRIES_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Global Payroll | Organization Payment Methods LOV | Use REST Service - Payroll Reference Data Lists of Values (ORA_PAY_REST_SERVICE_ACCESS_PAYROLL_REFERENCE_DATA_LOVS) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Global Payroll | Payslips | Use REST Service - Payslips Read Only (ORA_PAY_REST_SERVICE_ACCESS_PAYSLIPS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Global Payroll | Personal Payment Methods | Use REST Service - Personal Payment Methods Read Only (ORA_PAY_REST_SERVICE_ACCESS_PERSONAL_PAYMENT_METHODS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Global Human Resources | Allocated Checklists | Use REST Service - Allocated Checklists Read Only (ORA_PER_REST_SERVICE_ACCESS_ALLOCATED_CHECKLISTS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Global Human Resources | Areas of Responsibility | Use REST Service - Areas of Responsibility Read Only (ORA_PER_REST_SERVICE_ACCESS_AREAS_OF_RESPONSIBILITY_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Global Human Resources | Document Records | Use REST Service - Document Records Read Only (ORA_PER_REST_SERVICE_ACCESS_DOCUMENT_RECORDS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Global Human Resources | Workers | Use REST Service - Workers Read Only (PER_REST_SERVICE_ACCESS_WORKERS_RO_PRIV) | Use REST Service - Worker Details Read Only (ORA_PER_REST_SERVICE_ACCESS_WORKER_PERSON_RO) |
| Global Human Resources | Organization Payment Methods LOV | Use REST Service - Payroll Reference Data Lists of Values (ORA_PAY_REST_SERVICE_ACCESS_PAYROLL_REFERENCE_DATA_LOVS) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Global Human Resources | Public Workers | Use REST Service - Public Workers Read Only (ORA_PER_REST_SERVICE_ACCESS_PUBLIC_WORKERS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Global Human Resources | Actions Reasons LOV &amp; Actions LOV | Use REST Service - Person Reference Data Lists of Values (ORA_PER_REST_SERVICE_ACCESS_PERSON_REFERENCE_DATA_LOVS) | Human Resource Specialist (ORA_PER_HUMAN_RESOURCE_SPECIALIST_JOB) |
| Global Human Resources | Payroll Relationships | Use REST Service - Payroll Relationships Read Only (ORA_PAY_REST_SERVICE_ACCESS_PAYROLL_RELATIONSHIPS_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |
| Global Human Resources | Document Delivery Preferences | Use REST Service - Document Delivery Preferences Read Only (ORA_PER_REST_SERVICE_ACCESS_DOCUMENT_DELIVERY_PREFERENCES_RO) | Human Capital Management Integration Specialist (ORA_HRC_HUMAN_CAPITAL_MANAGEMENT_INTEGRATION_SPECIALIST_JOB) |

1. Record these parameters for later use:
  - Username
  - Password
  - Host
  - Module
2. Proceed to [Connect Oracle HCM connector with](/latest/docs/connect-oracle-hcm-connector-with-securiti) Securiti.
