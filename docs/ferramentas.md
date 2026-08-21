# Ferramentas

OpenAI Billing expõe 3 ferramentas (todas somente leitura).

### 1. `openai_billing_list_accounts`
**Input**: `account` (opcional)

List OpenAI Billing admin API connections linked to this install.

### 2. `openai_billing_usage`
**Input**: `kind` (opcional), `days_back` (opcional), `start_time` (opcional), `end_time` (opcional), `bucket_width` (opcional), `group_by` (opcional), `limit` (opcional), `account` (opcional)

Get normalized OpenAI organization usage for completions, embeddings, images, audio, vector stores, or code interpreter sessions.

### 3. `openai_billing_cost`
**Input**: `days_back` (opcional), `start_time` (opcional), `end_time` (opcional), `bucket_width` (opcional), `group_by` (opcional), `limit` (opcional), `account` (opcional)

Get normalized OpenAI organization costs for a date range.

## Prompts de exemplo

```
Show OpenAI costs for the last 30 days
Break down OpenAI completion usage by day
Compare OpenAI usage across embeddings and completions
```
