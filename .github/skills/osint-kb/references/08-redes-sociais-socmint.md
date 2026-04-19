<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 08
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 8. REDES SOCIAIS (SOCMINT)

### 8.1 Instagram

| Ferramenta | URL | Função |
|---|---|---|
| Instaloader | https://github.com/instaloader/instaloader | Download completo do perfil |
| OSINTgram | https://github.com/Datalux/Osintgram | Dados de perfil |
| Toutatis | https://github.com/megadose/toutatis | Dados avançados |
| IntelTechniques IG | https://inteltechniques.com/tools/Instagram.html | Ferramentas integradas |
| Picuki | https://www.picuki.com/ | Visualização sem conta |
| InstaNavigation | https://instanavigation.com/ | Espelho |
| Dumpoir | https://dumpoir.com/ | Espelho |
| StoriesIG | https://storiesig.info/ | Stories sem conta |
| CommentPicker | https://commentpicker.com/ | Extração de comentários |
| NotJustAnalytics | https://www.notjustanalytics.com/ | Análise de perfil |
| Mulkom (IG profile pic HD) | https://www.mulkom.com/ | Foto HD |
| InstaGramDirect | https://codeofaninja.com/tools/find-instagram-user-id/ | ID do usuário |
| ImgInn | https://imginn.com/ | Espelho |
| Pixwox | https://pixwox.com/ | Espelho |
| GramSpy | https://gramspy.com/ | Analytics |
| Inflact | https://inflact.com/ | Analytics + scraper |
| Hypeauditor | https://hypeauditor.com/ | Influencer intel |

**Técnicas Instagram:**
- ID do usuário: `instagram.com/USUARIO/?__a=1&__d=1` (mutável pela plataforma)
- Foto de perfil HD: buscar `profile_pic_url_hd` no JSON
- Dorks: `site:instagram.com "@username"`
- Verificar "followers" e "following" como pivô para rede social
- Tags em posts revelam padrões de localização e círculo social

### 8.2 Facebook

| Ferramenta | URL | Função |
|---|---|---|
| IntelTechniques FB | https://inteltechniques.com/tools/Facebook.html | Toolkit completa |
| IntelX FB | https://intelx.io/tools?tab=facebook | Ferramentas |
| WhoPostedWhat | https://whopostedwhat.com/ | Busca por data |
| OSINT Combine FB | https://www.osintcombine.com/facebook-search-tools | Busca avançada |
| Lookup-ID | https://lookup-id.com/ | ID de perfil |
| FindIDFB | https://findidfb.com/ | ID de perfil |
| ExportComments | https://exportcomments.com/ | Exporta comentários |
| Social-Searcher | https://www.social-searcher.com/ | Posts públicos |
| CyberChef | https://gchq.github.io/CyberChef/ | Converte UNIX timestamp |
| EpochConverter | https://www.epochconverter.com/ | Timestamp |
| ESUIT Chrome | Plugin Chrome | Extrai ID automaticamente |
| Instant Data Scraper | Plugin Chrome | Scraping de listas |
| StalkFace | https://stalkface.com/en/ | Fotos públicas |
| Graph.tips | (arquivo histórico) | Graph Search legacy |
| FB-Search | https://www.facebook.com/search/top/?q= | Busca nativa |
| FB Pages Dir | https://www.facebook.com/directory/pages/ | Páginas públicas |

**Técnicas Facebook:**
- ID no código-fonte: `userID`, `page_id`, `group_id`
- Data de criação: campo `creation_time` (formato UNIX)
- Marketplace: `facebook.com/marketplace/profile/ID`
- Técnica de página: adicionar e-mail como administrador
- Álbum de fotos: `facebook.com/USUARIO/photos`
- Check-ins históricos: `places_visited` (se público)

### 8.3 Twitter / X

| Ferramenta | URL | Função |
|---|---|---|
| TweetDeck (X Pro) | https://pro.twitter.com/ | Monitoramento |
| Twint | https://github.com/twintproject/twint | Scraping sem API (legacy) |
| Tinfoleak | https://github.com/vaguileradiaz/tinfoleak | Análise de metadados |
| Twitonomy | https://www.twitonomy.com/ | Analytics |
| Foller.me | https://foller.me/ | Report do perfil |
| AllMyTweets | https://www.allmytweets.net/ | Todos os tweets |
| TweetBeaver | https://tweetbeaver.com/ | Ferramentas variadas |
| Spoonbill | https://spoonbill.io/ | Monitora mudanças no perfil |
| TrendsMap | https://www.trendsmap.com/ | Trends por localização |
| Twiangulate | https://twiangulate.com/ | Análise de conexões |
| TweeterID | https://tweeterid.com/ | Username → ID |
| Followerwonk | https://followerwonk.com/ | Análise de seguidores |
| Nitter | https://nitter.net/ | Espelho sem rastreamento |
| IntelTechniques TW | https://inteltechniques.com/tools/Twitter.html | Toolkit |
| Social Bearing | https://socialbearing.com/ | Monitoramento |
| Tweepy (Python) | https://www.tweepy.org/ | API client |
| Hoaxy | https://hoaxy.osome.iu.edu/ | Disinfo spread |
| Botometer | https://botometer.osome.iu.edu/ | Bot detection |
| Twitter Archiver | https://archiver.digitalinspiration.com/ | Sheets + Twitter |
| Advanced Search X | https://twitter.com/search-advanced | Nativo |
| X (Grok) search | https://x.com/ | API oficial (paga agora) |

