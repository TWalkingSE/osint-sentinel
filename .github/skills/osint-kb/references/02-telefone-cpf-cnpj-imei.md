<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 02
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 2. NÚMERO DE TELEFONE, CPF E CNPJ

### 2.1 Telefone — Identificação e Pesquisa

#### 2.1.1 Verificação do Número

| Ferramenta | URL | Função |
|---|---|---|
| ABRTELECOM | https://consultanumero.abrtelecom.com.br | Operadora oficial (Anatel) |
| NumVerify | https://numverify.com/ | Valida + tipo (VOIP/fixo/móvel) |
| PhoneInfoga | https://github.com/sundowndev/phoneinfoga | OSINT de telefones |
| TrueCaller | https://www.truecaller.com/ | Nome + operadora |
| DonoDoZap | https://donodozap.com/ | WhatsApp — nome e foto |
| Epieos | https://epieos.com/ | Cruza com outros dados |
| MySmsBox | https://mysmsbox.ru/ | Busca russa para BR |
| Sync.me | https://sync.me/ | Identificador de chamadas |
| CallerID Test | https://calleridtest.com/ | Identifica nome associado |
| OSINT Industries | https://osint.industries/ | Paga (gov. gratuito) |
| Eyecon | https://eyecon-app.com/ | App de identificação |
| Hiya | https://www.hiya.com/ | Reputação de chamadas |
| Showcaller | https://www.showcaller.com/ | Alternativo ao Truecaller |
| Whoscall | https://whoscall.com/ | Global com foco em Ásia |
| OpenCNAM | https://www.opencnam.com/ | Nome associado (CNAM) |
| FreeCarrierLookup | https://freecarrierlookup.com/ | Operadora (EUA/global) |
| Twilio Lookup API | https://www.twilio.com/lookup | Comercial, confiável |
| Numlookup | https://www.numlookup.com/ | Gratuita |
| Spydialer | https://www.spydialer.com/ | Identificador reverso |
| BeenVerified Phone | https://www.beenverified.com/ | Paga (EUA) |
| CocoFinder | https://cocofinder.com/ | Paga (EUA) |
| Consulta Anatel (oficial) | https://sistemas.anatel.gov.br/ | Portabilidade numérica |
| Portabilidade ABR | https://consultanumero.abrtelecom.com.br | Operadora atual |

#### 2.1.2 Verificação de VOIP

| Ferramenta | URL |
|---|---|
| NumVerify | https://numverify.com/ |
| TeleSeer | https://www.teleseer.com/ |
| PhoneInfoga | https://github.com/sundowndev/phoneinfoga |
| HLR Lookup | https://hlrlookup.com/ |
| Maltego + LoginSoft OSINT | Via Transform Hub |
| IPQualityScore | https://www.ipqualityscore.com/free-ip-lookup-proxy-vpn-test |
| HLR-Lookups | https://www.hlr-lookups.com/ |
| TextMagic HLR | https://www.textmagic.com/free-tools/hlr-phone-number-lookup | Verificação de status |
| Phoneva | https://phoneva.com/ | OSINT de telefone |
| CallerAPI | https://callerapi.com/ | API comercial |

**Indicadores de VOIP:**
- Blocos de numeração atribuídos a operadoras 100% VOIP (ex: Voys, Aircall, 55Voip)
- Incapacidade de receber SMS A2P em plataformas bancárias
- Latência anormal em chamadas
- Ausência em bases HLR convencionais

#### 2.1.3 Técnica: Simulação de PIX
Ao cadastrar o número como chave PIX em um banco digital (com autorização legal), o sistema pode revelar nome completo e instituição financeira do titular. **Atenção:** registro de auditoria fica na instituição — documentar o procedimento.

#### 2.1.4 Técnica: WhatsApp Web
Via WhatsApp Web, é possível verificar foto de perfil, status e "visto por último" de um número alvo sem adicioná-lo, preservando sigilo operacional. Usar conta operacional descartável, nunca conta pessoal.

#### 2.1.5 Técnica: Telegram
Adicionar o número como contato em conta operacional revela se há conta Telegram, username (se público) e foto de perfil. Documentar via print com timestamp.

#### 2.1.6 Técnica: Google Contacts + Google Photos
Adicionar o número como contato em conta Google operacional pode, dependendo de configurações do alvo, revelar foto de perfil Google.

