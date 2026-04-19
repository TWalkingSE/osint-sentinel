---
name: checklist-opsec
description: >
  Gerar checklist de OPSEC pré-operação proporcional ao risco (BAIXO / MÉDIO /
  ALTO / CRÍTICO) para operações sensíveis — dark web, sockpuppet,
  monitoramento de alvo, acesso a fórum criminal, contato com threat actor.
  Corresponde à Ação G do system prompt v1.0. Use antes de qualquer operação
  que possa expor a identidade do investigador ou vazar metadata
  institucional. Exemplos: "vou acessar .onion, me dá checklist", "OPSEC
  para operar sockpuppet autorizado", "checklist antes de monitorar alvo".
---

# Checklist OPSEC Pré-Operação (Ação G)

## Quando usar

- Antes de operações sensíveis: dark web, sockpuppet, monitoramento, fórum criminal, contato com threat actor
- Complementa planejamento (`/planejar-investigacao`) e técnicas (`/tecnica-especifica`)
- Fase transversal do ciclo (sempre aplicável)

## Protocolo

### 1. Classifique o risco da operação

| Nível | Características | Exemplos |
|---|---|---|
| **BAIXO** | Consulta em ferramenta pública sem alvo identificado | WHOIS, Wayback, Google dorks |
| **MÉDIO** | Pesquisa em plataforma com login / conta operacional | Shodan, VirusTotal, IntelX, SOCMINT |
| **ALTO** | Acesso a infraestrutura adversária passiva | .onion, forums criminais (lurk only) |
| **CRÍTICO** | Interação ativa com alvo ou sockpuppet | Elicitação, sockpuppet ativo, HUMINT digital |

### 2. Monte checklist proporcional (KB §19)

- **BAIXO:** VPN institucional + navegador hardened + SingleFile
- **MÉDIO:** tudo de BAIXO + VM dedicada + conta operacional
- **ALTO:** tudo de MÉDIO + Tails/Whonix + Tor + snapshot da VM
- **CRÍTICO:** tudo de ALTO + autorização judicial + procedimento institucional + supervisão + log de ações

### 3. Identifique pontos específicos de vazamento da operação

Ex: se a operação envolve Shodan, logar em conta pessoal vaza metadata.

### 4. Inclua procedimento de encerramento e abortar

## Formato de saída obrigatório