**Twitter Dorks avançados:**
```
from:usuario                      # Tweets do usuário
to:usuario                        # Tweets para o usuário
since:2020-01-01 until:2023-01-01 "termo"
geocode:LAT,LON,RAIOkm "termo"
filter:images                     # Só imagens
filter:videos                     # Só vídeos
min_retweets:100                  # Muito compartilhado
url:dominio.com                   # Links para domínio
-filter:replies                   # Excluir respostas
filter:links                      # Com links
lang:pt                           # Idioma português
filter:verified                   # Usuários verificados
```

### 8.4 TikTok

| Ferramenta | URL | Função |
|---|---|---|
| OSINT Combine TikTok | https://www.osintcombine.com/tiktok-quick-search | Busca rápida |
| UrleBird | https://urlebird.com/ | Visualização de perfis |
| SnapTik | https://snaptik.app/ | Download de vídeos |
| TikTok Hashtags | https://tiktokhashtags.com/ | Hashtags similares |
| InfluenceGrid | https://influencegrid.com/ | Busca de usuários |
| Search4Faces TikTok | https://search4faces.com/tt00/ | Busca facial |
| CommentPicker TikTok | https://commentpicker.com/tiktok-id.php | ID do usuário |
| ExportComments | https://exportcomments.com/ | Exporta comentários |
| TTDown | https://ttdown.org/ | Download de vídeos |
| TikTok Analytics | https://tiktokanalytics.io/ | Analytics |
| CountTik | https://counttik.com/ | Métricas de conta |
| TokAudit | https://tokaudit.io/ | Auditoria de perfil |
| SaveTik | https://ssstik.io/ | Download sem watermark |
| Pentaclay | https://pentaclay.com/tiktok-downloader | Multi-função |

### 8.5 LinkedIn

| Ferramenta | URL | Função |
|---|---|---|
| LinkedIn Sales Navigator | Pago | Busca avançada |
| IntelTechniques LinkedIn | https://inteltechniques.com/tools/LinkedIn.html | Ferramentas |
| theHarvester | https://github.com/laramies/theHarvester | E-mails de empresa |
| LinkedInt | https://github.com/vysec/LinkedInt | OSINT em LinkedIn |
| CrossLinked | https://github.com/m8sec/CrossLinked | Enumeração de funcionários |
| Dork | `site:linkedin.com "empresa" "cargo"` | Busca de funcionários |
| InspyLinked | https://github.com/leapsecurity/InSpy | Enumeração |
| Hunter.io Company | https://hunter.io/search/ | E-mails + cargo |
| Rocketreach | https://rocketreach.co/ | Enriquecimento |
| Lusha | https://www.lusha.com/ | Contatos B2B |
| Apollo.io | https://www.apollo.io/ | Base B2B extensa |
| Kaspr | https://www.kaspr.io/ | Extração contatos |
| Phantombuster | https://phantombuster.com/ | Automação LinkedIn |
| LeadLeaper | https://www.leadleaper.com/ | Extrator |
| SignalHire | https://www.signalhire.com/ | B2B |
| Whoisme (plataforma) | https://whoisme.com/ | LinkedIn scraping |

### 8.6 Telegram

| Bot / Ferramenta | Link | Função |
|---|---|---|
| CreationDateBot | https://t.me/creationdatebot | Data de criação da conta |
| RegDateBot | https://t.me/RegDateBot | Data de registro |
| UserinfoBot | https://t.me/userinfobot | ID pelo username |
| GetMyID Bot | https://t.me/getmyid_bot | Seu próprio ID |
| SangMata BOT | https://t.me/SangMata_BOT | Histórico de usernames |
| TgScanRobot | https://t.me/TgScanRobot | Grupos de um usuário |
| ChatSearchRobot | https://t.me/ChatSearchRobot | Grupos similares |
| TGStat | https://tgstat.ru/ | Ranking e análise de canais |
| Telemetr | https://telemetr.io/ | Análise de canais |
| TDirectory | https://tdirectory.me/ | Diretório de grupos |
| XTEA | https://xtea.io/ | Busca no Telegram |
| Telegram Analytics (TGStat) | https://tgstat.com/ | Global |
| Lyzem | https://lyzem.com/ | Busca em mensagens |
| Telepathy | https://github.com/proseltd/telepathy | OSINT CLI |
| Telegago (Google CSE) | https://cse.google.com/cse?cx=006368593537057042503:efxu7xprihg | Dork para grupos |
| TeleSearch | https://en.telesear.ch/ | Busca agregadora |
| TGdev | https://tgdev.io/ | Analytics de canais |
| Telesco.pe (legacy) | — | Histórico |

