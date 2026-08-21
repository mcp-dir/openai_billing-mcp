# OpenAI Billing

### OpenAI Billing para Claude, ChatGPT e agentes de IA

OpenAI organization usage and cost reporting through an admin API key connected by the user.

- 📊 **3 ferramentas**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `OpenAI Billing` e **URL** `https://api.mcp.ai/p_openai_billing`.

### Cursor

[➕ Instalar OpenAI Billing no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=openai_billing&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9vcGVuYWlfYmlsbGluZyJ9)

### VS Code (Copilot Chat)

[➕ Instalar OpenAI Billing no VS Code](vscode:mcp/install?name=openai_billing&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_openai_billing%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_openai_billing
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Show OpenAI costs for the last 30 days
Break down OpenAI completion usage by day
Compare OpenAI usage across embeddings and completions
```

---

## 3 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `openai_billing_list_accounts` | List OpenAI Billing admin API connections linked to this install. |
| `openai_billing_usage` | Get normalized OpenAI organization usage for completions, embeddings, images, audio, vector stores, or code interpreter sessions. |
| `openai_billing_cost` | Get normalized OpenAI organization costs for a date range. |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Grátis.

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_openai_billing`.


---

## Suporte

- 📧 [openai_billing@mcp.ai](mailto:openai_billing@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/openai_billing-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_openai_billing` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
