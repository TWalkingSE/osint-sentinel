<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 04
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 4. DOMÍNIO E INFRAESTRUTURA WEB

### 4.1 WHOIS e Registro

| Ferramenta | URL | Observação |
|---|---|---|
| Registro.br | https://registro.br/tecnologia/ferramentas/whois/ | Domínios .br |
| ICANN Lookup | https://lookup.icann.org/ | Global |
| Who.is | https://who.is/ | Interface amigável |
| Whois.com | https://www.whois.com/ | Completo |
| DomainTools | https://whois.domaintools.com/ | Histórico + pivô |
| Whoxy | https://www.whoxy.com/ | Reverso por e-mail/nome |
| ReverseWhois | https://www.reversewhois.io/ | Busca por owner |
| Synapsint | https://www.synapsint.com/ | Multipivô |
| Robtex | https://www.robtex.com/ | DNS + IP |
| IANA WHOIS | https://www.iana.org/whois | Autoridade máxima |
| NetworkSolutions | https://www.networksolutions.com/domains/whois | Alternativa |
| Whoisology | https://whoisology.com/ | Banco histórico |
| DotDB | https://dotdb.com/ | Base de domínios |
| CentralOps | https://centralops.net/co/ | Multi-ferramenta |
| Hunter.how | https://hunter.how/ | Busca em código-fonte |
| DomainIQ | https://www.domainiq.com/ | WHOIS + reputação |
| JsonWHOIS | https://jsonwhois.com/ | API |
| WhoisXML | https://www.whoisxmlapi.com/ | API comercial |
| DNSlytics Owner Search | https://dnslytics.com/domain | Enriquecido |
| whois.ds (plataforma) | https://whois.ds/ | Unificado |
| WhoDoesThat | https://whodoesthat.com/ | Reverso por registrant |
| Snov.io Domain Search | https://snov.io/domain-search | E-mails + registrante |

### 4.2 DNS e Registros

| Ferramenta | URL | Função |
|---|---|---|
| DNSDumpster | https://dnsdumpster.com/ | Mapa DNS visual |
| MXToolbox DNS | https://mxtoolbox.com/DnsLookup.aspx | Todos os tipos de registro |
| ViewDNS | https://viewdns.info/ | Multi-consulta |
| SecurityTrails | https://securitytrails.com/ | DNS histórico |
| PassiveDNS (CIRCL) | https://www.circl.lu/services/passive-dns/ | Passivo |
| HackerTarget DNS | https://hackertarget.com/dns-lookup/ | Gratuito |
| DNSTwist | https://dnstwist.it/ | Domínios semelhantes (phishing) |
| DNSHistory | https://dnshistory.org/ | Histórico DNS |
| CompleteDNS | https://completedns.com/dns-history/ | Histórico de mudanças |
| DNSGrep (Rapid7) | https://scans.io/ | Dump de resoluções |
| intoDNS | https://intodns.com/ | Auditoria DNS |
| Google Public DNS | https://dns.google/ | Resolver |
| Cloudflare 1.1.1.1 Debug | https://1.1.1.1/help | Debug rápido |
| NSLookup.io | https://www.nslookup.io/ | Interface moderna |
| DNSChecker | https://dnschecker.org/ | Propagação global |
| Linux: `dig` | Linha de comando | Consulta nativa |
| Linux: `nslookup` | Linha de comando | Consulta interativa |
| Linux: `host` | Linha de comando | Simplificado |
| Linux: `dnsx` | https://github.com/projectdiscovery/dnsx | Toolkit avançado |

### 4.3 Hospedagem e Servidor

| Ferramenta | URL |
|---|---|
| HostingChecker | https://hostingchecker.com/ |
| WhoHostsThis | https://www.who-hosts-this.com/ |
| Digital.com | https://digital.com/who-is-hosting-this/ |
| Synapsint | https://www.synapsint.com/ |
| AdminKit | https://adminkit.net/traceroute.aspx |
| HostAdvice Host Detector | https://hostadvice.com/tools/web-host-lookup/ |
| Netcraft SiteReport | https://sitereport.netcraft.com/ |
| IsItWP Hosting Checker | https://www.isitwp.com/whos-hosting/ |

### 4.4 Tecnologias e Código-Fonte

