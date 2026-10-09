---
title: "Data Elements"
slug: "data-elements"
status: "update"
updated: 2026-04-20T17:31:57Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/data-elements"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Data Elements

A data element is a basic unit of data that represents a single piece of information. It is often defined by its name, type, and format, and it can be part of a larger data system, which can be structured, unstructured, or streaming. Data elements are essential for organizing, storing, and managing data, and they can vary widely depending on the context in which they are used, since every data element has a name, type, format, and specific purpose.

In your storage environment, which may comprise databases and/or file systems, the data element might include:

- Customer ID (Integer)
- Name (String)
- Email Address (String)
- Date of Birth (Date)
- Address (String)
- Passport Number
- Bank Accounts and so on

The Securiti platform has a pre-configured rich set of system data element types that it uses to identify types of personal data within your data systems. For a list of the available system data element types, see [System data element types](/v1/docs/system-data-element-types).

To view a list of all system and custom data elements in Securiti, open **Sensitive Data Intelligence** and from the left panel, choose **Data Classification** > **Data Elements**.

![Overview of data elements and categories in a system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.30.46 PM.png)

Sensitive information often includes personal details such as names, addresses, social security numbers, and medical records that may contain confidential or sensitive information, which may be compromised and could lead to harm, loss, or unauthorized access. Safeguarding this information is crucial to protecting privacy and preventing identity theft, fraud, or other forms of exploitation. Organizations have a responsibility to ensure that individuals’ personal data is handled securely and used only for legitimate purposes.

When you configure a discovery scan for any of the structured, unstructured, or streaming data systems, Securiti can scan your data to identify sensitive data elements that you can configure in your environment. For more information, see:

- [Customizing system data element types](/v1/docs/data-elements-customizing-system-data-element-types) and [Customizable system data element types](/v1/docs/customizable-system-data-element-types)
- [Configuring custom data element types](/v1/docs/configuring-custom-data-element-types)

## Related

- [System data element types](/system-data-element-types.md)
- [Customizable system data element types](/customizable-system-data-element-types.md)
- [Configuring custom data element types](/configuring-custom-data-element-types.md)
