---
title: "AI Tuning FAQs"
slug: "ai-tuning-faqs"
updated: 2026-09-24T14:12:19Z
published: 2026-09-24T14:12:19Z
canonical: "helpcenter.securiti.ai/ai-tuning-faqs"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# AI Tuning FAQs

---

### 

#### Does Securiti Sovereign Deployment support AI Tuning?

No, Securiti Sovereign Deployment does not currently support AI tuning.

#### Can classified columns be viewed if the discovery scan is deleted?

If a discovery scan is deleted, all columns, sample data, and vectors associated with that scan, whether classified or unclassified, are permanently removed.

#### Why is AI tuning not available for all the scanned columns?

- For columns without access to sample data, vectors cannot be generated, so AI Tuning is not supported. After access is granted, use Re-sync Classification Data to enable AI Tuning for those columns.
- AI Tuning may not be available for every column. You can reload failed columns for the AI Tuning feature using the Re-sync Classification Data. For more information, see [Configuring AI Tuning](/latest/docs/configuring-ai-tuning).
- Columns without sample data cannot generate vectors and therefore do not support AI Tuning.
- AI Tuning is supported for all columns except CLOB columns.

#### Are previously scanned columns supported by AI Tuning?

Yes, columns from earlier scans with sample data are supported once AI Tuning is configured.

#### Why can't I edit a column during the review process?

Edits are temporarily disabled for any column undergoing AI Tuning. You can make changes once the AI Tuning process is complete.

#### Why isn’t AI Tuning applied to the selected columns?

AI Tuning is not applied to columns that have already been manually updated or validated through the Validation Workbench. It only applies to columns that are unvalidated, untouched by the user, or previously tuned using AI Tuning.

#### Do the Validation sessions impact the future classifications?

Validation sessions in the Validation Workbench do not impact future classifications.

#### Do customers need explicit index creation permissions?

Yes. AI Tuning requires permission to create and manage indexes.

#### Who manages index retention?

Securiti manages retention. Data is deleted only when corresponding scans are deleted.

#### Do pods need direct access to Elasticsearch or OpenSearch?

Yes. They must reach the instance inside your environment.

#### Does AI Tuning support unstructured data systems?

Yes, Securiti provides AI Tuning support for Structured data and Document Type.

Structured data refers to data that is typically stored in well-defined, tabular, or hierarchical structures, such as databases, spreadsheets, or data tables. Examples of structured data include customer information in a CRM database, financial records in an accounting system, product catalog data in the Securiti platform, and so on.
