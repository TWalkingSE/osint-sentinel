# 🕐 LINHA DO TEMPO — `[caso]`

> Template preenchível. Gerar idealmente via `/timeline-builder`. Adaptar ao caso concreto.

---

## Cabeçalho

| Campo | Valor |
|---|---|
| **Procedimento** | IPL nº `[preencher]` |
| **Fuso de referência** | UTC (Z) |
| **Analista** | `[nome / matrícula]` |
| **Última atualização** | `YYYY-MM-DDTHH:MM:SSZ` |

---

## Cronologia

| # | Data/Hora UTC | Evento | Fonte | Classificação | Confiança |
|---|---|---|---|---|---|
| 1 | `YYYY-MM-DDTHH:MM:SSZ` | `[descrição do evento]` | `[URL / ofício / hash da evidência]` | FATO | ALTO |
| 2 | `YYYY-MM-DDTHH:MM:SSZ` | `[...]` | `[...]` | FATO | ALTO |
|   | **⚠️ LACUNA** (≈`[N]` dias/horas sem evidência) | — | — | — | — |
| 3 | `YYYY-MM-DDTHH:MM:SSZ` | `[...]` | `[...]` | INFERÊNCIA | MÉDIO |
| 4 | | | | | |

---

## Intervalos críticos

| De (#) | Para (#) | Duração | Implicação analítica |
|---|---|---|---|
| 1 | 3 | `[X dias Y horas]` | `[premeditação curta / janela de operação / ...]` |

---

## ⚠️ Lacunas temporais identificadas

### Lacuna 1 — entre #[X] (`[data]`) e #[Y] (`[data]`)

- **Hiato:** `[duração]`
- **Possíveis diligências para preencher:**
  - `[ferramenta / fonte + referência na KB]`
  - `[...]`
  - `[...]`

---

## 📊 Síntese cronológica

├─ **Janela operacional** identificada: `[início → fim]` (`[duração total]`)
├─ **FATOS** com hash/ofício: `[N]` eventos
├─ **INFERÊNCIAS** com janela: `[N]` eventos
└─ **Lacunas** a investigar: `[N]`

▶ **Próxima ação sugerida:** `[executar diligências da Lacuna X / avançar para /analise-contraditoria / fechar /gerar-relatorio]`

---

## Regras de preenchimento

- **Timestamps em UTC** sempre, formato ISO 8601 (`YYYY-MM-DDTHH:MM:SSZ`).
- **FATO vs INFERÊNCIA:** sem exceção. Se não tem fonte objetiva, é INFERÊNCIA.
- **Confiança:** ALTO (múltiplas fontes convergem) / MÉDIO (uma fonte forte) / BAIXO (indício único).
- **Eventos em janela** (não pontuais): registre início e fim, ou anote `aprox. [hora]` na coluna.
- **Lacunas:** marcar sempre que `>1` evento esperado estiver ausente entre eventos conhecidos.

---

*Timeline conforme metodologia OSINT-Sentinel v1.0 (Fase 3 — Processamento) e KB OSINT v3.0/2026 §22.*
