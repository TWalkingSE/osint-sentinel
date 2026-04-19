---
name: gerar-relatorio
description: >
  Produzir relatório OSINT estruturado em 13 seções para juntada em IPL,
  laudo pericial, representação ou dossiê de inteligência. Use quando a
  investigação (ou fase) estiver concluída e o usuário precisar consolidar
  dados em artefato formal. Corresponde à Ação E do system prompt v1.0,
  Fase 5 do Ciclo de Inteligência (Produção). Exemplos: "monta o relatório
  com esses dados", "preciso do documento para juntada", "consolida a fase
  concluída em relatório".
---

# Gerar Relatório OSINT (Ação E — Fase 5: Produção)

## Quando usar

- Fase de coleta/análise encerrada, dados consolidados
- Usuário precisa do documento para juntada, laudo ou representação
- Integra com `/cadeia-custodia` (Apêndice A) e `/grafo-conexoes` (Apêndice B)

## Protocolo

### 1. Solicite (ou extraia) os dados estruturados

Se algum campo estiver faltando, pergunte **antes** de preencher — não gere relatório com placeholders vazios nos campos críticos:

- **Número do procedimento / IPL / PIC**
- **Classificação de sigilo** (Sigiloso / Restrito / Público)
- **Autoridade destinatária** (delegado, MP, juízo)
- **Identificadores investigados** e resultados
- **Evidências coletadas** (arquivos + hashes + método)
- **Timeline dos fatos**
- **Conexões identificadas** (entidades + relações)
- **Hipóteses atuais** com plausibilidade

### 2. Preencha o template KB §23.3 (13 seções)

Use `templates/relatorio-osint.md` como base. Adapte ao caso concreto.

### 3. Separe FATO vs INFERÊNCIA

Nas seções analíticas (6. Conexões e 8. Conclusões), **sempre** separe:

- **FATOS CONFIRMADOS** — com fonte objetiva identificável
- **INFERÊNCIAS** — com grau de confiança ALTO/MÉDIO/BAIXO
- **LACUNAS** — o que falta

### 4. Integre apêndices

- **Apêndice A — Cadeia de Custódia** via `/cadeia-custodia`
- **Apêndice B — Grafo de Conexões** via `/grafo-conexoes` (exportação externa — Maltego, draw.io, Obsidian)
- **Apêndice C — Capturas de tela datadas** com referência cruzada ao Apêndice A

### 5. Entregue em artifact markdown (se Claude) ou bloco completo

Formato pronto para conversão em Word/PDF.

## Template obrigatório (13 seções)

```markdown
# RELATÓRIO DE INVESTIGAÇÃO OSINT

## 1. Identificação
- Procedimento: [IPL nº / PIC nº]
- Natureza do fato: [tipo penal + dispositivo]
- Data de início: [UTC]
- Data de encerramento desta fase: [UTC]
- Analista responsável: [nome / matrícula]
- Classificação: [Sigiloso / Restrito / Público]
- Autoridade destinatária: [delegado / MP / juízo]

## 2. Objetivo
[Reescrever objetivo a partir do briefing]
**Base legal:** [dispositivos — CP, Lei 14.155/2021, MCI, LGPD art. 7º]

## 3. Metodologia
Investigação conduzida conforme **Ciclo de Inteligência** (7 fases). Fontes
exclusivamente abertas (OSINT passivo) exceto onde explicitado. Todas as
evidências preservadas com hash SHA-256 e cadeia de custódia formal
(Apêndice A).

**Técnicas aplicadas:**
- [lista com referência a `references/NN-*.md §Y.Z`]

**Ferramentas empregadas:**
- [nome — URL — versão — data de uso]

## 4. Identificadores Investigados
| # | Identificador | Valor | Fonte consultada | Data UTC | Resultado |
|---|---|---|---|---|---|
| 1 | ... |

## 5. Linha do Tempo
| Data UTC | Evento | Fonte | Confiança |
|---|---|---|---|
| ... |

## 6. Conexões Identificadas

**FATOS CONFIRMADOS:**
- [conexão objetiva com fonte]

**INFERÊNCIAS:**
- [conexão hipotética] — confiança: [ALTO/MÉDIO/BAIXO]
  Base: [evidência de sustentação]

**Grafo exportado:** ver Apêndice B.

## 7. Evidências Coletadas
Referência ao Apêndice A — tabela completa com SHA-256, método, operador.

## 8. Conclusões e Hipóteses

**H1** (plausibilidade: [alta/média/baixa]): [hipótese]
- Sustentada por: [fatos]
- Limitação: [lacunas]

**H2** (plausibilidade: ...): [hipótese alternativa]
- ...

**Hipótese preferida no momento:** H[X], pelos seguintes motivos: [...]

## 9. Recomendações — Próximas Diligências
1. Ofício a [entidade] solicitando [dado] com fundamento em [dispositivo]
2. ...

## 10. Limitações
- [autorizações pendentes]
- [ferramentas não disponíveis no ambiente]
- [fontes indisponíveis no período investigado]
- [escopo não coberto por esta fase]

---

## Apêndice A — Cadeia de Custódia
Ver artefato gerado por `/cadeia-custodia`.

| # | Arquivo | Origem | Data/Hora UTC | Método | SHA-256 | Operador |
|---|---|---|---|---|---|---|
| ... |

## Apêndice B — Grafo de Conexões
Exportar Maltego/Obsidian/draw.io como PNG/PDF e anexar.

## Apêndice C — Capturas de Tela Datadas
| # | Arquivo | Descrição | Referência cruzada ao Apêndice A |
|---|---|---|---|
| ... |

---

*Relatório gerado conforme metodologia Ciclo de Inteligência, KB OSINT v3.0/2026.*
*Analista: [nome/matrícula] · Data UTC: [timestamp]*
```

## Regras

- **NUNCA** deixar campos críticos em branco — pergunte antes (IPL, classificação, autoridade destinatária).
- **NUNCA** misturar FATO com INFERÊNCIA no mesmo bullet — sempre separados.
- **NUNCA** citar ferramenta fora da KB v3.0/2026.
- **SEMPRE** incluir base legal em §2 (Objetivo) e §9 (Recomendações).
- **SEMPRE** incluir §10 (Limitações) — relatório sem limitações é sinal de viés.
- **Para Claude Code:** entregar como artifact markdown com filename `relatorio-[proc]-[data].md`.
- **Se CSAM aparecer** em evidências: ative Protocolo CSAM de `AGENTS.md` e **não processe** — redirecione para canais oficiais.
