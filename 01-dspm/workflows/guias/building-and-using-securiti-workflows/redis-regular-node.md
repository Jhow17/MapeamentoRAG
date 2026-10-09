---
title: "Redis"
slug: "redis-regular-node"
updated: 2025-10-30T19:07:33Z
published: 2025-11-03T07:40:59Z
canonical: "helpcenter.securiti.ai/redis-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# Redis

Redis is an in-memory data structure store. Think of it as a super-fast database optimized for specific use cases. It's commonly used as a cache to temporarily store frequently accessed data, speeding up applications or to facilitate communication between different parts of a system.

A Redis node in your Workflow automation tool provides a way to interact with a Redis instance to perform the following key actions:

- Remove a specific data item (and its associated value) from Redis.
- Retrieve the value stored under a specific key in Redis
- Get generic information about the connected Redis server, such as version, memory usage, uptime.
- Find keys in Redis that follow a certain patternStore a value in Redis under a specific key.

Refer to the [Node configurations section](/v1/docs/redis) to understand the node working and properties.

#### Prerequisites

You must have valid AWS credentials set to use the node. See [the setting up credentials section.](/v1/docs/redis)

#### Example use case

As an example, let’s create a Workflow that prevents duplicate lead records from cluttering your Salesforce instance. The Workflow is triggered whenever a new Lead record is created in Salesforce. The **Salesforce trigger node** fetches the relevant data from the newly created lead record, such as the lead's email address.

The Redis node then attempts to retrieve the value associated with this key from the Redis store. If a value is returned by the Get Key operation (indicating an existing lead with the same identifier), the Workflow ends (no duplicate created). If not, Workflow proceeds to create a unique identifier for the new lead record using the Redis node to set the value. This serves as a marker to prevent future duplicates with the same email address.

The following Nodes are used in this Workflow:

1. [Salesforce Trigger Node](/v1/docs/salesforce)
2. Redis Node
3. [IF Node](/v1/docs/if)

#### Optimizing Salesforce data quality with a Redis-integrated workflow

1. Add Salesforce trigger node that triggers on the set interval and fetches the data of the leads.
2. Add a Redis node to check if there is already existing data with the fetched ID on Redis store.
3. Add an If node to add condition logic so that if the data exists the Workflow stops, and if it doesn’t, a Redis node sets the value of the key by the retrieved value.

![Screenshot_2024-03-05_at_8_15_58_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-846f4b9b-4846-436a-3d51-aafed7629555.png)
4. Connect the Nodes and execute the Workflow.

![Screenshot_2024-03-05_at_8_15_27_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d424b69c-f1d5-6378-03ac-b75065c89439.png)
5. Once the Workflow is successfully executed, you can view both table view and JSON response.

![Screenshot_2024-03-05_at_8_10_30_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-828bc58b-3513-69bc-0057-26265dcbd2e2.png)

#### Node configurations

| Parameters |
| --- |
| Credentials | Choose or create credentials to access the Redis instance. Refer to the [setting up credentials section](/v1/docs/redis) to set up new credentials. |
| Operation | Delete | Delete a key from Redis |
| Get | Returns the value of a key from Redis |
| info | Returns generic information about the Redis instance |
| Keys | Returns all the keys matching a pattern |
| Set | Sets the value of a key in Redis |
| Key | The name of the Redis key to operate on |
| Key Type | For Get and Set operations, the type of key to get or set |
| Automatic | For Get, requests the type before requesting the data (slower). For Set, tries to determine the key type automatically based on the data |
| Hash | Data in key is of type "hash" |
| String | Data in key is of type "string" |
| List | Data in key is of type "list" |
| Sets | Data in key is of type "sets" |
| Key Pattern | For Keys operations, sets the pattern for the keys to return |
| Name | For Get operations, the name of the property to write received data to, for example "data.person[0].name" |
| Value | The value to write in Redis |
| Expire | For Set operations, enables timeout for the key |
| TTL | When Expire is enabled, sets the number of seconds before key expiration |

#### Setting up credentials

Fetch the values from the Redis management console and create credentials for the following fields.

| Parameters | Description |
| --- | --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself. |
| Password | Specify the password that shows on the management console, under user settings. |
| Host | Specify the host that shows on the management console, under user settings. |
| Port | Specify the port that shows on the management console, under user settings. |

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
