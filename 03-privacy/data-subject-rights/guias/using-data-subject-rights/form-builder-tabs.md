---
title: "Form Builder Tabs"
slug: "form-builder-tabs"
updated: 2026-01-14T08:15:49Z
published: 2026-01-14T08:15:49Z
canonical: "helpcenter.securiti.ai/form-builder-tabs"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Form Builder Tabs

You can use simple form builder tabs in DSR Form Builder to quickly create, customize and publish forms that data subjects use to submit DSR requests.

### Display

Use this tab to customize the appearance of the component. You can customize its position, description, and overall aspects of how you want your component to appear in the DSR form.

| Label | Description |
| --- | --- |
| Label | Adds a label for the field to display next to it |
| Hide Label | Hides/unhides the label of the component. When checked, it shows the label in the form builder, but not when the form is rendered |
| Label Position | Adjusts the position for the label of the field |
| Placeholder | Adds a placeholder text to appear in the text field when it is empty |
| Description | Adds a custom description below the input field |
| Tooltip | Adds a tooltip to the right side of the input field label |
| Error Label | Adds a custom error label for the field when an error occurs |
| Custom CSS Class | Adds a custom CSS class for the component > [!NOTE] > **Note** > > When you access a form using the direct URL, it loads with styles from the Securiti application. So, any custom CSS classes you define (like blue or text-white) apply correctly. But when you embed the form in an external website using the **Embedded Form URL**, it doesn't load Securiti's stylesheet. This means the form can't recognize your custom class names. To apply consistent styling in this case, use inline styles directly in your content. |
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
| Format | Adds a custom date format |
| Widget | Adds a widget to input the field value and adds a widget icon at the end of the input field |
| Rows | Provides control of the number of rows to be displayed in the text area |
| Editor | Selects the type of WYSIWYG editor to use for the text area |
| Enable Image Upload | Enables to add an image in the form when checked |
| Image Upload Storage | Selects storage service to save the uploaded image in |
| Image Upload Directory | Adds a field in the directory to store all the uploaded images |
| HTML Tag | Adds the tag of the HTML element |
| Content | Adds the content of the HTML element. You can also apply bold or italic styles to these elements. You can use the <do-not-translate> tag to keep specific keywords untranslated. For instance, if you want to keep the word “Data Subject Rights” untranslated, enter <do-not-translate> Data Subject Rights</do-not-translate>. You can also change the color of HTML elements. For instance, if you intend to set the color of specific text on a DSR form to blue and the background color to yellow, enter the following code: ```xml <p style="color:blue;background-color:yellow;">This is an html element </p> ``` |
| Label Width | Adds the width of the label on line in percentages |
| Label Margin | Adds the width of the label margin on line in percentages |
| Shortcut | Adds a shortcut for this component |

### Data

Use this tab to add a placeholder dummy value to let you know what syntax you should use before initial interaction with the component. You can also customize the refresh rate of data based on different scenarios if any change occurs.

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

Use this tab to add validation, restriction, and custom validation messages to your component. For instance, you can restrict your field to be unique and also make it a required field before you can submit information.

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

Use this tab to display the current component based upon a custom condition. You can show the component in the form based upon a certain condition. For instance, you can display dynamic request types on the DSR form based on other selected components such as country/region or Data Subject relationship. For more information, see [Configure DSR form for dynamic request types](/v1/docs/configure-dsr-form-for-dynamic-request-types)

| Label | Description |
| --- | --- |
| Advanced Condition | Offers several options to enhance the condition |
| JSONLogic | Executes the custom logic using [JSONLogic](/v1/docs/securiti-pods-and-elastic-pods) |

### Identity Profile

Use this tab to associate a **Data Element Type** of your choice from the menu list to integrate with your component.

| Label | Description |
| --- | --- |
| This field is a Data Subject identifier | Makes the field a Data Subject identifier |
| Data Element Type | Adds a Data Element Type to associate with the form |

---

### FAQ

#### 1. How do you add custom validation on form fields? "For example, making "Add an Attachment" required depending on the Data Subject Type selection."

While configuring the DSR form, you must write the JavaScript code and add the validation code in the Advanced Conditions section under the Conditional component to include custom validation on form fields.

#### 2. Can we rearrange the out of the box form configuration fields (the blue dotted lines)?

The blue dotted lines provide a fixed structure/layout to the form that cannot be changed. You can drag and drop fields outside of the blue dotted boxes, but it doesn't give any fixed structure to the form.

#### 3. How can we add horizontal lines to break up form fields into sections?

While configuring the DSR form, simply drag and drop the HTML element to the position where you want to add a horizontal line to break up form fields into sections. Next, add <hr> in the Content section of the HTML element and click Save.

![Screenshot_2024-03-14_at_10_46_46_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dc617da3-1f13-68ed-e902-045516f3d4ce.png)

#### 4. How do we change the style of radio buttons to mimic the style of the out of the box request type radio field?

While configuring the DSR form, simply drag and drop the **Radio** element from custom fields. Further, under the **Values** section specify the labels for radio form fields and in **Custom CSS Class** section, enter “**formio-component-inline-request-type mb-5 pb-1**”

![Screenshot_2024-03-17_at_5_18_10_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9780e2fa-7b75-5040-e060-5f7766d0823c.png)
