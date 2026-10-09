---
title: "XML"
slug: "xml-regular-node"
updated: 2025-10-30T19:09:10Z
published: 2025-11-03T07:40:08Z
canonical: "helpcenter.securiti.ai/xml-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# XML

An XML node in the Workflows module allows the conversion of data from JSON to XML and vice versa as per your Workflow’s requirements. You can also provide additional attributes for more specific conversion such as the attribute key, character key, explicit array etc.

See the Node Configurations section to understand the node working and properties.

#### Example use case

As an example, let’s consider a use case where your company has a legacy system that only accepts and processes data in XML format. You need to fetch data from a modern API that provides responses in JSON format. A Workflow can act as an intermediary, converting the JSON data into the required XML format for seamless integration.

The Workflow begins with an **HTTP Request node** that initiates an API call to the external service, fetching the required data in JSON format. An XML node transforms the JSON response into a well-structured XML document ensuring the generated XML adheres to any specific syntax requirements of the legacy system. An HTTP Request node then sends the generated XML payload to the legacy system's API endpoint. This Workflow automates the conversion and transmission process, reducing manual effort and potential errors.

The following Nodes are used in this Workflow:

- HTTP Request Node
- XML Node

#### Integrating with legacy systems using XML Node

1. Add the HTTP request node that fetches the data in JSON format.
2. Use the XML node to convert the fetched data into XML format for further processing.
3. Add the HTTP request to provide the fetched (xml) data as the payload.
4. Connect the Nodes and execute the Workflow.
5. Once the Workflow is executed, you can view the response in both JSON and table view.

#### Node configurations

| Parameters |
| --- |
| Mode | - JSON to XML - XML to JSON |
| Property Name | Name of the property that contains the data to be converted |
| Options | Allow Surrogate | Enable to allow the use of characters from the Unicode surrogate blocks |
| Attribute Key | Prefix to use to access the attributes |
| cdata | Enable to wrap text Nodes instead of escaping them when necessary. Ignored when not necessary |
| Character key | Prefix to use to access the character content |
| Headless | Enable to omit the XML header |
| Explicit Array | Enable to always put child Nodes in an array. When disabled, an array is only created if there is more than one node. |
| Root Name | The root element name to be used |
| Explicit Root | Enable to get the root node in the resulting object |
| Ignore Attributes | Enable to ignore all XML attributes, and only create text Nodes |
| Merge Attributes | When Ignore Attributes is disabled, enable to merge attributes and child elements as properties of the parent, instead of keying attributes off of a child attribute object |
| Normalize | Enable to trim white space inside text Nodes |
| Normalize Tags | Enable to normalize all tag names to lower case |
| Trim | Enable to trim white space at the beginnings and ends of text Nodes |

A series of connected nodes to automate a process. The Data System and Connector nodes in a workflow carry different operations of Securiti data systems. See Building and using workflows, for more information.

Node configurations are the essential settings and characteristics that define how each node works in the Workflows module. These details cover everything from basic operations to specific features needed for the functioning of each node. Since nodes have different purposes and functions, their configurations vary from node to node to ensure they work smoothly together in a workflow.

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
