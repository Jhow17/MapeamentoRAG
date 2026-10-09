---
title: "Extracting the form JSON"
slug: "extracting-the-form-json"
updated: 2026-06-19T09:09:47Z
published: 2026-06-19T09:09:47Z
canonical: "helpcenter.securiti.ai/extracting-the-form-json"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Extracting the form JSON

For each form, you use the Securiti browser plugin to extract the form fields and buttons and compile them into a JSON object that you upload to Securiti. Follow this procedure:

1. In a Chrome browser, browse to the web page that hosts the form for which you want to capture consent.
2. On the browser toolbar, click on the icon for the browser plugin.
3. Near the lower right corner of the browser window, click **Extract form(s) JSON** in the plugin box as shown below.

![form_consent_extract_form_json.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f5b5feb2-b0fe-a9da-7ad7-bcfa22f7760c.png)
4. Locate the JSON file in your **Downloads** folder and open it.
5. Inspect the JSON file to see if there is more than one **formSelector** field. If so, there is more than one form on the web page.

If this happens, enter the `formSelector` value for the correct form in the **Enter form selector** field in the plugin box. Omit **slashes** and **double quotes** outside the brackets, as shown in the following examples.

| JSON formSelector code: | Enter: |
| --- | --- |
| [data-form-id = \"97678952-c4a7-4e31-8d99-5a66d935e600\"] | [data-form-id = "97678952-c4a7-4e31-8d99-5a66d935e600"] |
| [data-formid = \"1098\"] | [data-formid = "1098"] |
6. Proceed to [Importing the form JSON into Securiti](/v1/docs/importing-the-form-json-into-securiti).

### Form JSON extraction examples

To successfully download the form JSON using Securiti's form extractor plugin, you must have a valid HTML tag with one of the following attributes:

- `'name'`
- `'id'`
- `'data-'`

#### Examples

- In this following case, you can use either `form` or `[id="form1"]` in the selector field of form extractor plugin for successful form JSON extraction.

```xml
<form id="form1">
</form>
```
- In this case, you can use either `div` or `[id="form2"]` or `[name="form2name"]` in the selector field of form extractor plugin for successful form JSON extraction.

```xml
<div id="form2" name="form2name">
  <div>
  </div>
</div>
```

####

## Related

- [Importing the form JSON into Securiti](/importing-the-form-json-into-securiti.md)
