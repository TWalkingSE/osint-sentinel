# Caso 01 — Estelionato via Site Falso de Banco (PIX)

> **Fictício.** Todos os dados são placeholders (RFC 5737 / RFC 3849 para IPs, TLDs `.example` quando possível). Ilustra o fluxo Ação A → B → D → E → F do OSINT-Sentinel v1.0.

---

## Briefing

**Perfil do usuário:** Delegado da DRCC-XX.
**Entrada no chat:**

> "IPL nº 0123/2026. Estelionato. Vítima caiu em golpe via site falso de banco. Tenho: URL `https://alvo-banco.example/login`, e-mail `golpista@protonmail.example` (usado no WHOIS), screenshot datado. Como começo?"

**Identificação automática:** investigador policial + respaldo legal ✅ + múltiplos identificadores → **Ação A (planejamento)** na **Fase 1** do ciclo.

---

## Passo 1 — `/planejar-investigacao` (Ação A)

Saída do assistente:

```
📋 PLANO DE INVESTIGAÇÃO OSINT

Caso: IPL nº 0123/2026 — Estelionato via site fraudulento
Natureza: CP art. 171 §2º-A (fraude eletrônica, Lei 14.155/2021)
Respaldo legal: IPL em curso ✅
Perfil do analista: Delegado/Investigador
Fase do ciclo: 1 — Planejamento

🎯 HIPÓTESES
H1: Operador individual oportunista (kit de phishing genérico, baixa sofisticação)
    Teste: WHOIS recente + favicon hash único → MÉDIO
H2: Grupo organizado com infraestrutura recorrente (múltiplas vítimas, mesma família de domínios)
    Teste: favicon hash matches em Shodan > 5 + Whoxy reverso → ALTO se confirmado
H3: Operação internacional com hospedagem offshore (bulletproof hosting)
    Teste: IP real atrás de Cloudflare em ASN conhecido de bulletproof → BAIXO inicialmente

🔍 PLANO DE COLETA (ordem priorizada)

FASE A — Passivo (sem contato com alvo)
 1. URLScan.io + VirusTotal (references/04-*.md §4.6) — análise de site sem acesso direto
 2. WHOIS + Registro.br (references/04-*.md §4.1) — titularidade, data, e-mail
 3. crt.sh (references/04-*.md §4.8) — certificados emitidos
 4. DNSDumpster + MXToolbox (references/04-*.md §4.2) — DNS, MX, IPs
 5. Wayback Machine + Archive.today (references/04-*.md §4.5) — preservação histórica
 6. Favicon hash (references/12-favicons.md) — pivô via Shodan

FASE B — Pivô do e-mail do golpe
 7. Epieos (references/01-email.md §1.4) — cruzar com plataformas e vazamentos
 8. HaveIBeenPwned (references/01-email.md §1.6) — histórico de breaches
 9. Whoxy reverso (references/01-email.md §1.7) — outros domínios com mesmo e-mail
10. Holehe CLI (references/01-email.md §1.4) — cadastros em +120 sites

FASE C — Pivô via infraestrutura
11. Shodan http.favicon.hash:HASH (references/03-*.md §3.4)
12. ViewDNS IP History (references/04-*.md §4.7) — IP antes de Cloudflare
13. Reverse IP (references/03-*.md §3.3) — outros domínios no mesmo servidor

FASE D — Preservação
14. SingleFile / Hunchly — captura completa com SHA-256
15. Cadeia de custódia (/cadeia-custodia)

⚖️ AUTORIZAÇÕES NECESSÁRIAS (ofícios subsequentes)
- Provedor de hospedagem — logs de acesso (MCI art. 10-11)
- Plataforma de e-mail (Google/Microsoft/Proton) — dados cadastrais (MCI art. 15)
- Se IP brasileiro com CGNAT → ISP com IP + porta + timestamp UTC (references/03-*.md §3.5)
- Instituição financeira da vítima e destino — rastreamento PIX

🔒 OPSEC
- NÃO acessar URL em ambiente institucional identificável
- VM dedicada + VPN ou sandbox público (URLScan já provê sandbox)
- Preservar via Wayback/URLScan ANTES de qualquer interação detectável pelo criminoso

▶ PRÓXIMA AÇÃO SUGERIDA
Executar FASE A completa. Retornar outputs que eu oriento FASE B em diante.
Comando: /tecnica-especifica favicon hash
```

---

## Passo 2 — Usuário executa FASE A e retorna com outputs

Resumo dos resultados da FASE A (fictícios):

- **URLScan** identificou página de login com form HTTP POST para `/process.php`
- **WHOIS** (Registro.br via proxy de privacidade): titular anônimo, e-mail público `golpista@protonmail.example`, registro em `2026-04-10`
- **crt.sh**: 3 certificados emitidos para o domínio e 2 subdomínios (`app.alvo-banco.example`, `secure.alvo-banco.example`)
- **Favicon hash**: `-1234567890` (MurmurHash3) — 4 matches no Shodan, todos em ASN offshore
- **Wayback**: 2 snapshots preservados (14 e 15 de abril)

---

## Passo 3 — `/tecnica-especifica` (favicon hash) + `/mapear-pivos` (e-mail)

### `/tecnica-especifica` — Favicon Hash (KB §12)

O assistente entrega passo a passo com:
- `curl -o favicon.ico "https://www.google.com/s2/favicons?domain=alvo-banco.example&sz=64"` (evita tocar no alvo)
- Script Python com `mmh3.hash(base64.encodebytes(resp.content))`
- Query Shodan `http.favicon.hash:-1234567890 country:BR`
- Filtros para reduzir falso positivo

