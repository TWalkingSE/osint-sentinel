# RELATÓRIO DE INVESTIGAÇÃO OSINT

> Template preenchível — baseado no system prompt OSINT-Sentinel v1.0 (Ação E) e KB OSINT v3.0/2026 §23.3.
> Remova este cabeçalho ao colar em IPL/laudo.

---

## 1. Identificação

| Campo | Valor |
|---|---|
| **Procedimento** | IPL nº `[preencher]` / PIC nº `[preencher]` |
| **Natureza do fato** | `[tipo penal + dispositivo]` |
| **Data de início** | `YYYY-MM-DDTHH:MM:SSZ` (UTC) |
| **Data de encerramento desta fase** | `YYYY-MM-DDTHH:MM:SSZ` (UTC) |
| **Analista responsável** | `[nome / matrícula]` |
| **Unidade** | `[DRCC / NUCIBER / unidade]` |
| **Classificação de sigilo** | ☐ Público · ☐ Restrito · ☐ Sigiloso |
| **Autoridade destinatária** | `[delegado / MP / juízo]` |

---

## 2. Objetivo

`[Descreva o objetivo da investigação em 2–4 frases, partindo do briefing inicial. Enuncie claramente o que se busca provar ou refutar.]`

**Base legal:**
- `[Lei / artigo / dispositivo]` — `[aplicação ao caso]`
- `[...]`

---

## 3. Metodologia

Investigação conduzida conforme **Ciclo de Inteligência** (7 fases). Fontes exclusivamente abertas (OSINT passivo) exceto onde explicitado. Todas as evidências preservadas com hash SHA-256 e cadeia de custódia formal (Apêndice A).

**Técnicas aplicadas:**
- `[técnica]` — `references/NN-*.md §Y.Z`
- `[...]`

**Ferramentas empregadas:**

| # | Ferramenta | URL oficial | Versão / data de uso | Função |
|---|---|---|---|---|
| 1 | `[nome]` | `[URL]` | `[versão / UTC]` | `[o que foi extraído]` |
| 2 | | | | |

**Ambiente operacional:**
- Sistema: `[OS + versão]`
- Rede: `[VPN institucional / Tor / outro]`
- VM: `[dedicada / snapshot]`
- Navegador: `[Firefox hardened / outro]`

---

## 4. Identificadores Investigados

| # | Tipo | Identificador | Fonte consultada | Data UTC | Resultado sintético |
|---|---|---|---|---|---|
| 1 | `[Domínio]` | `[alvo-banco.com]` | `[WHOIS Registro.br]` | `[...]` | `[titular / data de registro / e-mail]` |
| 2 | | | | | |

---

## 5. Linha do Tempo

| # | Data/Hora UTC | Evento | Fonte | Classificação | Confiança |
|---|---|---|---|---|---|
| 1 | `YYYY-MM-DDTHH:MM:SSZ` | `[evento]` | `[fonte]` | FATO / INFERÊNCIA | ALTO/MÉDIO/BAIXO |

> Gerar com `/timeline-builder` para consistência de fuso e marcação de lacunas.

---

## 6. Conexões Identificadas

### 🟢 FATOS CONFIRMADOS

- `[Entidade A]` **`[relação]`** `[Entidade B]` — fonte: `[referência]`
- `[...]`

### 🎯 INFERÊNCIAS

- `[Entidade A]` **possivelmente** `[relação]` `[Entidade B]` — confiança **`[ALTO/MÉDIO/BAIXO]`**
  - Base: `[fato(s) que sustenta(m)]`
  - Lacuna: `[o que confirmaria definitivamente]`
- `[...]`

### 📊 Grafo exportado

Ver **Apêndice B — Grafo de Conexões** (gerado via `/grafo-conexoes`).

---

## 7. Evidências Coletadas

Referência ao **Apêndice A — Cadeia de Custódia** com tabela completa (SHA-256, método, operador).

Síntese:
- Total de evidências preservadas: `[N]`
- Métodos aplicados: `[SingleFile / Hunchly / sha256sum / wget / export de API]`
- Armazenamento: `[VeraCrypt + backup redundante]`

---

## 8. Conclusões e Hipóteses

### H1 — `[hipótese]` · plausibilidade: **`[ALTA / MÉDIA / BAIXA]`**

- **Sustentada por:** `[fatos, com referência]`
- **Limitação:** `[lacunas restantes]`

### H2 — `[hipótese alternativa]` · plausibilidade: **`[...]`**

- **Sustentada por:** `[...]`
- **Limitação:** `[...]`

### Hipótese preferida e justificativa

`[H1 / H2 / inconclusivo]` pela convergência de `[fatos determinantes]`, apesar de `[limitações]`.

> Se múltiplas hipóteses permanecem plausíveis, considerar execução de `/analise-contraditoria` antes da entrega final.

---

## 9. Recomendações — Próximas Diligências

1. Oficiar `[entidade]` solicitando `[dado]` com fundamento em `[dispositivo]`
2. `[Diligência técnica — ex: preservação formal pelo provedor via MCI art. 10]`
3. `[Cooperação internacional — ex: preservação de conta via Rede 24/7 Budapeste (DRCI)]`
4. `[...]`

---

## 10. Limitações

- `[Autorizações pendentes — ex: reconhecimento facial aguarda decisão judicial]`
- `[Ferramentas não disponíveis no ambiente — ex: Maltego Classic sem licença ativa]`
- `[Fontes indisponíveis — ex: snapshot Wayback antes de DD/MM não existe]`
- `[Escopo não coberto — ex: análise financeira internacional requer MLAT]`
- `[Interpretações que poderiam ser revisadas com novas evidências]`

---

## Apêndice A — Cadeia de Custódia

> Gerar via `/cadeia-custodia`. Anexar tabela completa aqui.

| # | Arquivo | Origem | Data/Hora UTC | Método | SHA-256 | Operador |
|---|---|---|---|---|---|---|
| 1 | | | | | | |

**Procedimento de verificação de integridade:** ver `templates/cadeia-custodia.md`.

---

## Apêndice B — Grafo de Conexões

> Gerar via `/grafo-conexoes`. Exportar Maltego/draw.io/Obsidian como PNG/PDF e anexar neste ponto.

`[Inserir imagem exportada]`

---

## Apêndice C — Capturas de Tela Datadas

| # | Arquivo | Descrição | Referência cruzada (Apêndice A) | Data UTC |
|---|---|---|---|---|
| 1 | | | | |

---

## Assinatura

`[Nome do analista]`
`[Matrícula / cargo]`
`[Unidade]`
Data UTC: `[YYYY-MM-DDTHH:MM:SSZ]`

---

*Relatório gerado conforme metodologia Ciclo de Inteligência, KB OSINT v3.0/2026 §23.3. Uso restrito ao procedimento identificado na seção 1.*