### 8.7 YouTube

| Ferramenta | URL | Função |
|---|---|---|
| Comment Picker | https://commentpicker.com/ | Extrai comentários |
| YouTube Metadata | https://mattw.io/youtube-metadata/ | Metadados de vídeo |
| YouTube GeoFind | https://youtube.github.io/geo-search-tool/ | Busca geolocalizada |
| Amnesty YT DataViewer | https://citizenevidence.amnestyusa.org/ | Verificação de vídeo |
| IntelTechniques YT | https://inteltechniques.com/tools/YouTube.html | Toolkit |
| Dork | `site:youtube.com "canal" "palavra"` | Busca indexada |
| YouTube DL / yt-dlp | https://github.com/yt-dlp/yt-dlp | Download |
| VidIQ | https://vidiq.com/ | Analytics |
| Social Blade | https://socialblade.com/ | Stats histórico |
| Channel Crawler | https://www.channelcrawler.com/ | Busca de canais |
| Filmot | https://filmot.com/ | Busca em legendas |
| YouChat (CC search) | https://ccsubs.com/ | Legendas |
| NoxInfluencer | https://www.noxinfluencer.com/ | Influencer intel |

### 8.8 Reddit

| Ferramenta | URL | Função |
|---|---|---|
| Pushshift | https://pushshift.io/ | Histórico de posts (limitado) |
| RedditSearch | https://redditsearch.io/ | Busca avançada |
| Camas Reddit | https://camas.unddit.com/ | Posts deletados |
| KarmaDecay | http://karmadecay.com/ | Busca reversa de imagem |
| SnoopSnoo | https://snoopsnoo.com/ | Análise de usuário |
| Mostly Harmless | https://kerrick.github.io/Mostly-Harmless/ | Histórico |
| Subreddit Stats | https://subredditstats.com/ | Estatísticas |
| Revddit | https://www.revddit.com/ | Posts removidos |
| Unddit / Removeddit | https://www.unddit.com/ | Content removido |
| RedditMetis | https://redditmetis.com/ | Análise de usuário |
| Reddit Investigator | https://www.redditinvestigator.com/ | Perfil completo |
| Pullpush | https://pullpush.io/ | Sucessor Pushshift |
| Old.reddit Search | https://old.reddit.com/search | Interface antiga |

### 8.9 Redes Alternativas / Emergentes 🆕

| Rede | Ferramentas / Técnicas |
|---|---|
| **Bluesky** | API pública (bsky.app), bskydata.com, clearsky.app, firesky.tv (feed live) |
| **Mastodon** | Federação — buscar em instâncias, Fedi.tips, FediSearch |
| **Threads** | Pouca API — via web; ligado ao Instagram, então pivô via IG |
| **Truth Social** | Truthsocial-search, arquivos via Wayback |
| **Parler** | Arquivos via ADL / Kessler (dump de 2021 é famoso) |
| **Gab** | Busca direta gab.com; arquivos via investigadores |
| **Rumble** | Rumble.com pesquisa, Social Blade |
| **Telegram-like (TamTam, Signal)** | Signal: sem OSINT significativo por design |
| **VKontakte** | VK.com busca, Search4Faces, 220vk.com |
| **Odnoklassniki** | OK.ru + Yandex |
| **WeChat** | Sogou WeChat search, Weixin.qq.com |
| **Weibo** | Weibo.com busca, TheDataPack |
| **Line** | Line Today, limitado |
| **Kick** | Kick.com/USER, social Blade |
| **Discord** | Disboard (diretório), Discord.id, Top.gg |
| **Nostr** | nostr.directory, primal.net search |
| **Matrix** | Matrix.org search, Element directory |

### 8.10 Snapchat

| Ferramenta | URL | Função |
|---|---|---|
| Snapchat Map | https://map.snapchat.com/ | Snaps públicos |
| Ghost Codes | https://ghostcod.es/ | Diretório de Snapcodes |
| ConvoZ | https://convoz.com/ | Agregador |
| SnapCodes (arquivo) | via Yandex reverse | Snapcode identificação |

### 8.11 Ferramentas Multi-Plataforma

| Ferramenta | URL | Cobertura |
|---|---|---|
| Social Links (Maltego) | https://sociallinks.io/ | Multi-rede profissional |
| Babel X | https://www.babelstreet.com/ | Multi-linguagem |
| Fivecast | https://www.fivecast.com/ | Profissional |
| Skopenow | https://www.skopenow.com/ | Automated |
| Cobwebs / PenLink Tangles | https://cobwebs.com/ | WEBINT |
| ShadowDragon | https://shadowdragon.io/ | SocialNet |
| Liferaft | https://liferaftinc.com/ | SOCMINT profissional |
| Blackdot Videris | https://www.blackdotsolutions.com/ | Investigação |
| Flashpoint | https://flashpoint.io/ | Dark + surface |

---


