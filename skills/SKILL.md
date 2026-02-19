---
name: wiv-mcp-workflows
description: Use the WIV MCP to list and manage workflows, start or stop executions, and generate workflows from natural language descriptions in Cursor.
---

# WIV MCP workflows skill

Use this skill when the user wants to work with WIV workflows inside Cursor.

## When to use

- User asks to list workflows, spaces, or folders.
- User wants to start or stop a workflow execution.
- User wants to generate a workflow from a natural language description.
- User asks for workflow details or execution status.

## How to use

1. Ensure the WIV MCP server (`wiv-api`) is configured and connected (see plugin README).
2. Call the relevant MCP tool with the parameters the user provided:
   - `wiv_list_workflows`, `wiv_list_spaces`, `wiv_list_folders` for listing.
   - `wiv_get_workflow` for a single workflow by ID.
   - `wiv_start_execution` with `workflow_id` and optional `trigger_event`.
   - `wiv_list_workflow_executions`, `wiv_stop_execution` for executions.
   - `wiv_generate_workflow` with a `prompt` that includes the workflow name and, if needed, location (e.g. folder or space).

## Tips

- For `wiv_generate_workflow`, include the workflow name in the prompt (e.g. "Create a workflow named 'Daily Report' that...").
- Use `wiv_list_workflows` or `wiv_list_folders` first if the user refers to workflows or folders by name and you need an ID.
