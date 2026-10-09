---
title: "Assign permissions to pre-defined role in Elasticsearch"
slug: "assign-permissions-to-pre-defined-role-in-elasticsearch-en"
updated: 2026-07-04T22:22:56Z
published: 2026-07-04T22:22:56Z
canonical: "helpcenter.securiti.ai/assign-permissions-to-pre-defined-role-in-elasticsearch-en"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Assign permissions to pre-defined role in Elasticsearch

**Note**

You must assign permissions to the predefined role linked to the Elasticsearch user.

Perform the following steps to assign permissions and roles to an existing or new Elasticsearch user.

1. Assign the **viewer** role to the user.
  - To assign the viewer role to the existing user, use the PUT request. See the example below.
  - PUT /_security/user/<user_name> { "roles" : [ "viewer" ], }
  - To assign the viewer role to the new user, use the POST request. See the example below.
  - POST /_security/user/<user_name> { "password" : "<password>" "roles" : [ "viewer" ], }
2. Assign the following permissions to the role:
  - read
  - view_index_metadata

- **Note**
- You can assign these permissions to either:
  - **Viewer** role that has already assigned these permissions or
  - **Custom** role.
- To create a custom role, see the step 3.

1. If you want to create a custom role for the specific indices, use the POST request. See the example below.

- POST /_security/role/<role_name> { "cluster": ["all"], "indices": [ { "names": [<list of specific indices on which role will be applied>], "privileges": ["read", "view_index_metadata"] } ] } ------------------ EXAMPLE ------------------ POST /_security/role/<role_name> { "cluster": ["all"], "indices": [ { "names": ["my_index1", "my_index2"], "privileges": ["read", "view_index_metadata"] } ] }

1. Proceed to [Acquire authentication credentials in Elasticsearch](/latest/docs/acquire-authentication-credentials-in-elasticsearch).
