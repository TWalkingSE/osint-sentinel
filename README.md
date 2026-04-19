# OSINT-Sentinel

**OSINT agent kit** para investigação criminal digital brasileira, estruturado para IDEs agentic com foco em **planejamento**, **coleta**, **processamento**, **análise**, **produção de relatório** e **preservação probatória**.

O projeto combina:

- **AGENTS.md** com identidade, guardrails e protocolos forenses
- **14 skills canônicos** para tarefas investigativas recorrentes
- **KB modular** com **28 seções** carregadas sob demanda
- **Templates prontos para colagem** em IPL, laudo, representação e relatório de inteligência
- **Casos-exemplo completos** para demonstrar o fluxo de uso ponta a ponta

Toda resposta do agente é orientada por 4 pilares:

- **Ciclo de Inteligência** como espinha dorsal operacional
- **FATO vs INFERÊNCIA** como disciplina analítica
- **Autorização legal prévia** para técnicas sensíveis
- **OPSEC + cadeia de custódia** como requisito de validade probatória

## Visão geral

O **OSINT-Sentinel** transforma LLMs em um assistente especializado em **OSINT aplicado à investigação criminal digital brasileira**, com linguagem forense, foco em diligência concreta e respeito explícito à legislação nacional.

Em vez de jogar uma base de conhecimento inteira no contexto, o projeto usa **carregamento progressivo**:

1. **`AGENTS.md`** define identidade, regras, recusas e protocolos críticos
2. **`SKILL.md`** especializa a tarefa conforme o objetivo do usuário
3. **`references/NN-*.md`** carrega apenas a seção da KB necessária para o identificador investigado

O resultado é um projeto mais enxuto, auditável e fácil de adaptar a diferentes IDEs e modelos.

## O que está incluso

- **28 referências temáticas** da KB OSINT v3.0/2026
- **14 skills**:
  - 9 skills das Ações **A–I**
  - 4 skills extras operacionais
  - 1 skill índice da KB (`/osint-kb`)
- **9 templates** operacionais
- **3 casos-exemplo** completos
- **Compatibilidade multi-IDE** com Windsurf, Claude Code, Cursor, Copilot e uso manual em outros agentes

## Para quem é

- **Investigador policial** — foco em próxima diligência, ofício e sequência probatória
- **Perito digital / forense** — foco em integridade, hash, documentação e cadeia de custódia
- **Analista de threat intel / SOC / IR** — foco em infraestrutura, IOCs, pivôs técnicos e atribuição
- **Assessoria jurídica / MP** — foco em enquadramento legal e proporcionalidade investigativa

## IDEs e ferramentas compatíveis

O projeto usa o padrão **AGENTS.md + SKILL.md**, reconhecido nativamente por:

| IDE / Ferramenta | Arquivos carregados |
|---|---|
| **Windsurf / Cascade** | `AGENTS.md` + `.windsurf/rules/` + `.windsurf/skills/` |
| **Claude Code** | `AGENTS.md` + `CLAUDE.md` + `.claude/skills/` |
| **Cursor** | `AGENTS.md` + `.cursorrules` |
| **GitHub Copilot** | `.github/copilot-instructions.md` + `.github/prompts/` |
| **Qualquer outra (GPT, Gemini, Llama local)** | Use `AGENTS.md` como instrução principal e carregue `.github/skills/` sob demanda |

## Como usar

### Início rápido

1. Clone ou baixe este repositório
2. Abra a pasta na sua IDE com modo agente ativo
3. A IDE carrega automaticamente o `AGENTS.md` e as instruções
4. Invoque um skill via slash-command (ex: `/planejar-investigacao`) ou faça perguntas naturais
5. Quando necessário, complemente com `templates/` e `examples/`

### Fluxo recomendado de uso

