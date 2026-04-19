<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 05
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 5. USERNAMES E IDENTIDADES DIGITAIS

### 5.1 Busca por Username na Web

| Ferramenta | URL | Cobertura |
|---|---|---|
| Sherlock | https://github.com/sherlock-project/sherlock | +300 sites |
| WhatsMyName | https://whatsmyname.app/ | Visual + extenso |
| Maigret | https://github.com/soxoj/maigret | +2500 sites |
| Blackbird | https://github.com/p1ngul1n0/blackbird | Rápido |
| SocialScan | https://github.com/iojw/socialscan | E-mail + user |
| Investigo | https://github.com/tdh8316/Investigo | Go lang |
| Pyosint | https://github.com/d8rkmind/Pyosint | Python |
| Social Analyzer | https://github.com/qeeqbox/social-analyzer | Multi-thread |
| UserSearch | https://usersearch.org/ | Web |
| CheckUsernames | https://checkusernames.com/ | Web |
| KnowEm | https://knowem.com/ | Marcas + usuários |
| NameCheckr | https://www.namecheckr.com/ | Web |
| InstantUsername | https://instantusername.com/ | Web |
| Namevine | https://namevine.com/ | Web |
| Social-Searcher | https://www.social-searcher.com/ | Posts públicos |
| Snoop Project | https://github.com/snooppr/snoop | Ex-URSS + global |
| Thorndyke | https://github.com/markusbackstrom/thorndyke | Ruby |
| WhatsMyUsername | https://github.com/WebBreacher/WhatsMyName | Source do whatsmyname |
| NameRec | https://github.com/HA71/Namechk | Enum massivo |
| Profil3r | https://github.com/Rog3rSm1th/Profil3r | OSINT person |
| Recon OS | https://reconos.io/ | Web agregadora |
| UserProbe | https://userprobe.com/ | Web |
| NameCheckup | https://namecheckup.com/ | Web |
| CheckName | https://check-name.com/ | Web |
| Sawek (Checkusername) | https://checkuser.org/ | Web |

### 5.2 Correlação de Identidades

**Técnicas de pivô por username:**
1. Buscar o mesmo username em múltiplas plataformas
2. Analisar bio, foto de perfil e links cruzados
3. Buscar o username entre aspas no Google: `"username_alvo"`
4. Verificar variações: `username_`, `_username`, `username123`
5. Analisar histórico via Wayback Machine
6. Extrair hash de imagem de perfil e reversar em outras redes
7. Comparar estilo de escrita (stylometry) entre contas suspeitas
8. Verificar timestamps de posts (fuso horário do alvo)
9. Analisar padrões de hashtags e amigos em comum

**Google Dorks por username:**
```
"username" site:reddit.com
"username" site:github.com
"username" site:twitter.com
"username" -site:twitter.com -site:instagram.com
inurl:"/username" (plataforma)
"username" site:medium.com
"username" site:dev.to
"username" filetype:pdf
"username" AND ("nome" OR "cidade")
```

### 5.3 Identidades em Fóruns e Comunidades

| Plataforma | Técnica de Busca |
|---|---|
| Reddit | `site:reddit.com "username"` ou reddit.com/user/USERNAME |
| GitHub | `https://github.com/username` + API |
| Stack Overflow | Busca direta no perfil |
| Telegram | Bots: @SangMata_BOT, @TgScanRobot |
| Discord | Servidores de lookup (com cautela legal) |
| 4chan / 8chan / 8kun | Arquivo: https://archived.moe/ |
| Pastebin | `site:pastebin.com "username"` |
| HackForums | Busca interna |
| Dread (dark) | Apenas com OPSEC + autorização |
| Exploit.in | Monitoramento via intel |
| XSS.is | Monitoramento via intel |
| DuckDuckGo Forums | `site:duckduckgo.com "username"` |
| Steam | https://steamcommunity.com/id/USERNAME/ |
| Roblox | Roblox.com/users/ID |
| Xbox Live | https://xboxgamertag.com/ |
| PSN | https://psnprofiles.com/ |
| Epic Games | Fortnite tracker |
| Minecraft | https://namemc.com/ |
| Twitch | https://www.twitch.tv/USERNAME |

### 5.4 Análise de Atividade e Padrões

| Ferramenta | URL | Função |
|---|---|---|
| Tinfoleak | https://github.com/vaguileradiaz/tinfoleak | Padrões de atividade (Twitter) |
| Sleep Tracker (Twitter) | Via Tweetdeck + análise | Fuso horário |
| SocialBearing | https://socialbearing.com/ | Twitter analytics |
| Reddit User Analytics | https://www.redditinvestigator.com/ | Perfil Reddit |
| GitHub Activity | API + graph | Horários de commits |
| InstAnalytics | — | Padrões Instagram |