| Ferramenta | URL | Função |
|---|---|---|
| BuiltWith | https://builtwith.com/ | Stack tecnológico |
| Wappalyzer | https://www.wappalyzer.com/ | Plugin + site |
| WhatCMS | https://whatcms.org/ | CMS identificador |
| PublicWWW | https://publicwww.com/ | Busca em código-fonte |
| Hunter.how | https://hunter.how/ | Indexação de código |
| Shodan | https://www.shodan.io/ | Cabeçalhos HTTP |
| WebTech | https://github.com/ShielderSec/webtech | Alternativa ao Wappalyzer |
| Whatruns | https://www.whatruns.com/ | Extensão + site |
| Retire.js | https://retirejs.github.io/retire.js/ | JavaScript vulnerável |
| Netcraft | https://toolbar.netcraft.com/ | Reputação + tech |
| NerdyData | https://www.nerdydata.com/ | Busca em código em massa |
| Full Hunt | https://fullhunt.io/ | Attack surface |
| CRT Search Code | https://crt.sh/ | Certificados como pivô |

**Identificadores no código-fonte:**

| Identificador | Prefixo | Uso |
|---|---|---|
| Google Analytics | `UA-`, `G-` | Pivô entre sites |
| Google AdSense | `pub-` | Proprietário do site |
| Google Tag Manager | `GTM-` | Rastreamento |
| Facebook Pixel | `fbq('init', '` | ID do anunciante |
| Yandex Metrica | `ym(` | Proprietário |
| Microsoft Clarity | `clarity.ms` | ID de projeto |
| Hotjar | `hjid` | ID da conta |
| Mixpanel | `mixpanel.init(` | Token |
| Matomo/Piwik | `matomo.js` | Servidor próprio |
| Adobe Analytics | `s_account` | Report suite |
| Disqus | `disqus_shortname` | Conta Disqus |
| PayPal Button | `hosted_button_id` | Conta PayPal |
| Stripe | `pk_live_`, `pk_test_` | Chave pública |
| Segment | `analytics.load(` | Write key |
| reCAPTCHA | `data-sitekey` | Chave do site |
| Cloudflare Turnstile | `sitekey` | ID |
| Intercom | `app_id` | Conta Intercom |

### 4.5 Histórico e Cache

| Ferramenta | URL |
|---|---|
| Wayback Machine | https://archive.org/ |
| Archive.today | https://archive.ph/ |
| CachedView | https://cachedview.com/ |
| CachedPage | https://cachedpage.co/ |
| Google Cache | `cache:url` no Google |
| Timetravel | https://timetravel.mementoweb.org/ |
| Wayback Machine API | https://archive.org/help/wayback_api.php |
| UK Web Archive | https://www.webarchive.org.uk/ |
| Perma.cc (Harvard) | https://perma.cc/ | Preservação legal |
| Conifer (ex-Webrecorder) | https://conifer.rhizome.org/ |
| PageFreezer | https://www.pagefreezer.com/ | Preservação jurídica |
| Screenshots.com | https://www.screenshots.com/ |
| ArchiveBox | https://archivebox.io/ | Self-hosted |

### 4.6 Verificação de Segurança e Phishing

| Ferramenta | URL |
|---|---|
| VirusTotal | https://www.virustotal.com/ |
| URLScan | https://urlscan.io/ |
| DNSTwist | https://dnstwist.it/ |
| PhishTank | https://phishtank.org/ |
| SiteConfiável | https://www.siteconfiavel.com.br/ |
| AbuseIPDB | https://www.abuseipdb.com/ |
| Google SafeBrowsing | https://safebrowsing.google.com/safebrowsing/report_phish/ |
| Sucuri SiteCheck | https://sitecheck.sucuri.net/ |
| IsItPhishing | https://isitphishing.ai/ |
| PhishStats | https://phishstats.info/ |
| OpenPhish | https://openphish.com/ |
| URLhaus | https://urlhaus.abuse.ch/ |
| Joe Sandbox URL | https://www.joesandbox.com/ |
| AnyRun (URL) | https://any.run/ |
| Hybrid Analysis URL | https://www.hybrid-analysis.com/ |
| Kaspersky Threat Intel Portal | https://opentip.kaspersky.com/ |
| Talos Intelligence | https://talosintelligence.com/ |
| Quttera | https://www.quttera.com/ |
| Netcraft Takedown | https://www.netcraft.com/ |
| SafeBrowsing Lookup API | Google API | Integração |
| Bitdefender TrafficLight | https://trafficlight.bitdefender.com/ |
| CheckPhish.ai | https://checkphish.ai/ |

