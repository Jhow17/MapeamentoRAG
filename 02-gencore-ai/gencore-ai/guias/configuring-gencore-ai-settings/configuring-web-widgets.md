---
title: "Configuring Web Widgets"
slug: "configuring-web-widgets"
updated: 2026-09-01T10:01:41Z
published: 2026-09-01T10:01:41Z
canonical: "helpcenter.securiti.ai/configuring-web-widgets"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Configuring Web Widgets

**Scenario**

As a Data Governance Officer, you want to make GenAI tools easily accessible without forcing users to switch platforms. But building custom interfaces for each use case is resource-intensive. With **web widgets**, you embed a ready-to-use chat component directly into your website or app. Users interact with GenAI pipelines in context, improving usability while maintaining control over the AI experience.

The web widget is a self-contained chat component you can integrate into a webpage or application. This integration allows users to interact with Securiti's GenAI Pipelines directly from a website or app where this widget is integrated.

To open the **Web Widgets** page:

- in Securiti, open **Gencore AI**, choose **Settings** and select **Web Widgets**
- in Securiti, open **Settings**, choose **Gencore AI** and click **Web Widgets**. Here, you can manage the configuration and access details for web widgets.

![Overview of web widgets with details on names, owners, and creation dates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/WW.png)

The **Web Widgets** page offers the following capabilities:

- Search for existing web widgets
- Expand widgets to view pipelines linked with widget along with pipeline status and owner. We can view further information about the pipeline using the pipeline metadata explorer as well there.
- Managing web widgets
- Filter web widgets based on:
  - Name
  - Owner
  - Pipeline Owner
  - Pipeline
- Sort widgets based on **Name** and **Creation date**.

### Prerequisites

You must have at least one [GenAI pipeline](/v1/docs/using-genai-pipelines) configured.

### Adding a web widget

To add a web widget:

1. Click **+ Add Widget**. The **Configuration** tab displays by default. ![Add widget](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/WW Add Widget.png)
2. To configure your web widget, in the **Configuration** tab:
  1. Enter the Widget **Name**.
  2. Optionally add a **description**.
  3. Search for and select a pipeline. You can also filter out a pipeline based on name, status, and owner. Only those pipelines are available for selection that are enabled by the toggle **Enable Pipeline in Web Widget** in the **API Assistant** node.

![Configuration settings for a web widget including pipelines and their statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/WebWidget Config.png)

> [!NOTE]
> **Note**
> 
> You can bind one pipeline to multiple web widgets within your organization to enable engagement and access. However, one widget can be bound to only one pipeline.
3. To customize the appearance of your web widget:
  1. Click the **Appearance** tab.
  2. Select the **launcher style**.
  3. Select the **launcher position**.
  4. Select the **launcher icon**.
  5. Configure the **color palette**.
  6. To hide the display of the text **Powered by Securiti**, click the toggle button.
  7. To save the widget, click **Save Configuration**. The deployment code is generated in the **Deployment** tab.

![Appearance options for a web widget, including launcher style and color palette settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Web Widget - Appearance.png)
4. To deploy the widget, on the **Deployment** tab:

A signed identity establishes a digital signature that ensures the request originates from a specific entity and has not been altered since it was signed. This measure prevents malicious entities from the widget on behalf of your users by verifying signed applications and ensuring they haven't been altered since signing.

> [!NOTE]
> Important
> 
> In case of ​[self-hosted deployment​](/latest/docs/configuring-self-hosted-user-portal)​, before copying the code modify the base URLs in the following to your domain for your self-hosted deployment:
> 
> - BaseUrl
> - gencoreWidget.src
> 
> 
> 
> ![Deployment code for a web widget with highlighted URLs and configuration settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Web widget - deployment tab.png)
  1. Copy or download the displayed code. You must add it at the start of the **<head>** tag on your web page.
  2. Secure the identity verification code, which will be used in your .js snippet.
5. When you are satisfied with the provided details, click **Save Configuration**.

### Configuring web widget code

To configure the web widget code, you must:

1. Set up deployment code
2. Generate user token on the backend
3. Pass the granted user token to the widget
4. Generate Widget User Token.

#### Set up deployment code

Add the deployment code at the beginning of the <head> tag on your web page.

#### Generate User Token on backend

To initialize the Copilot widget, generate a user token on the backend using the user's email as the identifier. This token must be created by signing a JSON Web Token (JWT) with the widget's identity verification secret key, using the HS256 algorithm.

The script when loaded dispatches an event called `SecuritiCopilotReady`, which can be used to access the widget and initialize it. The script exposes the `window.SecuritiCopilot` object containing the public API of the widget. It has the following methods:

