---
title: "Generating and embedding the form consent code"
slug: "generating-and-embedding-the-form-consent-code"
updated: 2025-10-30T19:41:17Z
published: 2025-11-03T06:12:47Z
canonical: "helpcenter.securiti.ai/generating-and-embedding-the-form-consent-code"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Generating and embedding the form consent code

After you import the form JSON into Securiti and parse it, you generate code that you embed in the page with the form.

1. Click the **Consent Collection Code** tab.
2. Near the upper right corner of page, click **Generate** as shown below.

![Screenshot_2023-12-26_at_11_45_43_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2e18a669-6e8d-336c-3670-6a2708e84f1c.png)

Securiti generates the consent code for your form.
3. On the code snippert, near the bottom right corner, click the **Copy Code** icon to copy the code onto the clipboard as shown below.

![Screenshot_2023-12-26_at_11_45_43_AM_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a2234357-51ac-7f38-65dc-fb587edc6cc6.png)
4. Add the code to the form web page immediately before the `&lt;/body&gt;` tag.

> [!NOTE]
> **Important**
> 
> To enhance the security of your hosted consent form on your domain, we strongly recommend implementing **CAPTCHA** on it.
> 
> The CAPTCHA tool actively secures your consent form hosted on your domain against automated threats, ensuring that interactions with the form are conducted by genuine human users.
5. Save and publish the web form.

> [!NOTE]
> **Note**
> 
> Securiti collects the consent of your data subjects via the consent form even in case of network issues such as network or API gateway failure and unresponsive or down servers. When the network goes live again, we automatically retry and record the Data subject’s consent.
> 
> If you want to perform specific redirection on successful or failed consent collection, you must remove the assigned null values from the `onConsentSuccess` and `onConsentFailure` callbacks in the generated form consent code as shown below.
> 
> ```javascript
> onConsentSuccess: null --> onConsentSuccess, 
> onConsentFailure: null --> onConsentFailure
> ```
> 
> Now you can place the following code at the top of the form consent generated code. By modifying this code in the generated form consent code, Securiti lets you perform any redirection on success callback or know the status when the API is failing on failure callback.
> 
> ```javascript
> let onConsentSuccess = function(){
>     //  Write your code here on API success
> }
> 
> let onConsentFailure = function(status){
>     // write your code here on api failure
>         console.log('Failed with status code: ' + status)
> }  
> ```
6. Proceed to [Testing the form code](/v1/docs/testing-the-form-code).

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

A consumer or other member of the general public whose personal data is held by a controller or processor.

## Related

- [Testing the form code](/testing-the-form-code.md)
