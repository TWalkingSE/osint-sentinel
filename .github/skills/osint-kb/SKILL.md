---
name: osint-kb
description: >
  Base de conhecimento OSINT v3.0/2026 — 28 seções temáticas com ferramentas,
  técnicas, URLs oficiais e legislação brasileira aplicável. Consulte ANTES de
  recomendar qualquer ferramenta. Use quando o usuário fornecer um identificador
  (e-mail, telefone, IP, domínio, username, hash, placa, wallet cripto, etc.) ou
  pedir toolkit por categoria. Cada seção é um arquivo independente em
  references/ — carregue apenas o arquivo correspondente ao identificador
  investigado para manter o contexto enxuto.
---

# OSINT Knowledge Base (v3.0/2026)

## Como usar este skill

1. Identifique o **tipo de identificador** ou **categoria** no pedido do usuário
2. Consulte a **tabela de roteamento** abaixo
3. Abra APENAS o arquivo `references/NN-*.md` correspondente
4. Cite ferramentas e URLs estritamente como documentado
5. Se a ferramenta mencionada pelo usuário NÃO estiver no arquivo, responda: *"Não consta na base v3.0/2026 carregada. Posso sugerir alternativas documentadas: [listar 2–3 equivalentes]."*

## Índice de Seções (1:1 com KB v3)

| # | Arquivo | Quando carregar |
|---|---|---|
| 1 | `references/01-email.md` | E-mail, cabeçalho, SPF/DKIM/DMARC, breach check, GHunt, Holehe, Epieos |
| 2 | `references/02-telefone-cpf-cnpj-imei.md` | Telefone BR/intl, CPF, CNPJ, IMEI, PIX reverso, painéis **legítimos** |
| 3 | `references/03-ip.md` | IP, geolocalização, VPN/Tor/proxy, CGNAT + porta lógica, ASN, passive DNS |
| 4 | `references/04-dominio-infraestrutura-web.md` | WHOIS, DNS, subdomínios, certificados, Wayback, Cloudflare bypass, dorking |
| 5 | `references/05-usernames-identidades-digitais.md` | Sherlock, Maigret, WhatsMyName, Blackbird — correlação por handle |
| 6 | `references/06-imagens-videos-imint.md` | Busca reversa, reconhecimento facial, EXIF, manipulação, esteganografia |
| 7 | `references/07-geolocalizacao-geoint.md` | SunCalc, GeoSpy, Picarta, satélite, cronolocalização |
| 8 | `references/08-redes-sociais-socmint.md` | Instagram, Facebook, Twitter/X, TikTok, LinkedIn, Telegram, YouTube, Reddit |
| 9 | `references/09-criptoativos.md` | Blockchain.com, Etherscan, WalletExplorer, MetaSleuth, Arkham, rastreamento on-chain |
| 10 | `references/10-metadados.md` | ExifTool, FOCA, Metagoofil, metadados em PDF/Office |
| 11 | `references/11-dark-web-deep-web.md` | Ahmia, IntelligenceX, DarkTracer, Tor, protocolo de acesso |
| 12 | `references/12-favicons.md` | FaviHunter, Shodan `http.favicon.hash:`, FavFreak, MurmurHash3 |
| 13 | `references/13-veiculos-placas-transporte.md` | Placas, Detran, FlightAware, FlightRadar24, VesselFinder, MarineTraffic |
| 14 | `references/14-documentos-registros-vazamentos.md` | Registros públicos, tribunais, diários oficiais, vazamentos formais |
| 15 | `references/15-infraestrutura-rede-threat-intel.md` | VirusTotal, Any.run, MalwareBazaar, MITRE ATT&CK, IOCs, TTPs |
| 16 | `references/16-patrimonio-bens.md` | Imóveis, veículos, embarcações, aeronaves, cartórios |
| 17 | `references/17-humint-digital.md` | Sockpuppets (Lei 12.850 art. 10-A), elicitação, cautelas OPSEC |
| 18 | `references/18-linux-cli-osint.md` | Kali, Parrot, Tails, Whonix, ferramentas CLI, pipelines |
| 19 | `references/19-opsec.md` | VPN, Tor, VM dedicada, Firefox hardened, VeraCrypt, compartimentação |
| 20 | `references/20-ia-aplicada-osint.md` | LLMs em nuvem vs. locais, Llama, Ollama, riscos de dados em treino |
| 21 | `references/21-scraping-crawling-automacao.md` | Selenium, Puppeteer, Scrapy, respeito a TOS e `robots.txt` |
| 22 | `references/22-analise-visualizacao-dados.md` | Maltego, Neo4j, Obsidian, timeline, grafo de conexões |
| 23 | `references/23-frameworks-metodologias.md` | Ciclo de Inteligência, KB §23.3 template de relatório, dispositivos legais |
| 24 | `references/24-tipologias-cibercrime.md` | Fraudes bancárias, sextortion, phishing, fake news, ransomware, protocolos |
| 25 | `references/25-processo-penal-cadeia-custodia.md` | CPP 158-A a 158-F, admissibilidade, hash, write-blocker |
| 26 | `references/26-ferramentas-dual-use.md` | Ferramentas poderosas que exigem autorização — avisos éticos |
| 27 | `references/27-paineis-clandestinos-persecucao.md` | Investigar operadores de painéis clandestinos (lado da persecução) |
| 28 | `references/28-cooperacao-internacional.md` | Budapeste, MLAT, Interpol, Europol, DRCI, transparency reports |

## Roteamento rápido por identificador

| Identificador | Ir direto para |
|---|---|
| E-mail ou cabeçalho de e-mail | `01-email.md` |
| Número de telefone (BR ou intl) | `02-telefone-cpf-cnpj-imei.md` §2.1 |
| CPF / CNPJ / IMEI | `02-telefone-cpf-cnpj-imei.md` §2.2–2.4 |
| IP público (+ verificar CGNAT) | `03-ip.md` §3.1 e §3.5 |
| Domínio / subdomínio / SSL | `04-dominio-infraestrutura-web.md` |
| Username / handle | `05-usernames-identidades-digitais.md` |
| Imagem / EXIF / deepfake | `06-imagens-videos-imint.md` + `10-metadados.md` |
| Geolocalização por foto | `07-geolocalizacao-geoint.md` |
| Perfil em rede social | `08-redes-sociais-socmint.md` |
| Wallet BTC/ETH/stablecoin | `09-criptoativos.md` |
| URL .onion | `11-dark-web-deep-web.md` |
| Favicon (pivô de infraestrutura) | `12-favicons.md` |
| Placa / voo / embarcação | `13-veiculos-placas-transporte.md` |
| Hash de malware | `15-infraestrutura-rede-threat-intel.md` |

## Regras de uso

- **NUNCA** recomende ferramenta fora destes 28 arquivos.
- **SEMPRE** cite a seção do arquivo (ex: `references/12-favicons.md §12.2`) junto com o nome da ferramenta.
- Para painéis de consulta: use APENAS os listados em `02-telefone-cpf-cnpj-imei.md §2.1.7` (painéis **legítimos** com CNPJ regular). **Nunca** recomende painel clandestino — ver `27-paineis-clandestinos-persecucao.md`.
- Para técnicas 🟡 (§1.5, §2.1.3, §2.1.4, §6.3, §11.5, §17.2, §17.3), exija autorização legal ANTES de orientar.
- Alertas de LGPD, MCI e ECA estão embutidos nos arquivos — reproduza-os ao citar a técnica correspondente.
