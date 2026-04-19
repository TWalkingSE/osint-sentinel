---
name: mapear-pivos
description: >
  Derivar identificadores a partir de um inicial (e-mail → contas, username →
  plataformas, wallet → transações, IP → domínios no mesmo servidor) com
  indicação de ferramenta, confiança e autorização. Use quando o usuário
  tiver 1 identificador e quiser saber quais outros pode obter. Corresponde
  à Ação D do system prompt v1.0, Fase 2 (Coleta). Exemplos: "tenho esse
  e-mail, o que eu consigo derivar?", "username X em fórum criminal, quais
  pivôs?", "wallet BTC, como encontro o dono?".
---

# Mapear Pivôs (Ação D — Fase 2: Coleta)

## Quando usar

- Investigador tem **1 identificador** e quer o **mapa de derivações possíveis**
- Complementar a `/consultar-toolkit` (ferramentas) e `/tecnica-especifica` (passo a passo)
- Para planejar sequência de execução priorizada (passivo → caro → com autorização)

## Protocolo

### 1. Identifique o tipo do identificador inicial

- E-mail · Telefone · CPF/CNPJ · IP · Domínio · Username · Imagem · Wallet cripto · Hash · .onion · Placa · Favicon

### 2. Consulte a seção correspondente da KB

Abra `.github/skills/osint-kb/references/NN-*.md` e extraia as **técnicas de pivô** documentadas.

### 3. Liste 3–7 pivôs derivados

Para cada um:

- **Nova classe de identificador** obtível (ex: e-mail → telefone, IP → domínios, username → foto)
- **Técnica/ferramenta KB** que executa o pivô
- **Grau de confiança** (ALTO / MÉDIO / BAIXO) do resultado
- **Autorização legal** necessária (🟢 passivo / 🟡 requer IPL+PIC / 🔴 requer decisão judicial)

### 4. Proponha sequência de execução

Priorize: **passivo → barato → público**. Deixe 🟡 e 🔴 no final, com destaque de autorização prévia.

## Formato de saída obrigatório

```
🔗 MAPEAMENTO DE PIVÔS

Identificador inicial: [tipo + valor]
Fase do ciclo: 2 — Coleta

| # | Pivô (nova classe) | Ferramenta KB | Output | Confiança | Autorização |
|---|--------------------|---------------|--------|-----------|-------------|
| 1 | ... | §X — tool | ... | ALTO | Passivo 🟢 |
| 2 | ... | §Y — tool | ... | MÉDIO | 🟡 IPL/PIC |
...

▶ SEQUÊNCIA RECOMENDADA
1. [primeiro pivô + justificativa]
2. ...

📊 SÍNTESE TÉCNICA
├─ FATOS CONFIRMADOS
│   • [o que já é fato do identificador inicial]
├─ INFERÊNCIAS preliminares
│   • [pistas semânticas — ex: sufixo _br, leet, TLD]
├─ LACUNAS
│   • [o que só avança com cruzamento externo]
└─ PRÓXIMAS DILIGÊNCIAS (ver sequência acima)

⚖️ BASE LEGAL
• Pivôs 🟢 — MCI art. 7º IX (dado público)
• Pivôs 🟡 — [dispositivo específico]

🔒 OPSEC
• [cuidado operacional — nunca usar conta pessoal, VPN institucional, etc.]
```

## Tabela de Pivôs por Identificador (mapa rápido)

### E-mail
| Pivô | Ferramenta | Arquivo KB |
|---|---|---|
| Cadastros em +120 sites | Holehe (CLI) | `01-email.md` §1.4 |
| Breaches históricos | HaveIBeenPwned, IntelX | `01-email.md` §1.6 |
| Outros domínios do mesmo e-mail | Whoxy reverso | `01-email.md` §1.7 |
| Avatar universal | Gravatar | `01-email.md` §1.8 |
| Dados de conta Google | GHunt | `01-email.md` §1.4 |
| Telefone parcial (mascarado) | Recuperação de senha 🟡 | `01-email.md` §1.5 |

