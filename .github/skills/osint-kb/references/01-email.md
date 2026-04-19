<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 01
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 1. E-MAIL

### 1.1 Estrutura e Análise de Cabeçalho

**Campos críticos do cabeçalho de e-mail:**

| Campo | Função Investigativa |
|---|---|
| `Received` | Rota do e-mail; o registro mais antigo contém o IP de origem |
| `From` | Pode ser falsificado (spoofing) |
| `Return-Path` | Geralmente revela o verdadeiro remetente |
| `Reply-To` | Se diferente do `From`, possível indicador de engano |
| `Message-ID` | Identificador único gerado pelo servidor de origem |
| `Authentication-Results` | Resultado de SPF, DKIM e DMARC |
| `X-Originating-IP` | IP direto do remetente (nem sempre presente) |
| `X-Mailer` | Client de e-mail utilizado |
| `MIME-Version` | Versão do protocolo; útil em análise forense |
| `Sender` | Responsável pelo envio quando diferente do `From` |
| `ARC-Seal` / `ARC-Message-Signature` | Autenticidade da cadeia de encaminhamento |
| `BIMI-Location` | URL do logotipo BIMI — identifica domínio legítimo |
| `DKIM-Signature` | Assinatura criptográfica do domínio |
| `List-Unsubscribe` | Revela infraestrutura de mass-mail |
| `X-Spam-Score` / `X-Spam-Status` | Pontuação anti-spam |
| `Thread-Topic` / `Thread-Index` | Agrupamento de conversas (Outlook/Exchange) |
| `X-Microsoft-Antispam-Mailbox-Delivery` | Roteamento Microsoft 365 |
| `X-MS-Exchange-Organization-*` | Dados organizacionais Exchange |
| `X-Google-Smtp-Source` | Origem em infraestrutura Google |
| `X-Forwarded-For` / `X-Forwarded-Host` | Cadeia de proxies |

**Técnica para extração de IP:**
1. Copie o cabeçalho completo (opção "Ver original" ou "Show original")
2. Cole em uma das ferramentas de análise abaixo
3. Localize o campo `Received: from` mais antigo (mais abaixo na lista)
4. Extraia o IP entre colchetes `[xxx.xxx.xxx.xxx]`
5. Consulte o IP nas ferramentas de geolocalização e WHOIS
6. Correlacione com timestamp e SPF/DKIM para confirmar autenticidade

### 1.2 Ferramentas de Análise de Cabeçalho

| Ferramenta | URL | Observação |
|---|---|---|
| MXToolbox | https://mxtoolbox.com/EmailHeaders.aspx | Análise visual completa |
| Google Apps Toolbox | https://toolbox.googleapps.com/apps/messageheader/ | Oficial do Google |
| Mail Header Analyzer | https://mailheader.org/ | Interface simples |
| WhatIsMyIPAddress | https://whatismyipaddress.com/trace-email | Trace de e-mail |
| Trustifi | https://trustifi.com/email-analyzer/ | Análise avançada |
| DNSChecker | https://dnschecker.org/email-header-analyzer.php | Multi-função |
| Azure Email Header Analyzer | https://mha.azurewebsites.net/ | Desenvolvido pela Microsoft |
| EmailHeader.net | https://emailheader.net/ | Alternativa simples |
| IP2Location Header Analyzer | https://www.ip2location.com/free/email-header-analyzer | Com geo integrado |
| Mailtrap Header Analyzer | https://mailtrap.io/blog/email-header-analyzer/ | Gratuito |
| GoDaddy Email Header Tool | https://www.godaddy.com/help/investigate-an-email-header-2064 | Básico |
| SPF Surveyor (dmarcian) | https://dmarcian.com/spf-survey/ | Auditoria de SPF |
| DKIM Validator | https://dkimvalidator.com/ | Validação de assinatura |

### 1.3 Verificação e Validação de E-mail

