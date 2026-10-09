---
title: "Microsoft 365 OneDrive FAQs"
slug: "microsoft-365-onedrive-faqs"
updated: 2026-06-16T07:16:53Z
published: 2026-06-16T07:16:53Z
canonical: "helpcenter.securiti.ai/microsoft-365-onedrive-faqs"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Microsoft 365 OneDrive FAQs

This article answers frequently asked questions about the Microsoft 365 OneDrive connector.

### Scan coverage and file versions

The FAQs below cover the Microsoft 365 OneDrive scanning capabilities and limitations.

****Does the OneDrive connector process all file versions during a Discovery Scan or Data Inventory Sync, or only the latest version?****

Securiti processes only the current (latest) version of each file rather than the full version history. As a result, the actual scannable data may be significantly lower than the reported storage footprint. For example, 80 TB, including version history, may be reduced to 70 TB when considering only current versions.
