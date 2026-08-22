> **Chinese source (authoritative):** [`../../skills/legal-norm-validity-check/README.md`](../../skills/legal-norm-validity-check/README.md)

# Connecting Legal-Norm Validity Verification · PKULaw MCP

The `legal-norm-validity-check` skill itself **is not bound to any particular database**. It defines the methodology for judging whether a legal provision is currently in force, whether its hierarchical level is correct, and whether it conflicts with higher-level or same-level norms. To make verification results **traceable and trustworthy** (rather than judging from model memory whether a provision has been amended or repealed), the runtime environment needs an MCP service that can **trace provisions and verify current validity**.

> ⚠️ This skill’s risk level is marked **extremely high**—citing an invalid or conflicting provision will directly cause erroneous legal conclusions. Without a database connection, any validity status that cannot be verified online must, per the Legal Disclaimer in SKILL.md, **truthfully mark uncertainty** and must not be presented as a definitive conclusion.

The currently verified option is **[PKULaw MCP](https://mcp.pkulaw.com)** (5M+ laws and regulations library, real-time updates). The services that best match this skill are **provision/case-number identification and tracing** and **correction of hallucinated provision generation**.

---

## I. Configuration

Standard remote MCP Server, using Claude Code / Claude Desktop as an example:

```json
{
  "mcpServers": {
    "pkulaw-norm-trace": {
      "url": "https://apim-gw.pkulaw.com/{SERVICE_ID}/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_TOKEN"
      }
    }
  }
}
```

- Obtain the Token and `SERVICE_ID` from the [mcp.pkulaw.com console](https://mcp.pkulaw.com/console/apps); **never write them into SKILL.md or commit them to the repository**.
- For `SERVICE_ID`, choose a **provision identification and tracing** or **laws and regulations search** service in the [MCP App Center](https://mcp.pkulaw.com/apis) (used to retrieve provision text, document number, validity level, effective/expiry dates, and amendment history).

## II. How the Skill Calls the Interface (Interface Contract)

`legal-norm-validity-check` receives “one or more retrieved provisions (with source information),” verifies them one by one, and outputs a validity status report. Its expectation of the interface is that **the environment has a tool that can “take a provision identifier as input and return that provision’s current status and history”**:

| Skill side (this skill’s output/expectation) | Interface side (provided by PKULaw MCP) |
|---|---|
| Input: provision identifier to verify (law name + article number, or cited text) | **Provision/case-number identification and tracing** tool |
| Expected return: provision text, document number, **validity level**, **temporal status (currently in force / amended / repealed)**, amendment/amended-by relationships | Structured returns from the regulations library + regulation change/tracing information |
| Verification logic: judge 「current validity → hierarchical correctness → conflict with higher-/same-level norms」 (three steps in SKILL.md) | —— |
| Reverse check: hand model-cited provisions to the 「**correction of hallucinated provision generation**」 tool for comparison to detect wrong article numbers, outdated versions, fabricated provisions | Correction of hallucinated provision generation tool |

In other words, this skill depends only on two abstract actions: **“trace a provision’s current status”** and **“verify whether a provision citation is authentic/current.”** Any regulations library providing equivalent capability can replace PKULaw without changing `SKILL.md`.

> Note: In the table above, “provision tracing,” “correction of hallucinated provision generation,” etc. are **service categories** publicly described by PKULaw; the **exact tool names and parameters** exposed under the MCP protocol should follow the tool list you actually retrieve after connecting (`tools/list`) or the [official documentation center](https://mcp.pkulaw.com/docs).

## III. Usage Example

```
A provision is cited in reasoning → trigger the legal-norm-validity-check skill
→ the skill hands the provision identifier to the pkulaw-norm-trace MCP for tracing
→ obtain current status (valid / amended / repealed), validity level, amendment history
→ the skill verifies by the three steps 「current validity → hierarchy → conflict」 and outputs a validity status report (with reasons and confidence)
```

## IV. Notes

- **Time point:** Provision validity changes with legislative activity; the skill must, per SKILL.md, **clearly state the time point of verification**.
- **Official fallback:** For critical provisions, also check the official [National Database of Laws and Regulations](https://flk.npc.gov.cn).
- **Companion skills:** This repo’s `case-retrieval` and `legal-article-retrieval` can also connect to PKULaw with the same configuration approach, only swapping the corresponding `SERVICE_ID`—see [`../case-retrieval/README.md`](../case-retrieval/README.md).
- **Ultimate responsibility:** Regardless of which database the data comes from, verification results are drafts for review by licensed legal professionals; final judgment and responsibility rest with licensed professionals.

---

> Acknowledgment: This connection pattern references [fayayy888/legal-document-assistant](https://github.com/fayayy888/legal-document-assistant).
