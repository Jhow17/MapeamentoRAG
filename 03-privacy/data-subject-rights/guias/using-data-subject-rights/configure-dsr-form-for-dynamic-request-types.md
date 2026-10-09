---
title: "Configure DSR form for dynamic request types"
slug: "configure-dsr-form-for-dynamic-request-types"
updated: 2025-11-04T13:13:00Z
published: 2025-11-04T13:13:00Z
canonical: "helpcenter.securiti.ai/configure-dsr-form-for-dynamic-request-types"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Configure DSR form for dynamic request types

In DSR forms, you can display a form field based on values of two different components.

In this example, we will display dynamic request types on the DSR form based on other selected components such as country/region or data subject relationship. You can achieve such use cases using advanced conditions in DSR forms.

### Use Case

#### Dynamic display of DSR request types based on data subject type and location

**Scenario 1**: Customers based in China

- **Data Subject Type**: Customer
- **Location/Country**: China
- DSR request types to display:
  - Erasure
  - Confirmation

**Scenario 2:** Employee based in China

- **Data Subject Type**: Employee
- **Location/Country**: China
- DSR request types to display:
  - Rectify
  - Objection
  - Access
  - Portability

#### Procedure

1. In Securiti, open **Data Subject Rights**, then choose **Settings > Form Builder**.
2. Choose the form you want to use or create a new one.
3. In DSR **Form Settings**, in **Customize Content** section, click the **Edit**(gear icon) of the “I am a” field indicating data subject type and select the **Data** component.

![unnamed__4_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e7b83c12-bf34-289a-c87f-ec9bcb69abef.png)
4. Mark the "Refresh On" checkbox to refresh the data in this field based on the selected country during the request submission, then click **Save**.

![unnamed__5_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-51770b3a-ee9e-a2be-abba-d36e4108c843.png)

> [!NOTE]
> **Note**
> 
> In the current release, you can use the Refresh On capability for limited components in the DSR form such as drop-down menus, radio buttons, etc. The support for system fields will be enabled in future releases.
5. Then, Click the **Edit** (gear icon) of the “Request Type” field and select the Data component.
6. Mark the "Refresh On" checkbox to refresh the data in this field based on the value selected in the "I am a" field for data subject type during the request submission. Select the **Conditional** component of this field, click **Advanced Conditions**, add the sample code to the **JavaScript** section, and click **Save**. Once done, publish the DSR form.

![Screenshot_2024-07-14_at_9_41_46_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b3b528ee-0686-fd37-cb88-3c2da06bdd5f.png)

> [!NOTE]
> **Note**
> 
> When writing the JS code for the DSR request type dynamic triggering, use ALPHA-3 country codes in your code block. You can find a list of those codes [here](https://www.iban.com/country-codes).

```plaintext
if (data.country === 'CHN') {
  if (data.user_type === 'employee') {
    instance.component.values = [
       {
          "label": "Rectify",
          "value": "rectify"
        },
        {
          "label": "Objection",
          "value": "object"
        },
        {
          "label": "Access",
          "value": "access"
        },
        {
          "label": "Port",
          "value": "port"
        }

    ]  
  } else if (data.user_type === 'customer'){
    instance.component.values = [
      {
        "label": "Erasure",
        "value": "erasure"
      }, 
      {
        "label": "Confirmation",
        "value": "confirmation"
      }
    ]
  }     
  }
```

> [!WARNING]
> **Important**
> 
> The request types listed in the **Request Type** field configuration should include all the request types specified in the if-else conditions of the code. While the configuration may contain additional request types beyond those defined in the if-else conditions, it is essential that every request type present in the if-else conditions is also included in the configuration.
> 
> ![Screenshot_2024-07-15_at_9_40_21_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a75a58bd-3b79-4c3f-edfa-cfd950500eb0.png)
7. When a data subject first accesses the form, the DSR form displays all request types defined in the Request Type field configuration by default.

![Screenshot_2024-07-15_at_9_52_52_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-913dbe0b-97b3-7fd3-719d-7861ef853614.png)
8. When the data subject selects “China” as the country and type as "Customer," the DSR form dynamically adjusts to show only the relevant request types such as Erasure and Confirmation.

![Screenshot_2024-07-15_at_9_58_20_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-15db342d-1c86-0be3-5f00-920b89567613.png)

> [!NOTE]
> **Note**
> 
> If the data subject doesn't select any country or selects a country other than China, the DSR form displays all request types defined in the Request Type field configuration. Additionally, You can use the same approach to display dynamic DSR request types based on other fields in the DSR form.

---

### FAQs

#### 1. Why am I seeing the error "Unsupported request type provided" when submitting the DSR request for dynamic request types?

This error occurs because the request type you selected may not be defined in the Request Type field configuration, even though it is specified in the if-else conditions of the code. The Request Type field configuration must be a union of all request types specified in the if-else conditions. While the configuration may include additional request types, it is essential that every request type in the if-else conditions is included in the configuration.
