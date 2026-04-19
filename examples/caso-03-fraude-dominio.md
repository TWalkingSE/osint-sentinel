# Caso 03 — Fraude por Clonagem de Domínio (CGNAT + Favicon Hash)

> **Fictício.** Ilustra o fluxo Ação A → C (favicon hash + CGNAT) → D → E, com foco em pivôs técnicos (threat intel / infraestrutura). Perfil analista threat intel / perito.

---

## Briefing

**Perfil do usuário:** Analista de threat intel de SOC institucional (aplicado a caso aberto por PF).
**Entrada no chat:**

> "IPL PF nº 0789/2026 — phishing dirigido contra clientes do Banco XYZ. Campanha multi-onda. Tenho: 3 domínios clones (`bancoxyz-secure.example`, `xyzbanco-cliente.example`, `banco-xyz.example`), 1 IP de origem do primeiro acesso malicioso (`203.0.113.42`, timestamp `2026-04-15T19:23:47Z`), e uma lista de 47 hashes SHA-256 de arquivos de kit de phishing. Monta a investigação."

**Identificação automática:**
- Perfil: threat intel → calibração técnica/infraestrutura
- Respaldo legal: IPL PF ✅
- **Múltiplos identificadores técnicos** (3 domínios, IP + UTC, 47 hashes)
- Cenário ideal para pivôs de infraestrutura e consolidação em grafo

---

## Passo 1 — `/planejar-investigacao`

```
📋 PLANO DE INVESTIGAÇÃO OSINT

Caso: IPL PF nº 0789/2026 — Campanha de phishing contra Banco XYZ
Natureza: CP art. 171 §2º-A (fraude eletrônica, Lei 14.155/2021) + Lei 12.737/2012
Respaldo legal: IPL PF em curso ✅
Perfil do analista: Threat intel / SOC
Fase do ciclo: 1 — Planejamento

🎯 HIPÓTESES
H1: Operador solo com kit genérico reutilizado — BAIXA (3 domínios + 47 hashes é volume incompatível)
H2: Grupo organizado com infraestrutura recorrente — ALTA (hipótese de trabalho principal)
H3: Affiliate de operação maior (PaaS — Phishing as a Service) — MÉDIA

🔍 PLANO DE COLETA

FASE A — Passivo (infraestrutura)
 1. /ioc-extractor nos 3 domínios + hashes (já organizados)
 2. WHOIS nos 3 domínios — Registro.br, Whoxy, DomainTools (references/04-*.md §4.1)
 3. crt.sh — certificados + subdomínios dos 3 (references/04-*.md §4.8)
 4. Favicon hash de cada domínio (references/12-favicons.md) — consolidar operador único
 5. Passive DNS — SecurityTrails, Circl.lu (references/03-*.md §3.7)
 6. Reverse IP nos IPs de hospedagem (references/03-*.md §3.3)
 7. VirusTotal + MalwareBazaar + Any.run nos 47 hashes (references/15-*.md §15.1)
 8. Verificar TTP via MITRE ATT&CK (references/23-*.md)

FASE B — Pivô por IP (203.0.113.42, UTC 2026-04-15T19:23:47Z)
 9. IPInfo + Shodan + GreyNoise (references/03-*.md §3.1, §3.4)
10. Determinar se é IP brasileiro e se CGNAT — se CGNAT, preparar ofício com porta lógica
11. Reputação — AbuseIPDB, CriminalIP (references/03-*.md §3.1)
12. Domínios no mesmo IP — Reverse IP (§3.3)

FASE C — Preservação e ofícios
13. Todos os 3 domínios em URLScan + Wayback ANTES de qualquer análise ativa
14. Ofício ao registrador dos domínios (dados cadastrais)
15. Ofício à hospedagem (registros de acesso)
16. Ofício ao ISP brasileiro com IP + porta + timestamp UTC (CGNAT)
17. VirusTotal Enterprise (se disponível) para consultar regras/YARA correlatas

⚖️ AUTORIZAÇÕES
- Todas as técnicas da FASE A/B são 🟢 passivas
- Scraping em escala dos sites clones → 🟡 (ver /analise-juridica se for executar crawler)
- Varredura ativa (Shodan já provê dados passivos; evitar nmap contra IP sem autorização específica)

🔒 OPSEC
- VM Kali/Parrot dedicada
- VPN institucional ou Tor (para Shodan, usar conta operacional)
- Não acessar domínios clones diretamente — usar URLScan/sandbox
- Hunchly ligado em toda a investigação
- Clock UTC no OS

▶ PRÓXIMA AÇÃO SUGERIDA
Executar /ioc-extractor no bloco de dados + FASE A em paralelo (itens 2–8). Depois /mapear-pivos técnicos.
```

