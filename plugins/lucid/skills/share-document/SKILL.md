---
name: share-document
description: Share a Lucid document with others via a share link or by granting access to specific collaborators by email. Use when the user asks to share, invite, or grant access to a Lucidchart or Lucidspark document.
---

# Share Document

When the user asks you to share a Lucid document, follow these steps:

1. Identify the document to share. If the user hasn't specified one, use `mcp__lucid__search` to help them find it, or ask for the document ID or URL.

2. Determine the sharing method:
   - **Share link** — creates a URL that can be distributed to anyone (or restricted to account members)
   - **Direct collaborator access** — grants specific people access by email address

3. Determine the permission level. If not specified, ask the user:
   - `view` — view only
   - `comment` — view and comment
   - `edit` — view and edit
   - `editandshare` — view, edit, and reshare

4. Execute the appropriate sharing action:

   **For share links**, use `mcp__lucid__lucid_create_document_share_link`:
   - Set `role` to the chosen permission level
   - Optionally set `expires` (ISO 8601 timestamp) if the user wants a time-limited link
   - Set `allow_anonymous` to `true` only if the user explicitly wants anonymous access
   - By default, `restrict_to_account` is `true` (account members only)
   - Return the share link URL to the user

   **For direct collaborator access**, use `mcp__lucid__share_document_with_collaborators`:
   - Provide the list of email addresses
   - Set `role` (defaults to `editandshare` if not specified)
   - Report the results for each email (success or failure)
