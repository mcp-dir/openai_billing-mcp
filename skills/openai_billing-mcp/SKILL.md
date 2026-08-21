---
name: openai_billing-mcp
description: Skill da REST API do OpenAI Billing na MCP.AI: 3 endpoints em /api/openai_billing. OpenAI organization usage and cost reporting through an admin API key connected by the user. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# OpenAI Billing — REST API skill

Você tem acesso à **OpenAI Billing** REST API na MCP.AI.

> OpenAI organization usage and cost reporting through an admin API key connected by the user.

## Base URL

```
https://api.mcp.ai/api/openai_billing
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/openai_billing/cost \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/openai_billing/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (3)

#### `openai_billing_cost`

Get normalized OpenAI organization costs for a date range. _(POST /api/openai_billing/cost)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `days_back` | integer | Não | Relative range in days. Mapped to OpenAI unix start_time/end_time. |
| `start_time` | integer | Não | Unix start_time override. |
| `end_time` | integer | Não | Unix end_time override. |
| `bucket_width` | string | Não | OpenAI bucket_width parameter. |
| `group_by` | string | Não | Optional OpenAI group_by parameter. |
| `limit` | integer | Não | Per-page bucket limit; pagination is drained inside the adapter. |
| `account` | string | Não | When multiple OpenAI admin keys are connected: connection id or label. See openai_billing_list_accounts. |

#### `openai_billing_list_accounts`

List OpenAI Billing admin API connections linked to this install. _(POST /api/openai_billing/list/accounts)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | When multiple OpenAI admin keys are connected: connection id or label. See openai_billing_list_accounts. |

#### `openai_billing_usage`

Get normalized OpenAI organization usage for completions, embeddings, images, audio, vector stores, or code interpreter sessions. _(POST /api/openai_billing/usage)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `kind` | string | Não | OpenAI organization usage endpoint suffix. (completions, embeddings, moderations, images, audio_speeches, audio_transcriptions, vector_stores, code_interpreter_sessions) |
| `days_back` | integer | Não | Relative range in days. Mapped to OpenAI unix start_time/end_time. |
| `start_time` | integer | Não | Unix start_time override. |
| `end_time` | integer | Não | Unix end_time override. |
| `bucket_width` | string | Não | OpenAI bucket_width parameter. |
| `group_by` | string | Não | Optional OpenAI group_by parameter. |
| `limit` | integer | Não | Per-page bucket limit; pagination is drained inside the adapter. |
| `account` | string | Não | When multiple OpenAI admin keys are connected: connection id or label. See openai_billing_list_accounts. |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_openai_billing` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
