---
title: "Integrating the universal preference center with external website"
slug: "integrating-preference-center-with-external-website"
description: "You can embed Securiti’s Universal Preference Center into your organization’s website. Use an iframe to display the preference center on your site and let visitors manage their preferences in real time."
updated: 2026-07-20T08:45:56Z
published: 2026-07-20T08:45:56Z
canonical: "helpcenter.securiti.ai/integrating-preference-center-with-external-website"
stale: true
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Integrating the universal preference center with external website

You can also integrate Securiti’s universal preference center with your organizational website. You can build, configure and host the preference center on your organizational website to suit. Integrate the preference center utilizing the `iframe` to make it interactable in real time with your website.

### Prerequisites

Download the zip file below to access the required files.

[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti-preference-center-integration-iframe(1).zip)securiti-preference-center-integration-iframe11.70 KB[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti-preference-center-integration-iframe(1).zip)

> [!NOTE]
> **Note**
> 
> You must keep the files in the same structural folders as placed in the zip file.

The categorization of the pages is done with the use of the following terminologies.

| Terminology | Description |
| --- | --- |
| Parent website | Parent website is your organizational website. For instance, use *index.html* file for this purpose. |
| Securiti `iframe` | The `iframe` that integrates Securiti’s preference center with your website. For instance, `preference-center.html` and `preference-center.js` files. |
| Client | Parent website or your website. |
| Publisher | Publisher raises or emits the event. |
| Subscriber | Subscriber listens to any event emitted by the Publisher. |

### Integrating preference center with external website using iframe

To integrate the preference center with your website via `iframe`:

1. Add the `iframe` tag in the `index.html` file (parent page) as shown in the following code snippet.

```xml
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">   
    <meta name="viewport" content="width=device-width, initial-scale=1.0">   
    <title> - Iframe integration example</title>   
    <link rel="stylesheet" href="client.css">
</head>
<body>
    <section>
        <form id="iframeIntegrationExampleForm"> 
            <div class="form-group">
                <label for="firstName">First Name</label>
                <input name="firstName" id="firstName" placeholder="Enter FirstName" />
            </div>
            <div class="form-group">
                <label for="lastName">Last Name</label>
                <input name="lastName" id="lastName" placeholder="Enter LastName" />
            </div>
            <div class="form-group">
                <label for="email">Email</label>
                <input type="text" name="email" id="email" placeholder="Enter email" />
            </div>

 <!-- The iframe is added here by linking up with the source iframe file -->

            <iframe id="preferenceIframe" height="200" src="preference-center.html" ></iframe>
        </form>
    </section>
    <script src="client.js"></script>
</body>
</html>
```
2. Add preference center details in the `client.js` file because it integrates Securiti's universal preference center with your website. Add credentials such as your Securiti **tenant id (tenant auth token)** and **preference center id** in the `client.js` file as shown in the following code snippet.

![step2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-abde3afa-4d63-d717-bf39-f8ab6412469d.png)

```javascript
const CREDENTIALS = {
   tenantId: "app~3a25e717-55d8-4705-b590-ea947e480a29",
   preferenceCenterId: "3e78f5cd-fa19-4d2b-82e8-3b4bc87eb385",
   primaryIdentifier: '',
   locationCode: 'US',
   languageCode: 'en',
   implicitFlow: true,
   implicitRecordConsents: false,
   allMandatory: false
};
```
  1. The following table explains all the fields mentioned above in the credentials:

> [!NOTE]
> **Note**
> 
> Scroll horizontally on the table to see columns at the right side.