| Situação | Skill recomendado |
|---|---|
| Você ainda não sabe por onde começar | `/triagem-caso` |
| Há um caso novo com múltiplos identificadores | `/planejar-investigacao` |
| Você tem 1 identificador e precisa de ferramentas | `/consultar-toolkit` |
| Você quer um passo a passo de uma técnica | `/tecnica-especifica` |
| Você precisa derivar novos identificadores | `/mapear-pivos` |
| Você quer organizar eventos cronologicamente | `/timeline-builder` |
| Você quer consolidar vínculos entre entidades | `/grafo-conexoes` |
| Você já terminou a coleta e precisa do documento final | `/gerar-relatorio` |
| Você precisa formalizar a integridade das evidências | `/cadeia-custodia` |

### Exemplos de perguntas

```
Tenho um IPL de estelionato via site falso de banco. Como começo?
Me explica favicon hash passo a passo.
Username darkop3rator_br apareceu em fórum criminal. Quais pivôs eu derivo?
Monta o relatório OSINT com esses dados: [...]
Checklist OPSEC para operação em dark web.
```

### Skills disponíveis

Digite `/nome-do-skill` no chat:

| Slash | Função | Fase do ciclo |
|---|---|---|
| `/osint-kb` | Base de conhecimento (28 seções) | Todas |
| `/triagem-caso` | Classificação rápida em 5 perguntas | 1 — Planejamento |
| `/planejar-investigacao` | Plano estruturado (Ação A) | 1 — Planejamento |
| `/consultar-toolkit` | Ferramentas por categoria (Ação B) | 2 — Coleta |
| `/tecnica-especifica` | Passo a passo de técnica (Ação C) | 2 — Coleta |
| `/mapear-pivos` | Derivar identificadores (Ação D) | 2 — Coleta |
| `/ioc-extractor` | Extrai IOCs de texto livre | 2 — Coleta |
| `/timeline-builder` | Cronologia estruturada | 3 — Processamento |
| `/grafo-conexoes` | Grafo textual de conexões | 3 — Processamento |
| `/analise-contraditoria` | Red team de hipóteses (Ação I) | 4 — Análise |
| `/gerar-relatorio` | Relatório 13-seções (Ação E) | 5 — Produção |
| `/cadeia-custodia` | Tabela SHA-256 (Ação F) | 5 — Produção |
| `/checklist-opsec` | Checklist pré-operação (Ação G) | Transversal |
| `/analise-juridica` | Técnica × legislação BR (Ação H) | Transversal |

## Arquitetura do projeto

### Espinha dorsal metodológica

Toda saída do agente é ancorada em uma das 7 fases do **Ciclo de Inteligência**:

```text
1. Planejamento → 2. Coleta → 3. Processamento → 4. Análise → 5. Produção → 6. Disseminação → 7. Feedback
```

### Organização do conhecimento

- **Canônico:** `.github/skills/`
- **Wrappers para descoberta:** `.windsurf/skills/` e `.claude/skills/`
- **Regras sempre ativas:** `.windsurf/rules/`
- **Templates operacionais:** `templates/`
- **Casos demonstrativos:** `examples/`

Isso evita duplicação de conteúdo e mantém a manutenção simples.

## Estrutura do projeto

```
osint-sentinel/
├── README.md                              (este arquivo)
├── AGENTS.md                              (identidade e regras — padrão universal)
├── CLAUDE.md                              (ajustes para Claude Code)
├── .cursorrules                           (resumo para Cursor)
├── .github/
│   ├── copilot-instructions.md
│   ├── prompts/
│   │   └── osint-menu.prompt.md           (menu interativo)
│   └── skills/                            ← CANÔNICO
│       ├── osint-kb/
│       │   ├── SKILL.md                   (índice)
│       │   └── references/                (28 arquivos temáticos)
│       ├── planejar-investigacao/SKILL.md
│       ├── consultar-toolkit/SKILL.md
│       ├── tecnica-especifica/SKILL.md
│       ├── mapear-pivos/SKILL.md
│       ├── gerar-relatorio/SKILL.md
│       ├── cadeia-custodia/SKILL.md
│       ├── checklist-opsec/SKILL.md
│       ├── analise-juridica/SKILL.md
│       ├── analise-contraditoria/SKILL.md
│       ├── triagem-caso/SKILL.md          (EXTRA)
│       ├── timeline-builder/SKILL.md      (EXTRA)
│       ├── grafo-conexoes/SKILL.md        (EXTRA)
│       └── ioc-extractor/SKILL.md         (EXTRA)
├── templates/                             (artefatos preenchíveis para uso real)
├── examples/                              (casos-exemplo end-to-end)
├── .windsurf/
│   ├── rules/osint-sentinel.md            (regras always-on)
│   └── skills/                            (14 wrappers → .github/skills/)
└── .claude/
    └── skills/                            (14 wrappers → .github/skills/)
```

