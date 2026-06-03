# Other messages

**Route:** `/other_msg`  
**Template:** `other_messages`

Same table layout as [Messages](21-edi-messages.md) with different **header widgets** for exception categories.

## Header widgets

| Widget | Typical meaning |
|--------|-----------------|
| NRS Rejected | Messages rejected by NRS validation |
| Running | In-flight processing |
| Duplicates | Possible duplicate detections |
| Total | Clear filters |

## Table and tabs

Uses the same **Messages** Tabular definition and the same detail tabs (Document, Images, Attachments, Data, Log, Network, Debug).

## Toolbar

Toolbar and **Action** menu match Messages (`other_message_tool_buttons`): workflow, dimension moves, release, archive, delete, tickets, comments.

## When to use

- Investigate validation failures not visible on the main Messages queue
- Monitor long-running or duplicate cases

Always confirm **dimension** (often Test vs Production) before acting on rows.
