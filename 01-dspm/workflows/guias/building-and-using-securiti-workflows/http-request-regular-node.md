---
title: "HTTP Request"
slug: "http-request-regular-node"
updated: 2026-01-16T06:14:33Z
published: 2026-01-16T06:14:33Z
canonical: "helpcenter.securiti.ai/http-request-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# HTTP Request

The HTTP request node lets you make HTTP requests to query data from any app or service with a REST API. This node basically lets you create an API request by providing the API URL, request body parameters and headers.

### Example Use Case

As an example, we are creating a workflow that generates a [RoPA report](/v1/docs/creating-and-customizing-records-of-processing-activities-ropas) using the POST API endpoint. Every time any process is updated in the catalog, a new RoPA report is generated. This use case requires the following two nodes:

1. Data Maps trigger node
2. HTTP Request node

> [!NOTE]
> **Note**
> 
> Refer to the [Node Configuration section](/v1/docs/http-request) to understand the node parameters and descriptions.

#### Prerequisites

To make an API call using the HTTP request node, you must have the following information:

- API Endpoint URL
- Headers
- Request body (if any)
- Query Parameters (if any)

#### Generating a RoPA report via API endpoint

1. Fill up all the fields according to your requirements as shown below:

![HTTP-req-node-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae0a1ac1-efe5-a773-cf1f-a86d6ddd8456.png)
2. Add the details in the Data Map trigger node as per your requirement. Refer to [Data Maps](/v1/docs/data-maps) for details.
3. Connect the nodes to execute the workflow:

![HTTP-req-node-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0c1d8345-d722-e853-97fd-fbcd260bb15e.png)
4. Execute the workflow and on any event trigger, the workflow node provides a successful response. Once the workflow is successfully executed, you can view both table view and JSON response. This is how the success response looks like.

![HTTP-req-node-3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fc65aaff-5515-fb11-11ea-5744e1759550.png)

### Node Configuration

#### Parameters

In order to fill up the fields in the HTTP request node, look at the following table for details about the properties:

| Parameters |
| --- |
| Basic Auth/Digest Auth/Header Auth/OAuth2 | Select the credentials from the drop down list. If you do not have a list, select the Create New option to create a set of credentials. See the Set up Credentials section to see the steps. |
| Credentials Type | Basic Auth | Select this authentication type if you have username and password to log into the server. |
| Digest Auth | Select this authentication type if you have username and password to log into the server and the credentials are set in an encrypted form. |
| Header Auth | Select this authentication type if a user agent is used to authenticate with a server. |
| OAuth2 | Select this authentication type if you have OAuth token (client secret, key) to log into the server. |
| None | Select this option if no authentication is required to use the API. |
| Request Method | DELETE | Select this method if the API requests that the origin server delete the resource identified by the Request-URI. |
| GET | Select this method if the API is used to retrieve information from the given server using a given URI. |
| HEAD | Select this method if the API is similar to GET method but without any response body. |
| PATCH | Select this method if the API is used to update an already existing information. |
| POST | Select this method if the API is used to send data to a server to create/update a resource. |
| PUT | Select this method if the API updates an instance of a resource by replacing the existing resource with the resource provided in the request body. |
| URL | Add the address that allows you to access an API and its various features. For example, *https://app.securiti.ai/privaci/v1/admin/data_map/process/export*. |
| Ignore SSL Issues | Enable this to connect even if SSL certificate validation is not possible. |
| Response Format | File | Select this option if you want to get the response of the API in the form of a file. The maximum file size allowed for uploading via the node is 100 MB. |
| JSON | Select this option if you want to get the response of the API in JSON form. |
| String | Select this option if you want to get the response of the API in the form of string. |
| JSON/RAW Parameters | Turn this toggle on if the query or body parameters should be set using key value pairs or JSON/RAW. |
| **Options (Optional)** |
| Full Response | Select this option if you want full response data to be returned instead of only the body. |
| Ignore Response Code | Select this option when you want the response to be returned for other response codes as well instead of just successful responseAdd the HTTP proxy option. |
| Proxy | Add the HTTP proxy option. |
| Timeout | Specify the time in ms to wait for the server to send the response headers before aborting the request. |
| Headers | Use this option to include request headers. Headers contain metadata about your request. For example: {"X-API-KEY": "xxxxxxxxxxxx","X-API-SECRET": "xxxxxxxxxx","X-TIDENT": "xxxxxxxxxx"} |
| Name | Specify the name of the header. |
| Value | Specify the value of the header. |
| Query Parameters | Use this option to include query parameters. Query parameters are usually used as filters or searches on your query. |
| Name | Specify the name of the query parameter. |
| Value | Specify the value of the query parameter. |

#### Set up credentials

Refer to this section to understand the authentication types and setting up credentials for all the authentication types.

#### Basic Authentication/Digest Authentication

To set up credentials for basic/digest authentication select the authentication type in the authentication option and select **Create new** from the menu against **Basic Auth/Digest Auth**.

| Parameters | Description |
| --- | --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself. |
| User | Specify the username for the app or service your HTTP Request is targeting. |
| Password | Specify the password for the app or service your HTTP Request is targeting. |
| Nodes with access | Add the nodes who can access using the credentials and mark the checkbox to select them. |

#### Header Authentication

To set up credentials for header auth, select the authentication type in the authentication option and select **Create new** from the menu against **Header Auth**.

| Parameters | Description |
| --- | --- |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself. |
| Name | Specify the header name for the app or service your HTTP Request is targeting. |
| Value | Specify the header value for the app or service your HTTP Request is targeting. |
| Nodes with access | Add the nodes who can access using the credentials and mark the checkbox to select them. |

#### OAuth 2.0

To set up credentials for OAuth 2.0, select the authentication type in the authentication option and select **Create new** from the menu against **OAuth**.

| Parameters |
| --- |
| URL | Copy this callback URL appearing on top of the form. You have to add this callback url in your application in the callback or redirect URL option. |
| Credentials Name | Provide a valid name of the credentials. Use a name that makes it clear to what exactly the access is given. For example, for credentials of an email account, the name can be the email address itself. |
| **Credentials Data** |
| Grant type | Select the grant type according to the support of your application. |
|  | Authorization Code | Standard OAuth 2.0 |
| PKCE | Extended version of Authorization Code |
| Authorization URL | Specify the URL to authorize the user. You can find these in your application’s documentation, for example, *https://www.dropbox.com/oauth2/authorize*. |
| Access Token URL | Specify the access token URL to access the API. You can find these in your application’s documentation, for example, *https://www.dropbox.com/oauth2/token*. |
| Client ID | Specify the client ID associated with the account. |
| Client Secret | Specify the client secret associated with the account. |
| Scope | Specify the scope of the connection for according to your application and the permission you require, such as, account_info.read and events.read. |
| Auth URI Query Parameters: | Specify any additional parameters that need to be set. For example, Offline_access. *Offline access allows getting a new access token using the refresh token when the access token expires.*. |
| Authentication | Choose the authentication type to decides how to pass client credentials in the request. |
|  | Body | Specify the credentials in body if selected. |
| Header | Specify the credentials in header if selected. |
| Nodes with access | Add the nodes who can access using the credentials and mark the checkbox to select them. |

A node in workflow refers to a specific step or task within the overall process. Workflows are sequences of interconnected steps that represent a process or a set of activities to achieve a specific goal and each step or task in the workflow is referred to as a node. Nodes can represent various activities, such as data processing, decision points, approvals, or any other task that needs to be completed as part of the larger process.