#### 2.1.7 Painéis de Consulta **LEGÍTIMOS** (CNPJ regular + contrato com bureaus)

> ✅ Estes painéis operam com CNPJ regular, contratos de fornecimento com bureaus (Serasa, Boa Vista, Quod) ou bases públicas (Receita, SERPRO). Sempre exija contrato escrito e verifique o CNPJ antes de contratar.

| Serviço | URL |
|---|---|
| SisMix | https://sismix.com.br/ |
| Brasil Consultas | https://brasilconsultas.com.br/ |
| CheckTudo | https://www.checktudo.com.br/ |
| GigaDados | https://www.gigadados.com.br/ |
| MegaConsultas | https://megaconsultas.com.br/ |
| Credilink | https://www.credilink.com.br/ |
| Fênix Consultas | https://fenixconsultas.com.br/ |
| CATTA | https://www.catta.com.br/ |
| PROCOB | https://www.procob.com/ |
| UGGLE | https://www.uggle.com.br/ |
| ASSECC | https://www.assecc.com.br/ |
| Buscas Consultas | https://buscaconsultas.com.br/ |
| SERPRO Datavalid | https://www.datavalid.com.br/ | Oficial — convênio |
| Serasa Experian | https://www.serasaexperian.com.br/ | Bureau nacional |
| Boa Vista (Equifax) | https://www.boavistaservicos.com.br/ | Bureau nacional |
| Quod | https://www.quod.com.br/ | Bureau nacional |
| SPC Brasil | https://www.spcbrasil.org.br/ | Cadastros |
| BigDataCorp | https://bigdatacorp.com.br/ | Enriquecimento corporativo |

> 🛑 **Painéis clandestinos não são listados nesta base.** Ver seção 27 para investigar operadores desses painéis.

### 2.2 CPF — Pesquisa e Verificação

| Ferramenta | URL | Função |
|---|---|---|
| Receita Federal | https://www.cpf.receita.fazenda.gov.br/Consultacpf/ | Situação cadastral |
| CadastroPre | https://cadastropre.com.br/ | Linhas ativas por CPF |
| SrWatson | https://srwatson.io/ | Pesquisa agregada |
| RedeCNPJ | https://www.redecnpj.com.br/ | Vínculos societários |
| SINTEGRA | http://www.sintegra.gov.br/ | Inscrição estadual |
| Portal da Transparência | https://www.portaltransparencia.gov.br/pessoa | Servidor público + CPF parcial |
| CEIS/CNEP | https://www.portaltransparencia.gov.br/sancoes | Sanções administrativas |
| eProc/TJRJ, TJSP, etc. | Sites dos tribunais | Processos por CPF |
| Consulta Processual (CNJ) | https://www.cnj.jus.br/consulta-publica/ | Unificada |
| TSE — Filiação Partidária | https://www.tse.jus.br/eleitor/filiacao-partidaria | Por nome |
| CPF-CNPJ.com | https://www.cpfcnpj.com.br/ | Validadores |

**Técnicas legítimas para cruzamento de CPF:**
- Via ofício ao INSS (CNIS) — vínculos empregatícios
- Via ofício ao BACEN (SISBACEN CCS) — contas bancárias
- Via ofício à Receita (CAF, DITR, DIRPF) — declarações
- Via ofício ao SERPRO — Datavalid autenticação facial
- Via ofício ao TSE — situação eleitoral
- Via SINESP Infoseg (acesso regulado por credenciamento institucional)

### 2.3 CNPJ — Pesquisa e Análise

