# WIV Workflow MCP — Cursor Plugin

Exposes the **WIV Workflow API** to Cursor via the Model Context Protocol (MCP). Use natural language to list workflows, start and stop executions, generate workflows from descriptions, and manage spaces and folders.

## Prerequisites

- **Remote (recommended):** None. Use your hosted WIV MCP endpoint.
- **Local Docker:** Docker and a WIV API key (only if you run the MCP server locally via Docker).

## Setup

### Option 1: Connect to your hosted WIV MCP (recommended)

1. Install this plugin from the Cursor Marketplace (or add from repo: `cursor-plugin-wiv-mcp`).
2. Get your **API key** from the WIV connect page:
   - Open **https://mcp.wiv.ai/connect** and sign in with WIV (OAuth) if prompted.
   - Copy the **X-API-Key** value shown for Cursor.
3. In Cursor: **Settings → Tools & MCP → Add new MCP server** (or edit `~/.cursor/config/mcp.json`):
   - **Name:** `wiv-api`
   - **Type:** `streamableHttp` (or HTTP/SSE)
   - **URL:** `https://mcp.wiv.ai/sse`
   - **Headers:** `X-API-Key: <your-api-key>`
4. Restart Cursor so the MCP server loads.

The plugin’s `mcp.json` uses the WIV MCP endpoint `https://mcp.wiv.ai/sse`. Replace `YOUR_WIV_API_KEY` with your API key (from [mcp.wiv.ai/connect](https://mcp.wiv.ai/connect)), or add the server in Cursor’s UI as above.

### Option 2: Run MCP locally with Docker

If you have a WIV MCP Docker image that runs in **stdio** mode (with `MCP_TRANSPORT=stdio`), you can run it locally. Set `MCP_API_KEYS` and optionally `API_BASE_URL` in your environment or Cursor MCP config, and use the Docker command from the plugin docs. This option requires a published stdio-capable image (see the main plan for details).

## Tools

Once connected, the WIV MCP provides tools such as:

| Tool | Description |
|------|-------------|
| `wiv_list_workflows` | List workflows, with optional space filter |
| `wiv_get_workflow` | Get a workflow by ID |
| `wiv_list_spaces` | List spaces |
| `wiv_list_folders` | List workflow folders |
| `wiv_start_execution` | Start a workflow execution |
| `wiv_list_workflow_executions` | List executions for a workflow |
| `wiv_stop_execution` | Stop a running execution |
| `wiv_generate_workflow` | Generate a workflow from a natural language description |

For the full list and troubleshooting, see [WIV documentation](https://help.wiv.ai) or your WIV MCP server’s `/connect` page.

## License

MIT
