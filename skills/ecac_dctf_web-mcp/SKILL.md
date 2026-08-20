---
name: ecac_dctf_web-mcp
description: Skill da REST API do ECAC: DCTF WEB na MCP.AI: 1 endpoint em /api/ecac_dctf_web. ECAC: DCTF WEB, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# ECAC: DCTF WEB — REST API skill

Você tem acesso à **ECAC: DCTF WEB** REST API na MCP.AI.

> ECAC: DCTF WEB, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/ecac_dctf_web
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
curl -X POST https://api.mcp.ai/api/ecac_dctf_web/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"pkcs12_cert":"...","pkcs12_pass":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/ecac_dctf_web/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `ecac_dctf_web_consultar`

ECAC: DCTF WEB, consulta em fonte oficial. _(POST /api/ecac_dctf_web/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `pkcs12_cert` | string | Sim | Parâmetro de consulta "pkcs12_cert". |
| `pkcs12_pass` | string | Sim | Parâmetro de consulta "pkcs12_pass". |
| `data_inicial_apuracao` | string | Não | Parâmetro de consulta "data_inicial_apuracao". |
| `data_final_apuracao` | string | Não | Parâmetro de consulta "data_final_apuracao". |
| `data_inicial_transmissao` | string | Não | Parâmetro de consulta "data_inicial_transmissao". |
| `data_final_transmissao` | string | Não | Parâmetro de consulta "data_final_transmissao". |
| `perfil_procurador_cnpj` | string | Não | Parâmetro de consulta "perfil_procurador_cnpj". |
| `perfil_procurador_cpf` | string | Não | Parâmetro de consulta "perfil_procurador_cpf". |
| `categoria_declaracao` | string | Não | Parâmetro de consulta "categoria_declaracao". |
| `situacoes_declaracao` | string | Não | Parâmetro de consulta "situacoes_declaracao". |
| `numero_recibo` | string | Não | Parâmetro de consulta "numero_recibo". |
| `pagina` | string | Não | Parâmetro de consulta "pagina". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_ecac_dctf_web` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
