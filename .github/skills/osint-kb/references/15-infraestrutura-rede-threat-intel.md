<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 15
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 15. Infraestrutura de Rede, Threat Intelligence e Malware

### 15.1 Plataformas de Threat Intelligence (TI)

| Ferramenta | URL | Função |
|---|---|---|
| VirusTotal | https://www.virustotal.com/ | Multi-engine scanner + grafo |
| AlienVault OTX | https://otx.alienvault.com/ | Comunidade TI (pulses) |
| MISP | https://www.misp-project.org/ | Plataforma TI open-source (auto-hospedável) |
| OpenCTI | https://www.opencti.io/ | TI com STIX 2.1 |
| ThreatConnect | https://threatconnect.com/ | TI enterprise |
| Anomali ThreatStream | https://www.anomali.com/ | TI enterprise |
| Recorded Future | https://www.recordedfuture.com/ | TI + dark web |
| Mandiant Advantage | https://www.mandiant.com/advantage | TI Google |
| CrowdStrike Falcon X | https://www.crowdstrike.com/ | TI + atribuição APT |
| Kaspersky Threat Intelligence Portal | https://opentip.kaspersky.com/ | Lookup gratuito |
| Cisco Talos Intelligence | https://talosintelligence.com/ | Reputação IP/domínio/arquivo |
| IBM X-Force Exchange | https://exchange.xforce.ibmcloud.com/ | TI IBM |
| Microsoft Defender TI | https://ti.defender.microsoft.com/ | ex-RiskIQ PassiveTotal |
| ThreatBook | https://threatbook.io/ | TI asiática |
| QI-ANXIN | https://ti.qianxin.com/ | TI China |
| PulseDive | https://pulsedive.com/ | TI comunitária |
| GreyNoise | https://viz.greynoise.io/ | Scanners/ruído internet |
| SecurityTrails | https://securitytrails.com/ | Histórico domínios/DNS |
| DomainTools Iris | https://www.domaintools.com/ | Investigação domínios premium |
| Team Cymru Pure Signal | https://www.team-cymru.com/ | NetFlow + TI |
| Silent Push | https://www.silentpush.com/ | TI preditiva |
| Validin | https://www.validin.com/ | DNS/IP histórico |
| DNSDumpster | https://dnsdumpster.com/ | Mapeamento gratuito |

### 15.2 Repositórios Públicos de Malware e IoCs

| Ferramenta | URL | Função |
|---|---|---|
| MalwareBazaar (abuse.ch) | https://bazaar.abuse.ch/ | Amostras malware |
| URLhaus (abuse.ch) | https://urlhaus.abuse.ch/ | URLs maliciosas |
| ThreatFox (abuse.ch) | https://threatfox.abuse.ch/ | IoCs |
| Feodo Tracker (abuse.ch) | https://feodotracker.abuse.ch/ | Botnets bancários |
| SSL Blacklist (abuse.ch) | https://sslbl.abuse.ch/ | Certificados maliciosos |
| YARAify (abuse.ch) | https://yaraify.abuse.ch/ | YARA scanning |
| Any.Run | https://app.any.run/ | Sandbox interativa |
| Joe Sandbox | https://www.joesandbox.com/ | Sandbox profissional |
| Hybrid Analysis | https://www.hybrid-analysis.com/ | Sandbox CrowdStrike |
| Intezer Analyze | https://analyze.intezer.com/ | Genética de malware |
| Triage (Hatching) | https://tria.ge/ | Sandbox rápida |
| CAPE Sandbox | https://capev2.hatching.io/ | Open-source |
| Cuckoo Sandbox | https://cuckoosandbox.org/ | Auto-hospedável |
| VX Underground | https://vx-underground.org/ | Biblioteca histórica (uso com cautela) |
| MalShare | https://malshare.com/ | Compartilhamento amostras |
| VirusBay | https://beta.virusbay.io/ | Colaboração IR |
| Open Threat Exchange (OTX) | https://otx.alienvault.com/ | IoCs comunitários |

### 15.3 Análise Estática e Dinâmica

| Ferramenta | Função |
|---|---|
| PEStudio | Análise estática PE |
| Ghidra (NSA) | Engenharia reversa |
| IDA Free/Pro | Disassembler |
| Radare2/Cutter | RE open |
| Binary Ninja | RE comercial |
| x64dbg | Debugger |
| DIE (Detect It Easy) | Detecção packer |
| CAPA (Mandiant) | Capacidades de binários |
| Yara / YaraEditor | Regras de detecção |
| FLOSS (Mandiant) | Extração strings ofuscadas |
| PE-sieve / HollowsHunter | Injeção/hollowing |
| Volatility / MemProcFS | Forense memória |
| Autopsy / Sleuth Kit | Forense disco |
| Plaso / log2timeline | Timelines forenses |

### 15.4 Emulação e Phishing Kit Analysis

| Ferramenta | URL | Função |
|---|---|---|
| urlscan.io | https://urlscan.io/ | Sandbox URL |
| Browserling | https://www.browserling.com/ | Testar URLs com segurança |
| Phish.Report | https://phish.report/ | Takedown + análise |
| Sucuri SiteCheck | https://sitecheck.sucuri.net/ | Malware web |
| Quttera | https://quttera.com/ | Malware sites |
| VirusTotal URL | https://www.virustotal.com/gui/home/url | Multi-engine |
| Gophish | https://getgophish.com/ | Framework phishing (red team) |
| Zphisher / SocialFish | GitHub | Kits (uso apenas em lab autorizado) |
| PhishTool | https://www.phishtool.com/ | Triagem e-mails |
| Phishunt | https://phishunt.io/ | Caça phishing |

### 15.5 Inteligência sobre Vulnerabilidades

| Fonte | URL | Uso |
|---|---|---|
| NVD (NIST) | https://nvd.nist.gov/ | CVEs oficiais |
| MITRE CVE | https://cve.mitre.org/ | Catálogo CVE |
| CISA KEV | https://www.cisa.gov/known-exploited-vulnerabilities-catalog | Exploradas ativamente |
| Exploit-DB | https://www.exploit-db.com/ | PoCs |
| Packet Storm | https://packetstormsecurity.com/ | Exploits e advisories |
| Vulners | https://vulners.com/ | Busca unificada |
| OpenCVE | https://www.opencve.io/ | Monitor CVE |
| VulnCheck | https://vulncheck.com/ | TI vuln comercial |
| Zero Day Initiative | https://www.zerodayinitiative.com/ | Disclosures |
| Rapid7 AttackerKB | https://attackerkb.com/ | Contexto exploit |
| GitHub Advisory DB | https://github.com/advisories | Vulns em deps |
| OSV.dev (Google) | https://osv.dev/ | Vulns open-source |
| CERT.br | https://www.cert.br/ | Alertas BR |
| CTIR Gov (GSI/PR) | https://www.gov.br/ctir/pt-br | Incidentes governo BR |

### 15.6 Honeypots e Coleta de Scanners

| Ferramenta | Função |
|---|---|
| T-Pot (Telekom) | Plataforma honeypot unificada |
| Cowrie | SSH/Telnet honeypot |
| Dionaea | Serviços de rede |
| HoneyDB | API de atacantes |
| SANS ISC DShield | Feeds comunitários |
| GreyNoise Visualizer | Classifica scanners legítimos vs maliciosos |



