# 📋 PLANO DE INVESTIGAÇÃO OSINT

> Template preenchível. Gerar idealmente via `/planejar-investigacao`. Adaptar ao caso concreto.

---

## Identificação

| Campo | Valor |
|---|---|
| **Caso** | `[nome / IPL nº / PIC nº]` |
| **Natureza** | `[tipo penal + dispositivo — ex: CP art. 171 §2º-A, Lei 14.155/2021]` |
| **Respaldo legal** | `[IPL / PIC / decisão judicial / representação]` |
| **Perfil do analista** | `[investigador / perito / threat intel / jurídico]` |
| **Fase do ciclo** | 1 — Planejamento |
| **Data de elaboração** | `YYYY-MM-DDTHH:MM:SSZ` (UTC) |
| **Urgência** | `[ALTA / MÉDIA / BAIXA]` |

---

## 🎯 Hipóteses

| # | Hipótese | Fonte que confirma/refuta | Plausibilidade inicial |
|---|---|---|---|
| H1 | `[afirmação testável]` | `[fonte ou diligência]` | `[ALTA / MÉDIA / BAIXA]` |
| H2 | `[hipótese alternativa]` | `[...]` | `[...]` |
| H3 | `[...]` | `[...]` | `[...]` |

---

## 🔍 Plano de coleta (ordem priorizada)

### FASE A — Passivo (sem contato com alvo ou infraestrutura)

| # | Diligência | Ferramenta KB §X | Output esperado |
|---|---|---|---|
| 1 | `[preservação via Wayback antes de qualquer análise]` | `references/04-*.md §4.5` | `[snapshot histórico]` |
| 2 | `[WHOIS]` | `references/04-*.md §4.1` | `[titular / e-mail / data registro]` |
| 3 | `[crt.sh — certificados emitidos]` | `references/04-*.md §4.8` | `[subdomínios históricos]` |
| 4 | `[...]` | | |

### FASE B — Pivô de identificadores derivados

| # | Diligência | Ferramenta KB §X | Output esperado |
|---|---|---|---|
| N | `[Epieos cruzando e-mail encontrado]` | `references/01-email.md §1.4` | `[contas vinculadas]` |
| | `[...]` | | |

### FASE C — Ativo (após autorização específica)

| # | Diligência | Ferramenta KB §X | Autorização prévia | Base legal |
|---|---|---|---|---|
| N | `[técnica 🟡]` | `references/NN-*.md §Y.Z` | `[IPL / decisão judicial]` | `[dispositivo]` |

### FASE D — Preservação

| # | Ação | Ferramenta | Saída para cadeia de custódia |
|---|---|---|---|
| N | Captura completa HTML | SingleFile / Hunchly | Arquivo + SHA-256 |
| | Screenshot datado | Firefox + captura manual | PNG + SHA-256 |
| | Hash dos arquivos | `sha256sum` / `Get-FileHash` | Tabela `templates/cadeia-custodia.md` |

---

## ⚖️ Autorizações necessárias (ofícios subsequentes)

| Entidade | Dispositivo | O que pedir | Estimativa de prazo |
|---|---|---|---|
| `[provedor de aplicação]` | MCI art. 10, 15 | `[dados cadastrais + registros de acesso + porta CGNAT]` | `[15-30 dias]` |
| `[ISP]` | MCI art. 10, 13; Res. Anatel 614/2013 | `[identificação de assinante por IP+porta+timestamp UTC]` | `[15-30 dias]` |
| `[exchange cripto BR]` | LGPD art. 7º III + COAF | `[dados cadastrais do titular da wallet]` | `[15-60 dias]` |
| `[...]` | | | |

> Templates prontos:
> - `templates/oficio-provedor-aplicacao.md`
> - `templates/oficio-provedor-conexao-cgnat.md`

---

## 🔒 OPSEC

| Área | Cuidado operacional |
|---|---|
| **Rede** | `[VPN institucional / Tor — conforme risco]` |
| **Dispositivo** | `[VM dedicada com snapshot prévio]` |
| **Identidade** | `[conta operacional, nunca pessoal]` |
| **Navegador** | `[Firefox hardened + uBlock + NoScript + SingleFile]` |
| **Preservação** | `[Hunchly configurado antes de iniciar + VeraCrypt para storage]` |

> Checklist completo: `/checklist-opsec` ou `templates/checklist-opsec.md`.

---

## ▶ Próxima ação sugerida

`[Executar FASE A completa. Retornar com outputs para consolidação. Avaliar pivôs antes de ativar FASE B.]`

Skill recomendado: `/tecnica-especifica` se houver técnica-chave na FASE A, ou `/consultar-toolkit` se faltar ferramenta para algum identificador.

---

*Plano conforme metodologia OSINT-Sentinel v1.0 (Ação A — Fase 1: Planejamento) e KB OSINT v3.0/2026.*
