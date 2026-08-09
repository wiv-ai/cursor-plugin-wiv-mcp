# WIV Workflow MCP — Cursor Plugin

Connect Cursor to the hosted **WIV Workflow MCP server**. Use natural language to work with workflows, executions, cases, spaces, integrations, datastores, dashboards, and MSP customers.

## Prerequisites

- A Wiv account with access to a Wiv organization.
- A current version of Cursor with remote MCP and OAuth support.

## Setup

1. Install this plugin from the Cursor Marketplace or add the `wiv-ai/cursor-plugin-wiv-mcp` repository.
2. Open **Cursor Settings → Tools & MCP**.
3. Enable the **wiv-api** server.
4. Complete the Wiv OAuth sign-in in your browser.

The plugin connects to the Streamable HTTP endpoint:

```text
https://mcp.wiv.ai/mcp
```

No API key needs to be copied into the plugin configuration. Cursor discovers the Wiv OAuth endpoints and opens the sign-in flow automatically.

For one-click installation and setup instructions, open [mcp.wiv.ai/connect](https://mcp.wiv.ai/connect).

## What you can do

- List, create, update, run, and monitor workflows.
- Browse step templates and generate workflow drafts from natural language.
- Search and summarize cases.
- Manage spaces, folders, integrations, datastores, and dashboards.
- Work across customer tenants when connected to an MSP organization.

The server also exposes workflow and dashboard authoring resources. Read the relevant catalog or guide before creating complex objects.

## Other clients

- [Wiv in the Claude Connectors Directory](https://claude.ai/directory/connectors/wiv-mcp)
- [Wiv MCP setup for all supported clients](https://mcp.wiv.ai/connect)

## Documentation and support

- [Wiv MCP documentation](https://docs.wiv.ai/platform/ai/mcp-server)
- [Wiv support](mailto:support@wiv.ai)

## License

MIT
