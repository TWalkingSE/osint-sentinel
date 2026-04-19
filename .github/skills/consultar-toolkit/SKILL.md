---
name: consultar-toolkit
description: >
  Listar ferramentas OSINT acionáveis por categoria ou identificador, com
  separação gratuita/paga, web/CLI e recomendação priorizada. Use quando o
  usuário souber a categoria (ex: "toolkit para e-mail", "ferramentas de
  favicon hash") ou informar um identificador sem pedir técnica passo a passo.
  Corresponde à Ação B do system prompt v1.0, Fase 2 (Coleta). Exemplos:
  "quais ferramentas para investigar IP?", "me lista tudo que tem para
  SOCMINT Instagram", "toolkit para wallet BTC".
---

# Consultar Toolkit (Ação B — Fase 2: Coleta)

## Quando usar

- Usuário quer **lista de ferramentas** por categoria, não passo a passo (esse é `/tecnica-especifica`)
- Identificador conhecido mas sem diligência definida
- Para comparação rápida entre ferramentas da mesma categoria

## Protocolo

1. Identifique a **categoria** (1–28 da KB) ou use o **roteamento por identificador** (ver abaixo)
2. Abra **APENAS** o arquivo `references/NN-*.md` correspondente
3. Liste ferramentas separando por:
   - **Gratuita** vs. **paga**
   - **Web** vs. **CLI/Linux**
   - **Subcategoria** (ex: verificação, enriquecimento, breach, WHOIS reverso)
4. Para cada ferramenta documente: **URL oficial**, **o que extrai**, **quando escolher vs. alternativa**
5. Finalize com **2–3 ferramentas prioritárias** para o caso concreto do usuário

## Roteamento por identificador (atalho)

| Identificador do usuário | Arquivo a abrir |
|---|---|
| E-mail, cabeçalho, breach | `references/01-email.md` |
| Telefone, CPF, CNPJ, IMEI | `references/02-telefone-cpf-cnpj-imei.md` |
| IP, CGNAT, ASN | `references/03-ip.md` |
| Domínio, DNS, Wayback | `references/04-dominio-infraestrutura-web.md` |
| Username | `references/05-usernames-identidades-digitais.md` |
| Imagem / vídeo / EXIF | `references/06-imagens-videos-imint.md` + `10-metadados.md` |
| Geolocalização | `references/07-geolocalizacao-geoint.md` |
| Rede social | `references/08-redes-sociais-socmint.md` |
| Wallet cripto | `references/09-criptoativos.md` |
| .onion | `references/11-dark-web-deep-web.md` |
| Favicon | `references/12-favicons.md` |
| Placa / voo / embarcação | `references/13-veiculos-placas-transporte.md` |
| Hash de malware | `references/15-infraestrutura-rede-threat-intel.md` |

## Formato de saída

```markdown
## Toolkit — [categoria] (KB §[N])

### Gratuitas / Web
| Ferramenta | URL | Extrai | Observação |
|---|---|---|---|
| ... |

### Gratuitas / CLI
| Ferramenta | Repo/URL | Comando base | Observação |
|---|---|---|---|
| ... |

### Pagas (com versão gov./institucional)
| Ferramenta | URL | Diferencial | Quando compensar |
|---|---|---|---|
| ... |

---

### 🎯 RECOMENDAÇÃO PRIORIZADA (para seu caso)
1. **[Ferramenta 1]** — primeira diligência porque [motivo operacional]
2. **[Ferramenta 2]** — segunda, complementar porque [motivo]
3. **[Ferramenta 3]** — reserva / confirmação cruzada

▶ PRÓXIMA AÇÃO: `/tecnica-especifica` da ferramenta 1 ou `/mapear-pivos` se já tiver output.
```

## Regras

- **NUNCA** liste ferramenta que não está no arquivo `references/` correspondente.
- **NUNCA** invente URL — copie literalmente do arquivo de referência.
- **SEMPRE** marque 🟢 (passivo), 🟡 (requer autorização) ou 🔴 (restrita) ao lado da ferramenta quando a KB indicar.
- **Ignore painéis clandestinos** (não listados na KB v3.0/2026). Se o usuário pedir, redirecione para `references/02-telefone-cpf-cnpj-imei.md §2.1.7` (painéis legítimos) e `27-paineis-clandestinos-persecucao.md` (lado da persecução).
- **Para ferramentas dual-use** (reconhecimento facial, recuperação de senha, WhatsApp Web em alvo), inclua aviso de autorização antes de listar.
- **Priorize** ferramentas com cobertura brasileira quando o caso for BR (Registro.br, Receita Federal, Anatel, etc.).
