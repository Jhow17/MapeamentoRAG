---
title: "Fulfilling DSR requests for Twilio"
slug: "fulfilling-dsr-requests-for-twilio"
updated: 2026-06-28T14:41:31Z
published: 2026-06-28T14:41:31Z
canonical: "helpcenter.securiti.ai/fulfilling-dsr-requests-for-twilio"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Fulfilling DSR requests for Twilio

This article covers the DSR privacy settings and supported DSR request types for Twilio.

## DSR Privacy Settings

| Parameter | Description |
| --- | --- |
| Include this instance in the DSR Workflow | Enabling this option includes the respective data system in processing the DSR request. > [!WARNING] > **Important** > > For unstructured data system instances, the DSR workbench creates subtasks only if data is found in the data search. If no data is found, tasks are not created. |
| Guest Users | Enable this to automatically assign DSR subtasks created for the data system to guest users. See [Automatically assign DSR subtasks to guest users](/v1/docs/automatically-assigning-dsr-subtasks-to-guest-users), for more information. |
| Guest User Guidance Text | Enter the guidance text for guest users to fulfil DSR requests. |
| Limit Guest access to specific DSR types | If selected, collaborators will automatically be assigned only to the requests of the selected DSR types |
