# OpenAI Billing

### OpenAI Billing for Claude, ChatGPT and AI agents

OpenAI organization usage and cost reporting through an admin API key connected by the user.

- 📊 **3 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `OpenAI Billing`, URL `https://api.mcp.ai/p_openai_billing`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=openai_billing&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9vcGVuYWlfYmlsbGluZyJ9)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=openai_billing&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_openai_billing%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_openai_billing
```

---

## 3 tools

| Tool | Description |
|---|---|
| `openai_billing_list_accounts` | List OpenAI Billing admin API connections linked to this install. |
| `openai_billing_usage` | Get normalized OpenAI organization usage for completions, embeddings, images, audio, vector stores, or code interpreter sessions. |
| `openai_billing_cost` | Get normalized OpenAI organization costs for a date range. |

---

## Pricing

Free.

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_openai_billing` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