### Username
| Pivô | Ferramenta | Arquivo KB |
|---|---|---|
| Presença multi-plataforma | Sherlock, Maigret, Blackbird | `05-*.md` §5.1 |
| Variações leet | Google + variações manuais | `05-*.md` §5.2 |
| Histórico em fóruns arquivados | archived.moe, Pastebin dork | `05-*.md` §5.3 |
| GitHub (e-mail no `git log`) | API GitHub + dorks | `05-*.md` + `04-*.md` §4.9 |
| Posts deletados Reddit | Pushshift | `08-*.md` §8.8 |
| Telegram username histórico | SangMata_BOT, TgScanRobot | `08-*.md` §8.6 |

### Domínio
| Pivô | Ferramenta | Arquivo KB |
|---|---|---|
| Titular, e-mail registrante | WHOIS (Registro.br, ICANN) | `04-*.md` §4.1 |
| Subdomínios | Subfinder, Amass, DNSDumpster | `04-*.md` §4.2 |
| Certificados históricos | crt.sh, Censys | `04-*.md` §4.8 |
| Outros domínios do mesmo dono | Whoxy reverso | `01-*.md` §1.7 |
| IP real antes de Cloudflare | SecurityTrails, ViewDNS History | `04-*.md` §4.7 |
| Versões arquivadas | Wayback, Archive.today | `04-*.md` §4.5 |
| Outros sites no mesmo IP | Reverse IP (ViewDNS, HackerTarget) | `03-*.md` §3.3 |

### IP
| Pivô | Ferramenta | Arquivo KB |
|---|---|---|
| Geo + ASN + provedor | IPInfo, BGP.he.net | `03-*.md` §3.1 |
| Dispositivos expostos no IP | Shodan, Censys | `03-*.md` §3.4 |
| Domínios no mesmo IP | Reverse IP | `03-*.md` §3.3 |
| Reputação e blacklists | AbuseIPDB, Spamhaus | `03-*.md` §3.6 |
| Histórico de resoluções (passive DNS) | SecurityTrails, Circl.lu | `03-*.md` §3.7 |
| Assinante (se CGNAT) via ISP | Ofício: IP+porta+timestamp UTC | `03-*.md` §3.5 |

### Wallet cripto
| Pivô | Ferramenta | Arquivo KB |
|---|---|---|
| Transações completas | Blockchain.com, Etherscan | `09-*.md` §9.1 |
| Cluster de wallets do mesmo dono | WalletExplorer | `09-*.md` §9.2 |
| Fluxo + label + exchange | MetaSleuth, Arkham | `09-*.md` §9.2 |
| Reputação / scam report | BitcoinWhoIsWho, ChainAbuse | `09-*.md` §9.3 |
| Cashout em exchange BR | Ofício à exchange + MLAT | `09-*.md` + `28-*.md` |

### Favicon
| Pivô | Ferramenta | Arquivo KB |
|---|---|---|
| Outros sites do mesmo operador | Shodan `http.favicon.hash:`, Censys | `12-favicons.md` |
| Enumeração em bulk | FaviHunter, FavFreak | `12-favicons.md` |

(Demais tabelas — telefone, CPF/CNPJ, imagem, placa, hash — extraídas dos arquivos `references/` correspondentes conforme identificador.)

## Regras

- **NUNCA** listar pivô que não está no arquivo `references/` correspondente.
- **SEMPRE** marcar 🟢/🟡/🔴 e autorização necessária.
- **Para pivôs 🟡**: se o usuário escolher avançar, redirecione para `/tecnica-especifica` (onde autorização será exigida).
- **GitHub é o pivô de ouro** em username — `git log --all --format='%ae'` pode expor e-mail real (KB §5 + §4.9).
- **Não baixar breaches completas** — preserve apenas URL/hash/referência (LGPD art. 46, ver `AGENTS.md`).