```markdown
# 🔒 CHECKLIST OPSEC PRÉ-OPERAÇÃO

**Operação:** [descrição resumida]
**Classificação de risco:** [BAIXO / MÉDIO / ALTO / CRÍTICO]
**Autorização processual:** [IPL / PIC / decisão judicial nº]
**Operador:** [nome / matrícula]
**Coordenação:** [supervisor / equipe]
**Data prevista:** [UTC]

---

## REDE
- ☐ VPN institucional ativa ou Tor (conforme risco)
- ☐ IP de origem não vinculado à organização (exit node diferente do bloco institucional)
- ☐ DNS resolvido fora da rede institucional (ex: 1.1.1.1 via WireGuard dedicado)
- ☐ WebRTC desabilitado (vaza IP real mesmo com VPN)
- ☐ IPv6 desabilitado ou roteado via mesmo túnel (evita leak)

## DISPOSITIVO
- ☐ VM dedicada **criada especificamente para esta operação**
- ☐ Snapshot da VM tirado **antes** de iniciar (rollback pós-operação)
- ☐ Nenhuma credencial pessoal salva na VM (sem SSO, sem gerenciador de senhas pessoal)
- ☐ Clipboard isolado (extensões ou configuração de hipervisor)
- ☐ SO proporcional: Kali/Parrot (médio), Tails (alto), Whonix (crítico)
- ☐ Câmera e microfone cobertos/desabilitados
- ☐ Horário do sistema em UTC (evita inferência de fuso por timestamp)

## IDENTIDADE
- ☐ Conta operacional, **nunca** pessoal ou institucional real
- ☐ Se sockpuppet (operações ALTO/CRÍTICO):
  - ☐ Histórico compatível (posts, conexões, idade da conta — KB §17.2)
  - ☐ Foto de perfil gerada por IA (nunca imagem real de terceiro)
  - ☐ Autorização processual específica (Lei 12.850 art. 10-A)
  - ☐ Documento de aprovação anexado ao IPL/PIC
- ☐ E-mail dedicado (ProtonMail/Tutanota operacional)
- ☐ Número de telefone descartável (se necessário — nunca pessoal)

## NAVEGADOR
- ☐ Firefox hardened com `privacy.resistFingerprinting=true`
- ☐ uBlock Origin + NoScript + ClearURLs + SingleFile instalados
- ☐ Modo privativo padrão
- ☐ Cookies isolados por container (Multi-Account Containers)
- ☐ Nenhuma extensão de produtividade pessoal

## EVIDÊNCIA
- ☐ Hunchly / SingleFile configurado para captura automática
- ☐ Diretório de destino criptografado (VeraCrypt)
- ☐ Script de hash SHA-256 pronto para rodar pós-captura
- ☐ Planilha de cadeia de custódia aberta (ver `/cadeia-custodia`)
- ☐ Timestamp UTC ativo no OS
- ☐ Nunca capturar CSAM — se aparecer, ativar **Protocolo CSAM**

## COMUNICAÇÃO
- ☐ Signal para coordenação interna (nunca WhatsApp pessoal)
- ☐ Canal seguro com supervisor/coordenador
- ☐ Checkpoint de "vivo e sem incidente" definido (ex: a cada 30 min)

## PARA OPERAÇÕES ALTO/CRÍTICO
- ☐ Autorização judicial específica **anexada**
- ☐ Supervisor ciente e em linha de comunicação
- ☐ Equipe legal/jurídica institucional informada
- ☐ Critérios de abortar definidos (ex: identificação do operador, suspeita de contra-inteligência)
- ☐ Não interagir com usuários não alvo (dano colateral)
- ☐ Não fazer download de material de origem suspeita (malware/CSAM)

## ENCERRAMENTO
- ☐ Procedimento de logout documentado (sem deletar histórico — evidência)
- ☐ Captura final da sessão (Hunchly export)
- ☐ Snapshot da VM **antes do rollback** preservado
- ☐ Rollback do snapshot inicial
- ☐ Relatório OPSEC da sessão (log de ações, entidades contatadas, incidentes)
- ☐ Notificação ao coordenador da operação
- ☐ Hashes gerados e cadeia de custódia fechada

## CRITÉRIOS DE ABORTAR (aplicar a qualquer momento se ocorrer)
- 🛑 Suspeita de identificação do operador pelo alvo
- 🛑 Exposição acidental de dado institucional
- 🛑 CSAM ou conteúdo proibido por protocolo
- 🛑 Contato com vítima identificável (dano colateral)
- 🛑 Falha técnica (VPN caiu, VM comprometida) → rollback imediato

---

⚖️ **Base legal desta operação:** [dispositivos aplicáveis]
📎 **Documentação pós-operação:** ver `/cadeia-custodia` e `/gerar-relatorio`
```

## Regras

- **NUNCA** gere checklist sem identificar a **classificação de risco**.
- **NUNCA** trate operação CRÍTICO como se fosse MÉDIO — nível de OPSEC deve ser proporcional.
- **Para sockpuppet:** **sempre** exija autorização judicial específica (Lei 12.850 art. 10-A) antes de detalhar configuração. Se o usuário não tiver, redirecione para `/analise-juridica`.
- **Para operações em dark web:** reforce `references/11-dark-web-deep-web.md §11.5` (protocolo de acesso a fórum criminal).
- **Para CSAM:** ativar Protocolo CSAM de `AGENTS.md` imediatamente — não incluir "capturar material" no checklist.
- **Ambiente institucional:** nunca operar de estação principal do investigador. VM dedicada sempre.
