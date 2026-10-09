---
title: "Grant permissions and obtain credentials in Zendesk"
slug: "grant-permissions-and-obtain-credentials-in-zendesk-self-hosted"
updated: 2026-06-27T08:15:10Z
published: 2026-06-27T08:15:10Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-zendesk-self-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Zendesk

Use the matching procedure below to grant Zendesk (Self-hosted) Connector minimum Permissions and acquire Authentication Credentials.

1. The Connector uses READ and WRITE scopes to request access for the following objects in Zendesk (Self-hosted) data systems:

See [Zendesk's official documentation](https://support.zendesk.com/hc/en-us/articles/4408845965210) for more information.

> [!WARNING]
> **Important**
> 
> You don't need to specify any granular level scope request (as mentioned in the official documentation) because the Connector uses read scope for all objects by default.
  1. AccountSettings
  2. Automations
  3. Brands
  4. CustomObjects
  5. GroupMemberships
  6. Groups
  7. Holidays
  8. Macros
  9. OrganizationFields
  10. OrganizationMemberships
  11. Organizations
  12. OrganizationSubscriptions
  13. PostComments
  14. Posts
  15. SatisfactionRatings
  16. Schedules
  17. Sessions
  18. SharingAgreements
  19. SupportAddresses
  20. SuspendedTickets
  21. TicketFields
  22. TicketForms
  23. Topics
  24. Triggers
  25. UserFields
  26. UserIdentities
  27. Users
  28. Views
  29. ActivityStream
  30. AppLocations
  31. ArticleAttachments
  32. Articles
  33. Attachments
  34. Collaborators
  35. CustomAgentRoles
  36. JobStatus
  37. Locales
  38. MonitoredTwitterHandles
  39. Requests
  40. SlaPolicies
  41. TicketAudits
  42. TicketMetricEvents
  43. TicketMetrics
  44. UserRelatedInformation
2. Log in to your Zendesk Administrator account.
3. On the left sidebar, click the gear icon for Settings.
4. In the Channels area, click **API**.
5. On the Zendesk API page, click the **OAuth Clients** tab.
6. Near the right side of the page, click **+** to create a new OAuth client.

![C00048.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8a0843bb-cf9b-adc2-37a9-7830f7dc03ee.png)
7. Enter the following information:
  - Client Name
  - Description
  - Company
  - Logo
  - Unique identifier
8. In the Redirect URLs box, enter one of the following URLs:
  - US Cloud: `https://app.securiti.ai/static/activateConnector.html`
  - US1 Cloud: `https://app1.securiti.ai/static/activateConnector.html`
  - Canada Cloud: `https://app3.securiti.ai/static/activateConnector.html`
  - EU Cloud: `https://app.eu.securiti.ai/static/activateConnector.html`
  - Indonesia Cloud: `https://app2.securiti.ai/static/activateConnector.html`
  - Australia Cloud: `https://app4.securiti.ai/static/activateConnector.html`
  - UAE Cloud: `https://app5.securiti.ai/static/activateConnector.html`
  - Mumbai Cloud: `https://app6.securiti.ai/static/activateConnector.html`
  - KSA Cloud: `https://app7.securiti.ai/static/activateConnector.html`
  - Qatar Cloud: `https://app8.securiti.ai/static/activateConnector.html`
  - Sovereign deployment: `https://&lt;sovereign_deployment_portal_host&gt;/static/activateConnector.html`

![C00049.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-57a8f7b2-a300-f253-ce4e-92dd2ccd4ba5.png)
9. Click **Save**.

Zendesk alerts you to store the secret it will show you. It only shows you the secret once. If you lose it, you must reset it.

![C00050.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5aa22095-86e2-0ab2-585c-bcca81ebd7a6.png)
10. Click **OK**.
11. Record the text in the Unique Identifier and Secret boxes to use later.

![C00051.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-21344a55-5250-2339-52c3-a33d933b0b55.png)
12. Proceed to [Connecting Zendesk with Securiti](/latest/docs/connecting-zendesk-with-securiti).
