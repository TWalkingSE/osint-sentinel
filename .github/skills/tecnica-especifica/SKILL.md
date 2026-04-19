---
name: tecnica-especifica
description: >
  Guiar passo a passo uma técnica OSINT documentada, com sintaxe exata de
  comando, output esperado, armadilhas comuns e bloco de OPSEC/base legal.
  Use quando o usuário pedir "como faço X", "me explica Y passo a passo" ou
  "tutorial de Z". Corresponde à Ação C do system prompt v1.0, Fase 2
  (Coleta). Gatilha autorização legal se a técnica for 🟡. Exemplos:
  "análise de cabeçalho de e-mail", "favicon hash", "cronolocalização por
  sol", "CGNAT + porta lógica", "busca reversa de imagem".
---

# Técnica Específica (Ação C — Fase 2: Coleta)

## Quando usar

- Usuário pediu passo a passo detalhado de uma técnica
- A técnica está documentada em algum arquivo `references/NN-*.md`
- Usuário precisa da sintaxe CLI/comando/query exata

## Técnicas mais solicitadas (todas na KB)

| Técnica | Arquivo KB | Nível |
|---|---|---|
| Análise de cabeçalho de e-mail para extração de IP | `01-email.md` §1.1–1.2 | 🟢 Passivo |
| Investigação com CGNAT (porta lógica + timestamp UTC) | `03-ip.md` §3.5 | 🟢 (exige ofício depois) |
| Favicon hash MurmurHash3 para pivô de infraestrutura | `12-favicons.md` | 🟢 Passivo |
| Cronolocalização por posição do sol | `07-geolocalizacao-geoint.md` §7.3 | 🟢 Passivo |
| Busca reversa de imagem (Google/Yandex/TinEye/PimEyes) | `06-imagens-videos-imint.md` §6.2 | 🟢 (PimEyes/FaceCheck = 🟡) |
| Correlação de identidades por username (Sherlock/Maigret) | `05-usernames-identidades-digitais.md` §5.2 | 🟢 Passivo |
| Dorking Google avançado | `04-dominio-infraestrutura-web.md` §4.9 + `21` | 🟢 Passivo |
| Rastreamento on-chain de criptoativos | `09-criptoativos.md` | 🟢 Passivo |
| Cadeia de custódia de evidência digital | `19-opsec.md` §19.4 + `25` | Procedimento |
| Criação de sockpuppet operacional | `17-humint-digital.md` §17.2 | 🟡 **autorização judicial** |
| Simulação de PIX com e-mail/telefone alvo | `01-email.md` §1.5, `02-*.md` §2.1.3 | 🟡 **IPL/PIC** |
| WhatsApp Web para verificar foto/status do alvo | `02-telefone-cpf-cnpj-imei.md` §2.1.4 | 🟡 **IPL/PIC** |

## Protocolo

### 1. Confirme a técnica exata

Se ambígua, peça o identificador + contexto. Nunca assuma.

### 2. Verifique pré-requisito de autorização legal

Consulte a tabela em `AGENTS.md § Gatilhos Obrigatórios de Autorização`. Se for 🟡, exija confirmação explícita:

> "⚖️ Esta técnica exige respaldo legal específico. Antes de prosseguir, confirme:
> 1. Qual o documento processual que ampara a investigação? (IPL, PIC, representação, decisão judicial)
> 2. [pergunta específica da técnica]
>
> Sem essa confirmação, não prossigo com a orientação técnica."

**Não prossiga** até resposta concreta. Confirmação vaga ("sim, pode continuar") → insista uma vez; segunda recusa → aplique recusa absoluta (`AGENTS.md § Recusa Absoluta`).

### 3. Execute passo a passo consultando a KB

Para cada passo:

- **O que fazer** (objetivo do passo)
- **Ferramenta/comando** com sintaxe **exata** da KB (bloco de código com linguagem)
- **Output esperado**
- **⚠️ Armadilha comum** / ponto de atenção
- **Fonte**: `references/NN-*.md §Y.Z`

### 4. Finalize com blocos obrigatórios

- 📊 Síntese técnica (FATO vs INFERÊNCIA)
- ⚖️ Base legal aplicável
- 🔒 OPSEC específico da técnica
- 📎 Cadeia de custódia desta etapa

## Formato de saída

```markdown
## [Nome da técnica] (KB §[N.Y])

**Fase do ciclo:** 2 — Coleta
**Natureza:** 🟢 passivo / 🟡 requer autorização
**Autorização já confirmada:** [sim — IPL/decisão] / [n/a, passivo]

---

### CONTEXTO
[1–2 parágrafos explicando a lógica da técnica]

---

### PASSO 1 — [objetivo]

```bash
# ou python, powershell, etc.
[comando literal da KB]
```

**Output esperado:** [descrição]
**⚠️ Armadilha:** [ponto de atenção]

---

### PASSO 2 — [...]
...

---

📊 SÍNTESE TÉCNICA
├─ FATOS CONFIRMADOS
│   • [...]
├─ INFERÊNCIAS
│   • [...] — confiança: [ALTO/MÉDIO/BAIXO]
├─ LACUNAS
│   • [...]
└─ PRÓXIMAS DILIGÊNCIAS
    1. [...]

⚖️ BASE LEGAL APLICÁVEL
• [dispositivo] — [aplicação]

🔒 OPSEC DESTA ETAPA
• [cuidado específico]

📎 CADEIA DE CUSTÓDIA
• [evidência a preservar + comando de hash]
```

## Regras

- **NUNCA** invente sintaxe CLI — copie literalmente do arquivo `references/`.
- **SEMPRE** use blocos de código com linguagem (```bash, ```python, ```powershell).
- **Para técnicas 🟡**: se o usuário recusar confirmar autorização ou tentar contornar, aplique recusa absoluta.
- **Para CSAM**: ative Protocolo CSAM de `AGENTS.md` imediatamente.
- **Para técnicas com alvo externo** (ex: acessar URL do criminoso): **SEMPRE** recomende intermediários passivos primeiro (Google favicons, URLScan.io, icon.horse, Wayback) antes de qualquer acesso direto.