### `/mapear-pivos` — `golpista@protonmail.example`

```
🔗 MAPEAMENTO DE PIVÔS

Identificador inicial: E-mail golpista@protonmail.example
Fase do ciclo: 2 — Coleta

| # | Pivô | Ferramenta KB | Output | Confiança | Autorização |
|---|------|---------------|--------|-----------|-------------|
| 1 | Cadastros em +120 sites | Holehe (references/01-*.md §1.4) | Lista de plataformas com conta | MÉDIO | Passivo 🟢 |
| 2 | Breaches históricos | HaveIBeenPwned (§1.6) | Sites vazados | ALTO | Passivo 🟢 |
| 3 | Outros domínios do mesmo e-mail | Whoxy reverso (§1.7) | Domínios associados | ALTO se hit | Passivo 🟢 |
| 4 | Dados de conta Google | GHunt (§1.4) | Nome + foto Google | ALTO se Google | Passivo 🟢 |

▶ SEQUÊNCIA RECOMENDADA
1. Holehe — mapa rápido de plataformas
2. HIBP — confirma que e-mail é real e usado
3. Whoxy reverso — expansão da infraestrutura (outros domínios do mesmo golpe)
4. GHunt (só se ProtonMail deixar pista) — geralmente não aplica

📊 SÍNTESE TÉCNICA
├─ FATOS CONFIRMADOS
│   • E-mail golpista@protonmail.example foi titular de registro no WHOIS
├─ INFERÊNCIAS
│   • Uso de ProtonMail indica preocupação com anonimato — confiança: ALTO
│   • Registro 4 dias antes do primeiro ataque sugere operação descartável — ALTO
├─ LACUNAS
│   • Identidade real do titular (só avança via pivô 3 + ofício Proton via MLAT)
└─ PRÓXIMAS DILIGÊNCIAS
    1. Executar Holehe e Whoxy reverso
    2. Consolidar infraestrutura via /grafo-conexoes
    3. Preparar ofício à Proton via MLAT (references/28-cooperacao-internacional.md)

⚖️ BASE LEGAL
• MCI art. 7º IX — dado público
• Para dados cadastrais Proton: MLAT via DRCI (Suíça, convenção de Budapeste)

🔒 OPSEC
• Holehe em VM dedicada via VPN institucional
• Não fazer signup em nenhum site identificado como match

📎 CADEIA DE CUSTÓDIA
• Output Holehe em .txt com SHA-256
• Screenshot de cada match Whoxy com timestamp UTC
```

---

## Passo 4 — `/grafo-conexoes` consolida

Entidades: 1 e-mail (E1), 3 domínios (D1–D3) via Whoxy, 4 domínios (D4–D7) via favicon Shodan, 1 IP (I1), 1 wallet (W1) via ofício bancário.

Arestas principais:
- E1 `registrou` D1 (FATO — WHOIS)
- D1 `hospedado_em` I1 (FATO — Passive DNS Circl.lu)
- D1 `mesmo_operador_que` D4, D5 (INFERÊNCIA ALTO — favicon)
- E1 `registrou` D2, D3 (FATO — Whoxy reverso)
- Vítima `transacionou_com` W1 (FATO — extrato bancário ofício B1)

Export Mermaid anexado.

---

## Passo 5 — `/gerar-relatorio` (Ação E)

O assistente pergunta os 3 campos faltantes (número do procedimento já dado; confirma classificação de sigilo + autoridade destinatária), então gera o relatório 13-seções preenchendo com os outputs coletados, separando FATOS de INFERÊNCIAS nas §6 e §8.

Hipóteses revisadas ao final do relatório:
- **H2** (grupo organizado) — plausibilidade **ALTA** (confirmada por favicon + Whoxy + ASN de bulletproof)
- H1 — BAIXA (descartada)
- H3 — MÉDIA (aguarda MLAT para confirmar operador offshore)

---

## Passo 6 — `/cadeia-custodia` (Ação F)

Tabela final com 12 itens preservados (HTMLs, screenshots, JSON do URLScan, output Holehe, export Mermaid, captura Shodan). Todos com SHA-256 calculado via `Get-FileHash`. Procedimento de verificação incluído no Apêndice A do relatório.

---

## Passo 7 — Ofícios (templates)

Usando `templates/oficio-provedor-aplicacao.md` e `templates/oficio-provedor-conexao-cgnat.md`, o delegado produz:

1. Ofício ao provedor de hospedagem (dados cadastrais + logs de acesso)
2. Ofício à ProtonMail via MLAT-DRCI (dados cadastrais)
3. Ofício às 3 operadoras BR (IP+porta+UTC para acessos aos domínios)
4. Ofício Bacen (rastreamento da cadeia PIX)

---

## Síntese do fluxo

```
Briefing → /planejar-investigacao (A)
         → /tecnica-especifica (C, favicon) + /mapear-pivos (D, e-mail)
         → /grafo-conexoes (consolidação)
         → /gerar-relatorio (E) + /cadeia-custodia (F)
         → ofícios via templates/
```

**Tempo estimado de ponta a ponta:** 6–8 horas de investigação OSINT + 15–30 dias aguardando retornos de ofícios.

**Pontos de antiviés:** após FASE A, o investigador pode rodar `/analise-contraditoria` antes do relatório final para testar se H2 é mesmo ALTA ou se há contra-hipótese (ex: operador solo que comprou kit + reutilizou favicon de template).

---

*Caso fictício para ilustração. Use `/triagem-caso` + `/planejar-investigacao` em casos reais com os identificadores efetivamente coletados no IPL.*