Os diretórios `.windsurf/skills/` e `.claude/skills/` contêm apenas **wrappers de descoberta** (frontmatter `name`/`description` + ponteiro para o arquivo canônico). O conteúdo real vive em `.github/skills/`, evitando duplicação e *drift*.

## Carregamento progressivo

O projeto não despeja a KB inteira no contexto. Usa **três níveis**:

1. **Sempre ativo** — `AGENTS.md` com identidade, regras e gatilhos de autorização
2. **Sob demanda** — `SKILL.md` do skill invocado
3. **Sob demanda aninhada** — `references/NN-*.md` da KB carregado apenas para o identificador consultado

Isso mantém o contexto inicial enxuto e permite que a KB cresça sem custo para cada interação.

## Diferenciais do projeto

- **Foco brasileiro** — LGPD, MCI, CPP 158-A, Lei 12.850, Lei 14.155, ECA e prática investigativa nacional
- **Recusas explícitas** — painéis clandestinos, alvo sem vínculo processual, técnicas ofensivas, bypass de autenticação e protocolos CSAM
- **Artefatos prontos para uso** — relatório, cadeia de custódia, ofícios, timeline, checklist OPSEC
- **Escalável** — KB modular, skills independentes e wrappers leves
- **Publicável** — estrutura limpa, sem dependência de notas internas para funcionar

## Casos-exemplo incluídos

| Arquivo | Cenário | Fluxo demonstrado |
|---|---|---|
| `examples/caso-01-estelionato-pix.md` | Site falso + PIX | A → B → D → E → F |
| `examples/caso-02-sextortion.md` | Sextortion com alerta ECA/CSAM | A → C(🟡) → H → E → F |
| `examples/caso-03-fraude-dominio.md` | Phishing em escala / threat intel | A → C → D → I → E |

## Publicação e uso responsável

Este repositório foi organizado para **publicação pública**, mas o conteúdo foi desenhado para uso por perfis profissionais e institucionais.

Antes de publicar ou redistribuir, revise:

- `AGENTS.md`
- `.windsurf/rules/osint-sentinel.md`
- `.github/skills/osint-kb/references/`
- `examples/` e `templates/`

Se você gerar capturas, evidências, exports de Hunchly, dados de casos reais ou artefatos operacionais, **não os versiona neste repositório**. Use diretórios ignorados pelo `.gitignore`.

## Uso responsável

Este material destina-se **exclusivamente** a profissionais de segurança pública, investigação criminal, perícia digital, Ministério Público, Poder Judiciário, advocacia, pesquisa acadêmica e cibersegurança corporativa. O uso inadequado, sem autorização judicial ou legal pertinente, pode configurar crime.

Legislação a respeitar: **LGPD** (Lei 13.709/2018), **Marco Civil da Internet** (Lei 12.965/2014), **Código Penal**, **Lei 12.850/2013**, **Lei 14.155/2021** e correlatas.

## Contribuindo

Ao sugerir ferramentas, inclua:

- nome
- link oficial
- se é open-source
- plataformas suportadas
- diferencial principal
- base legal aplicável
- alertas de incidentes, controvérsias ou limitações

Priorize sempre documentação oficial e fontes já alinhadas à KB do projeto.

## Licença

Uso profissional com responsabilidade individual do operador.

---

*OSINT-Sentinel v1.0 · Baseado em CyberShield (TWalkingSE) · 2026*
