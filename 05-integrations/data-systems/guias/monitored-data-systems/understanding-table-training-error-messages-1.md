---
title: "Understanding table training error messages"
slug: "understanding-table-training-error-messages-1"
updated: 2026-02-09T20:36:17Z
published: 2026-02-09T22:00:18Z
canonical: "helpcenter.securiti.ai/understanding-table-training-error-messages-1"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Understanding table training error messages

During Table training, Securiti shows popups with error messages for Table Joins that might disrupt the uniqueness of primary identifiers, as shown in the examples below:

- For a given Table if a Column is enabled for scanning and there is another Column in the same Table with the same core Data element type we show a warning.
- For a given Table if a Column is marked as "Primary Identifier" and there is already a Column in that Table which is also marked as primary identifier and has the same Data element type then we show an error message.
- If introducing a join results in two or more Primary Identifier tables joining together (directly or indirectly), we stop this join and show an error.
