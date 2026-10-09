---
title: "Custom universal preference center form tabs"
slug: "custom-preference-center-form-tabs"
updated: 2025-11-06T07:06:04Z
published: 2025-11-06T07:06:04Z
canonical: "helpcenter.securiti.ai/custom-preference-center-form-tabs"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Custom universal preference center form tabs

You can use the following custom field tabs to fully customize and publish your universal preference center.

### Display

Use this tab to customize the appearance of the form component. You can customize its position, description, and overall aspects of how you want your form component to appear in the preference center.

| Label | Description |
| --- | --- |
| Label | Adds a label for the field to display next to it |
| Hide Label | Hides/unhides the label of the component. When checked, it shows the label in the form builder, but not when the form is rendered |
| Label Position | Adjusts the position for the label of the field |
| Placeholder | Adds a placeholder text to appear in the text field when it is empty |
| Description | Adds a custom description below the input field |
| Tooltip | Adds a tooltip to the right side of the input field label |
| Error Label | Adds a custom error label for the field when an error occurs |
| Custom CSS Class | Adds a custom CSS class for the component |
| Tab Index | Sets the tab index attribute of this component to override the tab order of the form |
| Persistent | Stores a persistent field in the database on the form submission on either Server-side or Client-side |
| Multiple Values | Allows to enter multiple values for this field |
| Allow Reordering | Allows changing the order of multiple values using drag and drop |
| Clear Value When Hidden | Clears the value when the input field is hidden |
| Protected | Protected field never returns when queried via API |
| Hidden | Hides the field from the view, but it remains a part of the form |
| Hide Input | Hides the input in the browser, but does not encrypt on the server |
| Disabled | Disables the form input for the field |
| Initial Focus | Makes the field the primarily focused element of the form |
| Table View | Shows the field value within the table view of the submissions |
| Always Enabled | Makes the field always enabled even when the form is disabled |
| Input Mask | Adds a predefined format for accuracy |
| Allow Multiple Masks | Adds multiple Input Masks when checked |
| Prefix | Adds a hardcoded prefix value at the start of the input field |
| Suffix | Adds a hardcoded suffix value at the end of the input field |
| Show Word Counter | Displays a word counter at the bottom right side of the input field |
| Show Character Counter | Displays a character counter at the bottom right side of the input field |
| Display in Timezone | Displays the captured date time in the selected timezone |
| Use Locale Settings | Provides locale settings to display date and time |
| Allow Manual Input | Provides manual entry of the date |
| Format | Adds a custom date format |
| Widget | Adds a widget to input the field value and adds a widget icon at the end of the input field |
| Rows | Provides control of the number of rows to be displayed in the text area |
| Editor | Selects the type of WYSIWYG editor to use for the text area |
| Enable Image Upload | Enables to add an image in the form when checked |
| Image Upload Storage | Selects storage service to save the uploaded image in |
| Image Upload Directory | Adds a field in the directory to store all the uploaded images |
| HTML Tag | Adds the tag of the HTML element |
| Content | Adds the content of the HTML element |
| Label Width | Adds the width of the label on line in percentages |
| Label Margin | Adds the width of the label margin on line in percentages |
| Shortcut | Adds a shortcut for this component |

### Data

Use this tab to add a placeholder dummy value to let you know what syntax you should use before initial interaction with the form component. You can also customize the refresh rate of data based on different scenarios if any change occurs.

| Label | Description |
| --- | --- |
| Default Value | Adds a default value for this field before user interaction and overrides the placeholder text |
| Refresh On | Refreshes the data when another field changes |
| Clear Value On Refresh | Clears the value of the component when **Refresh On** field changes |
| Custom Default Value | Overrides the default value chosen in the **Default Value** configuration |
| Calculated Value | Overrides the initially submitted value |
| Allow Manual Override of Calculated Value | Allows to manually override the calculated value when checked |
| Encrypt | Encrypts the field on the server and works as two-way encryption that is not suitable for passwords |
| Database Index | Sets the field as an index within the database and increases performance for the submission queries |
| Input Format | Provides **Plain**, **HTML**, and **Raw** input formats to choose from |
| Lazy Load URL | Controls the focus and does not fire off the request to the URL until the control is within the focus |
| Value Property | Adds the property of each item in the data source to use as the select value and if not specified then the item itself is used |
| Data Source Values | Provides a list of data source values to choose from |

### Validation

Use this tab to add validation, restriction, and custom validation messages to your form component. For instance, you can restrict your field to be unique and also make it a required field before you can submit information.

| Label | Description |
| --- | --- |
| Required | Restricts the field as a must before the form submission |
| Unique | Makes the field unique to ensure no same data is submitted previously |
| Validate On | Determines when this component should trigger frontend validation |
| Custom Error Message | Adds a custom error message if any kind of error occurs |
| Custom Validation | Adds custom validation for the field |
| JSONLogic Validation | Executes the custom logic using [JSONLogic](https://jsonlogic.com/) |
| Minimum Length | Adds the minimum length requirement that the field must meet |
| Maximum Length | Adds the maximum length requirement that the field must meet |
| Minimum Word Length | Adds the minimum amount of words that can be added to this field |
| Maximum Word Length | Adds the maximum amount of words that can be added to this field |
| Regular Expression Pattern | Tests that the field value must pass before the form is submitted |

### API

Use this tab to specify a unique key to send values to the database on form submission.

| Label | Description |
| --- | --- |
| Property Name | Adds the name of this field in the API endpoint |
| Field Tags | Tags the field for use in custom logic |
| Custom Properties | Lets you configure any custom properties for the component |

### Conditional

Use this tab to display the current component based upon a custom condition. You can show the form component in the preference center based upon a certain condition. For instance, you can display the text field based on the condition when the radio type is set to **access**.

| Label | Description |
| --- | --- |
| Advanced Condition | Offers several options to enhance the condition |
| JSONLogic | Executes the custom logic using [JSONLogic](https://jsonlogic.com/) |

### Logic

Use this tab to add a custom logic to your form component.

| Label | Description |
| --- | --- |
| Logic Name | Adds the name of the logic in this custom field |
| Type | Select the type of the logic from the following: - Simple - JavaScript - JSON Logic - Event |
| Add Action | Adds a new action to the custom field |
| Action Name | Adds the name of the action to the field |
| Type | Select the type of the action from the following: - Property - Value - Validation |

### Identity Profile

Use this tab to associate a **Data Element Type** of your choice from the menu list to integrate with your form component.

| Label | Description |
| --- | --- |
| This field is a data subject identifier | Makes the field a Data Subject identifier |
| Data Element Type | Adds a Data Element Type to associate with the form |

## Related

- [Building a universal preference center](/building-a-universal-preference-center.md)
- [Customizing your universal preference center](/customizing-your-preference-center.md)
- [Location and Language Intelligence](/location-and-language-intelligence.md)
- [Universal preference center translations](/universal-preference-center-translations.md)
