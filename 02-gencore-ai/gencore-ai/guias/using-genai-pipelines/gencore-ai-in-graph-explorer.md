---
title: "Gencore AI in Graph Explorer"
slug: "gencore-ai-in-graph-explorer"
updated: 2026-01-13T06:06:21Z
published: 2026-01-13T06:06:21Z
canonical: "helpcenter.securiti.ai/gencore-ai-in-graph-explorer"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Gencore AI in Graph Explorer

You can view the details related to Gencore AI entities and GenAI pipelines in Graph explorer. To do so, create your queries using the properties and relationships. Additonally, you can also view entitlements in Graphs.

> [!NOTE]
> **Note**
> 
> For more information, see [Using Data Command Graph](/latest/docs/using-data-command-graph).

### Example for viewing Gencore AI details in Graph Explorer

To find details about pipelines with Amazon S3 configured data system, in Graph:

1. Click **Add (+)**.
2. Select **Gencore AI>GenAI pipeline**.
3. Select **Add Relationship** and choose **Data System**.
4. Select Add **Property>Asset Type.**
5. Select operator as **Equals**.
6. Choose **Amazon S3**.
7. Click **Apply**. Securiti displays the relevant results.

![Gencore_AI_in_Graph_Explorer_Use_Case.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7a135954-2600-f4bd-ff50-a8252e0bfada(1).png)

> [!NOTE]
> **Note**
> 
> For more information, see [Using Data Command Graph](/v1/docs/using-graph-explorer).

The GenAI pipeline continuously load structured and unstructured data from supported data sources and safely transforms it to be used by GenAI models.

## Related

- [Using GenAI pipelines](/using-genai-pipelines.md)
