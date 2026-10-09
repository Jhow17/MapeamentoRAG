---
title: "Customizing data breach management"
slug: "customizing-data-breach-management"
updated: 2026-04-28T05:30:42Z
published: 2026-04-28T05:30:42Z
canonical: "helpcenter.securiti.ai/customizing-data-breach-management"
area: privacy
modulo: data-breach-management
tipo: guia
data_captura: 2026-10-08
---

# Customizing data breach management

### Customizing data breach management stages

You can choose either the SANS or Securiti standards for the names of the stages for data breach incidents.

1. In Securiti, open **Data Breach Management**, then choose **Settings > Settings**.
2. In the **Stages Settings** area, choose either **SANS** or **Securiti Incident & Breach Management**, then click Save Standard.

The table below shows the correlations between the different stages under the two systems:

| Securiti Incident & Breach Management | SANS |
| --- | --- |
| Verify | Identification |
| Detect | Analyze |
| Analyze | Containment |
| Remediate | Eradication/Recovery |
| Notify | Notify |
| Complete | Lessons Learned |

Except where noted, our documentation refers to these stages using the Securiti Incident & Breach Management standard.

### Customizing the data breach intake form and workbench stages

Securiti lets the following roles in your Securiti tenant customize data breach intake form:

- Super Admin
- Module Owner
- DPO
- Org Admin
- Operator

You can use reference lists to customize the information collected on the data breach intake form and in the workbench, as follows:

1. In Securiti, open **Data Breach Management**, then choose **Settings > Reference Lists**.
2. On the Data Breach Management Reference Lists page, click the reference list you want to modify.
3. On the page for the reference list, click the section you want to modify.
4. To modify an existing reference list:
  1. In the main part of the page, click the reference list you want to modify.
  2. On the popup, near the upper right corner click **Edit**, then customize the available options as follows:
    - To disable an option without removing it permanently, toggle the slider at its left end.
    - To permanently remove an option, click the delete (trash can) icon at its right end.
    - To add a new menu option, type the option description in the box at the bottom of the options list, then press Enter.
5. To delete an existing reference list, at its right end choose **Options** (three dots) **> Delete**., then click **Yes** to confirm.

> [!NOTE]
> **Important**
> 
> The breach intake form limits modification options to customizing existing field names and drop-down menu choices. It does not support adding new fields or options within the current framework.

---

### FAQ

#### 1. Can I create custom breach intake forms?

As per the current implementation, the breach intake form limits modification options to customizing existing field names and drop-down menu options. It does not support adding new fields in the breach intake form

#### 2. Can I create custom reference lists?

Within the current framework, you cannot create a new reference list.
