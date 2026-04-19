<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 14
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 14. DOCUMENTOS, REGISTROS E VAZAMENTOS

### 14.1 Registros Públicos (Brasil)

| Fonte | URL | Dados |
|---|---|---|
| Portal da Transparência | https://www.portaltransparencia.gov.br/ | Servidores, salários |
| Diário Oficial da União | https://www.in.gov.br/ | Atos oficiais |
| Tribunal de Contas | https://portal.tcu.gov.br/ | Contratos |
| CNJ | https://www.cnj.jus.br/ | Processos judiciais |
| Jusbrasil | https://www.jusbrasil.com.br/ | Processos e empresas |
| Brasil.io | https://brasil.io/ | Dados governamentais abertos |
| Receita Federal | https://www.gov.br/receitafederal/ | CPF/CNPJ |
| IBGE | https://www.ibge.gov.br/ | Dados demográficos |
| Governo Federal Dados | https://dados.gov.br/ | Datasets abertos |
| Diários Oficiais Estaduais | Site de cada estado | Atos estaduais |
| Diários Oficiais Municipais | Varia | Atos municipais |
| TSE Repositório | https://dadosabertos.tse.jus.br/ | Dados eleitorais |
| INEP | https://www.gov.br/inep/ | Educação |
| DataSUS | https://datasus.saude.gov.br/ | Saúde pública |
| MapBiomas | https://mapbiomas.org/ | Uso do solo |
| FiscalLista | — | Agentes públicos |
| Portal do Software Público | https://www.gov.br/governodigital/ | Softwares |
| LAI — Acesso à Informação | https://www.gov.br/acessoainformacao/ | Pedidos formais |

### 14.2 Registros de Propriedade

| Fonte | Função |
|---|---|
| Cartório de Registro de Imóveis (por estado) | Matrícula de imóveis |
| SENARC | Beneficiários sociais |
| Detran (estadual) | Veículos |
| Receita Federal | Declarações e bens (via ofício) |
| INPI | Marcas e patentes |
| Receita Federal - DIMOB | Imóveis (declaração) |
| Cartórios ORETs | Atos e protestos |
| IRIB - Indicador Nacional | https://www.irib.org.br/ | Registro imobiliário |
| Central de Registro de Imóveis | https://www.registradores.org.br/ | Unificado |
| Serviço Registral Eletrônico (SREI) | Por estado | Digital |

### 14.3 Busca de Documentos Vazados / Expostos

| Ferramenta | URL |
|---|---|
| Google Drive Search | `site:drive.google.com "dado_alvo"` |
| Dork Documentos | `"dado_alvo" filetype:pdf site:gov.br` |
| Scribd | https://www.scribd.com/ |
| Academia.edu | https://www.academia.edu/ |
| DocumentCloud | https://www.documentcloud.org/ |
| Court Listener | https://www.courtlistener.com/ |
| PACER (EUA) | https://pacer.gov/ |
| ResearchGate | https://www.researchgate.net/ |
| SSRN | https://www.ssrn.com/ |
| Calaméo | https://www.calameo.com/ | Revistas digitais |
| Issuu | https://issuu.com/ | Publicações |
| Slideshare | https://www.slideshare.net/ | Apresentações |
| Speaker Deck | https://speakerdeck.com/ | Slides dev |
| Archive.org Documents | https://archive.org/details/texts | Livros/docs |
| OffshoreLeaks (ICIJ) | https://offshoreleaks.icij.org/ | Empresas offshore |
| Distributed Denial of Secrets (DDoSecrets) | https://ddosecrets.com/ | Base de vazamentos (uso ético!) |
| Aleph (OCCRP) | https://aleph.occrp.org/ | Investigativo |

### 14.4 Google Dorks para Documentos Sensíveis

```
filetype:xls "confidencial"
filetype:doc "lista de funcionários"
filetype:pdf "nome_empresa" "interno"
intext:"Não divulgar" filetype:pdf
intitle:"index of" "passwords.txt"
site:empresa.com filetype:xls
inurl:backup filetype:sql
filetype:env DB_PASSWORD
filetype:ini inurl:"database"
filetype:log inurl:"/www/"
filetype:sql "INSERT INTO users"
intitle:"index.of" "parent directory" sensitive
inurl:"/phpinfo.php" OR inurl:"/.env" OR inurl:"/config.yml"
filetype:conf inurl:nginx
filetype:txt "RSA PRIVATE KEY"
"BEGIN CERTIFICATE" filetype:pem
```

### 14.5 OSINT Corporativo e Investigativo

| Fonte | URL | Uso |
|---|---|---|
| OpenCorporates | https://opencorporates.com/ | Empresas globais |
| Aleph (OCCRP) | https://aleph.occrp.org/ | Base investigativa |
| OpenSanctions | https://www.opensanctions.org/ | Sanções |
| Sayari | https://sayari.com/ | Risk + networks |
| Orbis (BvD) | Comercial | Ownership profundo |
| Dun & Bradstreet | https://www.dnb.com/ | Crédito global |
| LittleSis | https://littlesis.org/ | Poder + conexões |
| Kompass | https://www.kompass.com/ | B2B diretório |
| CorporateInformation | https://www.corporateinformation.com/ | Análise financeira |
| SEC EDGAR | https://www.sec.gov/edgar | Empresas públicas EUA |
| CVM Brasil | https://www.gov.br/cvm/ | Empresas listadas BR |
| Companies House (UK) | https://www.gov.uk/government/organisations/companies-house | Empresas UK |



