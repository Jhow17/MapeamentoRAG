---
title: "Inspecting instances in Graph Explorer"
slug: "inspecting-instances-in-graph-explorer"
updated: 2026-05-25T16:46:24Z
published: 2026-05-25T21:00:10Z
canonical: "helpcenter.securiti.ai/inspecting-instances-in-graph-explorer"
area: dspm
modulo: data-command-graph
tipo: guia
data_captura: 2026-10-06
---

# Inspecting instances in Graph Explorer

The Instance Explorer lets you view details and explore all entity relationships for a particular entity. It provides a granular view of a single instance and its related entities in a graphical view while displaying counts for each entity.

> [!NOTE]
> **Important**
> 
> The Instance Explorer may not return complete results for all the related entities shown in the view. We recommend that you do not use the Instance Explorer results for reporting purposes.

### Using metadata explorer

To open the Metadata explorer for an instance.

1. Click on the instance you want to visualize from the Graph Explorer grid. Securiti also lets you access it by clicking the metadata explorer icon, as shown below.

![Graph Explorer interface displaying data system and security posture findings with highlighted elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Metadata Explorer_Graph Explorer.png)
2. In the **Metadata explorer** popup, you can view the metadata for your instance. The metadata explorer provides the following options:
  - **Explore**: From the upper left corner of the metadata explorer, click **Explore** to open the Instance Explorer. The Instance Explorer provides a granular view of your instance and its connections in the graph.
  - **View JSON**: From the upper right corner of the metadata explorer, click **View JSON** to see the JSON expression for your query.

> [!NOTE]
> **Note**
> 
> This JSON expression is only available as a read-only view and cannot be edited.
  - **Hide from Table**: Click options (three dots) next to the metadata fields, and click **Hide from Table** to hide that property from the grid.
  - **Include Filter Value**: Click options (three dots) next to the metadata fields, and click **Include Filter Value** to include that property in your query.
  - **Exclude Filter Value**: Click options (three dots) next to the metadata fields, and click **Exclude Filter Value** to exclude that property in your query.
  - **Copy to Clipboard**: Click options (three dots) next to the metadata fields, and click **Copy to Clipboard** to copy the value of that property.

![Overview of AWS Athena security posture findings and related asset details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Copy to Clipboard_Graph Explorer.png)

### Using Instance Explorer

The Instance Explorer helps you analyze and visualize the relationships between data entities within an instance. You can view related entities, explore connections, and examine properties in a unified interface.

To open the Instance Explorer, click **Explore** from the Metadata Explorer or select the Instance Explorer icon for an instance, as shown below. Once opened, the Instance Explorer displays the instance name in the upper-left corner.

![Graph Explorer interface displaying data system and security posture findings with highlighted elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Instance Inspector_Graph Explorer.png)

![Diagram illustrating data system components, including policies, regulations, and security findings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Graph View_Graph Explorer.png)

#### Components of the Instance Explorer

The Instance Explorer includes the following components:

- **Graph view**: Displays a visual representation of related entities and their relationship counts for the selected instance.
- **Entities panel**: Lists all related entities for the selected instance in the left panel. Click any entity to view its related instances and properties.
- **Properties grid**: Displays all properties of an instance as individual columns in a tabular format.

#### Graph View controls

Securiti provides the following controls in the Instance Explorer for managing the graph view:

| Control | Description |
| --- | --- |
| Hide Graph | Click Hide Graph to hide the visual representation of related entities. This expands the view to display instance properties in more detail, as shown below. ![Diagram illustrating data system components and their relationships in policy labeling.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Hide Graph Button_Graph Explorer.png) ![Overview of the Policy-Labeling data system with asset details and hosting information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Hide Graph_Result_Graph Explorer.png) |
| Reset Graph | Click Reset Graph to refresh the graph and update the view with the latest data, as shown below. ![Diagram illustrating data system components and their relationships in policy labeling.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Reset Graph Button_Graph Explorer.png) |
| Rotate Screen | Click Rotate Screen to rotate the graph for better visualization and to view relationships from different angles, as shown below. ![Diagram illustrating data system components, including policies, regulations, and security posture findings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Rotate Screen_Graph Explorer.png) |
| Minimize Zoom | Click Minimize Zoom to reduce the zoom level and view a wider section of the graph, as shown below. ![Diagram illustrating data system policies, regulations, and security posture findings in cloud environments.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Minimize Zoom_Graph Explorer.png) |
| Zoom in and Zoom out | Use Zoom In and Zoom Out controls to adjust the view for closer or broader visualization of related entities, as shown below. ![Diagram illustrating data system components, including policies, regulations, and security posture findings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Zoom In and Zoom Out_Graph Explorer.png) |
