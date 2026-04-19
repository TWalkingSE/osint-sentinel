---
name: ioc-extractor
description: >
  Extrair indicadores de comprometimento (IOCs) de texto livre — IPs, domínios,
  URLs, hashes (MD5/SHA1/SHA256), wallets cripto (BTC/ETH), e-mails,
  CPF/CNPJ, IMEI, placas, números de telefone. Defang/refang automático,
  deduplicação e classificação por tipo. Útil para colar logs, e-mails de
  phishing, pastes de fórum ou dumps e extrair tudo que é pivotável. Skill
  extra, Fase 2 (Coleta). Exemplos: "extrai os IOCs desse log", "puxa tudo
  de relevante desse e-mail", "identifica indicadores nesse paste".
---

# IOC Extractor (Fase 2 — Coleta)

## Quando usar

- Usuário cola texto bruto (log, e-mail, paste, dump, header, relatório) e quer identificadores acionáveis
- Antes de `/consultar-toolkit` ou `/mapear-pivos` — transforma texto em entidades
- Particularmente útil para threat intel (SOC/IR) e análise de campanhas de phishing

## Protocolo

### 1. Identifique tipos de IOC presentes

Padrões regex aplicáveis (apenas referência — use processamento semântico + padrões):

| Tipo | Regex aproximado |
|---|---|
| **IPv4** | `\b(?:\d{1,3}\.){3}\d{1,3}\b` (validar 0–255 cada octeto) |
| **IPv6** | padrões RFC 4291 |
| **Domínio** | `\b[a-z0-9-]+(?:\.[a-z0-9-]+)+\b` (validar TLD) |
| **URL** | `https?://\S+` |
| **E-mail** | `[\w.+-]+@[\w-]+(?:\.[\w-]+)+` |
| **MD5** | `\b[a-f0-9]{32}\b` |
| **SHA-1** | `\b[a-f0-9]{40}\b` |
| **SHA-256** | `\b[a-f0-9]{64}\b` |
| **SHA-512** | `\b[a-f0-9]{128}\b` |
| **Wallet BTC (bech32)** | `\bbc1[a-z0-9]{38,62}\b` |
| **Wallet BTC (legacy)** | `\b[13][a-km-zA-HJ-NP-Z1-9]{25,34}\b` (base58, validar) |
| **Wallet ETH** | `\b0x[a-fA-F0-9]{40}\b` |
| **CPF** | `\b\d{3}\.\d{3}\.\d{3}-\d{2}\b` ou `\b\d{11}\b` (validar DV) |
| **CNPJ** | `\b\d{2}\.\d{3}\.\d{3}/\d{4}-\d{2}\b` ou `\b\d{14}\b` (validar DV) |
| **IMEI** | `\b\d{15}\b` (validar Luhn) |
| **Placa BR (antiga)** | `\b[A-Z]{3}-?\d{4}\b` |
| **Placa BR (Mercosul)** | `\b[A-Z]{3}\d[A-Z]\d{2}\b` |
| **Telefone BR** | `\+55\s?\d{2}\s?9?\d{4}-?\d{4}` |
| **Onion v3** | `\b[a-z2-7]{56}\.onion\b` |
| **ASN** | `\bAS\d{1,10}\b` |
| **CVE** | `\bCVE-\d{4}-\d{4,}\b` |

### 2. Defang / refang

Aplique conversão quando relevante:

- Texto contém `hxxp://` / `[.]` / `[:]` → **refang** para análise (`http://`, `.`, `:`)
- Output para armazenamento → manter **defanged** (`hxxp://alvo[.]com`) para evitar cliques acidentais
- Marque claramente qual versão está sendo entregue

### 3. Deduplique e classifique

- Remova duplicatas (case-insensitive para domínios/e-mails/hashes)
- Agrupe por tipo
- Conte ocorrências (indicador forte se aparece várias vezes)

### 4. Valide o que for validável

- **CPF/CNPJ**: dígitos verificadores
- **IMEI**: Luhn
- **BTC legacy**: checksum base58
- **ETH**: checksum EIP-55 se presente
- Marque inválidos como `⚠️ formato ok, checksum falhou` (podem ser placeholders/exemplos)

### 5. Recomende próximos skills

