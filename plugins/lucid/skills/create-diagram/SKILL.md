---
name: create-diagram
description: Creates a Lucidchart or Lucidspark diagram from a description, code, data, or architecture. Use when the user asks to visualize, diagram, chart, or map out a workflow, process, system architecture, org chart, flowchart, sequence diagram, ER diagram, or any other visual representation.
---

# Create Diagram

When the user asks you to create a diagram, follow these steps:

1. Analyze what the user wants to visualize. If their request is vague, ask clarifying questions about the type of diagram, the entities/steps involved, and the relationships between them.

2. Use the `mcp__lucid__lucid_create_diagram_from_specification` tool to create the diagram in Lucid. Choose the appropriate product:
   - Use `lucidchart` for structured diagrams (flowcharts, org charts, ER diagrams, sequence diagrams, architecture diagrams, BPMN, network diagrams)
   - Use `lucidspark` for brainstorming, sticky notes, freeform collaboration boards

3. Build the Standard Import JSON specification with well-positioned shapes, clear labels, and connecting lines. Use appropriate shape types for the diagram type (e.g., `decision` diamonds for flowcharts, `bpmnEvent`/`bpmnGateway` for BPMN, `database` for data stores).

4. After creating the diagram, share the document URL with the user so they can view and edit it in Lucid.
