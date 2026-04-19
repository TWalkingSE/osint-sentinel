# OFÍCIO — Provedor de Aplicação de Internet

> Template preenchível para requisição de dados cadastrais e de registros de acesso a aplicações, com fundamento em Marco Civil da Internet (Lei 12.965/2014) art. 10, 11 e 15.
>
> Adaptar cabeçalho ao órgão emissor e à autoridade destinatária. Remover este cabeçalho ao finalizar.

---

```
[TIMBRE DA INSTITUIÇÃO]

Ofício nº [número]/[ano] - [unidade]
[Cidade/UF], [data por extenso]

À
[NOME DA EMPRESA / PROVEDOR DE APLICAÇÃO]
[Departamento Legal / Law Enforcement Response]
[endereço — físico e/ou e-mail jurídico oficial]

Assunto: Requisição de dados cadastrais e de registros de acesso a aplicações
         de internet, com fundamento na Lei 12.965/2014 (Marco Civil da
         Internet), nos autos do IPL/PIC nº [número].

Senhor(a) Representante Legal,

Com o devido respeito, no âmbito da investigação criminal consubstanciada
no(a) [IPL nº XXXX/AAAA / PIC nº XXXX/AAAA], que apura suposta prática do
crime tipificado no [artigo do Código Penal / Lei especial], REQUISITO, com
fundamento nos artigos 10, 11 e 15 da Lei 12.965/2014 (Marco Civil da
Internet), a disponibilização dos seguintes dados e registros:

1. DADOS CADASTRAIS
   - Nome completo e/ou razão social do titular da conta
   - Documento de identificação fornecido no cadastro
   - Endereço eletrônico (e-mail) vinculado
   - Data e hora de criação da conta (UTC)
   - Telefone(s) vinculado(s)

2. REGISTROS DE ACESSO A APLICAÇÕES (art. 15 MCI)
   Referentes à conta/perfil/URL identificado como:
   ▸ Identificador: [e-mail / username / URL / ID interno]
   ▸ Período: de [DATA UTC INÍCIO] a [DATA UTC FIM]

   Para cada acesso no período:
   - Data e hora (UTC)
   - Endereço IP de origem (IPv4 e IPv6 quando aplicável)
   - PORTA LÓGICA DE ORIGEM (essencial para identificação com CGNAT)
   - User-Agent
   - Device fingerprint / ID de dispositivo (se disponível)
   - Ação realizada (login, post, envio de mensagem, upload, etc.)

3. PRESERVAÇÃO IMEDIATA
   Com fundamento no art. 13, §2º e §3º da Lei 12.965/2014, requisito a
   PRESERVAÇÃO IMEDIATA dos dados e registros acima indicados pelo prazo de
   180 (cento e oitenta) dias, prorrogáveis por igual período mediante
   justificativa, enquanto tramita eventual autorização judicial para
   obtenção de conteúdo de comunicações (art. 7º, III da LGPD c/c art. 22
   do MCI).

JUSTIFICATIVA DA NECESSIDADE E PROPORCIONALIDADE:
[Descrever, em 2-4 parágrafos, a conexão do identificador com o fato
investigado, a impossibilidade de obtenção por outros meios, e a
proporcionalidade do que está sendo requisitado em relação ao
bem jurídico tutelado.]

FORMATO DE ENTREGA SOLICITADO:
- CSV ou JSON estruturado
- Hash SHA-256 do arquivo entregue
- Assinatura digital (e-CPF/e-CNPJ ICP-Brasil) ou declaração formal
- Encaminhamento por [canal seguro — e-mail institucional criptografado /
  portal oficial LEA]

PRAZO SOLICITADO: [15/30 dias úteis] a contar do recebimento.

Em caso de dúvida técnica ou jurídica, o contato institucional é:
  [Nome do responsável]
  [Cargo / matrícula]
  [E-mail institucional / telefone]

Ao ensejo, subscrevo-me respeitosamente.

Atenciosamente,

_________________________________________
[NOME DA AUTORIDADE]
[Cargo — Delegado de Polícia / Promotor de Justiça / etc.]
[Matrícula]
[Unidade]
```

---

## Campos de referência rápida

| Lei / Artigo | Aplicação |
|---|---|
| **MCI art. 10** | Responsabilidade do guardião + provisão mediante ordem judicial para conteúdo |
| **MCI art. 11** | Aplicação ao estrangeiro com repercussão no Brasil |
| **MCI art. 13, §2º–3º** | Preservação de registros de conexão (pode ser solicitada sem ordem judicial) |
| **MCI art. 15** | Guarda de registros de acesso a aplicações — 6 meses |
| **MCI art. 22** | Disposição judicial para conteúdo de comunicações |
| **LGPD art. 7º, III** | Base legal de tratamento para cumprimento de obrigação legal |

## Observações operacionais

- **CGNAT:** sempre pedir **IP + porta lógica + timestamp UTC** juntos. Sem a porta, o ISP não consegue identificar o assinante em redes com CGNAT (ver `references/03-ip.md §3.5`).
- **Preservação vs. obtenção:** a preservação pode ser requisitada diretamente; a obtenção do **conteúdo** (mensagens, arquivos) exige ordem judicial (MCI art. 22).
- **Timestamp UTC:** sempre informar fuso explícito. Nunca "horário local".
- **Para plataformas estrangeiras** (Meta, Google, Microsoft, Apple, X, TikTok): consultar `references/28-cooperacao-internacional.md` e usar canais específicos (LEA portal, MLAT via DRCI, Rede 24/7 Budapeste para urgência).
- **Transparency Reports** das principais plataformas: ver `references/28-cooperacao-internacional.md §28.5`.

---

*Template conforme metodologia OSINT-Sentinel v1.0 e KB OSINT v3.0/2026 §25 e §28.*
