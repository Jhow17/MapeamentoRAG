---
title: "G Suite Google Calendar (Securiti Cloud)"
slug: "g-suite-google-calendar-securiti-cloud-connectors-1"
status: "new"
updated: 2026-09-30T10:25:20Z
published: 2026-09-30T10:25:49Z
canonical: "helpcenter.securiti.ai/g-suite-google-calendar-securiti-cloud-connectors-1"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# G Suite Google Calendar (Securiti Cloud)

Google Calendar, part of the Google Workspace, is a powerful scheduling and time management tool. It lets you create, manage, and share events, appointments, and meetings across teams or organizations. It handles structured data, such as event details, attendee lists, and calendar entries, providing users with an organized view of their time. G Suite Google Calendar connector lets you scan and secure this data in Securiti

G Suite Google Calendar falls under [Monitored, Unstructured data systems](/latest/docs/managing-data-system-connectors).

### Supported connector type and module

| Connector type | Module supported |
| --- | --- |
| G Suite Google Calendar (Securiti-Cloud) | Breach Analysis |

### Supported authentication methods

For Breach Analysis, the OAuth-based authentication method is supported.

### Prerequisites for configuring the G Suite Google Calendar connector

#### 1. Admin access

- You must be an admin for your Google account to create projects and allow scopes.
- You must have the admin role in your Securiti accounts.

#### 2. Enable APIs in Google Workspace

In the Google Workspace account, enable the following APIs:

- Google Calendar API
- Admin SDK API

#### 3. Use cases and permissions for Google Calendar

This section covers use cases and permissions required for the G Suite Google Calendar Securiti cloud connector.

#### Use case and permissions

Use the table below for permissions and use cases if you are not using a custom role.

| Use case | Permissions | Explanation of use case |
| --- | --- | --- |
| Data Subject Requests (DSR) Automation | **OAuth scopes:** ```plaintext https://www.googleapis.com/auth/gmail.readonly, https://www.googleapis.com/auth/admin.directory.customer.readonly, https://www.googleapis.com/auth/admin.directory.resource.calendar.readonly, https://www.googleapis.com/auth/drive.metadata.readonly, https://www.googleapis.com/auth/admin.directory.domain.readonly, https://www.googleapis.com/auth/drive.readonly, https://www.googleapis.com/auth/calendar.readonly, https://www.googleapis.com/auth/calendar.events.readonly, https://www.googleapis.com/auth/admin.directory.user.readonly, https://www.googleapis.com/auth/drive.photos.readonly, https://www.googleapis.com/auth/admin.directory.group.readonly ``` | These permissions build the Personal Data Index for DSR Automation. |

### Connect the G Suite Google Calendar connectors with Securiti

This section covers the methods to integrate your G Suite Google Calendar with Securiti using the cloud connector.

#### Steps to connect the G Suite Google Calendar ( Securiti cloud) connector with Securiti

To activate the G Suite Google Calendar connector, perform the procedures in the following topics:

1. [Prerequisites and obtaining authentication credentials in Google apps](/latest/docs/g-suite-google-calendar-connectors-prerequisites-and-obtaining-authentication-credentials-in-google-apps).
2. [Connecting Google Calendar (Securiti cloud) with Securiti](/latest/docs/new-ui-connecting-google-calendar-securiti-cloud-with-securiti).
3. [Configuring General permissions for G Suite Google Calendar](/latest/docs/configuring-general-permissions-for-g-suite-google-calendar)

**Additional resources**

- [Fulfilling DSR requests for G Suite Google Calendar](/latest/docs/fulfilling-dsr-requests-for-g-suite-google-calendar)
