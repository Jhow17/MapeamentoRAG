---
title: "DSP"
slug: "dsp-regular-node"
updated: 2026-02-12T06:01:00Z
published: 2026-02-12T06:01:00Z
canonical: "helpcenter.securiti.ai/dsp-regular-node"
area: dspm
modulo: workflows
tipo: guia
data_captura: 2026-10-06
---

# DSP

Manage DSR requests via the Data Subject Portal using available DSR request forms

| Parameters | Description |
| --- | --- |
| Operation | Create | Create a DSR request |
| Form | Choose the DSR request form from among those available to use to create the DSR request |
| DSR type | Build a list of the DSR types for the new DSR request. Select one or more DSR types from the menu.The menu shows all system and custom request types defined in the [Request Types page](/v1/docs/configuring-dsr-request-types) of the DSR settings. You can configure these request types at the tenant level, ensuring they apply across all organizations. While you can switch between organizations, the request types remain consistent across all organizations within the same tenant. For more information, see [Configuring DSR request types.](/v1/docs/configuring-dsr-request-types) |
| Payload | The payload for the DSR request. Must be a valid JSON object |
| Metadata | The metadata for the DSR request. Must be a valid JSON object |
