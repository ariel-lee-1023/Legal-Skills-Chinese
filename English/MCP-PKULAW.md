# PKULaw MCP (English)

This is the English parallel of [`../MCP-PKULAW.md`](../MCP-PKULAW.md).

Retrieval skills (`case-retrieval`, `legal-article-retrieval`, `legal-norm-validity-check`) define **methodology only** and do not bind to a vendor database. To retrieve real, current, citable cases and statutes, connect a compatible MCP legal data service in your client.

The configuration already validated by this project is **PKULaw MCP** (pku law / 北大法宝). Obtain `SERVICE_ID` and token from the [PKULaw MCP console](https://mcp.pkulaw.com); configure them **only in your local client** — never commit tokens into `SKILL.md` or the repo.

Example client config:

```json
{
  "mcpServers": {
    "pkulaw": {
      "url": "https://apim-gw.pkulaw.com/{SERVICE_ID}/mcp",
      "headers": { "Authorization": "Bearer YOUR_TOKEN" }
    }
  }
}
```

Without a live database, skills may still run, but every case/statute citation must be marked `[待检索]` / `[to be retrieved]` — never fabricate.

**Authoritative Chinese document:** [`../MCP-PKULAW.md`](../MCP-PKULAW.md)  
**Per-skill MCP notes (Chinese):** `../skills/case-retrieval/README.md`, `../skills/legal-article-retrieval/README.md`, `../skills/legal-norm-validity-check/README.md`
