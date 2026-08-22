> **Chinese source (authoritative):** [`../../skills/legal-article-retrieval/README.md`](../../skills/legal-article-retrieval/README.md)

# Connecting a Statute Database · PKULaw MCP

The `legal-article-retrieval` (statute retrieval) skill itself **does not bind to any specific database**; it defines the methodology for retrieval and for generating retrieval reports. To retrieve **real, currently effective, and sourceable** laws and regulations, the runtime environment must connect an MCP service capable of searching statutes.

> ⚠️ When no database is connected, any statute that cannot be verified online must be marked `[待查]` / `[to be verified]`; **do not fabricate article numbers or content from model memory**.

The currently verified option is **[PKULaw MCP](https://mcp.pkulaw.com)** (a library of 5 million+ laws and regulations).

## Configuration

Standard remote MCP Server, using Claude Code / Claude Desktop as an example:

```json
{
  "mcpServers": {
    "pkulaw-law-semantic": {
      "url": "https://apim-gw.pkulaw.com/{SERVICE_ID}/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_TOKEN"
      }
    }
  }
}
```

- Obtain the Token and `SERVICE_ID` from the [mcp.pkulaw.com console](https://mcp.pkulaw.com/console/apps); **do not commit them to the repository**.
- Choose a `SERVICE_ID` for **laws and regulations semantic/keyword search** or **statute identification and provenance** services.

## Interface Contract

The skill depends only on the abstract action of "retrieval": output search terms → MCP returns structured regulations (title, document number, hierarchical force, effective date, article text, source link) → the skill generates a retrieval report from that. Any statute library providing equivalent capability may replace PKULaw without modifying `SKILL.md`.

> For complete Token acquisition, CLI, usage examples, and notes, see [`../case-retrieval/README.md`](../case-retrieval/README.md); the configuration approach is identical, only the `SERVICE_ID` differs.
> For the full list of PKULaw services and links, see [`../../MCP-PKULAW.md`](../../MCP-PKULAW.md).

---

> Acknowledgments: The connection paradigm references [fayayy888/legal-document-assistant](https://github.com/fayayy888/legal-document-assistant).
