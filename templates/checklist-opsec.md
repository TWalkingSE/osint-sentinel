# 🔒 CHECKLIST OPSEC PRÉ-OPERAÇÃO

> Template preenchível. Gerar idealmente via `/checklist-opsec` (gera versão calibrada ao risco). Adaptar ao caso concreto.

---

## Identificação

| Campo | Valor |
|---|---|
| **Operação** | `[descrição resumida]` |
| **Classificação de risco** | ☐ BAIXO · ☐ MÉDIO · ☐ ALTO · ☐ CRÍTICO |
| **Autorização processual** | `[IPL / PIC / decisão judicial nº]` |
| **Operador** | `[nome / matrícula]` |
| **Coordenação** | `[supervisor / equipe]` |
| **Data prevista** | `YYYY-MM-DDTHH:MM:SSZ` (UTC) |

---

## REDE

- ☐ VPN institucional ativa ou Tor (conforme risco)
- ☐ IP de origem não vinculado à organização
- ☐ DNS resolvido fora da rede institucional
- ☐ WebRTC desabilitado (vaza IP real)
- ☐ IPv6 desabilitado ou roteado pelo mesmo túnel (evita leak)

## DISPOSITIVO

- ☐ VM dedicada **criada especificamente para esta operação**
- ☐ Snapshot da VM tirado **antes** de iniciar (rollback pós-operação)
- ☐ Nenhuma credencial pessoal salva na VM
- ☐ Clipboard isolado (extensões ou configuração de hipervisor)
- ☐ SO proporcional: Kali/Parrot (médio), Tails (alto), Whonix (crítico)
- ☐ Câmera e microfone cobertos/desabilitados
- ☐ Horário do sistema em UTC

## IDENTIDADE

- ☐ Conta operacional, **nunca** pessoal ou institucional real
- ☐ Se sockpuppet (operações ALTO/CRÍTICO):
  - ☐ Histórico compatível (posts, conexões, idade da conta)
  - ☐ Foto de perfil gerada por IA (nunca imagem real de terceiro)
  - ☐ Autorização processual específica (Lei 12.850 art. 10-A)
  - ☐ Documento de aprovação anexado ao IPL/PIC
- ☐ E-mail dedicado (ProtonMail/Tutanota operacional)
- ☐ Número de telefone descartável se necessário

## NAVEGADOR

- ☐ Firefox hardened com `privacy.resistFingerprinting=true`
- ☐ uBlock Origin + NoScript + ClearURLs + SingleFile
- ☐ Modo privativo padrão
- ☐ Cookies isolados por container (Multi-Account Containers)
- ☐ Nenhuma extensão de produtividade pessoal

## EVIDÊNCIA

- ☐ Hunchly / SingleFile configurado para captura automática
- ☐ Diretório de destino criptografado (VeraCrypt)
- ☐ Script de hash SHA-256 pronto para rodar pós-captura
- ☐ Planilha de cadeia de custódia aberta (`templates/cadeia-custodia.md`)
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
- ☐ Critérios de abortar definidos
- ☐ Não interagir com usuários não alvo (dano colateral)
- ☐ Não fazer download de material de origem suspeita

## ENCERRAMENTO

- ☐ Procedimento de logout documentado
- ☐ Captura final da sessão (Hunchly export)
- ☐ Snapshot da VM **antes do rollback** preservado
- ☐ Rollback do snapshot inicial
- ☐ Relatório OPSEC da sessão (log de ações)
- ☐ Notificação ao coordenador da operação
- ☐ Hashes gerados e cadeia de custódia fechada

## CRITÉRIOS DE ABORTAR (aplicar a qualquer momento)

- 🛑 Suspeita de identificação do operador pelo alvo
- 🛑 Exposição acidental de dado institucional
- 🛑 CSAM ou conteúdo proibido por protocolo
- 🛑 Contato com vítima identificável (dano colateral)
- 🛑 Falha técnica (VPN caiu, VM comprometida) → rollback imediato

---

⚖️ **Base legal desta operação:** `[dispositivos aplicáveis]`
📎 **Documentação pós-operação:** `/cadeia-custodia` e `/gerar-relatorio`

---

*Checklist conforme metodologia OSINT-Sentinel v1.0 (Ação G) e KB OSINT v3.0/2026 §19.*
