---
name: wiv-mcp-workflows
description: Use the Wiv MCP to work with workflows, executions, cases, spaces, integrations, datastores, dashboards, and MSP customers in Cursor.
---

# WIV MCP workflows skill

Use this skill when the user wants to inspect or change data in their Wiv organization from Cursor.

## When to use

- User asks to list, create, edit, or run workflows.
- User wants to start, stop, or inspect workflow executions.
- User asks about cases, spaces, folders, integrations, datastores, or dashboards.
- User wants to generate a workflow from natural language.
- User manages customer tenants through a Wiv MSP organization.

## How to use

1. Ensure the WIV MCP server (`wiv-api`) is configured and connected (see plugin README).
2. Use list/search tools to resolve names to IDs instead of guessing identifiers.
3. Read `wiv://catalog/steps` and `wiv://guides/workflow-authoring` before creating or replacing workflows.
4. Read `wiv://catalog/widgets` and `wiv://guides/dashboard-authoring` before creating dashboard layouts.
5. Retrieve the current object before a full update, preserve fields the user did not ask to change, and confirm destructive operations.

## Tips

- Workflow JSON uses `snake_case`, starts with one `TRIGGER` step, ends with one `EXIT` step, and links steps through `next_step`.
- Create schedules with trigger tools after creating the workflow. Do not invent scheduled trigger parameters on the workflow's `TRIGGER` step.
- Use `wiv_patch_workflow` for metadata-only edits and `wiv_update_workflow` for full step changes.
- Use `wiv_generate_workflow` for natural-language drafts. Poll with `wiv_get_generated_workflow` when the client does not support MCP Tasks.
- When connected as an MSP parent, pass `customer_id` only for supported read operations. Reconnect as the customer organization before writing customer data.
