---
title: "API workflows"
slug: "data-subject-rights-api-workflows"
updated: 2025-10-30T19:20:50Z
published: 2025-11-03T07:39:28Z
canonical: "helpcenter.securiti.ai/data-subject-rights-api-workflows"
area: privacy
modulo: data-subject-rights
tipo: api
data_captura: 2026-10-08
---

# API workflows

## DSR forms

### Fetch list of forms

Fetches a list of published DSR forms.

```plaintext
GET https://privacy-central.securiti.ai/integration/v1/forms HTTP/1.1
```

Response:

```plaintext
{
    "message": "Tenant Forms Received successfully",
    "data": [
        {
            "title": "Sample CCPA Request Intake form",
            "tenant_form_id": "ab7f57c9-46c5-4c2d-9002-642fb8f1a5d3"
        },
        {
            "title": "Id ver Multi No Restriction",
            "tenant_form_id": "642f6bfe-acf0-41d0-b495-40a39554f3f8"
        },
        {
            "title": "Id ver disabled restrictions 2 per 30 parallel",
            "tenant_form_id": "e9dbfdce-73c3-44b8-9a13-97c5e85159ff"
        },
        {
            "title": "No Attach",
            "tenant_form_id": "564f21ef-cd86-4b2c-a40f-9dc995e4824f"
        }
    ]
}
```

### Fetch DSR Form metadata

```plaintext
GET https://privacy-central.securiti.ai/integration/v1/form/metadata/<formID> HTTP/1.1
```

Response:

```plaintext
{
    "custom_types": {
        "attr_name": {
            "key": "attr_name",
            "label": "Attribute",
            "required": "true",
            "type": "Select"
        },
        "curr_val": {
            "key": "curr_val",
            "label": "Current",
            "required": "true",
            "type": "Text field"
        },
        "new_val": {
            "key": "new_val",
            "label": "Change To",
            "required": "true",
            "type": "Text field"
        }
    },
    "metadata": {
        "account_email": {
            "key": "account_email",
            "label": "Account Email",
            "required": "false",
            "type": "Email"
        },
        "additionalCustomCheckbox": {
            "description": "Select this option to temporarily suspend the use of your data until a response to your request is delivered.",
            "key": "additionalCustomCheckbox",
            "label": "Additional custom checkbox",
            "required": "false",
            "type": "Checkbox"
        },
        "apt_no": {
            "key": "apt_no",
            "label": "Apt/Unit/Suite",
            "required": "false",
            "type": "Text field"
        },
        "attachments": {
            "additional_notes": "Maximum allowed attachments are 3 of 10 MB each",
            "allowed_values": [
                {
                    "originalName": "<<uploaded file name>>",
                    "url": "<<Base64 encoded value of file prefixed with content type eg: data:image/png;base64,iVBORw0KGgo...>>"
                }
            ],
            "key": "attachments",
            "label": "Add Attachments",
            "required": "false",
            "type": "Multiple Files"
        },
        "city": {
            "key": "city",
            "label": "City",
            "required": "false",
            "type": "Text field"
        },
        "country": {
            "additional_notes": "Three letter code of a country Eg. For United States, the code is USA",
            "key": "country",
            "label": "Country",
            "required": "false",
            "type": "Select"
        },
        "custom_radio": {
            "allowed_values": [
                "opt_1",
                "opt_2"
            ],
            "key": "custom_radio",
            "label": "custom_radio",
            "required": "false",
            "type": "Radio"
        },
        "custom_select": {
            "allowed_values": [
                "a",
                "b"
            ],
            "key": "custom_select",
            "label": "Custom Select",
            "required": "false",
            "type": "Select"
        },
        "custom_text_field": {
            "key": "custom_text_field",
            "label": "Custom Text Field",
            "required": "true",
            "type": "Text field"
        },
        "dob": {
            "additional_notes": "Date format should be YYYY-MM-DD Eg: 2019-03-31",
            "key": "dob",
            "label": "Date of Birth",
            "required": "false",
            "type": "Date"
        },
        "email": {
            "key": "email",
            "label": "Email",
            "required": "true",
            "type": "Email"
        },
        "first_name": {
            "key": "first_name",
            "label": "First Name",
            "required": "true",
            "type": "Text field"
        },
        "last_name": {
            "key": "last_name",
            "label": "Last Name",
            "required": "true",
            "type": "Text field"
        },
        "phone": {
            "key": "phone",
            "label": "Phone",
            "required": "false",
            "type": "Phone Number"
        },
        "postal_code": {
            "key": "postal_code",
            "label": "Zip/Postal Code",
            "required": "false",
            "type": "Text field"
        },
        "rectification_details": {
            "additional_notes": "This field is mandatory for \"rectify\" ticket type",
            "allowed_values": [
                {
                    "attr_name": "refer to attr_name type under custom types",
                    "curr_val": "refer to curr_val type under custom types",
                    "new_val": "refer to new_val type under custom types"
                }
            ],
            "key": "rectification_details",
            "label": "Rectification Details",
            "required": "false",
            "type": "Json array"
        },
        "state": {
            "additional_notes": "Two letter code of a State under corresponding country. Eg. For California, the code is CA",
            "key": "state",
            "label": "State",
            "required": "false",
            "type": "Select"
        },
        "street": {
            "key": "street",
            "label": "Street",
            "required": "false",
            "type": "Text field"
        },
        "ticket_type": {
            "additional_notes": "Data should be sent as a string array Eg: [\"access\"]. If type is Multi Select the array can contain multiple request types",
            "allowed_values": [
                "access",
                "erasure",
                "do-not-sell",
                "confirmation"
            ],
            "key": "ticket_type",
            "label": "Request Type",
            "required": "true",
            "type": "Radio"
        },
        "user_type": {
            "allowed_values":[
                "employee",
                "customer",
                "other"
            ],
            "key": "user_type",
            "label": "I am a...",
            "required": "true",
            "type": "Select"
        }
    }
}
```

