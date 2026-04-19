# 📎 CADEIA DE CUSTÓDIA DIGITAL

> Template preenchível — baseado no system prompt OSINT-Sentinel v1.0 (Ação F) e KB OSINT v3.0/2026 §19.4 e §25.1.
> Remova este cabeçalho ao colar em IPL/laudo.

---

## Identificação

| Campo | Valor |
|---|---|
| **Procedimento** | IPL nº `[preencher]` / PIC nº `[preencher]` / Auto de apreensão nº `[preencher]` |
| **Data de geração deste documento** | `YYYY-MM-DDTHH:MM:SSZ` (UTC) |
| **Operador responsável pela coleta** | `[nome / matrícula / cargo]` |
| **Local / ambiente de coleta** | `[estação / VM / rede institucional]` |
| **Rede de origem** | `[VPN institucional / rede segregada]` |
| **Supervisor / coordenador** | `[nome / matrícula]` |

---

## Itens preservados

| # | Arquivo | Origem | Data/Hora UTC | Método | SHA-256 | Operador | Observação |
|---|---------|--------|---------------|--------|---------|----------|------------|
| 1 | `site_fraudulento.html` | `https://alvo.com` (via SingleFile) | `2026-04-19T14:22:03Z` | SingleFile 1.x + `sha256sum` | `a1b2c3...` | `[nome]` | Página de login falso |
| 2 | `screenshot-01.png` | Navegador Firefox hardened | `2026-04-19T14:22:30Z` | Captura manual + `sha256sum` | `d4e5f6...` | `[nome]` | Tela de pagamento |
| 3 | | | | | | | |

---

## 🔒 Procedimento de verificação de integridade

### Geração do hash

**Linux / WSL / macOS:**
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

### Verificação pela autoridade destinatária

**Linux / WSL:**
```bash
echo "[HASH-SHA256]  arquivo.ext" | sha256sum -c -
# Saída esperada: "arquivo.ext: OK"
```

**Windows PowerShell:**
```powershell
$expected = "[HASH-SHA256]"
$actual   = (Get-FileHash -Algorithm SHA256 .\arquivo.ext).Hash
if ($actual -eq $expected) { "OK" } else { "FALHA - integridade comprometida" }
```

---

## 🗄️ Armazenamento seguro

| Aspecto | Procedimento |
|---|---|
| **Mídia criptografada** | VeraCrypt (`references/19-opsec.md §19.5`) ou LUKS (Linux) |
| **Backup redundante** | Segundo meio físico, também com hash e cadeia separada |
| **Carimbo de tempo externo** | Servidor NTP autoritativo (`pool.ntp.org`, `a.ntp.br`) ou cartório digital |
| **Para dispositivos físicos** | Write-blocker obrigatório (`references/25-processo-penal-cadeia-custodia.md`) |
| **Acesso** | Somente operador e supervisor, mediante registro em planilha de acessos |

---

## ⚖️ Base legal

| Dispositivo | Aplicação |
|---|---|
| **CPP art. 158-A a 158-F** | Cadeia de custódia de vestígios (aplicável analogicamente ao meio digital) |
| **CPC art. 369** | Admissibilidade de prova digital |
| **Marco Civil da Internet (Lei 12.965/2014)** art. 10–15 | Preservação de registros de conexão e de acesso a aplicações |
| **LGPD (Lei 13.709/2018)** art. 7º e 46 | Base legal de tratamento e segurança |
| `references/25-processo-penal-cadeia-custodia.md` | Detalhamento técnico-forense |

---

## 📝 Observações da coleta

`[Registre condições do ambiente, limitações encontradas, ausências de dados esperados, incidentes durante a coleta.]`

Exemplos:
- `"Acesso ao alvo sempre via Wayback Machine; site original foi derrubado em 2026-04-15T00:00:00Z; preservação feita a partir do snapshot de 2026-04-14T22:10:03Z."`
- `"Captura feita em VM dedicada, snapshot preservado antes e depois da operação."`
- `"Operador atuou sob supervisão de [nome/matrícula] durante toda a coleta."`

---

## Assinatura

`[Nome do operador]`
`[Matrícula / cargo]`
Data UTC: `[YYYY-MM-DDTHH:MM:SSZ]`

`[Nome do supervisor]`
`[Matrícula / cargo]`
Data UTC: `[YYYY-MM-DDTHH:MM:SSZ]`

---

*Cadeia de custódia conforme metodologia OSINT-Sentinel v1.0 / KB OSINT v3.0/2026.*
