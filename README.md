# WIV Workflow MCP — Cursor Plugin

Exposes the **WIV Workflow API** to Cursor via the Model Context Protocol (MCP). Use natural language to list workflows, start and stop executions, generate workflows from descriptions, and manage spaces and folders.

## Authentication required

The WIV MCP uses your WIV organization account. You must **authenticate once at [https://mcp.wiv.ai](https://mcp.wiv.ai)** to get your API key and server URL. Sign in with WIV (OAuth), then use the one-click install or copy the API key into Cursor.

## Prerequisites

- A WIV account. Authenticate at [mcp.wiv.ai](https://mcp.wiv.ai) to get your API key.

## Setup

1. Install this plugin from the Cursor Marketplace (or add from repo: `cursor-plugin-wiv-mcp`).
2. **Authenticate and get your API key:** Open **[https://mcp.wiv.ai](https://mcp.wiv.ai)** and sign in with your WIV organization account. After sign-in, copy the **X-API-Key** (and Server URL if shown) for Cursor.
3. In Cursor: **Settings → Tools & MCP → Add new MCP server** (or edit `~/.cursor/config/mcp.json`):
   - **Name:** `wiv-api`
   - **Type:** `streamableHttp` (or HTTP/SSE)
   - **URL:** `https://mcp.wiv.ai/sse`
   - **Headers:** `X-API-Key: <your-api-key>`
4. Restart Cursor so the MCP server loads.

The plugin’s `mcp.json` uses the WIV MCP endpoint `https://mcp.wiv.ai/sse`. Replace `YOUR_WIV_API_KEY` with the API key you get after signing in at [mcp.wiv.ai](https://mcp.wiv.ai), or add the server in Cursor’s UI as above.

## Tools

Once connected, the WIV MCP provides these tools:

| Tool | Description |
|------|-------------|
| `wiv_list_workflows` | List all workflows |
| `wiv_get_workflow` | Get details of a specific workflow |
| `wiv_update_workflow` | Update an existing workflow |
| `wiv_list_spaces` | List all available spaces |
| `wiv_get_space` | Get details of a specific space |
| `wiv_get_space_resources` | Get resources in a space |
| `wiv_list_folders` | List workflow folders |
| `wiv_get_folder` | Get a specific workflow folder |
| `wiv_start_execution` | Start/run a workflow execution |
| `wiv_list_all_executions` | List executions for all workflows |
| `wiv_list_workflow_executions` | List executions for a specific workflow |
| `wiv_stop_execution` | Stop a workflow execution |
| `wiv_get_execution_status` | Get the status of a workflow execution |
| `wiv_list_cases` | List cases with optional filters |
| `wiv_search_cases` | Search cases with filters, date range, and pagination |
| `wiv_get_cases_summary` | Get cases summary/statistics |
| `wiv_get_cases_filters` | Get available case filters |
| `wiv_get_cases_filter_values` | Get possible values for a case filter |
| `wiv_cases_query` | Flexible cases query using OpenSearch |
| `wiv_search_msp_cases` | Search cases across MSP child tenants |
| `wiv_get_msp_cases_summary` | Get MSP cases summary across child tenants |
| `wiv_get_msp_cases_filter_values` | Get possible values for MSP case filter |
| `wiv_list_msp_cases_types` | List case types across MSP child tenants |
| `wiv_msp_cases_query` | Flexible MSP cases query using OpenSearch |
| `wiv_generate_workflow` | Generate a workflow using AI from natural language |
| `wiv_get_generated_workflow` | Poll for AI-generated workflow result |

For troubleshooting, see [WIV documentation](https://help.wiv.ai) or [mcp.wiv.ai](https://mcp.wiv.ai).

## License

MIT