---

## Passo 2 — `/ioc-extractor` consolida

O usuário cola os 3 domínios + 47 hashes + IP. O assistente retorna:

```
🎯 IOCs EXTRAÍDOS

Total de IOCs únicos: 51
Defanging aplicado: sim

IPv4:
| # | Valor | Ocorrências | Ação recomendada |
|---|---|---|---|
| 1 | 203.0.113.42 (203.0.113[.]42) | 1 | /consultar-toolkit → references/03-ip.md |

Domínios (3):
| # | Valor | Ação |
|---|---|---|
| 1 | bancoxyz-secure[.]example | WHOIS + crt.sh + favicon hash |
| 2 | xyzbanco-cliente[.]example | idem |
| 3 | banco-xyz[.]example | idem |

Hashes (47 SHA-256): todos com comprimento válido, checksum não verificável offline.

📊 Síntese
├─ Clusters: infraestrutura ([3 domínios + 1 IP]) | arquivos ([47 hashes])
├─ Pivô prioritário: favicon hash dos 3 domínios — maior valor de consolidação
└─ Próxima ação: /tecnica-especifica favicon hash + /mapear-pivos cada hash no VirusTotal
```

---

## Passo 3 — `/tecnica-especifica` favicon hash em bulk

Para os 3 domínios:

```bash
# 1. Baixar favicons via Google (evita tocar nos alvos)
for dom in bancoxyz-secure.example xyzbanco-cliente.example banco-xyz.example; do
  curl -s -o "${dom}.ico" "https://www.google.com/s2/favicons?domain=${dom}&sz=64"
done

# 2. Calcular hash (Python)
python3 - <<'EOF'
import mmh3, base64, os
for f in sorted(os.listdir('.')):
    if f.endswith('.ico'):
        with open(f, 'rb') as fh:
            content = fh.read()
        b64 = base64.encodebytes(content)
        h = mmh3.hash(b64)
        print(f"{f}: {h}")
EOF
```

Resultado (fictício):
- `bancoxyz-secure.example.ico`: `-1234567890`
- `xyzbanco-cliente.example.ico`: `-1234567890`
- `banco-xyz.example.ico`: `-1234567890`

**Hash idêntico nos 3 — INFERÊNCIA ALTO: mesmo operador.**

Query Shodan:
```
http.favicon.hash:-1234567890
```
→ 22 matches adicionais, **INFERÊNCIA MÉDIO-ALTO** de que existem mais 22 domínios/IPs da mesma família de phishing.

---

## Passo 4 — `/tecnica-especifica` CGNAT

Para o IP `203.0.113.42` com timestamp `2026-04-15T19:23:47Z`:

1. **Consulta passiva** em IPInfo: ISP = operadora brasileira `OperaX`, cidade = São Paulo
2. **WHOIS Registro.br**: bloco de IPs atribuído à `OperaX` como operadora móvel 4G
3. **Interpretação:** 4G no Brasil usa CGNAT por padrão (RFC 6888)
4. **Ação:** ofício à `OperaX` com **IP público + porta + timestamp UTC** usando `templates/oficio-provedor-conexao-cgnat.md`

O assistente destaca:

> ⚠️ **Verifique a porta lógica no ofício ao provedor de aplicação (plataforma onde ocorreu o acesso — ex: site clonado)**. Sem ela, a `OperaX` não identifica o assinante em CGNAT.

---

