---
title: "Known limitations"
slug: "known-limitations"
updated: 2025-10-30T18:20:14Z
published: 2025-11-03T06:13:35Z
canonical: "helpcenter.securiti.ai/known-limitations"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# Known limitations

This document shows the known limitations regarding scanning or the performance of the pods.

**SQL scan performance limitation**

SQL scanning performance shows lesser improvement with the addition of extra nodes in your cluster if you have massive data in your database. This limitation is because the SQL connector processes each table by collecting metadata. Parallelism in the connector pod is limited to avoid overloading source connections. This limited parallelism slows down the task production. Therefore, scan performance doesn't scale proportionally against the number of nodes.
