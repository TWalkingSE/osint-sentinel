# Caso 02 — Sextortion via Instagram

> **Fictício.** Ilustra o fluxo Ação A → C (WhatsApp Web + recuperação de senha parcial, 🟡) → H (análise jurídica) → E → F, incluindo o gatilho de autorização legal.

---

## Briefing

**Perfil do usuário:** Analista de Inteligência Criminal de MP estadual.
**Entrada no chat:**

> "PIC nº 45/2026 em andamento. Vítima adolescente (16 anos) está sendo extorquida após envio de imagens íntimas. Temos o Instagram do extorsor @exemplo_agressor, WhatsApp `+55 11 99999-XXXX` (usado na ameaça), e o e-mail `exemplo@outlook.example` que a vítima identificou no cabeçalho de uma mensagem. Como identificar o operador?"

**Identificação automática:**
- Natureza: **sextortion com vítima adolescente** → atenção redobrada (ECA)
- Perfil: analista MP → calibração jurídico-operacional
- Respaldo legal: PIC formalizado ✅
- 3 identificadores → múltiplos pivôs disponíveis

**⚠️ Gatilho ECA:** vítima é adolescente (16 anos). **Qualquer material íntimo dela é CSAM (art. 241 ECA)** — não processar, não baixar, não reproduzir. A investigação é contra o **agressor**, não dados da vítima.

---

## Passo 1 — Alerta preliminar obrigatório

O assistente responde primeiro:

> ⚠️ **Alerta — vítima adolescente**
>
> Por envolver menor de 18 anos, esta investigação está sob proteção reforçada:
> - **ECA art. 240–241** — produção/posse/transmissão de material íntimo de adolescente é crime
> - **LGPD art. 14** — tratamento de dados de adolescente requer finalidade específica em interesse do menor
>
> Procedimentos obrigatórios:
> 1. Qualquer material encaminhado pelo extorsor que contenha imagem da vítima deve ser preservado por requisição judicial específica (nunca por download direto pelo analista)
> 2. Se houver conteúdo de abuso explícito, aplicar **Protocolo CSAM** (SaferNet, PF Operação Luz na Infância)
> 3. Vítima e família devem ser orientados por equipe especializada (DCA, DEAM, rede socioassistencial)
>
> Confirme: **nenhum material íntimo da vítima será acessado fora do ambiente controlado pela autoridade policial?** Com essa confirmação, prossigo com a investigação do **agressor**.

---

## Passo 2 — Após confirmação, `/planejar-investigacao`

```
📋 PLANO DE INVESTIGAÇÃO OSINT

Caso: PIC nº 45/2026 — Sextortion contra adolescente
Natureza: CP art. 158 (extorsão) + ECA art. 241 (se houver transmissão de imagens da vítima) + Lei 14.155/2021
Respaldo legal: PIC formalizado ✅
Perfil do analista: Inteligência Criminal MP
Fase do ciclo: 1 — Planejamento

🎯 HIPÓTESES
H1: Operador individual do Brasil (conhece a vítima, oportunista)
H2: Sextortionist em rede (modus operandi repetido, múltiplas vítimas)
H3: Operador internacional com infraestrutura offshore (script de sextortion em massa)

🔍 PLANO DE COLETA

FASE A — Passivo (imediato)
 1. Instagram público do @exemplo_agressor — OSINTgram, Picuki (references/08-*.md §8.1)
    → bio, contagem de seguidores, data de criação, posts iniciais (mais velhos deixam pistas)
 2. Número +55 11 99999-XXXX via ABRTELECOM (operadora) + TrueCaller (references/02-*.md §2.1.1)
    → operadora, nome associado (se público)
 3. E-mail exemplo@outlook.example — Epieos (§1.4), HaveIBeenPwned (§1.6), Whoxy reverso (§1.7)
 4. Imagem da foto de perfil do Instagram — busca reversa Google/Yandex (references/06-*.md §6.2)
    → outras contas com mesma foto (evita PimEyes por enquanto — 🟡 requer decisão judicial)

FASE B — Técnicas 🟡 (requerem confirmação explícita antes)
 5. WhatsApp Web — verificar foto atual e status (references/02-*.md §2.1.4) 🟡
 6. Telegram — adicionar número em conta operacional (§2.1.5) 🟡
 7. Recuperação de senha — login.live.com com e-mail (§1.5) 🟡

FASE C — Ofícios
 8. Meta (Facebook/Instagram) via LEA portal — dados cadastrais de @exemplo_agressor
 9. Microsoft via LEA portal — dados cadastrais de exemplo@outlook.example
10. Operadora — dados cadastrais do número + registros de conexão (IP+porta+UTC)

FASE D — Preservação
11. Hunchly para capturar perfil Instagram datado antes de agressor deletar
12. SingleFile para capturar conversa (se vítima/responsável consentir — evitar reproduzir conteúdo sensível)
13. Cadeia de custódia formal (/cadeia-custodia)

⚖️ AUTORIZAÇÕES NECESSÁRIAS
- Técnicas 🟡 da FASE B: compatibilidade com PIC + proporcionalidade LGPD art. 7º VI (ver /analise-juridica)
- Ofícios MCI art. 10, 15 (FASE C)
- Cooperação internacional via Meta LEA / Microsoft LEA portal (ver references/28-*.md §28.3)
- Se Meta/Microsoft exigirem MLAT, acionar DRCI

🔒 OPSEC
- Conta operacional dedicada no Instagram (nunca a pessoal do analista)
- VM dedicada para todas as consultas
- Não curtir/seguir perfil — apenas visualizar (modo lurk)
- Hunchly configurado antes de abrir qualquer tela do agressor

🛑 LIMITES RÍGIDOS
- NÃO acessar material íntimo da vítima, mesmo que disponível em algum local
- NÃO baixar conteúdo enviado pelo agressor à vítima (preservação via requisição judicial)
- Se em algum momento aparecer CSAM: ativar Protocolo CSAM

▶ PRÓXIMA AÇÃO SUGERIDA
Executar FASE A completa (~2 horas). Antes da FASE B, /analise-juridica das técnicas 🟡.
```

