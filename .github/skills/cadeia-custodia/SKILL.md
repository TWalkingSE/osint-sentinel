---
name: cadeia-custodia
description: >
  Produzir tabela formal de cadeia de custódia digital com SHA-256, método de
  coleta, operador responsável e procedimento de verificação de integridade.
  Use quando o usuário tiver evidências digitais que precisam ser
  documentadas para laudo pericial, IPL ou processo judicial. Pode ser skill
  standalone ou integrado ao /gerar-relatorio (Apêndice A). Corresponde à
  Ação F do system prompt v1.0. Exemplos: "monta cadeia de custódia desses
  arquivos", "preciso formalizar a preservação", "gera tabela SHA-256".
---

# Cadeia de Custódia Digital (Ação F)

## Quando usar

- Qualquer evidência digital precisa ser documentada formalmente
- Laudo pericial, IPL, representação, processo judicial
- Integração com `/gerar-relatorio` como Apêndice A
- Preservação feita via SingleFile / Hunchly / wget / screenshot / export de API

## Protocolo

### 1. Solicite a lista de arquivos/evidências

Para cada item, colete:

| Campo | Descrição | Exemplo |
|---|---|---|
| **Nome do arquivo** | Nome exato (com extensão) | `site_fraudulento.html` |
| **Origem** | URL, dispositivo, sistema, API | `https://alvo.com (via SingleFile)` |
| **Data/hora UTC** | Timestamp de coleta em UTC | `2026-04-19T14:22:03Z` |
| **Método de coleta** | Ferramenta + procedimento | `SingleFile + sha256sum` |
| **Operador responsável** | Nome + matrícula | `Delegado J. Silva / DPF-123` |
| **Local da coleta** | Estação, rede, VM | `VM OSINT-01, VPN institucional` |
| **SHA-256** | Hash do arquivo | `a1b2c3...` |

### 2. Oriente geração do hash

Se o usuário ainda não calculou:

**Linux / macOS / WSL:**
```bash
sha256sum arquivo.ext
```

**Windows PowerShell:**
```powershell
Get-FileHash -Algorithm SHA256 .\arquivo.ext | Format-List
```

**Em lote (todos os arquivos de um diretório):**
```bash
# Linux
find ./evidencias -type f -exec sha256sum {} \; > cadeia-custodia.txt
```
```powershell
# PowerShell
Get-ChildItem .\evidencias -Recurse -File |
  Get-FileHash -Algorithm SHA256 |
  Select-Object Algorithm, Hash, Path |
  Export-Csv .\cadeia-custodia.csv -NoTypeInformation -Encoding UTF8
```

### 3. Entregue tabela formal

Pronta para laudo. Use artifact markdown se Claude Code.

### 4. Inclua procedimento de verificação de integridade

Como a autoridade destinatária confere que o arquivo não foi alterado.

## Formato de saída obrigatório

```markdown
# 📎 CADEIA DE CUSTÓDIA DIGITAL

**Procedimento:** [IPL nº / PIC nº / auto de apreensão]
**Data de geração deste documento:** [UTC]
**Operador responsável pela coleta:** [nome / matrícula]
**Local / ambiente de coleta:** [estação / VM / rede]

---

## Itens preservados

| # | Arquivo | Origem | Data/Hora UTC | Método | SHA-256 | Operador |
|---|---|---|---|---|---|---|
| 1 | site_fraudulento.html | https://alvo.com (via SingleFile) | 2026-04-19T14:22:03Z | SingleFile + sha256sum | a1b2c3... | [nome] |
| 2 | screenshot-01.png | Navegador Firefox hardened | 2026-04-19T14:22:30Z | Captura manual + sha256sum | d4e5f6... | [nome] |
| 3 | ... |

---

## 🔒 Procedimento de verificação de integridade

### Geração do hash
```bash
# Linux / WSL
sha256sum arquivo.ext

# Windows PowerShell
Get-FileHash -Algorithm SHA256 .\arquivo.ext
```

### Verificação pela autoridade destinatária
```bash
# Linux / WSL
echo "[HASH]  arquivo.ext" | sha256sum -c -

# Windows PowerShell
(Get-FileHash -Algorithm SHA256 .\arquivo.ext).Hash -eq "[HASH]"
```

### Armazenamento seguro
- **Mídia criptografada** recomendada: VeraCrypt (KB §19.5 em `references/19-opsec.md`)
- **Carimbo de tempo** externo: servidor NTP autoritativo (`pool.ntp.org`, `a.ntp.br`) ou cartório digital
- **Para imagens forenses de dispositivo:** uso de **write-blocker** obrigatório conforme `references/25-processo-penal-cadeia-custodia.md`
- **Backup redundante:** cópia em segundo meio físico, também com hash e cadeia documentada

---

## ⚖️ Base legal

- **CPP art. 158-A a 158-F** — cadeia de custódia de vestígios (aplicável analogicamente ao meio digital)
- **CPC art. 369** — admissibilidade de prova digital
- **Marco Civil da Internet art. 10–15** — preservação de registros de acesso
- **Lei 12.965/2014** — diretrizes gerais
- Ver detalhamento em `references/25-processo-penal-cadeia-custodia.md`

---

## Observações da coleta
[Registros de OPSEC, condições do ambiente, ausências/limitações, incidentes
durante a coleta. Ex: "Acesso ao alvo sempre via Wayback Machine; site original
foi derrubado em [data]; preservação feita a partir do snapshot de [data UTC]."]

---

*Cadeia de custódia conforme metodologia KB OSINT v3.0/2026, §19.4 e §25.1.*
```

## Regras

- **NUNCA** gere tabela sem **todos** os campos críticos (nome, origem, UTC, método, SHA-256, operador). Se faltar, pergunte.
- **NUNCA** sugira MD5 ou SHA-1 como hash primário — sempre SHA-256 (ou SHA-512 em casos específicos).
- **SEMPRE** inclua procedimento de verificação que a autoridade destinatária pode rodar.
- **SEMPRE** timestamp em UTC (Z), nunca horário local sem offset.
- **Para dispositivos físicos apreendidos** (pendrive, HD, celular): write-blocker obrigatório. Se usuário não souber, redirecione para `references/25-processo-penal-cadeia-custodia.md`.
- **Para Claude Code:** entregar como artifact markdown com filename `cadeia-custodia-[proc].md` + versão CSV em `templates/cadeia-custodia.csv`.
- **Nunca** documente como evidência material que seja CSAM — aplique Protocolo CSAM imediatamente.
