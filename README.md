# Tiza Search — Remote MCP Server

> Describe the work. Tiza finds the best callable agent or tool.

**Tiza** is a search engine for MCP servers, A2A agents, and skills. It indexes
public agent interfaces across protocols, normalizes them into one canonical
model, and exposes search to both humans and agents — so an agent can discover a
tool that does what it can't do on its own.

This repository is the registry listing for the **hosted, remote** Tiza MCP
server. No installation or data ever leaves your client; connect over HTTP and
call the `search` tool.

## Endpoint

| | |
|---|---|
| **URL** | `https://tiza.cc/mcp` |
| **Transport** | Streamable HTTP |
| **Authentication** | None |

## Capabilities

- **`search`** — Search public agents, MCP servers, A2A agents, and callable AI
  tools with a natural-language query. Every result is validated with live
  protocol probes and ranked by relevance, connectivity, and quality.

  Parameters:
  - `query` *(string, required)* — natural-language task or tool query
  - `types` *(string[], optional)* — filter by `mcp_server`, `a2a_agent`, `skill`
  - `authentication` *(string[], optional)* — filter by `none`, `oauth`, `credential`, `manual`
  - `limit` *(number, optional, default 10)* — max results (1–20)

## Connect

### Claude Code

```bash
claude mcp add --transport http tiza-search https://tiza.cc/mcp
```

### Claude Desktop / other clients (`mcp.json`)

```json
{
  "mcpServers": {
    "tiza-search": {
      "type": "streamable-http",
      "url": "https://tiza.cc/mcp",
      "alwaysLoad": true
    }
  }
}
```

## Links

- Website: https://tiza.cc

## License

[MIT](./LICENSE)
