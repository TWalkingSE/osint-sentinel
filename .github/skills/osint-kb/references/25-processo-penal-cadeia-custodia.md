<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 25
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 25. 🆕 Integração com o Processo Penal Brasileiro

### 25.1 Cadeia de Custódia Digital (CPP 158-A a 158-F)

| Etapa | Ação |
|---|---|
| Reconhecimento | Identificar fonte de prova digital |
| Isolamento | Evitar contaminação (modo avião, bloqueador de escrita) |
| Fixação | Hash SHA-256/SHA-3, fotografias, lacre |
| Coleta | Clonagem bit-a-bit quando possível (dd, FTK Imager) |
| Acondicionamento | Recipiente lacrado, etiqueta com hash |
| Transporte | Registro de quem, quando, como |
| Processamento | Laudo em ambiente controlado |
| Armazenamento | Servidor institucional com backup |
| Descarte | Conforme determinação judicial |

### 25.2 Preservação de Evidência Volátil Web

| Situação | Ferramenta |
|---|---|
| Print simples | ❌ Frágil juridicamente |
| Screenshot + hash manual | ⚠️ Aceitável com narrativa |
| **Ata notarial** (CPC 384) | ✅ Forte (tabelião fé pública) |
| **Hunchly** | ✅ Hash + metadados + cadeia |
| **Wayback Machine** | ✅ Fonte independente (corroboração) |
| **WebPreserver / Page Vault** | ✅ Preservação jurídica |

### 25.3 Laudos Periciais Digitais — Estrutura Típica

1. Identificação (autoridade solicitante, número de caso)
2. Descrição da autoridade e do perito
3. Material recebido (hash, lacre)
4. Quesitos formulados
5. Metodologia empregada (ferramentas, versões, hashes)
6. Exame (passo a passo, comandos, screenshots)
7. Respostas aos quesitos
8. Conclusão
9. Anexos (relatórios, capturas, códigos-fonte quando relevante)
10. Identificação digital e assinatura com e-CPF/ICP-Brasil

### 25.4 Modelos de Ofício (Requisição)

| Destinatário | Fundamento |
|---|---|
| Provedor de aplicação (Meta, Google, Microsoft etc.) | MCI art. 15 + art. 10, §1º (decisão judicial para conteúdo) |
| Provedor de conexão (ISP) | MCI art. 13 |
| Instituição financeira | LC 105/2001 (quebra de sigilo bancário) |
| Operadora de telecom | Lei 9.472/1997 + 9.296/1996 (interceptação) |
| Exchange de cripto | IN RFB 1.888/2019 + Lei 14.478/2022 |
| Prestadores internacionais | MLAT BR-EUA / Convenção Budapeste |
| Redes sociais (portais LEA) | https://www.facebook.com/records / https://lers.google.com/ / https://cs.linkedin.com/ etc. |

### 25.5 Portais LEA (Law Enforcement) dos Principais Provedores

| Provedor | Portal |
|---|---|
| Meta (Facebook/Instagram/WhatsApp) | https://www.facebook.com/records/ |
| Google (todos serviços) | https://lers.google.com/ |
| Microsoft | https://leportal.microsoft.com/ |
| X/Twitter | https://legalrequests.x.com/ |
| LinkedIn | https://cs.linkedin.com/ |
| Apple | legal@apple.com + Portal dedicado |
| TikTok | https://www.tiktok.com/legal/law-enforcement |
| Snap | https://www.snapchat.com/lawenforcement |
| Discord | https://discord.com/safety-policies |
| Telegram | abuse@telegram.org (limitado) |
| Cloudflare | https://support.cloudflare.com/hc/en-us/requests/new |
| GoDaddy | legal@godaddy.com |
| Registro.br | https://registro.br/ |
| NIC.br | https://cert.br/ / https://nic.br/ |
| Binance | law.enforcement@binance.com |
| Coinbase | https://www.coinbase.com/legal |
| Amazon AWS | https://pages.awscloud.com/LERS |
| Oracle / Microsoft Azure | Via forms corporativos |



