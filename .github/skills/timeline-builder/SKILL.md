---
name: timeline-builder
description: >
  Construir linha do tempo estruturada a partir de eventos desordenados, em
  formato markdown pronto para colagem em relatório. Normaliza timestamps
  para UTC, sinaliza lacunas temporais, calcula intervalos e classifica
  cada evento como FATO/INFERÊNCIA. Skill extra, útil na Fase 3
  (Processamento). Exemplos: "monta timeline desses eventos", "organiza
  cronologicamente essas ações", "linha do tempo do caso".
---

# Timeline Builder (Fase 3 — Processamento)

## Quando usar

- Investigador tem **lista desordenada de eventos** coletados em diligências
- Antes de `/gerar-relatorio` (será o §5 — Linha do Tempo) ou `/analise-contraditoria` (teste de consistência)
- Para identificar **lacunas temporais** (períodos sem evidência) que podem virar diligências

## Protocolo

### 1. Solicite eventos

Cada evento com:
- **Data/hora** (melhor esforço — pode estar em fuso local, ajustaremos)
- **Evento** (descrição objetiva)
- **Fonte** (URL, arquivo, ofício, hash)

### 2. Normalize timestamps para UTC

- Se fuso não informado: **pergunte**, nunca assuma
- Formato final: `YYYY-MM-DDTHH:MM:SSZ` (ISO 8601 UTC)
- Se evento tem apenas data (sem hora): marcar como "data apenas" (resolução 1 dia)
- Se evento tem apenas intervalo (ex: "entre 10h e 12h"): registrar ambos os extremos

### 3. Ordene cronologicamente

Do mais antigo para o mais recente.

### 4. Classifique cada evento

- **FATO** — timestamp verificável por fonte objetiva (headers de e-mail, timestamp de bloco blockchain, log de CDN, metadado de arquivo, imagem EXIF original)
- **INFERÊNCIA** — timestamp inferido (ex: "post provavelmente feito entre X e Y") com grau de confiança

### 5. Sinalize lacunas temporais

Se há **hiato > 1 evento-esperado** entre dois eventos, marque com `⚠️ LACUNA` e sugira diligência para preencher.

### 6. Calcule intervalos críticos

Entre eventos-chave, mostre **duração** (ex: "registro do domínio → primeira vítima: 3 dias 14h"). Isso apoia análise de premeditação, janela de operação, etc.

## Formato de saída obrigatório

```markdown
# 🕐 LINHA DO TEMPO — [caso]

**Procedimento:** [IPL nº]
**Fuso de referência:** UTC (Z)
**Analista:** [nome/matrícula]
**Última atualização:** [UTC]

---

## Cronologia

| # | Data/Hora UTC | Evento | Fonte | Classificação | Confiança |
|---|---|---|---|---|---|
| 1 | 2026-04-10T14:22:03Z | Registro do domínio `alvo-banco.com` | WHOIS Registro.br (captura 2026-04-19, hash `a1b2...`) | FATO | ALTO |
| 2 | 2026-04-11T03:17:42Z | Primeira submissão do site ao VirusTotal | VT API (consulta 2026-04-19) | FATO | ALTO |
|   | **⚠️ LACUNA** (≈3 dias sem evidência) | — | — | — | — |
| 3 | 2026-04-14T18:05:11Z | Vítima acessa URL e faz PIX | Extrato bancário da vítima (ofício B1) | FATO | ALTO |
| 4 | 2026-04-14T18:05:14Z | PIX liquidado em conta destino | SPI Bacen (via ofício B2) | FATO | ALTO |
| 5 | aprox. 2026-04-14T18:06 | Transferência a segunda conta (triangulação) | Extrato B2 — horário na resolução de minuto | INFERÊNCIA (janela 18:05–18:10) | ALTO |
| 6 | 2026-04-15T00:00:00Z | Domínio `alvo-banco.com` derrubado (SOA removido) | DNS snapshot Circl.lu | FATO | MÉDIO (resolução 1 dia) |

---

## Intervalos críticos

| De | Para | Duração | Implicação |
|---|---|---|---|
| Registro do domínio (#1) | Primeira vítima (#3) | 4 dias 03h 43m | Premeditação curta; indicativo de kit de phishing preparado com antecedência |
| Primeira vítima (#3) | Derrubada do domínio (#6) | 6h 55m | Janela operacional curta — típico de campanha descartável |

---

## ⚠️ Lacunas temporais identificadas

### Lacuna 1 — entre #2 (2026-04-11) e #3 (2026-04-14)
- **Hiato:** ≈3 dias
- **Possíveis diligências para preencher:**
  - URLScan retrospectivo (`references/04-dominio-infraestrutura-web.md §4.6`) — submissões no período
  - Passive DNS no período (`references/03-ip.md §3.7`)
  - Wayback Machine do domínio (`references/04-dominio-infraestrutura-web.md §4.5`)
  - Ofício à plataforma de divulgação (se conhecida — SMS, e-mail de massa, rede social)

---

## 📊 Síntese cronológica

├─ **Janela operacional** identificada: 2026-04-10 → 2026-04-15 (5 dias)
├─ **FATOS** com hash/ofício: 5 eventos
├─ **INFERÊNCIAS** com janela: 1 evento
└─ **Lacunas** a investigar: 1

▶ **Próxima ação:** executar diligências da Lacuna 1 antes de fechar relatório.
```

## Regras

- **NUNCA** assuma fuso horário — pergunte se o usuário não informar.
- **SEMPRE** use UTC (Z) no formato final, mesmo que o evento tenha ocorrido em BRT/BRST.
- **SEMPRE** separe FATO de INFERÊNCIA na tabela.
- **Eventos com resolução de minuto em casos criminais** (PIX, autenticação): marcar explicitamente o nível de resolução.
- **Se o usuário fornecer eventos sem fonte:** marque como INFERÊNCIA com confiança BAIXA e sugira confirmação antes de usar em relatório.
- **Para casos com blockchain:** timestamp do bloco é FATO ALTO (consensuado pela rede). Cite altura do bloco e hash.
- **Para e-mails:** timestamp de `Received:` mais antigo é mais próximo do fato original — ver `references/01-email.md §1.1`.