## Passo 5 — `/mapear-pivos` para cada hash

Primeiros 5 hashes (exemplo):

| Hash (últimos 8) | VirusTotal | MalwareBazaar | Any.run | Família inferida |
|---|---|---|---|---|
| `...a1b2c3d4` | 58/72 detect | Presente | Sandbox run | Agent Tesla variante |
| `...e5f6g7h8` | 12/72 detect | Ausente | Rotina de exfiltração | Kit de phishing (HTML+PHP) |
| `...` | | | | |

**INFERÊNCIA ALTO:** Campanha combina infostealer (Agent Tesla) + kit de phishing bancário para credenciais. TTP consistente com grupo **TA558 / similares** (ver MITRE ATT&CK via `references/23-*.md`).

---

## Passo 6 — `/grafo-conexoes` consolida 47+22=69 entidades

Cluster principal:
- 25 domínios (3 iniciais + 22 do Shodan) com mesmo favicon
- 18 IPs únicos de hospedagem (várias regiões, ASNs mistos)
- 1 endereço IPv4 do cliente (203.0.113.42) — vítima potencial #1
- 47 artefatos (hashes de binários e arquivos web)

Export Mermaid anexado ao relatório.

---

## Passo 7 — `/analise-contraditoria` antes de fechar

Teste de H2 (grupo organizado):
- **Sustentam:** favicon hash comum, 25 domínios, kit com infostealer complexo, infraestrutura multi-ASN
- **Contradizem:** nenhum sinal de C2 centralizado (cada domínio parece exfiltrar separadamente)
- **Contra-hipótese H2-alt:** affiliate model (PaaS) — operador central vende kit + infra para múltiplos operadores regionais
  - Fato que a H2-alt explica melhor: exfiltração descentralizada + domínios com WHOIS de registrantes distintos
- **Viés identificado:** âncora em "grupo organizado monolítico" (narrativa dominante em reports de threat intel)
- **Teste discriminante:** analisar destinos de exfiltração dos 47 hashes (Any.run + VirusTotal). Se convergem para poucos servidores → grupo monolítico. Se divergem para muitos → PaaS affiliate.

Resultado (fictício): divergência — **H2-alt reforçada, H2 original enfraquecida**. Ranking atualizado: H3 > H2-alt > H1.

---

## Passo 8 — `/gerar-relatorio` + `/cadeia-custodia`

Relatório de 13 seções + Apêndice A (cadeia de custódia de todos os artefatos capturados via VT / MalwareBazaar / sandbox run) + Apêndice B (grafo Mermaid exportado).

Recomendações:
1. Alertar Banco XYZ sobre 25 domínios para bloqueio em filtros corporativos
2. Ofício à `OperaX` com IP+porta+UTC
3. Ofício a registradores dos 25 domínios
4. MLAT via DRCI para provedores offshore dos IPs fora do BR (`references/28-*.md`)
5. Compartilhar IOCs via canais institucionais (CERT.br, CTIR Gov) — `references/28-*.md §28.2`

---

## Síntese do fluxo

```
Briefing → /planejar-investigacao (A)
        → /ioc-extractor (consolida IOCs)
        → /tecnica-especifica favicon + CGNAT (C) em paralelo
        → /mapear-pivos hashes (D)
        → /grafo-conexoes (consolida 69 entidades)
        → /analise-contraditoria (I) — refuta H2 monolítico, reforça H2-alt (PaaS)
        → /gerar-relatorio (E) + /cadeia-custodia (F)
        → compartilhamento de IOCs com rede institucional
```

**Aprendizado do caso:**
- Threat intel casos se beneficiam de **consolidação em grafo cedo** — entidades de mesma família viram evidentes
- **Análise contraditória (`/analise-contraditoria`) refina hipótese** antes da entrega — mudou o "enredo" do relatório (grupo → affiliate)
- **CGNAT + porta é crítico** em casos BR — sem a porta, ofício ao ISP é inútil

---

*Caso fictício para ilustração. Em campanhas reais, coordenação com CERT.br e bloqueio rápido dos domínios é tão importante quanto a identificação do operador.*
