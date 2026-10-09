---
title: "Understanding identifiers for DSR request processing"
slug: "understanding-identifiers-for-dsr-request-processing"
updated: 2025-11-02T11:22:49Z
published: 2025-11-02T11:22:49Z
canonical: "helpcenter.securiti.ai/understanding-identifiers-for-dsr-request-processing"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Understanding identifiers for DSR request processing

**Scenario**

As a Data Privacy Officer, you manage DSR requests for systems that don’t identify users by email or use more than one identifier to identify data subjects. A standard request using only email may only return partial results or may not return any results. By configuring identity profiles with alternate identifiers like phone number, you ensure accurate data retrieval even from data systems especially scanless systems. You can also apply strict access controls to prevent misuse, ensuring compliance without sacrificing security.

### Overview

Normally, Securiti processes DSR requests using only their email address to identify the data subject when it queries your data systems for personal data. However, you can configure Securiti DSR request forms and Data System connectors to use an Identity Profile consisting of a group of other identifiers (identity PDs) to locate and extract the Data Subject personal data.

For example, a scanless data system might identify data subjects using phone number instead of email address. A DSR request for such a data system processed normally would return no results. However, using this feature data subject phone number as identity PD returns positive results.

One important aspect of DSR requests with identity PDs is that you must process them carefully to prevent submitters from exploiting them to gain unauthorized access to personal data. When using email address as the only identity PD, our standard verification process validates that the address is indeed controlled by the data subject in question. When using additional identity PD, you have no such assurance that the request submitter is the data subject in question. Therefore you must build that verification into your system, either by using a verification service such as ID.me or by controlling access to the DSR form so that it can only be accessed using the identity PD as access credentials.

Note that the identity PDs you can use depends on those present in your data systems. For scanless data systems each connector has a specific set of Identity PDs you can use. For more information, see the topics for your data systems in [Data stores and connectors](/v1/docs/managing-data-system-connectors).

To configure identity PDs for DSR requests:

1. Configure your structured Data System connectors to accept identity PD other than email address as described in [Configuring structured data systems for multiple identifiers](/v1/docs/configuring-structured-data-systems-for-multiple-identifiers).
2. Configure your DSR request forms to collect identity PD for enhanced DSR request processing as described in [Configuring DSR request forms for multiple identifiers](/v1/docs/configuring-dsr-request-forms-for-multiple-identifiers).
