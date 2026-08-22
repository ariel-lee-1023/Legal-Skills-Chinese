> **Chinese source (authoritative):** [`../../skills/case-retrieval/README.md`](../../skills/case-retrieval/README.md)

# Connecting a Case Database · PKULaw MCP

The `case-retrieval` (case retrieval) skill itself **is not bound to any particular database**. It defines the methodology of “how to extract retrieval elements, design retrieval strategies, assess similarity, and generate retrieval reports.” To retrieve **real, current, and traceable** judicial cases, you need to connect to the runtime environment an MCP (Model Context Protocol) service that can search cases.

> ⚠️ Without connecting any database, this skill can still run—but all cases should be marked `[to be retrieved]`, and **case numbers, parties, or holdings must never be fabricated from model memory**. This is consistent with this repository’s bottom line of “prefer leaving blanks over fabricating.”

The currently verified workable solution is **[PKULaw MCP](https://mcp.pkulaw.com)** (160M+ judicial case library). Connection steps follow.

---

## I. Obtain a Token

1. Visit [mcp.pkulaw.com](https://mcp.pkulaw.com) and register an account.
2. Go to the [console](https://mcp.pkulaw.com/console/apps) → create an application → obtain an API Token.
3. In the [MCP App Center](https://mcp.pkulaw.com/apis), find the **judicial case retrieval** related service and note its `SERVICE_ID`.

> Token and SERVICE_ID are your private credentials; **do not write them into any SKILL.md or commit them to the repository**. Configure them only in your local MCP client.

## II. Configure the Server in the MCP Client

PKULaw is a standard remote MCP Server (URL + Bearer auth). Example `mcpServers` configuration for Claude Code / Claude Desktop:

```json
{
  "mcpServers": {
    "pkulaw-case-search": {
      "url": "https://apim-gw.pkulaw.com/{SERVICE_ID}/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_TOKEN"
      }
    }
  }
}
```

Replace `{SERVICE_ID}` with the actual ID of the case retrieval service, and `YOUR_TOKEN` with the Token obtained in step one. Other MCP-compatible clients (Cursor, Dify, etc.) use the same configuration fields; see the [official integration docs](https://mcp.pkulaw.com/docs?doc=mcp-integration).

> If you prefer not to go through a large model and want to pull data in bulk directly, PKULaw also provides a CLI: `npm i -g @pkulaw/mcp-cli`, sharing the same Token as MCP. See [@pkulaw/mcp-cli](https://www.npmjs.com/package/@pkulaw/mcp-cli).

## III. How the Skill Invokes the Interface (Interface Contract)

After configuration, when `case-retrieval` reaches “**IV. Retrieval Methods and Paths**”, it hands the retrieval expressions it has designed to the connected MCP case retrieval tool, rather than generating cases from thin air. The skill’s expectation of the interface is very simple—**so long as the environment has a tool that “takes a query and returns a real case list”**:

| Skill side | Interface side (provided by PKULaw MCP) |
|---|---|
| Output: semantic query terms / keyword combinations (see SKILL.md §3) | Judicial case **semantic search** / **keyword search** tools |
| Expected return: case number, court, year, cause of action, holding, full-text link | Structured case JSON returned by the MCP tool |
| Skill consumption: similarity assessment per §5, filtering/ranking per §6, report generation per §7 | —— |

In other words, **the skill depends only on the abstract act of “retrieval.”** Any case library that can provide equivalent capability (other vendors’ MCP, an internal case library, a self-built retrieval API) can replace PKULaw without changing `SKILL.md`. That is the meaning of “give an interface” rather than “bind a vendor.”

## IV. Usage Example

Once connected, converse normally in Claude Code or similar environments:

```
Provide case materials and say "help me retrieve similar cases" → triggers the case-retrieval skill
→ skill extracts retrieval elements and designs retrieval expressions
→ skill calls pkulaw-case-search MCP to obtain real cases
→ skill assesses similarity, filters and ranks, and outputs a structured Case Retrieval Report
```

## V. Notes

- **Authority and currency:** Cases returned by PKULaw must be labeled for authority level (guiding cases / ordinary cases) and currency per SKILL.md §5.1; avoid citing holdings that have been overruled.
- **Companion skills likewise:** This repository’s `legal-article-retrieval` (statutory retrieval) and `legal-norm-validity-check` (norm validity verification) can likewise connect to PKULaw, with the same configuration approach, only swapping the corresponding `SERVICE_ID`. See their connection notes at [`../legal-article-retrieval/README.md`](../legal-article-retrieval/README.md) and [`../legal-norm-validity-check/README.md`](../legal-norm-validity-check/README.md).
- **Full service and link list:** See the repository root [`MCP-PKULAW.md`](../../MCP-PKULAW.md).
- **Ultimate responsibility:** Regardless of which library the data comes from, retrieval results are only drafts for review by practicing legal professionals; final judgment and responsibility rest with practitioners.

---

> Acknowledgments: This connection paradigm references the `anli-jiansuo` skill in [fayayy888/legal-document-assistant](https://github.com/fayayy888/legal-document-assistant).
