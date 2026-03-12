---
name: search-documents
description: Search for existing Lucid documents (Lucidchart or Lucidspark) by keyword. Use when the user asks to find, locate, or list their diagrams, charts, boards, or Lucid documents.
---

# Search Documents

When the user asks you to find or search for Lucid documents, follow these steps:

1. Identify the keywords from the user's request. If the request is vague (e.g., "find my diagrams"), ask what topic, project, or name to search for.

2. Use the `mcp__lucid__search` tool with the relevant keywords (max 400 characters). The search returns documents sorted by relevance, up to 200 results.

3. Present the results to the user in a clear list showing:
   - Document title
   - Document URL (so they can open it directly)

4. If the user wants to see the contents of a specific document, use the `mcp__lucid__fetch` tool with the document's ID to retrieve its details.
