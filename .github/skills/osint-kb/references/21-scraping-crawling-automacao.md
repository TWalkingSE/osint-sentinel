<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 21
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 21. Scraping, Automação e Coleta em Escala

⚠️ **Legalidade**: observar **Marco Civil da Internet** (art. 7º, 8º), **LGPD**, **Lei 12.965/2014**, termos de serviço dos sites e **robots.txt**. Scraping automatizado em escala pode configurar abuso de acesso. Em investigação oficial, documente a necessidade e a finalidade legítima.

### 21.1 Frameworks

| Ferramenta | Linguagem | Uso |
|---|---|---|
| Scrapy | Python | Crawler robusto |
| Scrapy-Splash / Scrapy-Playwright | Python | Páginas JS |
| Playwright | Python/JS | Automação headless moderna |
| Puppeteer | JS | Headless Chrome |
| Selenium | Multi | Clássico |
| Crawlee (Apify) | Node | Framework completo |
| Colly | Go | Alta performance |
| Requests + BeautifulSoup | Python | Simples/rápido |
| httpx (python) + selectolax | Python | Paralelo e rápido |
| curl-impersonate / curl_cffi | — | TLS fingerprint real |
| undetected-chromedriver | Python | Bypass básico anti-bot |
| Hrequests / Nodriver | Python | Anti-detect moderno |

### 21.2 Plataformas e Serviços

| Serviço | URL | Uso |
|---|---|---|
| Apify | https://apify.com/ | Actors prontos |
| Bright Data | https://brightdata.com/ | Proxies + scraping |
| Oxylabs | https://oxylabs.io/ | Proxies enterprise |
| Smartproxy | https://smartproxy.com/ | Residencial |
| ScrapFly | https://scrapfly.io/ | API anti-bloqueio |
| ScrapingBee | https://www.scrapingbee.com/ | API |
| ZenRows | https://www.zenrows.com/ | Anti-bot |
| Browserless | https://www.browserless.io/ | Chrome remoto |

### 21.3 Bypass de Proteções

| Desafio | Abordagem |
|---|---|
| Cloudflare | curl_cffi, FlareSolverr, Playwright stealth |
| reCAPTCHA v2/v3 | 2Captcha, Anti-Captcha, CapSolver (serviços) |
| hCaptcha | idem |
| Akamai / DataDome | Residencial proxy + browser real |
| Rate limit | Rotação de user-agent, IPs, throttle |
| Fingerprint TLS/HTTP2 | curl-impersonate, Hrequests |

### 21.4 Pipelines e Orquestração

- **Airflow / Prefect / Dagster** — workflows
- **Celery / RQ / Dramatiq** — filas
- **n8n / Node-RED** — low-code
- **GitHub Actions** — agendamento leve
- **Kubernetes Jobs / CronJobs** — escala