> [!NOTE]
> **Note**
> 
> - The values with key “metadata” give the basic information of the fields that are supported by the form.
> - The values with key “custom_types” give the information about the fields used in the metadata which are specific to Privacy Central.

## DSR requests

### Submit a DSR Request

```plaintext
POST https://privacy-central.securiti.ai/integration/v1/request-submission HTTP/1.1Content-Type: application/json
```

Request body:

```plaintext
{
	"tenant_form_uuid": "ab7f57c9-46c5-4c2d-9002-642fb8f1a5d3",
	"form_data": "{\"ticket_type\":[\"access\"],\"email\":\"john2@access.ai\",\"first_name\":\"John Two\",\"last_name\":\"Intg Two Access\",\"apt_no\":\"Abcd\",\"street\":\"Abcd\",\"dob\": \"2020-06-25\", \"country\":\"usa\", \"state\":\"ca\",\"user_type\":\"customer\",\"custom_text_field\": \"test\"}",
        "enforce_email_verification": true,
	"interop_metadata": "{\"service_id\":\"DSRJohn234578\" }",
	"language": "en"
}
```

Set **enforce_email_verification** to true to send a verification email to data subjects. The actual behavior depends on the combination of this flag, the DSR form's email verification setting, and whether the data subject is a new or existing user.

| New Users |
| --- |
| **enforce_email_verification** | **form.emailVerification** | **Sent verification email to data subject** |
| True | True | Yes |
| True | False | No |
| False | True | Yes |
| False | False | No |

For new users, Securiti ignores the enforce flag and uses the form setting.

| Old |
| --- |
| **enforce_email_verification** | **form.emailVerification** | **Sent verification email to data subject** |
| True | True | Yes |
| True | False | No |
| False | True | No |
| False | False | No |

For existing users, verification occurs only when both are set to true.

Response:

```plaintext
{
    "message": "Request created successfully",
    "data": {
        "request_id": "2913176b-ed36-4e20-8204-31e9ed8afe2a"
    }
}
```

> [!NOTE]
> **Note**
> 
> - Mandatory fields are marked in bold.
> - The “form_data” value is dynamic and depends upon the metadata returned by Form metadata endpoint

To get the **country** to be set in the location object when creating the DSR, you can fetch IDs of all available countries with:

```plaintext
GET https://privacy-central.securiti.ai/api/v1/geo/countries
```

To get the state for a specific country, you can fetch IDs of all available states with:

```plaintext
GET https://privacy-central.securiti.ai/api/v1/geo/countries/<countryID>/states
```

The following table describes the fields available in DSR request submission API.

| Field | Description |
| --- | --- |
| tenant_form_uuid | Form ID retrieved from list forms endpoint (mandatory) |
| form_data | Stringified JSON contain the attributes needed for DSR Request creation (mandatory) |
| interop_metadata | Stringified JSON of some data that clients wants to pass to our system like some ID generated by client system and associate it with a DSR request in the Securiti portal (optional) |
| language | One of the languages enabled in the form and the DSR request would be created in this language. (optional) |
