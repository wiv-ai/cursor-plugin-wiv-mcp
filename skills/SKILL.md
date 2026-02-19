---
name: wiv-mcp-workflows
description: Use the WIV MCP to work with workflows, spaces, folders, executions, cases, and AI-generated workflows in Cursor.
---

# WIV MCP workflows skill

Use this skill when the user wants to work with WIV workflows, spaces, folders, executions, or cases inside Cursor.

## When to use

- User asks to list or manage workflows, spaces, or folders.
- User wants to start, stop, or inspect workflow executions.
- User asks about cases (list, search, summary, filters) or MSP cases.
- User wants to generate a workflow from a natural language description.

## How to use

1. Ensure the WIV MCP server (`wiv-api`) is configured and connected (see plugin README).
2. Call the relevant MCP tool: workflows (`wiv_list_workflows`, `wiv_get_workflow`, `wiv_update_workflow`), spaces (`wiv_list_spaces`, `wiv_get_space`, `wiv_get_space_resources`), folders (`wiv_list_folders`, `wiv_get_folder`), executions (`wiv_start_execution`, `wiv_list_all_executions`, `wiv_list_workflow_executions`, `wiv_stop_execution`, `wiv_get_execution_status`), cases (`wiv_list_cases`, `wiv_search_cases`, `wiv_get_cases_summary`, etc.), or AI generation (`wiv_generate_workflow`, `wiv_get_generated_workflow`).

## Tips

- For `wiv_generate_workflow`, include the workflow name in the prompt; use `wiv_get_generated_workflow` to poll for the result.
- Use `wiv_list_workflows`, `wiv_list_folders`, or `wiv_list_spaces` first when you need an ID the user referred to by name.