| Ferramenta | URL | Tipo |
|---|---|---|
| EmailHippo | https://tools.emailhippo.com/ | Valida se e-mail existe |
| EmailRep | https://emailrep.io/ | Reputação + histórico |
| Hunter.io Verifier | https://hunter.io/email-verifier | Valida endereço |
| Email-Checker | https://email-checker.net/ | Verificação simples |
| Defastra | https://defastra.com/ | Risco + análise |
| NeverBounce | https://neverbounce.com/ | Verificação em bulk |
| MailboxValidator | https://www.mailboxvalidator.com/ | API disponível |
| Skymem | https://www.skymem.info/ | Busca indexada |
| Verifalia | https://verifalia.com/ | Verificação profissional |
| Abstract API | https://www.abstractapi.com/email-validation | API REST |
| ZeroBounce | https://www.zerobounce.net/ | Enriquecimento de dados |
| Kickbox | https://kickbox.com/ | Validação em tempo real |
| Bouncer | https://www.usebouncer.com/ | Anti-fraude de e-mail |
| Clearout | https://clearout.io/ | API + dashboard |
| Snov.io Email Verifier | https://snov.io/email-verifier | Gratuita até 50/dia |
| Prowl | https://prowl.lupovis.io/ | Análise de reputação |
| Truemail | https://truemail.io/ | Validação múltipla |
| Proofy | https://proofy.io/ | Bulk checker |

### 1.4 Pesquisa por E-mail (OSINT)

| Ferramenta | URL | Tipo |
|---|---|---|
| Epieos | https://epieos.com/ | Gratuita — cruza dados |
| OSINT Industries | https://osint.industries/ | Paga (gov. gratuito) |
| Spokeo | https://www.spokeo.com/ | Paga |
| Huntter.is | https://www.huntter.is/ | Paga |
| IntelligenceX | https://intelx.io/ | Paga — dark web incluso |
| Holehe (Linux) | https://github.com/megadose/holehe | Checa cadastros em +120 sites |
| SocialScan (Linux) | https://github.com/iojw/socialscan | E-mail + username |
| GHunt (Linux) | https://github.com/mxrch/GHunt | OSINT em contas Google |
| H8mail (Linux) | https://github.com/khast3x/h8mail | Cruza com breaches |
| Infoga (Linux) | https://github.com/The404Hacking/Infoga | Coleta info de e-mails |
| theHarvester | https://github.com/laramies/theHarvester | Coleta e-mails de domínios |
| EmailFinder | https://github.com/Josue87/EmailFinder | Enumeração de e-mails |
| MOSINT | https://github.com/alpkeskin/mosint | Automated email OSINT |
| ReverseMX | https://reversemx.io/ | MX reverso por e-mail |
| Castrick Clues | https://castrickclues.com/ | OSINT agregador |
| Email2PhoneNumber | https://github.com/martinvigo/email2phonenumber | Tenta recuperar fone |
| ScyllaHide (scylla.sh) | https://scylla.sh/ | Busca em breaches |
| AnyWho | https://www.anywho.com/ | Pesquisa reversa (EUA) |
| That'sThem Email | https://thatsthem.com/reverse-email-lookup | Gratuita (EUA) |
| Skymem Domain Search | https://www.skymem.info/ | E-mails por domínio |

### 1.5 Verificação de Vínculos com Plataformas

**Técnica: Simulação de PIX**
Ao cadastrar o e-mail como chave PIX em um banco digital, o sistema pode revelar o nome associado ao titular. Procedimento com autorização legal.

**Técnica: Recuperação de senha**
Ao inserir o e-mail na opção "Esqueci minha senha" de plataformas como Google, Apple, Microsoft, LinkedIn — o sistema mascara o número de telefone vinculado, revelando dígitos parciais. Ideal para triangulação com outros fragmentos.

**Técnica: Página do Facebook**
Criar uma página no Facebook e adicionar o e-mail como administrador — se o Facebook reconhecer o endereço, pode revelar o perfil vinculado.

**Técnica: Apple ID**
Em appleid.apple.com, a tentativa de login com um e-mail informa se há conta Apple associada.

**Técnica: Outlook/Microsoft Account**
O mesmo vale para login.live.com — também revela se o e-mail é uma conta Microsoft.

**Técnica: Adobe Creative Cloud**
O login em adobe.com revela se o e-mail tem conta Adobe (útil para investigações envolvendo profissionais gráficos).

**Técnica: Netflix/Spotify/Outros**
Páginas de login de grandes plataformas revelam (ou mascaram) dados úteis em recuperação de senha.

> ⚠️ **Atenção:** Essas técnicas devem ser registradas como diligência investigativa, documentadas com print e hash, e realizadas em ambiente OPSEC segregado. Não gerar interação ativa com o alvo (não clicar em recuperação de senha se gerar e-mail/SMS para o alvo).

### 1.6 Verificação de Vazamentos

