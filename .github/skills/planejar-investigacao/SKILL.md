---
name: planejar-investigacao
description: >
  Estruturar plano de coleta OSINT do zero para um caso novo. Use quando o
  usuário apresentar um caso em andamento, tiver identificadores iniciais e
  precisar definir hipóteses, sequência de diligências e autorizações
  necessárias. Corresponde à Ação A do system prompt v1.0, Fase 1 do Ciclo de
  Inteligência (Planejamento). Exemplos de gatilhos: "IPL em curso, como
  começo?", "montei caso novo de estelionato", "tenho um URL e um e-mail, qual
  a sequência?".
---

# Planejar Investigação (Ação A — Fase 1: Planejamento)

## Quando usar

- Usuário tem caso novo, sem plano estruturado
- Já existe respaldo legal (IPL, PIC, representação, decisão judicial)
- Usuário forneceu 1+ identificador e quer sequenciar diligências
- Se o caso for muito vago, encaminhe antes para `/triagem-caso`

## Protocolo

### 1. Solicite briefing em 5 campos (só pergunte o que faltar):

| Campo | O que coletar |
|---|---|
| **Natureza do fato** | Tipo penal provável (ex: CP art. 171 §2º-A, Lei 14.155/2021) |
| **Respaldo legal** | IPL nº, PIC, decisão judicial, representação formal |
| **Identificadores iniciais** | URLs, e-mails, telefones, CPF, imagens, wallets, IPs |
| **Hipóteses preliminares** | O que o investigador já suspeita (se houver) |
| **Prazo / urgência** | Flagrante, tempestividade de ofício, decurso prescricional |

### 2. Gere plano de coleta estruturado

- **Hipóteses numeradas (H1, H2, H3)** — cada uma **testável**, com indicação da fonte que confirma/refuta
- **Identificadores mapeados** para seções da KB (use `/osint-kb` índice)
- **Sequência priorizada**: passivo primeiro, ativo depois; barato antes de caro; público antes de sob ofício
- **Pontos de OPSEC** aplicáveis (remeta para `/checklist-opsec` se operação sensível)
- **Autorizações eventualmente necessárias** (remeta para `/analise-juridica` em técnicas 🟡)

### 3. Encerre propondo próxima ação concreta

Indique qual skill rodar a seguir (`/tecnica-especifica`, `/mapear-pivos`, `/consultar-toolkit`).

## Formato de saída obrigatório

```
📋 PLANO DE INVESTIGAÇÃO OSINT

Caso: [nome/número do procedimento]
Natureza: [tipo penal com dispositivo]
Respaldo legal: [documento]
Perfil do analista: [investigador/perito/TI]
Fase do ciclo: 1 — Planejamento

🎯 HIPÓTESES
H1: [hipótese] — testar via: [fonte]
H2: ...
H3: ...

🔍 PLANO DE COLETA (ordem priorizada)

FASE A — Passivo (sem contato com alvo)
1. [diligência] → [ferramenta KB §X] → [output esperado]
2. ...

FASE B — Pivô de identificadores derivados
N. [diligência] → [ferramenta KB §X] → [autorização prévia]

FASE C — Ativo (após autorização específica)
N. [diligência] → [ferramenta KB §X] → [autorização prévia]

FASE D — Preservação
N. [SingleFile / Hunchly / sha256sum / cadeia de custódia — Ação F]

⚖️ AUTORIZAÇÕES NECESSÁRIAS (ofícios subsequentes)
- [entidade] → [dispositivo legal] → [o que pedir]

🔒 OPSEC
- [cuidado operacional específico da operação]

▶ PRÓXIMA AÇÃO SUGERIDA: [recomendação concreta com slash-command]
```

## Regras

- **NUNCA** propor plano sem confirmar **respaldo legal** — se o usuário não informar, pergunte antes de elaborar.
- **NUNCA** incluir ferramenta fora da KB v3.0/2026 — consulte `/osint-kb`.
- **Priorize sempre** técnicas passivas (🟢) na Fase A. Técnicas 🟡 vão em Fase B/C com autorização destacada.
- **Cite o dispositivo** (CP art. X, Lei Y, MCI art. Z) junto à autorização, sem inventar jurisprudência.
- **Se faltar identificador**: não imprima o template vazio; pergunte antes.
- Se natureza envolver CSAM, ative **Protocolo CSAM** de `AGENTS.md` e não prossiga com orientação técnica.

## Exemplo-guia (estelionato via site falso de banco)

Ver caso completo em `examples/caso-01-estelionato-pix.md`.
