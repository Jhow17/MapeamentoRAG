---
title: "Acquire authentication credentials in Workday"
slug: "acquire-authentication-credentials-in-workday"
updated: 2026-08-10T20:19:54Z
published: 2026-08-10T20:19:54Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-workday"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in Workday

1. Workday requires the following parameters for Activation:
  - **User** - Your username

> [!WARNING]
> **Important**
> 
> The username follows the format *username@tenant*.
  - **Password** - Your password
  - **Tenant** - Your Workday tenant name.
  - **Host** - Your Workday hostname.
  - **WSDL Version** - WWS (Workday Web Services) version.

> [!NOTE]
> **Note**
> 
> *v35.0* is the default WSDL Version.
  - **Module/Service** - Your supported module
2. To obtain the username, see the create Integration System User in [Integration details required for Workday authentication](/v1/docs/integration-details-required-for-workday-authentication).
3. Obtain the hostname:
  1. Log in to the Workday Sandbox or production Instance.
  2. Search **Public Web Service** in the search box and select it from the results page.
  3. Under **Actions**, click the "Web Services list" and select **View WSDL**.

The WSDL file opens for viewing.
  4. The hostname value appears at the bottom of the file against the **location** element. For example:

`Copylocation="https://hostname/ccx/....)"`
  5. Record the hostname value to use later. For example:

**wd5-impl-services1.workday.com**
4. Workday also supports the OAuth method of Authentication. Use the matching procedure below.

> [!NOTE]
> **Note**
> 
> We expect you to be a Workday System Administrator for OAuth Support.
  1. On your Workday dashboard, search "Register API Client."
  2. On the Register API Client popup, do the following:
    - Enter a name in the Client Name field.
    - Mark the **Authorization Code Grant** radio button in the Client Grant Type.
    - Mark the **Non-Expiring Refresh Tokens** checkbox.
    - Enter the URI in the Redirection URI field.

*Select the URL from the Table below that applies*.

| Cloud | URL |
| --- | --- |
| US | `https://app.securiti.ai/static/activateConnector.html` |
| US1 | `https://app1.securiti.ai/static/activateConnector.html` |
| Canada | `https://app3.securiti.ai/static/activateConnector.html` |
| EU | `https://app.eu.securiti.ai/static/activateConnector.html` |
| Indonesia | `https://app2.securiti.ai/static/activateConnector.html` |
| Australia | `https://app4.securiti.ai/static/activateConnector.html` |
| UAE | `https://app5.securiti.ai/static/activateConnector.html` |
| Mumbai | `https://app6.securiti.ai/static/activateConnector.html` |
| Sovereign deployment | `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html` |
  3. Add scopes from the Scope (Functional Areas) menu. Workday OAuth uses "Workday REST API" and "Custom Objects" as scopes.
    1. Select **Staffing and Organizations and Roles** from Workday REST API.
    2. Select options to suit from the Custom Objects menu based on **Staffing and Organizations and Roles** modules you selected in c (i).

Give Permissions for the objects necessary according to module.
      - Academic Advising
      - Academic Faculty
      - Academic Foundation
      - Accounting Center
      - Action Items and Holds
      - Adaptive Planning
      - Adaptive Planning for Financial Plans
      - Adaptive Planning for the Workforce
      - Admissions
      - Adoption
      - Advanced Close and Consolidation
      - Advanced Compensation
      - Analytical Framework
      - Application: MetadataAccessTestOne
      - Backpack Hub Service
      - Banking and Settlement
      - Benchmarking
      - Benefits
      - Budgets
      - Business Asset Accounting
      - Business Asset Tracking
      - Campus Engagement
      - Candidate Engagement
      - CAN Payroll
      - Capital Projects
      - Career and Development Planning
      - Career Hub
      - Cash Management
      - CCB
      - Cloud Connect for Learning
      - Common Financial Management
      - Contact Information
      - Core Compensation
      - Core Payroll
      - Customer Accounts
      - Customer Central
      - Customer Contracts
      - Customers
      - Duplicate Management
      - Endowment Accounting
      - Expenses
      - Extended Enterprise for Learning
      - Financial Accounting
      - Financial Aid
      - Financial Insight Apps
      - FRA Payroll
      - Grants Management
      - Headcount Planning
      - Headcount Plans
      - Headcount Plans (HCM)
      - Help
      - Implementation
      - Innovation Services
      - Inventory
      - Jobs & Positions
      - Journeys
      - Labor Optimization
      - Learning Core
      - Miscellaneous Payments
      - Onboarding
      - Organizations and Roles
      - Payroll Interface
      - People Analytics
      - People Experience
      - Performance Enablement
      - Personal Data
      - Planning
      - Pre-Hire Process
      - Prism Analytics
      - Procurement
      - Project Billing
      - Projects
      - Project Tracking
      - Public Data
      - PulsePoint (Use with Workday permission only)
      - Recruiting
      - Regulatory Reporting (HCM)
      - Safety Incident Tracking
      - Staffing
      - Student Core
      - Student Financials
      - Student Records
      - Student Recruiting
      - Supplier Accounts
      - Supplier Contracts
      - Suppliers
      - System
      - System Health Dashboard
      - Talent Insight Apps
      - Talent Marketplace
      - Talent Pipeline
      - Tenant Non-Configurable
      - Time Off and Leave
      - Time Tracking
      - Time Tracking Calculations
      - Time Tracking Hub
      - UK Payroll
      - Unions
      - USA Payroll
      - Vaccination Tracking
      - Workday Designer
      - Workday Everywhere
      - Workday Scheduling
      - Worker Profile and Skills
      - Workplace Test Tracking
      - Worktags
  4. After you have created the client, record these for later use:
    - **Client Id**
    - **Client Secret**
    - **Authorization Endpoint**
5. Proceed to [Connecting the Workday (Self-hosted) connector in Securiti](/latest/docs/connecting-the-workday-self-hosted-connector-in-securiti) or [Connecting Workday (Securiti Cloud) with Securiti](/latest/docs/connecting-workday-securiti-cloud-with-securiti).
