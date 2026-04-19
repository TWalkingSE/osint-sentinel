<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 27
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 27. 🆕 Investigação de Operadores de Painéis Clandestinos

> **Nota importante**: esta seção substitui e desaconselha qualquer listagem de painéis clandestinos. A orientação correta não é "usar painéis com aviso legal", mas sim **investigar quem os opera**. Painéis não oficiais no Brasil são sustentados por **crimes-meio** — acesso indevido a Infoseg/Detran/Receita/Siapa (CP 154-A), divulgação ilegal de dados sigilosos (LGPD arts. 42-45), receptação de dados (CP 180), associação/organização criminosa (CP 288, Lei 12.850/2013), e frequentemente **vazamentos originados dentro de órgãos públicos** (corrupção, prevaricação). Usar tais painéis, mesmo em investigação, contamina a cadeia de custódia (CPP 157) e expõe o próprio investigador a imputações graves — há jurisprudência consolidada nesse sentido (STJ HC 598.051/SP e operações como Data Call, Datasan, Vazabus, Blackout do MPF/CGU).

### 27.1 Tipologia dos Operadores

| Perfil | Vetor |
|---|---|
| Agente público vazador | Login legítimo Infoseg/Detran/Receita usado para extrair lotes |
| Ex-agente público | Credenciais ainda válidas, estrutura de relações |
| Broker intermediário | Compra de múltiplas fontes, revende em painéis/bots |
| Operador de painel web | Hospeda interface, cobra mensalidade |
| Bot Telegram | Distribuição escalável (consulta por PIX) |
| Call center de golpe | Consome painéis para aplicar fraudes |
| Grupo cibercriminoso organizado | Combina painéis + malware + lavagem |

### 27.2 Vetores de Investigação

| Vetor | Detalhes |
|---|---|
| **Dinheiro** | Pix das mensalidades → CPFs/CNPJs recebedores → quebra bancária → lavagem |
| **Infraestrutura** | Domínio do painel → WHOIS → hospedagem → CDN → IP de origem → provedor |
| **Operacional** | Bot Telegram → @username do admin → dump de usuários → recon em OSINT |
| **Fonte primária** | Logs de acesso nos sistemas oficiais → correlação de consultas de massa → identificação do servidor público |
| **Marketing** | Anúncios em Telegram/WhatsApp/Instagram → perfis do anunciante |
| **Suporte técnico** | Grupos/canais de ajuda → membros → redes |
| **Criptomoedas** | Quando aceita cripto, rastreio on-chain (seção 9) |
| **SaaS usados** | Cloudflare (retirar proteção via ofício), hospedagem, gateway Pix |

### 27.3 Técnicas Específicas

| Técnica | Como |
|---|---|
| **Undercover/infiltração** | Lei 12.850/2013 — com MP/autorização judicial |
| **Auditoria de acessos Infoseg/Detran** | Via ofício + cooperação institucional; buscar padrões anômalos (muitas consultas/h, CPFs não relacionados a ocorrências) |
| **Análise de logs SIAPE/servidor** | Correlação temporal entre consultas oficiais e publicação no painel |
| **Cloudflare bypass** | Certificados (crt.sh), histórico DNS (SecurityTrails, Netlas), cabeçalhos de erro originais, origem IP em subdomínios esquecidos |
| **Pivot em Telegram** | Telepathy, Telegago, TGStat, análise de admins e mensagens encaminhadas |
| **Quebra de sigilo Pix** | Via ofício → Bacen/SPI → destinatários → rede de contas laranja |
| **Quebra de sigilo telefônico** | Lei 9.296/1996 para interceptação; MCI art. 10 para registros de conexão |
| **Cooperação internacional** | Se infra hospedada fora — MLAT ou Budapeste |

### 27.4 Legislação Aplicável aos Operadores

| Norma | Aplicação |
|---|---|
| CP art. 154-A / 154-B | Invasão de dispositivo informático (quando há acesso indevido) |
| CP art. 180 | Receptação (comercialização de dados obtidos ilicitamente) |
| CP art. 288 / 288-A | Associação criminosa |
| CP art. 313-A / 313-B | Inserção e modificação não autorizada em sistema da administração pública |
| CP art. 325 | Violação de sigilo funcional |
| CP art. 327 | Conceito de funcionário público (alcance ampliado) |
| Lei 12.737/2012 | Crimes informáticos |
| Lei 8.137/1990 | Crimes contra ordem tributária (se dados da Receita) |
| Lei 12.850/2013 | Organização criminosa |
| Lei 9.613/1998 | Lavagem (quando há movimentação estruturada) |
| LGPD art. 42-45 | Responsabilização civil/administrativa + art. 52 (sanções) |
| Lei 13.709/2018 art. 46-49 | Segurança e governança de dados |
| Lei 14.155/2021 | Estelionato eletrônico agravado |

### 27.5 Coordenação Institucional

| Órgão | Papel |
|---|---|
| **Polícia Federal — DICOR/GGI** | Vazamentos em órgãos federais |
| **MPF — GCCC / CAEX** | Cooperação nacional + internacional |
| **PCDF / Polícias Civis estaduais — DRCCs** | Painéis regionais |
| **CGU** | Corregedoria (servidor vazador) |
| **AGU** | Defesa da União quando órgão lesado |
| **ANPD** | Incidentes LGPD (notificação art. 48) |
| **SERPRO / Dataprev / RFB** | Auditoria técnica |
| **Bacen / COAF** | Movimentações financeiras |
| **CGI.br / NIC.br / CERT.br** | Coordenação com infraestrutura internet |



