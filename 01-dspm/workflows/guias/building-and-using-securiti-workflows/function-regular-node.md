---
title: "Function"
slug: "function-regular-node"
updated: 2026-08-10T10:21:42Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/function-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Function

Function node in a workflow is a versatile component that allows you to write custom code or logic to manipulate data or perform specific actions within the workflow. It serves as a bridge between nodes in the workflow, providing a way to execute JavaScript code. Its versatility and ability to execute custom code make it an essential component in many automation workflows.

This node can be used for a variety of reasons. You can access data from previous nodes in the workflow and apply custom logic to modify, filter, or transform it. You can also use the Function node to handle errors and exceptions by implementing error-catching mechanisms. You can define how the workflow should behave when errors occur, whether it's logging the error, retrying a failed operation, or taking other corrective actions.

#### Security restrictions

Securiti restricts network access and blocks privileged internal functions in the Function node to protect against unauthorized network access, credential misuse, code injection, and other exploit attempts originating from workflow code.

> [!CAUTION]
> Warning
> 
> - Do not use `helpers.requestOAuth2(),` `helpers.updateCredentialsInDb()`, `helpers.getAndUpdateRefreshToken()`, or `helpers.getUpdatedOptionsWithToken()` in your Function node code. These functions are unavailable, and workflows that reference them fail.
> - Do not use `helpers.request()` to send requests to internal or private IP addresses (such as `127.x`, `10.x`, `172.16.x`, `192.168.x`, or `169.254.x` ranges), through a proxy option pointing to an internal address, or through a redirect to a private IP address. These requests return an error.

The Function node now blocks:

- Use of potentially harmful code constructs, including `buffer`, `process`, `eval`, and `wasm`.
- Requests to internal, private, and reserved network ranges, including loopback addresses (`127.0.0.0/8`, `::1`), private IPv4 ranges (`10.0.0.0/8`, `172.16.0.0/12`, `192.168.0.0/16`), IPv6 unique local addresses (`fc00::/7`, `fd00::/8`), link-local addresses (`169.254.0.0/16`, `fe80::/10`), unspecified addresses (`0.0.0.0/8`), carrier-grade NAT (`100.64.0.0/10`), benchmarking and reserved ranges (`198.18.0.0/15`), multicast (`224.0.0.0/4`), reserved/broadcast ranges (`240.0.0.0/4`), and IPv4-mapped IPv6 addresses (`::ffff:x.x.x.x`).
- Requests to Kubernetes service discovery endpoints, whether referenced by the original hostname (`kubernetes.default.svc`), its fully qualified domain name (`kubernetes.default.svc.cluster.local`), a short hostname (`kubernetes.default`), a case-variant form (`KUBERNETES.DEFAULT.SVC`), the GCP metadata hostname (`metadata.google.internal`), or a cluster-internal IP address such as `10.100.0.1`.
- Use of privileged internal helper functions, including `helpers.requestOAuth2`, `helpers.updateCredentialsInDb`, `helpers.getAndUpdateRefreshToken`, and `helpers.getUpdatedOptionsWithToken`.
- Access to `.process` and `.constructor` properties on runtime objects within the Function node sandbox, which could otherwise be used to reach the underlying JavaScript runtime indirectly.
- Server-side request forgery (SSRF) attempts made through the `helpers.request` function, including direct requests to cloud metadata addresses, obfuscated address representations, redirects to internal destinations (including through URL-shortening services), and requests routed to internal destinations via base URL or proxy configuration options.

See the [Node Configuration section](/v1/docs/function) to understand the node properties and their examples.

#### Example use case

As an example, we will create a workflow to manage consent preferences for various communication channels (loyalty, email, mail, SMS) and update corresponding fields in Salesforce based on the user's preferences.

The Consent Management trigger node initiates this workflow when a user updates their preferences in a preference center. The custom javascript in the Function node extracts information from the trigger data, specifically the user’s email address. The IF node then branches the workflow with respect to the consent granted. For example if the consent is granted for email, the records are updated on Salesforce based on the IF node.

The following nodes are being used in this workflow:

1. Consent Management Trigger node
2. Function Node
3. IF Node
4. Salesforce Node

#### Prerequisites

The Function node uses the Javascript code to be executed, so the code must be in Javascript.

#### Creating Consent Management Workflow for Salesforce Integration

1. Start creating the workflow by adding a Consent Management Trigger node and set the trigger type to receive a trigger from the preference center. Refer to the [Consent Management Trigger node](/v1/docs/consent-management) for more detail.
2. Add the Function node to extract the email address from the consent trigger node. In this case, this is how the custom javascript looks like:

![function-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-39ec6e6a-38f7-81c4-e47d-392d41cc82e1.png)
3. Add conditional logic by adding IF nodes to record the consent type. For example if the consent type is email and the consent is granted, the if node leads the workflow to the corresponding node.
4. Add Salesforce nodes to update the record based on the user’s preferences. Refer to the [Salesforce node reference](/v1/docs/salesforce) for more detail.
5. Connect the nodes and execute the workflow. This is how the workflow looks like:

![function-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f44b30aa-4df2-4ffd-5213-3ca8e268f7a2.png)
6. Upon successful execution, the workflow Node will provide a successful response. After the workflow runs successfully, you can access the results in two formats i.e. table view and JSON response.

#### Node configuration

| Parameter |  | Description |
| --- | --- | --- |
| Function | Specify the required javascript code to execute. |
