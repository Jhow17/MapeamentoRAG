---
title: "AI Security Posture Management"
slug: "ai-security-posture-management"
updated: 2025-11-06T04:35:13Z
published: 2025-11-06T04:35:13Z
canonical: "helpcenter.securiti.ai/ai-security-posture-management"
area: dspm
modulo: security-posture-management
tipo: guia
data_captura: 2026-10-06
---

# AI Security Posture Management

Securiti provides visibility into your AI infrastructure by discovering AI services and mapping how they connect to each other and to the underlying data they use. The platform identifies relationships among AI components such as AI Models, AI Platforms, AI Knowledge Bases, and AI Agents and highlights the data elements, personal data, and content profiles associated with each.

This helps you understand what types of data your AI services use, including whether that data is personal, sensitive, or subject to specific compliance controls. To understand how security posture management works, see [Using Security Posture Management](/v1/docs/using-security-posture-management).

### Overview

Securiti helps you gain a comprehensive understanding of your organization’s AI landscape. By discovering AI assets, mapping their data relationships, and identifying the types of data they process, Securiti lets you assess potential security, privacy, and compliance risks associated with AI services. It enables informed decision-making and strengthens data governance across your AI ecosystem. To see the list of supported AI services, see [List of Support Cloud Native Services](/v1/docs/data-security-posture-management-solution#list-of-supported-cloud-native-services).

### Understanding AI Relationships and Connections

Securiti maps relationships between AI components to help you understand how AI services interact with data systems and posture findings. These relationships show how AI assets connect to each other and to the underlying data, posture policies, and compliance rules.

For example, **AI Agent → AI Knowledge Base → Data System → Files → Data Element & Content Profile**.

This relationship shows how an AI Agent interacts with an AI Knowledge Base to retrieve or process information stored in connected data systems. It helps you trace what kind of data an AI Agent can access through its knowledge sources and connected systems, including personal or sensitive data.

![Overview of AI Agent's security posture and related data systems in AWS Cloud.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ai-1.png)

For example, **AI Agent → Posture Policy & Posture Finding → Posture Rule**.

This relationship shows the compliance and security posture of the AI Agent, helping you identify whether it meets defined security policies or if any risks are detected.

For example, **AI Knowledge Base → AI Agent → Data System → Files → Data Element & Content Profile**.

This relationship provides a data-centric view. It helps you explore which AI Agents use a particular Knowledge Base and what data flows are triggered as a result, allowing you to assess the exposure of specific data sources.

![Overview of AI Knowledge Base structure and related components in AWS Cloud environment.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ai-2.png)

For example, **AI Knowledge Base → Posture Policy & Posture Finding → Posture Rule**.

This relationship highlights the compliance evaluation of the Knowledge Base itself, showing posture checks applied to its configuration or connected data sources.

Together, these relationships provide a comprehensive view of your AI environment, how AI components interact, what data they access, and where potential security or compliance risks may exist. This visibility helps you strengthen governance, assess posture, and build a more reliable Retrieval-Augmented Generation (RAG) model.

## Related

- [Getting Started with Security Posture Management](/getting-started-with-security-posture-management.md)
- [Using Security Posture Management](/using-security-posture-management.md)
