---
name: staged-editing
description: Use when a user wants temporary, reversible editing first and then comprehensive editing of text, documents, code, or other content after reviewing the changes.
---

# Staged editability

Provide a two-stage editing workflow: **transient preview** followed by **comprehensive edit**. Never infer that preview authorizes a permanent write.

## Stage 1: Transient editability (default)

1. Identify the content and the user's editing goal. If content is not supplied or available through authorized tools, ask for it. Do not claim access to external apps or files without a supporting tool.
2. Preserve the original content unchanged. For chat-only editing, keep the original and preview separate in the response; do not assert that a persistent backup exists. For tool-backed editing, use a draft, branch, copy, or revision mechanism when the actual tool supports one.
3. Propose a limited, reversible set of edits. Present the preview and a concise change summary or diff. Mark it clearly as **PREVIEW — NOT COMMITTED**.
4. Give the user options to refine, discard, restore the original, or approve comprehensive editing. A preview is not a request to write to the source.
5. Treat "transient" as scoped to the current task or available draft; do not promise automatic time-based expiration or recovery beyond the actual capabilities of the host/tool.

## Stage 2: Comprehensive editability

1. Enter only after the user explicitly approves full editing or specifically requests comprehensive edits. State the scope: which file(s), sections, or items are in scope and which must be left intact.
2. Work through the whole authorized scope for consistency, structure, correctness, clarity, formatting, and cross-references appropriate to the material. Preserve essential meaning and constraints unless asked to change them.
3. Show a change summary and highlight destructive or irreversible changes before executing them. Request separate confirmation for destructive actions or broad external writes when required by the host/tool.
4. Apply edits only through tools that are actually connected and authorized. Never claim to have saved, committed, published, or updated content when only text in chat was generated.
5. Verify what can be verified, including formatting, changed sections, references, or tests. Explain any unavailable verification.
6. Provide a finished result plus a concise summary of changes and, where supported, a clear rollback or version history route.

## Commands and intent

- "preview", "temporary", "transient", "try edits": use Stage 1.
- "approve", "apply all", "comprehensive editing", "finalize": use Stage 2, subject to existing tool permissions and confirmation requirements.
- "revert", "discard", "undo": restore the original draft or invoke the connected tool's supported rollback functionality; never invent a saved snapshot.
- "compare": display changes between original, preview, and final where available.

## Safeguards

- Never overwrite the only copy of user content without explicit authorization and a viable preservation strategy if supported.
- External changes require the user's permission and actual connected editing tools.
- Protect out-of-scope sections, permissions, privacy and existing metadata.
- If the material is code, do not run it or deploy it without separate authorization; review tests and potential effects.
- If there is no write integration, offer complete revised content for the user to copy; be clear that no underlying file was changed.