| Ferramenta | URL | Tipo |
|---|---|---|
| HaveIBeenPwned | https://haveibeenpwned.com/ | Gratuita |
| Firefox Monitor | https://monitor.firefox.com/ | Gratuita |
| DeHashed | https://www.dehashed.com/ | Paga |
| IntelX | https://intelx.io/ | Paga |
| Breach Directory | https://breachdirectory.org/ | Semi-gratuita |
| AmIBreached | https://amibreached.com/ | Gratuita |
| Leak-Lookup | https://leak-lookup.com/ | Paga |
| LeakIX | https://leakix.net/ | Foco em servidores expostos |
| SnusBase | https://snusbase.com/ | Paga |
| Proxynova | https://www.proxynova.com/tools/comb | Combo lists |
| Scylla.sh | https://scylla.sh/ | Gratuita — grandes breaches |
| LeakPeek | https://leakpeek.com/ | Paga |
| BreachForums Alternatives | (variados) | Monitorar via intel — não acessar sem autorização |
| RaidForums Archive | (variados) | Arquivo histórico |
| LeakBase | https://leakbase.cc/ | Paga |
| Inoitsu | https://www.inoitsu.com/ | Breach risk scoring |
| XposedOrNot | https://xposedornot.com/ | Gratuita |
| PSBDMP (pastes) | https://psbdmp.ws/ | Arquivo de pastes vazados |
| WeLeakInfo (sucessores) | (variados) | Monitorar via intel formal |
| Leaked.zone | https://leaked.zone/ | Paga |

> ⚠️ **Para agentes públicos:** Sempre prefira HaveIBeenPwned, IntelX com conta institucional e DeHashed com conta corporativa. **Nunca** faça download de combolists de fóruns clandestinos para "uso investigativo" — isso caracteriza receptação de dados (art. 180 CP) e violação de LGPD. Dados de breach podem ser requisitados formalmente via MLAT ou via acordo com provedores internacionais.

### 1.7 Domínio e WHOIS por E-mail

| Ferramenta | URL | Função |
|---|---|---|
| Whoxy | https://www.whoxy.com/ | WHOIS reverso por e-mail |
| DomainTools | https://whois.domaintools.com/ | Histórico + owner |
| Registros associados | https://viewdns.info/reversewhois/ | Domínios pelo e-mail |
| WhoisXML Reverse | https://reverse-whois.whoisxmlapi.com/ | API + web |
| Whoisology | https://whoisology.com/ | Banco histórico |
| DNSlytics Reverse | https://dnslytics.com/reverse-whois | Paga |

### 1.8 E-mail em Plataformas Específicas

| Plataforma | Técnica | Link |
|---|---|---|
| Skype | Busca por e-mail | https://www.vedbex.com/email2skype |
| Google Account | GHunt | https://github.com/mxrch/GHunt |
| Apple ID | Tentativa de login parcial | https://iforgot.apple.com/ |
| Gravatar | Avatar universal | https://en.gravatar.com/site/check/ |
| Pastebin | Dork: `site:pastebin.com "email@dominio.com"` | — |
| GitHub | Dork: `"email@dominio.com" in:file` | GitHub Search |
| Telegram | WhatAPI (não oficial) | Via bots de lookup — com cautela |
| Discord | Discord.id | https://discord.id/ |
| Steam | SteamID Finder | https://steamid.io/ |
| Slack Enum | `email_check` na API de times públicos | Limitado |

### 1.9 Ferramentas Avançadas (Pagas)

| Ferramenta | URL | Observação |
|---|---|---|
| Lampyre | https://lampyre.io/ | OSINT visual + timeline |
| Maltego + Social Links | https://www.maltego.com/ | Grafo de conexões |
| Pipl | https://pipl.com/ | Busca por pessoa |
| SpiderFoot | https://github.com/smicallef/spiderfoot | Open-source, automação |
| Recon-ng | https://github.com/lanmaster53/recon-ng | Framework modular |
| OSINT Industries | https://osint.industries/ | Extensa cobertura |
| IRBIS (Social Links) | https://irbis.espysys.com/ | Plataforma profissional |
| Skopenow | https://www.skopenow.com/ | Investigações comerciais |
| Babel X | https://www.babelstreet.com/ | Análise multilíngue |
| Cobwebs | https://cobwebs.com/ | WEBINT |
| Voyager Labs | https://voyagerlabs.co/ | Análise social |