- `setUserAuthToken`: Sets the user authentication token to authenticate the user.
- `init`: Initializes the widget and adds it to document/website.
- `updateConfig`: Updates the configuration of the widget.
- `destroy`: Destroys the widget i.e. deletes it from the document/website.

To show the widget on screen, we wait for the `SecuritiCopilotReady` event, then set the user token using `window.SecuritiCopilot.setUserAuthToken` and call `window.SecuritiCopilot.init` method.

Note: `setUserAuthToken` expects a JWT token signed with the secret key that is shared in the widget's deployment tab. For example, in python, the code looks as follows:

```python
***** START OF SERVER SIDE CODE *******
import jwt

signing_key = "485cde88711bf90942878c95f0c5ca3f994588a6c0fa6cf8c8ea7b6e22783397cd "

token_info = {
    "uid": "JohnDoe",
    "hst": "securiti.ai",
}

token = jwt.encode(token_info, signing_key, algorithm='HS256')

*****  END OF SERVER SIDE CODE *******
```

Once we have the token, we can call `window.SecuritiCopilot.setUserAuthToken` (token) with it.

#### Pass the granted user token to the widget

Once the user token is generated on the backend, the JavaScript for the Copilot widget is loaded on your web application. Authenticate the user by passing the token to the `setUserAuthToken` method of the globally available `window.SecuritiCopilot` object. After setting the token, initialize the widget by calling the init method of the same object. The relevant JavaScript code snippet is provided below:

```python
window.addEventListener('CopilotReady', function () {
	window.Copilot.setUserAuthToken("{user_token}")
window.Copilot.init()
})
```

You must replace {user_token} with the actual token generated for the user. This code listens for the `SecuritiCopilotReady` event to ensure the widget is loaded before initialization and user token is set.

#### Widget User Token Generation

To integrate the widget SDK, clients need an additional JWT token signed with the widget's designated signing key. This token must be generated dynamically by the client. The following is the JWT token payload structure:

```python
{"uid": "{{logged in user email}}"}
```

#### Specification

**Properties**:

- uid (type = string): The client must provide the ID of the logged-in user from its web portal.

**Algorithm**:

- HS256: Use this algorithm to sign the JWT token.

#### User token generation examples in different languages

**Python 2.x / 3.x**

```python
#requirements jwt

import jwt

signing_key = "{{widget_sk}}"
user_email = "{{logged_in_user_email}}"

token_info = {
    "uid": user_email
}
jwt_token = jwt.encode(token_info, signing_key, algorithm='HS256')
```

**Java**

```java
#dependencies 
 #io.jsonwebtoken:jjwt:0.12.5
 #com.fasterxml.jackson.core:jackson-databind:2.16.0  

 
String signingKey = "{{widget_sk}}";
String userEmail = "{{logged_in_user_email}}"

Map<String, String> tokenInfo = new HashMap<String, String>();
tokenInfo.put("uid", userEmail);
        
byte[] signingKeyBytes = signingKey.getBytes(Charset.forName("UTF-8"));

String jwtToken = Jwts.builder()
.setClaims(tokenInfo)
       .signWith(SignatureAlgorithm.HS256, signingKeyBytes)
       .compact();
```

**Ruby** (Unset)

```ruby
#requirements jwt //gem install jwt

import jwt

signing_key = "{{widget_sk}}"
user_email = "{{logged_in_user_email}}"

token_info = {
    "uid": user_email,
}

jwt_token = jwt.encode(token_info, signing_key, algorithm='HS256')
```

**Node JS**

```node-repl
#requirements jsonwebtoken //npm install jsonwebtoken
const jwt = require('jsonwebtoken');

var signingKey ="{{widget_sk}}"; 
var userEmail = "{{logged_in_user_email}}"

const tokenInfo = {
  uid: userEmail,
};

const jwtToken = jwt.sign(tokenInfo, signingKey, { algorithm: 'HS256' });
```

**JavaScript**

```javascript
<script src="https://cdn.jsdelivr.net/npm/jsrsasign@10.5.3/lib/jsrsasign-all-min.js"></script>

<script type="text/javascript">
function generateJWT() {
    const header = {alg: 'HS256', typ: 'JWT'};
    var signingKey ="{{widget_sk}}"; 
    var userEmail = "{{logged_in_user_email}}"

    const payload = {
        uid: userEmail,
    };

    const sHeader = JSON.stringify(header);
    const sPayload = JSON.stringify(payload);
    const sJWT = KJUR.jws.JWS.sign(null, sHeader, sPayload, {utf8:signingKey});
    return sJWT;
}
</script>
```

A set of criteria that focuses your view by eliminating elements that fall outside the scope of interest. When you filter Securiti pages and dashboards, you choose criteria in the filter panel to reduce the number of elements Securiti displays to just those of interest.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
- [Assistant API](/assistant-api.md)