| Name | Description | isMandatory | Possible Values | Default Value |
| --- | --- | --- | --- | --- |
| `tenantId` | Your Securiti tenant ID. You can copy this from the admin portal, as shown below. > [!NOTE] > **Note** > > In the admin portal, the `tenantID` is listed as the **Tenant Auth Token**. ![Linking-PC-with-External-Website-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-70705714-c135-b0ac-3170-9e6a238fb0f9.png) | Yes | UUID | - |
| `preferenceCenterId` | The ID of your preference center from Securiti. You can copy this from the admin portal, as shown below. ![Linking-PC-with-External-Website-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2f8bab19-d5d0-a2b9-d476-ad1760fc7235.png) | Yes | UUID | - |
| `locationCode` | Pass the location code of a specific region in this field to render the location specific preference center. **locationCode** is set to default and a default configured preference center is rendered if you pass no value in this field. > [!NOTE] > **Important** > > You must enable the **location intelligence** toggle in the portal to use this field. The default preference center is rendered if you have not enabled this toggle. | No | [ISO 2 Format](https://www.nationsonline.org/oneworld/country_code_list.htm) | default |
| `languageCode` | Pass this field to render the preference center in the given language. By default it is set to **en**. > [!NOTE] > **Important** > > You must enable the **language intelligence** toggle in the portal to use this field. | No | [ISO 2 Format](https://www.nationsonline.org/oneworld/country_code_list.htm) | en |
| `allMandatory` | If this is true then Securiti treats all of the consent records as mandatory and displays you the submit button only if the consent records are provided by your data subjects. If this is false, consents whose required flag is true are treated as mandatory and the submit button is enabled once those consents are given. | No | true/false | false |
| `implicitFlow` | You can control when to render the preference center using this flag. - If this flag is set as true, the preference center gets loaded when the SDK is initialized. - If this is set as false then you must explicitly call the loadPreferenceCenter method after initializing the SDK to render the preference center. | No | true/false | false |
| `implicitRecordConsents` | This flag controls the flow of recording consents. - If this is true, the consents are recorded when the data subject clicks on submit. - If this is false, the consents are recorded upon receiving parent website acknowledgement. | No | true/false | false |
  2. Configure the mandatory custom events triggered to establish the necessary communication between the `iframe` and the website. These events are called within the `function()` class in the `client.js` file. You can pass the primary identifier to the `iframe` as shown in the following code snippet.

```javascript
// Update primary identifier in SDK    
function handlePrimaryIdChange(ev){   
    const value = ev.target.value;        
    PUB({            
        type: 'SET_PRIMARY_IDENTIFIER',            
        value: value        
        }, '*')    
}
```

> [!NOTE]
> **Note**
> 
> For information on these events, see [Communication between website and iframe](/v1/docs/integrating-preference-center-with-external-website).
3. You can view and understand the logic behind how the custom events operate in the `iframe/iframe/preference-center.js` file. This file is divided into the following four parts:
  1. **Region Mapping**: This section contains the list of regions in which Securiti is deployed. All the environments are listed inside this function.
  2. **Load Securiti’s SDK:** `loadSecuritiSDK()` loads Securiti’s SDK files such as JavaScript and CSS based on the region code. You can call this function as shown in the following code snippet.

```javascript
// iframe/preference-center.js
// Example: Call with configured credentials loadSDK(CREDENTIALS)
// OR
// This can be called on an event also inside iframe, i.e., preference-center.js

window.parent.addEventListener('message', async (evt) => {
    if (evt.data.type && evt.data.type.toUpperCase() == 'INIT_PREFERENCE_CENTER') {
        loadSDK(evt.data.config);
        
        setTimeout(async () => {
            // see STEP #6 for more info
            await initSDK(evt.data.config);
        }, 2000)
    }
});

// From parent page (i.e., customer.js) pass the config data to iframe

window.postMessage(
  {
    type: "INIT_PREFERENCE_CENTER",
    config: CREDENTIALS
  },
  '*'
);
```
  3. **Initialize the SDK:** `initSDKConfig(config)` initializes Securiti’s SDK after loading it. To initialize it, pass the `userConsents` object in the `client.js` file as shown in the following code snippet.

```javascript
// This is a sample consent format.
// If you want to load the consents then you need to pass the consents in this format (i.e., it should be in the client.js).

const userConsents = {
: {
    "processing_purpose_id": 1,
    "consented_items": [
       {
        "consent_purpose_id": 1,
        "granted": true
      },
      {
        "consent_purpose_id": 4,
        "granted": true
      },
      {
        "consent_purpose_id": 3,
        "granted": true
      }
    ]
  }
};
```
  4. **Subscribe to Securiti Events:** If you need to perform actions using the preference center events, subscribe to those events by mentioning the event name in the `eventsToSubscribe` array as shown in the following code snippet.

```javascript
const eventsToSubscribe = [
      'INVALID_CONFIG',
      'PREFERENCE_CENTER_LOADED',
      'FAILED_TO_LOAD_PREFERENCE_CENTER',
      'CONSENTS_PROVIDED',
      'CONSENTS_RECORDED',
      'CONSENTS_FAILED_TO_RECORD'
    ]
```

> [!NOTE]
> **Important**
> 
> You do not have to update anything here because all the configurations are already in place in the provided files.
4. Run the `index.html` file after making all aforementioned changes to see the integrated version of your website with the preference center.

### Communication between website and iframe

You can use the following table to understand the consent related preference center events that can be triggered when integrating your preference center with the `iframe`.

> [!NOTE]
> **Note**
> 
> Scroll horizontally on the table to see columns at the right side.

| Custom Event | Description | Publisher | Subscriber | Payload |
| --- | --- | --- | --- | --- |
| `INIT_PREFERENCE_CENTER` | Use this event to pass the config to the `iframe` to successfully render the preference center. | Website parent page should publish this event when the `iframe` is loaded. | `iframe` listens to this event. | ```javascript { type: 'INIT_PREFERENCE_CENTER', config: CREDENTIALS } ``` |
| `SET_PRIMARY_IDENTIFIER` | Use this event to pass the primary identifier to `iframe`. You must add some value in the primary identifier to enable the submit button. | Website parent page should publish this event whenever the primary identifier changes. | `iframe` listens to this event, and updates the primary identifier when it gets a new value. | ```javascript { type: 'SET_PRIMARY_IDENTIFIER', value: '<PrimaryIdentifier>' } ``` |
| `CONSENTS_PROVIDED` | This event is fired on the submit button click. This event is fired only if the `implicitRecordConsents` is false. > [!NOTE] > **Note** > > `consentsProvided` true means all the mandatory consents are granted. | `iframe` publishes this event when the data subject clicks on the submit button. | Website parent page listens to this event to check the consent status to let the `iframe` know about the consent status. | ```javascript { type: 'CONSENTS_PROVIDED', consentsProvided: true/false, onsentStatus: [{purpose: 'Newsletter', consent: 'Granted/Declined'} ... ]} } ``` |
| `CONSENTS_RECORDED` | This final event from `iframe` is fired after consents are recorded successfully. Use this event in the website parent page to perform any actions on success. For instance, use when you want to navigate to a different page, show toast messages, or remove `iframe` from the DOM. | `iframe` publishes this event after storing the consents. | Website parent page listens to this event, and can perform success actions. | ```javascript { type: 'CONSENTS_RECORDED', consentsRecorded: true } ``` |
| `GET_USER_CONSENTS_SNAPSHOT` | Website parent page should emit this event to get the consent status of data subjects. You can call this event any number of times. For instance, you can store this in the consents and prepopulate the consents when the data subject comes back and forth to the page. | Website parent window should publish this event. | `iframe` listens to this event, and emits `USER_CONSENTS_SNAPSHOT` event along with consents object. > [!NOTE] > **Note** > > Parent window must subscribe to `USER_CONSENTS_SNAPSHOT` event to get the consents. | ```javascript { type: 'GET_USER_CONSENTS_SNAPSHOT' } ``` |
| `LOAD_PREFERENCE_CENTER` | Website parent page should emit this event to render the preference center explicitly. If `implicitFlow` is set to **false** then the parent window must publish this event to render the preference center. | Website parent window should publish this event. | `iframe` listens to this event, and loads the preference center as soon as it receives the event. | ```javascript { type: 'LOAD_PREFERENCE_CENTER' } ``` |
| `LOAD_USER_CONSENTS` | Website parent page should emit this event to prepopulate the consents. For instance, to maintain the same state when a data subject goes back and forth, the website parent page can use this event. | Website parent window should publish this event. | `iframe` listens to this event, and prepopulates the consents as per the payload. | ```javascript { type: 'LOAD_USER_CONSENTS', consents: <userConsents> (Provided the example json format below.) } ``` |
| `INVALID_CONFIG` | `iframe` should publish this event when the provided configuration does not meet the required constraints. For instance, if any required fields are missing or any invalid values are passed. | `iframe` should publish this event. | Website parent window can subscribe to this window. | ```javascript { type: 'INVALID_CONFIG', data: <CREDENTIALS> } ``` |
| `CONSENTS_FAILED_TO_RECORD` | Securiti `iframe` should publish this event if there are any errors when recording consents. | `iframe` should publish this event. | Website parent window can subscribe to this window. | ```javascript { type: 'CONSENTS_FAILED_TO_RECORD', consentsRecorded: false } ``` |
| `RECORD_CONSENTS` (optional) | Use this event to confirm the submission of consents. Parent window should publish this event only if the `implicitRecordConsents` flag is set to **false**, otherwise the API call is triggered on the submit click. > [!NOTE] > **Note** > > Using this event is mandatory if the implicitRecordConsents flag is set to false. If it is set to true then this event is not required. | Website parent page should publish this event after receiving the `CONSENTS_PROVIDED `event. | `iframe` listens to this event and triggers the rest API call upon receiving this event. | ```javascript { type: 'RECORD_CONSENTS', storeConsents: true } ``` |
| `SET_CUSTOM_PARAMETERS` (optional) | Use this event to pass the custom parameters to `iframe`. This information is stored along with the consents. | Website parent page should publish this event once it has information. | `iframe` listens to this event and updates the custom parameters when it gets a new value. | ```javascript { type: 'SET_CUSTOM_PARAMETERS', value: {<key>: <value>} } ``` |
| `SET_FORM_STATE` (optional) | Use this event to pass the form state (valid/invalid) to `iframe`. For instance, you can use this event If the website parent form has any mandatory fields and you do not want to enable the submit button until the data subject enters values in the fields. | Website parent page should publish this event once the form state is updated. | `iframe` listens to this event and enables or disables the submit button if needed. | ```javascript { type: 'SET_FORM_STATE', formState: 'valid/invalid' } ``` |

A token is a small piece of data, typically in the form of a string, that serves as an authentication or authorization mechanism. It is used to verify the identity of a user or application and grant access to specific resources or functions. Tokens are commonly used for security and access control in API interactions.

Universally Unique Identifier (UUID) is an alphanumeric string that is used to identify information in computer systems. For instance, they are often used to identify rows of data within a database table, with each row assigned a specific UUID.

## Related

- [Building a universal preference center](/building-a-universal-preference-center.md)
- [Customizing your universal preference center](/customizing-your-preference-center.md)
