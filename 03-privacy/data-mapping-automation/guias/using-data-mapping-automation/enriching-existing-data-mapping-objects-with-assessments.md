---
title: "Enriching existing data mapping objects with assessments"
slug: "enriching-existing-data-mapping-objects-with-assessments"
updated: 2025-12-11T11:35:04Z
published: 2025-12-11T11:35:04Z
canonical: "helpcenter.securiti.ai/enriching-existing-data-mapping-objects-with-assessments"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Enriching existing data mapping objects with assessments

**Scenario**

As a Data Privacy Officer preparing for a new product launch, you need to ensure data processing activities comply with regulations. Without visibility into data flows, hidden risks can delay release. By using data mapping, you pinpoint where personal data is collected, stored, and shared. This helps you identify compliance gaps early and take corrective action before the product goes live.

### Initiate Assessment

You can use assessments to quickly enrich existing data mapping objects by collecting the necessary information from those who know the most about the item in question. When the assessment is published, Securiti applies the information collected to the data mapping object.

To initiate an assessment:

1. Open **Data Mapping Automation** and from the left hand side menu, choose the type of object (asset, process, vendor, institution) you want to enrich. ![Screenshot_2025-05-20_at_12_52_33_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-59d52c10-206a-29b2-f9c8-0a960f1f88b0.png)
2. Click the specific object item you want to enrich.
3. Near the upper right corner of the page, click **Initiate Assessment**. ![Screenshot_2025-05-20_at_12_50_57_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1015401a-6825-9c1b-9034-470606de8e9e.png)
4. On the Launch New Assessment popup, apply the settings to suit. For more information, see [Launching a new assessment in Securiti](/v1/docs/launching-a-new-assessment-in-securiti).
5. Click **Launch New Assessment**.

Securiti creates the new assessment and alerts the participants, who can then proceed to answer the assessment.

Upon assessment completion, Securiti populates any linked assessments under the Assessments tab in object details.

### Link Assessment

> [!NOTE]
> **Note**
> 
> Object linking is available for all assessment types.

Similar to initiating an assessment from a data object item, you can link existing assessments with the object. These assessments can contain sections or questions that are relevant to the data mapping object in question or have participants with the knowledge about the item.

Linking assessments can speed up the process as opposed to creating assessments from scratch. As the assessment transitions to complete stage, Securiti applies the information gathered to the data mapping object where applicable.

To link an assessment:

1. On the object (asset, process, vendor, institution) details page, near the upper right corner, click **Link Assessment**.

![Screenshot_2025-05-20_at_12_53_03_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8a2e9c33-8958-1fbd-34bd-3cf910173f7d.png)
2. On the Link Assessment to Object popup (Securiti also shows the name of the object at the top), you can view any existing linked assessments, search for assessments by their ID or name, and configure how many rows you want to see per page.
3. Mark the checkbox next to the assessment you want to link. To unlink, clear the checkbox next to the assessment.

Enable the **View Selected Only** toggle to narrow down the assessments you've selected. Click **Clear Selections** to remove all selections from assessments.
4. Based on if you want to link or unlink assessments, click **Link** or **Update** accordingly. ![Screenshot_2025-05-20_at_12_54_08_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0a73addd-8b68-eb8a-470e-0b0111a0f0c7.png) ![Screenshot_2025-05-20_at_12_55_56_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4aa883ad-4d95-f78b-eaf3-061633e82488.png)

> [!NOTE]
> **Note**
> 
> Unlinking only applies to assessments that you have manually linked with an object. You can't unlink the object association for [Object Field Assessments](/v1/docs/answering-assessment-questions-in-securiti) after they're approved.

You can also remove the linked assessment(s) from an object using the Assessments tab. Click options **(three vertical dots)** next to the assessment and choose **Clear Association**.

### Linked Objects on Assessment details

Assessment details also provide the ability to link multiple objects or unlink existing ones.

To link or unlink via assessment details:

1. On the Internal Assessments list, click the assessment with an associated object(s).
2. Near the upper right corner of the details page, click **Actions > Linked Objects**.

![Screenshot_2025-05-20_at_12_57_38_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c4a423d-97b6-53ab-12a7-e8a96f2d7b78.png)
3. On the Linked Objects popup, Securiti shows the associated object.

Mark the checkbox next to the object(s) and click **Unlink All Selection**. ![Screenshot_2025-05-20_at_1_26_48_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d8f2a981-7c6f-f116-1619-aa651b227f04.png)
4. To link new a new object(s), click **Link New Objects**. ![Screenshot_2025-05-20_at_1_23_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6fe013a7-f1d2-c5d5-a601-6696467f7ab5.png)

On the Link New Objects popup, search for or select the object type (Asset, Vendor, Institution, Process). The number of objects for each type is also shown.
5. Mark the checkbox against an asset(s), vendor(s), etc. and click **Link Objects**. ![Screenshot_2025-05-20_at_1_31_32_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2c0fb378-0c05-9811-f4a7-618ae7b859ca.png)
6. (Optional) Click **View Selected Only** or **Clear Selections** to filter out selected objects or clear selections, respectively.

You can also initiate objects association via assessments list, as shown below. This opens up the popup to link desired object(s).

![Screenshot_2025-05-21_at_1_23_30_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c2e06ba8-bbff-fd7d-0bd9-d949043e4885.png)

Assessments answer different questions related to an entity, such as purpose, etc. Also, with each assessment, you can associate risks.

An asset records data for any application or store. You can use It to record an asset's name, description, purpose, etc. Also, you can use an asset in processes.

Institution is the same as an asset - an entity that serves a different purpose.

A process defines the flow of data between entities and processes.

## Related

- [Creating and editing processes](/creating-and-editing-processes.md)
- [Importing and exporting data mapping items](/importing-and-exporting-data-mapping-items.md)
