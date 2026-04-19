---
name: analise-contraditoria
description: >
  Executar red team sobre as hipóteses atuais da investigação para evitar viés
  de confirmação antes do relatório final. Para cada hipótese: que fatos
  sustentam, que fatos contradizem, qual hipótese alternativa explica os
  mesmos dados, que viés pode estar influenciando e qual diligência
  discriminaria entre hipóteses. Corresponde à Ação I do system prompt v1.0,
  Fase 4 (Análise). Exemplos: "desafia minhas hipóteses", "red team no
  caso", "estou enviesado, me prova o contrário".
---

# Análise Contraditória — Red Team (Ação I — Fase 4: Análise)

## Quando usar

- Hipóteses atuais precisam ser testadas antes de fechar relatório (`/gerar-relatorio`)
- Investigador quer evitar **viés de confirmação**, **âncora** ou **narrativa dominante**
- Múltiplas hipóteses plausíveis e investigador precisa priorizar

## Protocolo

### 1. Solicite (ou extraia) as hipóteses atuais

Numeradas (H1, H2, H3), com:
- Afirmação central
- Fatos que sustentam (FATOS)
- Base atual de plausibilidade (ALTA/MÉDIA/BAIXA)

### 2. Para cada hipótese execute 4 passos

#### a) Inventário de sustentação
Liste fatos objetivos que sustentam, com fonte.

#### b) Inventário de contradição e lacunas
- Quais fatos **contradizem** a hipótese?
- Quais fatos a hipótese **não explica**?
- Quais fatos estão **ausentes** que, se existissem, reforçariam/refutariam?

#### c) Contra-hipótese
Gere uma **hipótese alternativa plausível** que também explique os fatos — de preferência **não trivial** (ex: operador solo vs. grupo organizado vs. insider vs. operação de bandeira falsa).

#### d) Viés cognitivo identificado
Declare explicitamente se há sinal de:
- **Viés de confirmação** — só coletou evidência a favor
- **Âncora** — primeira hipótese prendeu o raciocínio
- **Disponibilidade** — caso anterior parecido influenciou
- **Narrativa dominante** — enredo "bonito" em detrimento de fatos
- **Halo/demonização** — atribuição moral antes da técnica

### 3. Proponha teste discriminante (falseabilidade)

Qual **diligência concreta**, **se executada**, discriminaria entre H1 e H2?

Formato: "Se output = X → H1 reforçada; Se output = Y → H2 reforçada; Se output = Z → ambas precisam revisão".

### 4. Conclua com ranking revisado

Com justificativa — e, se o ranking mudou, **por que** mudou.

## Formato de saída obrigatório

```markdown
# 🎯 ANÁLISE CONTRADITÓRIA (Red Team)

**Caso:** [procedimento]
**Fase do ciclo:** 4 — Análise
**Hipóteses submetidas:** [N]

---

## H1: [afirmação da hipótese original]

**Ranking anterior:** [ALTA/MÉDIA/BAIXA]

### Sustentam (FATOS)
- [fato] — fonte: [referência + data UTC]
- [...]

### Contradizem / Lacunas
- [fato contrário / lacuna com impacto]
- [fato que a hipótese não explica]

### Contra-hipótese plausível
**H1-alt:** [hipótese alternativa]
- Explica os mesmos fatos porque [...]
- Diferença crítica com H1: [...]

### Vieses identificados
- [âncora / confirmação / disponibilidade / narrativa / halo]
- Como se manifesta neste caso: [...]

---

## H2: [...]
*(mesmo tratamento)*

---

## H3: [...]
*(mesmo tratamento)*

---

## 🔬 TESTES DISCRIMINANTES

### Teste 1 — entre H1 e H2
**Diligência concreta:** [ação, ferramenta KB §X]
- Se output = **A** → H1 reforçada, H2 refutada
- Se output = **B** → H2 reforçada, H1 refutada
- Se output = **C** → ambas precisam revisão, gerar H4

### Teste 2 — entre H1 e H3 (se aplicável)
[...]

---

## 📊 RANKING REVISADO DE PLAUSIBILIDADE

| Posição | Hipótese | Plausibilidade atualizada | Justificativa |
|---|---|---|---|
| 1 | H[X] | **ALTA** | [resumo — o que a sustenta mais fortemente] |
| 2 | H[Y] | **MÉDIA** | [...] |
| 3 | H[Z] | **BAIXA** | [...] |

**Mudança de ranking em relação ao inicial:** [sim/não + por quê]

---

## ▶ PRÓXIMAS AÇÕES

1. **Executar teste discriminante 1** ANTES de fechar relatório (`/tecnica-especifica` ou `/mapear-pivos`)
2. Documentar resultado no relatório como evidência de **antiviés metodológico**
3. Se nenhum teste for possível no prazo: registrar limitação em `/gerar-relatorio` §10 (Limitações)

---

*Red team é prática de maturidade investigativa — relatório sem análise contraditória é relatório com viés invisível.*
```

## Regras

- **NUNCA** gere análise contraditória sem listar **ao menos 1 contra-hipótese** plausível por hipótese original.
- **NUNCA** pule o passo de "vieses identificados" — o ponto da Ação I é nomear vieses.
- **SEMPRE** proponha teste discriminante **executável** com a KB v3.0/2026 (sem inventar técnica).
- **SEMPRE** declare se o ranking mudou após a análise. Ranking imutável = sinal de red team fraco.
- **Para investigações sensíveis** (suspeito identificado, prisão iminente): considerar análise contraditória **obrigatória** antes do relatório de indiciamento.
- **Se o usuário resistir** ("tenho certeza que é H1"): reforce que é prática de antiviés, não ataque à competência.
