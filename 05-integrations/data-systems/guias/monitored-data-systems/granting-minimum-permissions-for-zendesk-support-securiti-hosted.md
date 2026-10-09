---
title: "Granting minimum permissions for Zendesk Support (Securit-Cloud)"
slug: "granting-minimum-permissions-for-zendesk-support-securiti-hosted"
updated: 2026-06-27T09:00:54Z
published: 2026-06-27T09:00:54Z
canonical: "helpcenter.securiti.ai/granting-minimum-permissions-for-zendesk-support-securiti-hosted"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Granting minimum permissions for Zendesk Support (Securit-Cloud)

1. Zendesk Connector uses *scope=read* when requesting access which means READ access for the following objects in Zendesk:

See [Zendesk's official documentation](https://support.zendesk.com/hc/en-us/articles/4408845965210) for more information.

> [!WARNING]
> **Important**
> 
> You don't need to specify any granular level scope request (as mentioned in the official documentation) because Zendesk uses read scope for all objects by default.
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
  21. Tickets
  22. TicketComments
  23. TicketFields
  24. TicketForms
  25. Topics
  26. Triggers
  27. UserFields
  28. UserIdentities
  29. Users
  30. Views
  31. ActivityStream
  32. AppLocations
  33. ArticleAttachments
  34. Articles
  35. Attachments
  36. Collaborators
  37. CustomAgentRoles
  38. JobStatus
  39. Locales
  40. MonitoredTwitterHandles
  41. Requests
  42. Requests_Collaborators
  43. SlaPolicies
  44. TicketAudits
  45. TicketMetricEvents
  46. TicketMetrics
  47. Ticket_Collaborators
  48. Ticket_Followers
  49. Ticket_Followups
  50. Tickets_Macros
  51. Tickets_SatisfactionRatings
  52. Tickets_Tags
  53. Tickets_Viasources
  54. UserRelatedInformation
2. Proceed to [Register an application in Zendesk Support (Securiti Cloud)](/latest/docs/register-an-application-in-zendesk-support-securiti-hosted).