| Ferramenta | URL | Função |
|---|---|---|
| Receita Federal CNPJ | https://solucoes.receita.fazenda.gov.br/servicos/cnpjreva/cnpjreva_solicitacao.asp | Dados cadastrais |
| RedeCNPJ | https://www.redecnpj.com.br/rede/ | Grafo de sócios |
| CNPJ.biz | https://cnpj.biz/ | Dados completos |
| Jusbrasil Empresas | https://www.jusbrasil.com.br/busca | Processos e dados |
| QSA (Quadro Societário) | Via CNPJ.biz | Sócios e participações |
| Brasil.io | https://brasil.io/datasets/ | Dados abertos do governo |
| Econodata | https://www.econodata.com.br/ | Empresas e porte |
| Consulta Sócios | https://consultasocios.com.br/ | Vínculos societários |
| Speedio | https://speedio.com.br/ | B2B intel |
| Cortex Intelligence | https://www.cortex-intelligence.com/ | Dados empresariais |
| Casa dos Dados | https://casadosdados.com.br/ | Grátis com consulta aberta |
| OpenCorporates | https://opencorporates.com/ | Empresas globais |
| TJ Oficial (cada estado) | Site oficial | Processos por CNPJ |
| CNPJ.ws | https://www.cnpj.ws/ | API RESTful gratuita |
| Minha Receita | https://minhareceita.org/ | API da Receita |
| JUCESP / JUCERJA / etc. | Juntas Comerciais | Atos constitutivos |
| OffshoreLeaks (ICIJ) | https://offshoreleaks.icij.org/ | Paraísos fiscais |
| Panama/Pandora Papers | Base ICIJ | Offshore |
| SIAPE Transparência | https://transparencia.gov.br/servidores | Servidores federais |

### 2.4 IMEI — Dispositivos Móveis

| Ferramenta | URL | Função |
|---|---|---|
| Consulta Aparelho | https://consultaaparelhoimpedido.com.br/ | Verificar furto/roubo |
| IMEI.info | https://www.imei.info/ | Modelo e fabricante |
| IMEI24 | https://imei24.com/ | Dados do dispositivo |
| IMEICheck | https://imeicheck.com/ | Verificação completa |
| IMEI Pro | https://imeipro.info/ | Dados de operadora |
| DeviceAtlas | https://deviceatlas.com/ | Dados técnicos do dispositivo |
| CEABS / Proteste IMEI | https://www.celularseguro.gov.br/ | Plataforma oficial MJSP |
| Celular Seguro (MJSP) | https://www.gov.br/mj/pt-br/assuntos/noticias/celular-seguro | App oficial |
| Anatel IMEI | https://www.gov.br/anatel/pt-br | Homologação |
| Swappa IMEI Check | https://swappa.com/esn/check | Verifica por operadora (EUA) |
| ChipMunk IMEI | https://imei.org/ | Consulta internacional |
| FMiPhone Status | https://www.iphoneimei.info/free | Apple iCloud lock |
| Samsung IMEI | https://www.samsung.com/global/ | Informações oficiais |

**Procedimentos formais:**
- Bloqueio pela Anatel (via operadora) e pelo Celular Seguro (MJSP)
- Pedido via ofício à Anatel para histórico de IMEI
- Via operadora: último IMSI associado ao IMEI, última ERB conectada, duplas SIM
- Para crimes: Operação *Carrefour* / *Mão de Ouro* — padrões conhecidos de reset de IMEI

### 2.5 Validadores e Geradores Úteis para Investigação

| Ferramenta | URL | Uso |
|---|---|---|
| Validar CPF/CNPJ | https://www.4devs.com.br/validador_cpf | Confirmar se dígitos são válidos |
| Validador Matemático de CPF | Algoritmo público | Verificar integridade |
| CEP — Correios | https://buscacepinterno.correios.com.br/ | Endereços por CEP |
| CEP API (ViaCEP) | https://viacep.com.br/ | JSON gratuito |
| CEP API (BrasilAPI) | https://brasilapi.com.br/ | Múltiplas APIs |
| Receita WS | https://www.receitaws.com.br/ | CNPJ via API |

### 2.6 Pesquisa por Nome (Brasil)

| Ferramenta | URL | Função |
|---|---|---|
| Jusbrasil Pessoas | https://www.jusbrasil.com.br/ | Processos por nome |
| LinkedIn Search | `site:linkedin.com/in "nome"` | Profissional |
| Escavador | https://www.escavador.com/ | Processos + currículo |
| JusBrasil Processos | — | Agregador jurídico |
| Portal da Transparência | https://www.portaltransparencia.gov.br/pessoa | Servidor público |
| Plataforma Lattes | http://lattes.cnpq.br/ | Pesquisador / acadêmico |
| Tribunais Eleitorais | TSE/TRE | Candidatos, filiações |
| Google Dorks | `"Nome Completo" site:gov.br` | Oficiais |
| OAB | https://cna.oab.org.br/ | Advogados |
| CFM / CRM | https://portal.cfm.org.br/ | Médicos |
| CREA / CAU | Conselhos regionais | Engenheiros/arquitetos |
| CRC / CRO / CRP / CRF | Conselhos regionais | Demais profissionais |



