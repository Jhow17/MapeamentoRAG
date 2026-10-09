---
title: "Connecting Webhooks with Securiti"
slug: "user-defined-webhooks-connectors"
status: "new"
updated: 2026-04-06T05:47:37Z
published: 2026-04-06T08:37:04Z
canonical: "helpcenter.securiti.ai/user-defined-webhooks-connectors"
area: integrations
modulo: webhooks
tipo: guia
data_captura: 2026-10-08
---

# Connecting Webhooks with Securiti

> [!NOTE]
> **Note**
> 
> You must not use the same data system instance name for both cloud and self-hosted webhook connectors.
> 
> 
> 
> Currently, User-Defined (Webhook) connectors use the same connector type ID for both Securiti cloud and self-hosted environments. However, the system requires that each connector instance name be unique within your organizational setup. This uniqueness is based on a combination of internal identifiers such as your account, team, connector type, and the instance name.

You configure user-defined connectors to connect your proprietary data systems to Securiti so you can process DSR requests for personal data they contain.

To configure a user-defined connector:

1. Implement the APIs as described in [Implement APIs for the user-defined connector](/latest/docs/implement-apis-for-the-user-defined-connector).
2. Activate the connector in Securiti with the URL and authentication information for the APIs as described in [Activate the user-defined connector in Securiti](/latest/docs/activate-the-user-defined-connector-in-securiti).

For more information, see [Trigger Node in Workflow module](/latest/docs/trigger-nodes-1) to add the external trigger node for Webhooks.

For more information, see [Managing Webhook URLs](/latest/docs/managing-credentials-managing-webhook-urls) to generate Webhook URLs in Securiti

The only three DSR types supported for a user-defined connector are:

- Access
- Port
- Erasure

For all other DSR request types, you must manually access the data system to process the request.

The Securiti user-defined connectors use the OpenGDPR APIs described in the [Github documentation](https://github.com/opengdpr/OpenDSR/blob/master/specification.md):

## Related

- [Implement APIs for the user-defined connector](/implement-apis-for-the-user-defined-connector.md)
- [Activate the Webhooks connector in Securiti](/activate-the-user-defined-connector-in-securiti.md)
- [Trigger nodes](/trigger-nodes.md)