### 4.7 Cloudflare e Bypass (técnicas legítimas de descoberta de origem)

| Ferramenta | URL | Técnica |
|---|---|---|
| CloudFlare IP Range | https://www.cloudflare.com/pt-br/ips/ | Lista de IPs CF |
| SecurityTrails | https://securitytrails.com/ | Histórico DNS antes do CF |
| Shodan | `ssl.cert.subject.cn:dominio.com` | Certificado TLS |
| CrimeFlare (legacy) | — | Bypass CF (histórico) |
| ViewDNS History | https://viewdns.info/iphistory/ | IP histórico |
| SUIP | https://suip.biz/?act=iscloudflare | Detecta CF |
| CloudFail | https://github.com/m0rtem/CloudFail | Automação |
| CloudUnflare | https://github.com/jaynakrani/cloudunflare | Subdominio discovery |
| Censys Cert Search | https://search.censys.io/ | Por CN/SAN |
| CrimeScan | https://www.criminalip.io/ | Attack surface |
| DNSdb (Farsight) | — | Passive histórico |

> ⚠️ **Nota:** Bypass de WAF/proxy é legítimo em investigações para **identificar o servidor de origem** de serviços criminosos (phishing, carding, CSAM). Não confundir com "bypass de proteção" de sites legítimos (isso violaria termos de serviço e pode configurar invasão).

### 4.8 Certificados SSL/TLS

| Ferramenta | URL |
|---|---|
| crt.sh | https://crt.sh/ |
| Censys | https://search.censys.io/ |
| SSLLabs | https://www.ssllabs.com/ssltest/ |
| Cert Spotter | https://sslmate.com/certspotter/ |
| Censys Certs | https://search.censys.io/certificates |
| Google CT Log | https://crt.sh/?q=&caid= |
| CertStream (live) | https://certstream.calidog.io/ |
| Facebook CT Monitor | https://developers.facebook.com/tools/ct/ |
| CertDB | https://certdb.com/ |
| Merklemap | https://www.merklemap.com/ |
| Entrust CT Search | https://ui.ctsearch.entrust.com/ |

### 4.9 Subdomínios — Descoberta

| Ferramenta | URL | Tipo |
|---|---|---|
| Subfinder | https://github.com/projectdiscovery/subfinder | CLI |
| Amass | https://github.com/owasp-amass/amass | CLI completo |
| assetfinder | https://github.com/tomnomnom/assetfinder | CLI rápido |
| chaos-client | https://github.com/projectdiscovery/chaos-client | ProjectDiscovery |
| crt.sh (dork) | `%.dominio.com` | Web |
| HackerTarget | https://hackertarget.com/find-dns-host-records/ | Web |
| Certspotter | https://sslmate.com/certspotter/api | API |
| VirusTotal Subdomains | https://www.virustotal.com/ | Domain relations |
| SecurityTrails | https://securitytrails.com/ | Comercial |
| Shodan | `hostname:dominio.com` | Paga |
| GitHub Dork | `"dominio.com"` in repos | Manual |
| DNS Brute-force | wordlists + dnsx | CLI |
| FindSubdomains | https://findsubdomains.com/ | Web |
| Sublist3r | https://github.com/aboul3la/Sublist3r | CLI Python |

### 4.10 Google Dorks para Domínios

```
site:dominio.com                    # Tudo indexado
site:dominio.com filetype:pdf       # PDFs expostos
site:dominio.com inurl:admin        # Painéis admin
site:dominio.com intext:"password"  # Senhas expostas
site:dominio.com ext:sql            # Bancos de dados
inurl:dominio.com intitle:index.of  # Directory listing
link:dominio.com                    # Backlinks
"UA-XXXXXXXX" -site:dominio.com     # Outros sites com mesmo Analytics
site:dominio.com inurl:wp-content   # WordPress
site:dominio.com inurl:"/.git"      # Git exposto
site:dominio.com intitle:"phpinfo()" # Info PHP
site:dominio.com intitle:"swagger"  # API docs
site:dominio.com intitle:"Login" OR intitle:"Sign In" # Páginas auth
site:dominio.com ext:env OR ext:log OR ext:bak # Arquivos sensíveis
```

---