---

## Passo 3 — Após FASE A, usuário pede técnica 🟡

> "A FASE A deu: Instagram criado há 3 meses, 12 seguidores, foto de perfil é avatar genérico. Holehe indica conta ativa em Skype, Spotify, Discord com o mesmo e-mail. Quero usar WhatsApp Web para ver se o número ainda está ativo e pegar foto de perfil atual."

O assistente, por se tratar de técnica 🟡:

> ⚖️ **Esta técnica exige respaldo legal específico. Antes de prosseguir, confirme:**
>
> 1. O PIC nº 45/2026 **ampara explicitamente** diligência de identificação de autor via WhatsApp Web? (recomenda-se memorando/despacho interno citando a proporcionalidade)
> 2. A conta WhatsApp Web a ser usada é **conta operacional dedicada** do órgão (não pessoal do analista, não institucional identificável)?
> 3. A diligência será **documentada como ato investigativo** (print datado + hash, não como consulta casual)?
>
> Sem essa confirmação, não prossigo com a orientação técnica.

---

## Passo 4 — Após confirmação, `/tecnica-especifica`

O assistente guia:

1. Abertura do WhatsApp Web em **conta operacional** em VM dedicada
2. Adição do número `+55 11 99999-XXXX` como **novo contato** (apenas no aparelho operacional)
3. Consulta à lista de conversas **sem enviar mensagem** (modo passivo)
4. Captura de: foto atual, status "visto por último" (se o agressor permitir), recado
5. **Hunchly roda em background** capturando tudo
6. Logout imediato da conta operacional após captura
7. `sha256sum` do HTML capturado pelo Hunchly
8. Registro em planilha de cadeia de custódia

Com bloco obrigatório:

```
📊 SÍNTESE TÉCNICA
├─ FATOS CONFIRMADOS
│   • Técnica WhatsApp Web preserva sigilo operacional (sem notificação ao alvo) — references/02-*.md §2.1.4
├─ INFERÊNCIAS
│   • Se foto de perfil = foto já vista em outras plataformas, operador é constante — confiança: ALTO
│   • Se "visto por último" oculto, alvo com OPSEC básica — MÉDIO
├─ LACUNAS
│   • Número pode ser chip queimado, sem vínculo identitário útil
└─ PRÓXIMAS DILIGÊNCIAS
    1. Cruzar foto capturada com /mapear-pivos em outras plataformas
    2. Ofício à operadora com dados cadastrais e IP+porta+UTC do último uso

⚖️ BASE LEGAL
• MCI art. 7º IX — perfil público no WhatsApp é visível por qualquer contato
• LGPD art. 7º VI — tratamento para execução de política pública investigativa
• Compatibilidade com ECA: investigação busca o agressor, não dados do menor

🔒 OPSEC DESTA ETAPA
• Conta operacional dedicada, nunca pessoal
• VM com snapshot antes e depois
• Logout imediato pós-captura
• Nunca enviar mensagem ao alvo

📎 CADEIA DE CUSTÓDIA
• HTML Hunchly + screenshot + SHA-256 + timestamp UTC
• Registro na planilha cadeia-custodia.csv
```

---

## Passo 5 — `/analise-juridica` do conjunto

O usuário pede análise consolidada das técnicas 🟡 antes de representar por quebra de sigilo judicial. O assistente entrega mapeamento completo contra ECA art. 241, LGPD art. 14, MCI art. 10–22, CP art. 158, Lei 14.155/2021 — com disclaimer de que a análise é orientativa.

---

## Passo 6 — `/gerar-relatorio` + `/cadeia-custodia`

Relatório de 13 seções consolidando:
- Foto do agressor no WhatsApp Web **corresponde** à foto encontrada em Discord e em uma conta LinkedIn pública de outro nome (hipótese: identidade real identificada — INFERÊNCIA ALTA)
- Busca reversa da foto LinkedIn deu 3 resultados em outros portais profissionais (FATO ALTO de identidade real)
- Recomendação: representar por quebra de sigilo de dados do LinkedIn + ofício à Microsoft/Meta

---

## Síntese do fluxo

```
Briefing → Alerta ECA (obrigatório)
        → /planejar-investigacao (A)
        → Execução FASE A
        → /analise-juridica (antes de 🟡)
        → /tecnica-especifica WhatsApp Web (C, 🟡 após autorização)
        → /mapear-pivos com a foto capturada (D)
        → /gerar-relatorio (E) + /cadeia-custodia (F)
        → Representação formal por quebra de sigilo
```

**Aprendizado do caso:**
- Qualquer caso com menor envolvido tem **tripla camada** (CP + ECA + LGPD art. 14)
- Alerta inicial antes do plano é obrigatório — estrutura o restante da investigação
- Técnicas 🟡 **sempre** com pergunta de autorização antes do passo a passo

---

*Caso fictício para ilustração. Em casos reais envolvendo adolescente, acione paralelamente DCA/DEAM, SaferNet e equipe psicossocial para atendimento da vítima.*
