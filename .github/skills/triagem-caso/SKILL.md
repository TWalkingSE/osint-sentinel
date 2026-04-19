---
name: triagem-caso
description: >
  Classificar rapidamente um caso OSINT em 5 perguntas estruturadas (natureza,
  respaldo legal, perfil, identificadores, urgência) e recomendar o próximo
  skill a acionar. Use quando o usuário chega com pergunta vaga, sem contexto
  processual claro, ou quando quer decidir qual Ação (A–I) rodar primeiro.
  Skill extra, anterior à Ação A. Exemplos: "não sei por onde começar", "me
  ajuda a classificar esse caso", "qual skill uso primeiro?".
---

# Triagem de Caso (pré-Fase 1)

## Quando usar

- Usuário sem contexto claro, precisa de classificação antes de planejar
- Decidir entre `/planejar-investigacao` (caso completo), `/consultar-toolkit` (identificador apenas) ou recusa (falta de respaldo)
- Identificar rapidamente gatilhos de **CSAM**, **alvo sem respaldo** ou **painel clandestino**

## Protocolo

### 1. Apresente 5 perguntas sequenciais

Não espere todas de uma vez — pergunte, espere resposta, vá para próxima.

#### Pergunta 1 — Natureza do fato
> "Qual o tipo de crime ou fato sob investigação? (ex: estelionato via PIX, sextortion, fraude de domínio, ransomware, ameaça, pornografia infantil, fake news, outro)"

**⚠️ Se a resposta indicar CSAM/pornografia infantil:** ativar **Protocolo CSAM** de `AGENTS.md` imediatamente. Não prossiga.

#### Pergunta 2 — Respaldo legal
> "Qual o documento que ampara a investigação? (IPL nº, PIC, representação formal, decisão judicial, instauração em andamento, ou é consulta informal/pessoal?)"

**⚠️ Se resposta = "pessoal / particular / sem processo":** aplique **recusa absoluta** (alvo sem vínculo processual). Redirecione para canais formais (B.O., advogado, ouvidoria).

#### Pergunta 3 — Perfil do usuário
> "Você atua como: investigador policial (delegado/agente/escrivão), perito digital, analista de threat intel/SOC/IR, promotor/analista MP, advogado/assessoria, ou outro?"

Calibra profundidade: policial = operacional; perito = forense; threat intel = infraestrutura; jurídico = dispositivos legais.

#### Pergunta 4 — Identificadores conhecidos
> "Quais identificadores você já tem? (URL, e-mail, telefone, CPF, CNPJ, IP, domínio, username, imagem, wallet cripto, hash, placa, IMEI — quais e quantos?)"

Se 0 identificadores → caso ainda em briefing, prossiga para `/planejar-investigacao` com foco em **Fase 1** (hipóteses antes de diligência).
Se 1 identificador → `/consultar-toolkit` + `/mapear-pivos`.
Se múltiplos identificadores → `/planejar-investigacao` completo.

#### Pergunta 5 — Urgência / prazo
> "Há flagrante, tempestividade de ofício, risco de apagamento de evidência ou prazo processual? Qual o horizonte?"

Urgência ALTA → priorize preservação (Wayback, URLScan, SingleFile) antes de análise.
Urgência MÉDIA/BAIXA → fluxo padrão.

### 2. Produza a classificação e o encaminhamento

```markdown
# 🔍 TRIAGEM DE CASO

| Eixo | Classificação |
|---|---|
| **Natureza** | [tipo penal + dispositivo] |
| **Respaldo legal** | [IPL/PIC/decisão + nº] |
| **Perfil operador** | [investigador/perito/TI/jurídico] |
| **Maturidade de dados** | [0 ids / 1 id / múltiplos ids] |
| **Urgência** | [ALTA / MÉDIA / BAIXA] |

## Fase do ciclo recomendada
[1 — Planejamento / 2 — Coleta / 3 — Processamento / 4 — Análise / 5 — Produção]

## Gatilhos detectados
- ✅ / ❌ Respaldo legal presente
- ✅ / ❌ Técnica 🟡 envolvida (se sim, preparar autorização)
- ✅ / ❌ Identificador com roteamento direto para KB
- 🚨 / ❌ CSAM → se sim, Protocolo CSAM
- ❌ / 🛑 Alvo sem respaldo → se sim, recusa absoluta

## ▶ Próximo skill recomendado
1. **[skill]** — porque [justificativa]
2. Alternativa: **[skill]** — se [condição]

## OPSEC mínimo desta etapa
[Proporcional à urgência e à classificação]
```

### 3. Se houver gatilho de recusa/CSAM

Não prossiga para outro skill — entregue o protocolo adequado de `AGENTS.md` e encerre a triagem.

## Regras

- **NUNCA** gere plano completo na triagem — é apenas classificação para rotear.
- **SEMPRE** rode as 5 perguntas em sequência, não em bloco. Espere cada resposta antes da próxima.
- **Pergunta 1 com CSAM** = Protocolo CSAM imediato, sem passar para pergunta 2.
- **Pergunta 2 com "caso pessoal"** = recusa absoluta imediata, sem passar para pergunta 3.
- **Se o usuário chegar com contexto completo na primeira mensagem**, pule a triagem e vá direto para o skill apropriado.
