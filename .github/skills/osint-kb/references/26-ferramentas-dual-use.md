<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 26
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 26. 🆕 Ferramentas Dual-Use — Avisos Éticos e Legais

Esta seção reúne ferramentas **poderosas** cujo uso **exige fundamentação legal clara**, autorização institucional e respeito à LGPD/ANPD. Não são recomendadas para uso "livre" — são citadas porque investigadores precisam **conhecer** (tanto para operar quando autorizado quanto para defender vítimas que sofreram abuso dessas ferramentas).

### 26.1 Reconhecimento Facial em Escala Aberta

⚠️ **LGPD arts. 5º, II; 7º; 11 (dado sensível biométrico)** + **Decreto 10.046/2019** + **recomendações ANPD**. Uso em investigação depende de base legal específica (inciso III art. 4º LGPD para segurança pública) e proporcionalidade. Não use de forma indiscriminada.

| Ferramenta | Observação |
|---|---|
| PimEyes | Busca facial em fotos públicas; polêmica ética significativa |
| FaceCheck.ID | Similar |
| Lenso.ai | Busca facial + imagem reversa |
| Clearview AI | Apenas LEA autorizado (EUA); banido em várias jurisdições |
| Paravision / NEC / Cognitec | Enterprise |
| FindClone (RU) | Cobre VK russo |
| Search4Faces (RU) | VK/OK |
| DeepFace / InsightFace / CompreFace (open) | Auto-hospedado |

**Uso correto**: identificação de vítima desconhecida, reconhecimento de autor de crime com autorização, investigação com ordem judicial. **Uso incorreto**: vigilância em massa, perfilamento arbitrário.

### 26.2 Scraping Agressivo de Dados Pessoais

⚠️ **LGPD** + **Marco Civil**. Raspagem massiva de dados pessoais fora de base legal é ilícita — mesmo que tecnicamente viável.

| Ferramenta | Alerta |
|---|---|
| Datasets de "vazamentos" em Telegram/fóruns | Geralmente **crime-meio** (acesso indevido, receptação); prova contaminada |
| ProPrivacy / Hudson Rock | Comerciais com governança; usam fontes declaradas |
| SpyCloud / Constella Intelligence | LEA com contrato |
| Have I Been Pwned | Transparência + responsabilidade |
| DeHashed / Leak-Lookup | **Uso controverso** — verifique base legal antes |

### 26.3 Detecção de Stalkerware (Defesa de Vítimas)

✅ **Uso pró-vítima recomendado**:

| Ferramenta | Função |
|---|---|
| Coalition Against Stalkerware | https://stopstalkerware.org/ |
| TinyCheck (Kaspersky) | Detecção em Raspberry Pi |
| ISDi (Univ. Cornell) | Indicadores stalkerware |
| MVT (Amnesty) | Mobile Verification Toolkit — checa comprometimento |
| iVerify | iOS segurança |
| CERT.br Checagens | Material educativo |

### 26.4 Interceptação e Coleta de Tráfego

🛑 **Lei 9.296/1996** — interceptação telefônica/telemática requer **ordem judicial**. Fora disso, é crime (art. 10 da própria lei).

| Ferramenta | Alerta |
|---|---|
| Wireshark/tshark passivo | OK em rede própria/lab |
| Bettercap / Ettercap / mitmproxy | MITM — apenas em rede própria/autorizada |
| IMSI catchers (Stingray) | Uso restrito a LEA com mandado |
| FinFisher / Pegasus / Predator | Mercenários — polêmicas graves; cuidado jurídico máximo |

### 26.5 Vigilância de Redes Sociais em Escala

⚠️ **LGPD** — mesmo dados "públicos" em redes sociais têm limites para tratamento (finalidade, necessidade, base legal).

| Plataforma | Observação |
|---|---|
| Babel X / Cobwebs / Voyager / Fivecast / ShadowDragon / Social Links CRIMEWALL | Enterprise LEA — exigem contrato + governança |
| Palantir Gotham | Grandes operações policiais |
| Skopenow / Liferaft / Flashpoint Social | Investigação corporativa + LEA |



