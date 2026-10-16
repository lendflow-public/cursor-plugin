# Lendflow

Cursor plugin that connects agents to [Lendflow](https://lendflow.com) through Lendflow's remote [Model Context Protocol](https://modelcontextprotocol.io/) server.

Agents can look up and update applications, read offers and placements, browse funders and workflow templates, and add notes, all as the Lendflow user who signs in.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **Lendflow**.
3. Click **Install**, then complete the Lendflow sign-in prompt.

Or run `/add-plugin lendflow` in chat.

## MCP

```json
{
  "mcpServers": {
    "lendflow": {
      "type": "http",
      "url": "https://mcp.api.lendflow.com"
    }
  }
}
```

Sign-in uses OAuth against your Lendflow account. Cursor opens the Lendflow sign-in page when the plugin first connects. There is no API key or client ID to configure.

## Before you connect

You need a Lendflow dashboard account. The agent sees the same data your account sees and nothing more.

## What agents can do

| Area | Capabilities |
| --- | --- |
| Applications | List and search applications, read an application with its stage data, create and update applications, move an application through its workflow |
| Offers and placements | List an application's offers and placements, read a single offer or placement, update a placement's status |
| Documents | List an application's files and required documents, and upload documents |
| Notes and communications | Add notes to an application or a business, and read communication logs |
| Funders and clients | List and read funders, list and read clients and their brand names |
| Workflows | List workflow templates, data orchestration templates, and an application's workflow stages and statuses |

The server is the source of truth for tool names and schemas. Use the tools the connected server advertises.

## Notes

- Dates of birth, driver's license numbers, tax identifiers, bank account and routing numbers, and credit report values come back as `REDACTED`.
- List tools return one page at a time. `meta.total` holds the size of the whole result set.

## License

[MIT](LICENSE)
