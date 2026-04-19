<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 24
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 24. 🆕 Tipologias de Cibercrime e Protocolos Investigativos

### 24.1 Fraudes Bancárias e Estelionato Digital

| Tipologia | Indicadores / Fontes |
|---|---|
| Phishing bancário | URLs clonadas, SMS/WhatsApp, TXID Pix, contas laranjas |
| SIM swap | Portabilidade irregular, perda súbita de sinal, acesso a OTP |
| Stealer + invasão de conta | Credenciais em infostealer logs, TOTP comprometido |
| Fraude em e-commerce | Chargeback, entrega em endereço falso |
| Fraude em marketplace (OLX/Mercado Livre) | Perfis recentes, pressa, pagamento fora da plataforma |
| Golpe do falso leilão | Sites clonados, boleto adulterado |
| Golpe do motoboy | Ligação falsa bancária + retirada cartão |
| Falso suporte bancário | Vishing, TeamViewer/AnyDesk |
| Pix malicioso (QR adulterado) | Chaves falsas, beneficiário divergente |

**Artefatos de interesse**: logs de acesso, registros SPI/Bacen (via ofício), dispositivo apreendido, telemetria do app bancário, TXIDs Pix, e-mails de confirmação, números chamadores (via operadora).

### 24.2 Sextorsão e Crimes Sexuais Online

| Tipologia | Observações |
|---|---|
| Sextorsão adulta | Grooming → captura → extorsão. CP art. 158 |
| Revenge porn / NCII | Lei 13.718/2018 — 1 a 5 anos |
| Stalking digital | Lei 14.132/2021 — até 2 anos |
| Cyberbullying com vítima menor | ECA + CP |
| Deepfake pornográfico sem consentimento | Lei 14.811/2024 agravou CSAM; analisar enquadramento vítima adulta |

**Canais oficiais**:
- **SaferNet (disque 100)**: https://new.safernet.org.br/
- **NCMEC CyberTipline**: https://report.cybertip.org/
- **INHOPE**: https://www.inhope.org/
- **Interpol Baseline / ICSE DB** (via PF)
- **ESTUPRO / Central Mulher**: 180

### 24.3 Ransomware e Extorsão Corporativa

| Passo | Ação |
|---|---|
| Triagem inicial | Variante (ID Ransomware), vetor (phishing/RDP/CVE), impacto |
| IoCs | Extensões, notas de resgate, endereço BTC/Monero |
| Blockchain | Rastrear carteira de resgate — seção 9 |
| TOR leak site | Monitorar exposição de dados — seção 11 |
| Cooperação | CERT.br, CTIR Gov, FBI IC3, Europol |
| Decryptors | No More Ransom (nomoreransom.org) |

### 24.4 Pirâmides Financeiras e Golpes em Criptoativos

- **CVM** — Processos Administrativos Sancionadores públicos
- **COAF** — Relatórios RIF
- **Cadastro CVM de não autorizados**
- **MPF Força-Tarefa Tsunami Cripto** (precedente)
- Ferramentas seção 9 (Chainalysis/TRM/Arkham/Misttrack)

### 24.5 Violência Digital contra Mulher

**Canais**:
- **Ligue 180** — Central de Atendimento à Mulher
- **Delegacia Virtual (variável por UF)**
- **Lei Maria da Penha** online
- **SaferNet Helpline**
- Ferramentas de reconhecimento de imagem íntima: **StopNCII.org** (hashing consentido)

### 24.6 Material de Abuso Sexual Infantil (CSAM) — Protocolo Crítico

🛑 **PROTOCOLO**:
1. **NÃO baixar, não salvar, não encaminhar.** Apenas URL/hash é suficiente para a denúncia.
2. **Registrar hora, URL, screenshot com Hunchly** (sem baixar mídia).
3. **Denúncia imediata**: SaferNet (canais.safernet.org.br) + Polícia Federal
4. **Identificação**: PhotoDNA (Microsoft), Project Arachnid (C3P), NCMEC hashes
5. **Colaboração**: via PF → Interpol ICSE → Operação Luz na Infância / Darknet

### 24.7 Crimes contra Honra Online

- **Calúnia/Difamação/Injúria** — CP 138–140
- **Racismo/Injúria racial** — Lei 7.716/1989 + Lei 14.532/2023
- **Provas**: ata notarial (CPC 384), preservação via Marco Civil (MCI art. 10 § 2º: até 6 meses registros de conexão; 6 meses aplicação)



