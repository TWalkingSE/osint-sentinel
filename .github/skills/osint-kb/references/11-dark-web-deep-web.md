<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 11
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 11. DARK WEB E DEEP WEB

### 11.1 Conceitos e Diferenciação

| Camada | Definição | Acesso |
|---|---|---|
| **Surface Web** | Conteúdo indexado por buscadores | Qualquer navegador |
| **Deep Web** | Conteúdo não indexado (logins, sistemas) | Autenticação necessária |
| **Dark Web** | Redes overlay (Tor, I2P, Freenet) | Software específico |

### 11.2 Acesso Seguro à Dark Web

> ⚠️ **OPSEC CRÍTICO:** Nunca acesse a dark web sem configuração adequada de OPSEC. Veja seção 19.

| Ferramenta | URL | Função |
|---|---|---|
| Tor Browser | https://www.torproject.org/ | Acesso à rede Tor |
| Tails OS | https://tails.boum.org/ | SO amnésico para anonimato |
| Whonix | https://www.whonix.org/ | VM isolada com Tor |
| I2P | https://geti2p.net/ | Rede alternativa |
| Freenet / Hyphanet | https://hyphanet.org/ | Rede descentralizada |
| ZeroNet | https://zeronet.io/ | P2P web |
| Lokinet | https://lokinet.org/ | Oxen-based |
| Yggdrasil | https://yggdrasil-network.github.io/ | Mesh IPv6 |

### 11.3 Buscadores da Dark Web

| Buscador | URL Onion | Observação |
|---|---|---|
| Ahmia | https://ahmia.fi/ | Também na surface |
| Torch | (onion) | Antigo e confiável |
| DuckDuckGo Onion | (onion) | Privacidade |
| Not Evil | (onion) | Indexação |
| Haystak | (onion) | Foco em conteúdo |
| OnionLand Search | http://onionlandsearchengine.com/ | Agregador |
| Phobos | http://phoboshryxpxdh4tuieoqpbsgxkjqomoq6qroeqkhjrbdgxqyszh6wqd.onion/ | Cauteloso |
| DarkSearch (legacy) | — | Histórico |
| Kilos | (onion - cauteloso, ligado a mercados) | Não usar sem OPSEC |

> ⚠️ URLs onion são voláteis. Prefira começar pelo Ahmia e Tor Project para recursos atualizados.

### 11.4 Monitoramento e Inteligência na Dark Web

| Ferramenta | URL | Tipo |
|---|---|---|
| IntelligenceX | https://intelx.io/ | Paga — dark + surface |
| DarkTracer | https://darktracer.io/ | Threat intel |
| Flare | https://flare.io/ | Monitoramento contínuo |
| Recorded Future | https://www.recordedfuture.com/ | Comercial |
| Digital Shadows (ReliaQuest) | https://www.reliaquest.com/ | Comercial |
| SOCRadar | https://socradar.io/ | Semi-gratuito |
| DeHashed | https://www.dehashed.com/ | Vazamentos |
| SnusBase | https://snusbase.com/ | Vazamentos |
| Flashpoint | https://flashpoint.io/ | Líder em dark intel |
| Sixgill (Cybersixgill) | https://cybersixgill.com/ | Automação |
| KELA | https://www.kelacyber.com/ | Cibercrime |
| IntSights (Rapid7) | https://www.rapid7.com/ | Threat intel |
| ZeroFox | https://www.zerofox.com/ | External threat |
| CTM360 | https://www.ctm360.com/ | Monitoramento |
| DarkOwl | https://www.darkowl.com/ | Ampla coleção |
| Prodaft | https://www.prodaft.com/ | Criminal intel |
| Group-IB | https://www.group-ib.com/ | CERT + intel |

### 11.5 Fóruns e Marketplaces de Interesse Investigativo

> ⚠️ **AVISO:** O acesso a fóruns de crime é permitido apenas em contexto de investigação legal, com autorização judicial (ou enquadramento em infiltração policial virtual pela Lei 12.850/2013, art. 10-A, e Lei 13.441/2017 para crimes contra criança/adolescente), procedimentos documentados de cadeia de custódia digital e OPSEC rigoroso.

**Tipos de ambientes monitorados:**
- Fóruns de venda de dados (fullz, CC, credenciais) — ex.: XSS, Exploit.in, BreachForums (sucessores)
- Marketplaces de drogas e armas — ex.: sucessores AlphaBay, ASAP, Incognito, Abacus
- Fóruns de hacking e malware — ex.: Nulled, Cracked, Hack Forums (surface + dark)
- Canais de CSAM — **notificação obrigatória às autoridades e NCMEC** via SaferNet (BR)
- Grupos de ransomware e extorsão — Ranzy, LockBit leaks, BlackCat/ALPHV, Clop
- Fraude SIM swap — fóruns em Telegram/Discord

**Frameworks úteis para investigação em fóruns:**
- TOAR (Tor-Onion Asset Rating) — classificação de importância
- MITRE ATT&CK + Diamond Model — caracterizar atores
- ADMT (Actor-Driven Monitoring Triage)

### 11.6 Investigação de Paste Sites

| Ferramenta | URL |
|---|---|
| Pastebin | https://pastebin.com/ |
| PasteBin.pl | https://pastebin.pl/ |
| GitHub Gists | https://gist.github.com/ |
| Riseup Pad | https://pad.riseup.net/ |
| Ghostbin | https://ghostbin.com/ |
| Dork | `site:pastebin.com "dado_alvo"` |
| Psbdmp | https://psbdmp.ws/ |
| Paste.ee | https://paste.ee/ |
| Rentry | https://rentry.co/ |
| Dpaste | https://dpaste.com/ |
| Hastebin | https://www.toptal.com/developers/hastebin |
| ControlC | https://controlc.com/ |
| PrivateBin (self-hosted instances) | Vários | Criptografado |
| 0bin | https://0bin.net/ | Client-side crypt |
| Just Paste It | https://justpaste.it/ | |
| Pastelink | https://pastelink.net/ | |

### 11.7 Buscadores Especializados em Vazamentos

| Ferramenta | URL | Tipo |
|---|---|---|
| IntelX | https://intelx.io/ | Vazamentos + dark |
| Leaked Source (sucessores) | (variados) | Monitorar via intel |
| Leak-Lookup | https://leak-lookup.com/ | Paga |
| WeLeakInfo (sucessores) | (variados) | Monitorar |
| Hudson Rock | https://www.hudsonrock.com/ | Infostealer intel |
| BreachDirectory | https://breachdirectory.org/ | Gratuita |
| SpyCloud | https://spycloud.com/ | Comercial |

### 11.8 Infostealer Logs — ecosystem

Infostealers (RedLine, Raccoon, Vidar, Lumma, StealC, Meduza, etc.) geram logs vendidos/compartilhados em fóruns. Para pesquisa investigativa legítima:

- **Hudson Rock** — fornece consulta de logs para LEA e empresas
- **SpyCloud** — exposição corporativa
- **Flare** — monitoramento
- **KELA** — cenário russo de stealer logs

> ⚠️ **Não baixe dumps brutos de infostealer para "análise".** Isso pode caracterizar receptação de dados. Trabalhe com fornecedores legítimos e com acordos formais.



