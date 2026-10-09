---
title: "EPod V2 FAQs"
slug: "epod-v2-faqs"
updated: 2026-06-19T15:59:42Z
published: 2026-06-22T21:00:21Z
canonical: "helpcenter.securiti.ai/epod-v2-faqs"
area: platform
modulo: pods
tipo: guia
data_captura: 2026-10-08
---

# EPod V2 FAQs

**Why does EPod V2 require `SYS_ADMIN` privileges?**

EPod V2 requires `SYS_ADMIN` to dynamically mount NFS and SMB file systems during scans. This privilege lets the scanning pods perform mount operations and actively enforce governance actions such as file labeling and quarantine workflows. It is granted only to the scanning pods and is not applied globally across the platform.

For more information, see [EPod V2 installation](/latest/docs/epod-v2-installation-1).