Mapeie cada IOC para o arquivo `references/NN-*.md` aplicável e sugira skill.

## Formato de saída obrigatório

```markdown
# 🎯 IOCs EXTRAÍDOS

**Texto analisado:** [N caracteres / N linhas]
**Total de IOCs únicos:** [N]
**Defanging aplicado no output:** [sim/não]

---

## IPv4 / IPv6
| # | Valor | Ocorrências | Ação recomendada |
|---|---|---|---|
| 1 | `203.0.113.42` | 3 | `/consultar-toolkit` → `references/03-ip.md` |

## Domínios
| # | Valor (defanged) | Valor (refanged) | Ocorrências | Ação |
|---|---|---|---|---|
| 1 | `alvo-banco[.]com` | `alvo-banco.com` | 5 | `references/04-*.md` §4.1 (WHOIS) |

## URLs
| # | Valor (defanged) | Ação |
|---|---|---|
| 1 | `hxxps://alvo-banco[.]com/login` | URLScan.io (`references/04-*.md` §4.6) |

## E-mails
| # | Valor | Ocorrências | Ação |
|---|---|---|---|
| 1 | `golpista@protonmail.com` | 2 | Holehe + Epieos (`references/01-email.md` §1.4) |

## Hashes
| # | Algoritmo | Valor | Ação |
|---|---|---|---|
| 1 | SHA-256 | `a1b2...ff` | VirusTotal / MalwareBazaar (`references/15-*.md`) |

## Wallets cripto
| # | Rede | Valor | Validação | Ação |
|---|---|---|---|---|
| 1 | BTC (bech32) | `bc1q...` | ✅ válida | Blockchain.com / MetaSleuth (`references/09-*.md`) |

## Documentos BR
| # | Tipo | Valor | Checksum | Ação |
|---|---|---|---|---|
| 1 | CPF | `123.456.789-00` | ⚠️ inválido (placeholder?) | — |
| 2 | CNPJ | `12.345.678/0001-90` | ✅ válido | RedeCNPJ (`references/02-*.md` §2.3) |

## Outros
| # | Tipo | Valor | Ação |
|---|---|---|---|
| 1 | ASN | `AS12345` | BGP.he.net (`references/03-*.md` §3.8) |
| 2 | Onion v3 | `abc...xyz.onion` | `references/11-dark-web-deep-web.md` (🟡 requer protocolo) |
| 3 | CVE | `CVE-2024-1234` | Contexto externo (NVD/MITRE) |

---

## 📊 Síntese
├─ IOCs mais repetidos (pivô prioritário): [domínio X, IP Y]
├─ Clusters naturais:
│   • Cluster de infraestrutura: [domínio + IP + ASN]
│   • Cluster de financeiro: [wallets + CNPJ]
├─ IOCs com alerta:
│   • Onion v3 detectada — 🟡 acesso requer protocolo OPSEC (`/checklist-opsec`)
│   • Hash MD5 detectado — preferir SHA-256 se disponível
└─ Ausências notáveis:
    • Nenhum username detectado — considerar se operador usa handle não listado no texto

## ▶ Próximas ações recomendadas
1. `/mapear-pivos` sobre [IOC prioritário]
2. `/consultar-toolkit` para [categoria dominante]
3. `/grafo-conexoes` se múltiplos clusters identificados
```

## Regras

- **NUNCA** clique em URL extraída nem acesse domínio/onion — apenas catalogue.
- **SEMPRE** ofereça versão **defanged** como padrão (evita clique acidental por quem consome o relatório).
- **NUNCA** gere IOC sintético / de exemplo no output final — apenas os do texto de entrada.
- **Se o texto contiver CSAM** (URLs, hashes, nomes de arquivos indicativos): **NÃO catalogue** — ative Protocolo CSAM de `AGENTS.md`.
- **Para hashes de MD5/SHA-1 antigos**: indique que são legados mas pode haver valor arqueológico (campanhas antigas); preferência por SHA-256.
- **Valide checksums** quando possível (CPF, CNPJ, IMEI, BTC legacy) — flag de placeholder vs. real.
- **Privacidade:** se o usuário colar dados pessoais reais (CPF/nome/endereço), alerte sobre LGPD e pergunte se há respaldo processual.
