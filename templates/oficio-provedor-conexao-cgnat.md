# OFÍCIO — Provedor de Conexão (ISP) com CGNAT

> Template preenchível para requisição de identificação de assinante em rede CGNAT, com IP público + porta lógica + timestamp UTC.
> Fundamento: Marco Civil da Internet (Lei 12.965/2014) art. 10 e 13; Resolução Anatel 614/2013; RFC 6888.
>
> Adaptar cabeçalho ao órgão emissor. Remover este cabeçalho ao finalizar.

---

```
[TIMBRE DA INSTITUIÇÃO]

Ofício nº [número]/[ano] - [unidade]
[Cidade/UF], [data por extenso]

À
[NOME DA OPERADORA / ISP]
[Departamento de Atendimento a Órgãos Públicos / Legal]
[endereço oficial da operadora]

Assunto: Requisição de identificação de assinante em rede CGNAT, com
         fundamento nos artigos 10 e 13 da Lei 12.965/2014 (Marco Civil da
         Internet), nos autos do IPL/PIC nº [número].

Senhor(a) Representante Legal,

No curso da investigação formalizada no(a) [IPL nº XXXX/AAAA / PIC nº], que
apura a prática do crime tipificado no [artigo da lei penal], REQUISITO, com
fundamento nos artigos 10 e 13 da Lei 12.965/2014 (Marco Civil da Internet),
a identificação do assinante associado aos seguintes parâmetros de conexão:

DADOS DA CONEXÃO A IDENTIFICAR

▸ IP público de origem (IPv4 ou IPv6): [X.X.X.X]
▸ PORTA LÓGICA DE ORIGEM: [porta numérica, 0-65535]
▸ Data e hora EXATA em UTC (Z): [YYYY-MM-DDTHH:MM:SSZ]
▸ Protocolo (se conhecido): [TCP / UDP / SCTP]
▸ IP de destino (plataforma onde ocorreu o acesso): [Y.Y.Y.Y]
▸ Porta de destino (se conhecida): [porta]

Estes dados foram fornecidos pelo provedor de aplicação [NOME] em resposta
ao Ofício nº [X] de [data], cuja cópia acompanha esta requisição (em anexo).

DADOS SOLICITADOS

Para a tupla acima (IP + porta + timestamp UTC), informe:

1. Nome completo e/ou razão social do assinante
2. Documento de identificação (CPF/CNPJ)
3. Endereço de instalação do ponto de conexão
4. Data de contratação do serviço
5. Outras linhas/contas vinculadas ao mesmo assinante (quando aplicável)
6. Se a conexão foi realizada via IPv6 nativo (sem CGNAT), confirmar a
   atribuição direta do prefixo ao assinante
7. Registros de atribuição (CGNAT translation log) no instante exato
   da conexão, preservando:
      - IP público externo
      - Porta pública atribuída
      - IP privado interno
      - Timestamp de início e fim da sessão NAT

JUSTIFICATIVA DA NECESSIDADE E PROPORCIONALIDADE

[Descrever, em 2-4 parágrafos, a conexão do IP+porta+timestamp com o fato
investigado, a necessidade de identificação do assinante para continuidade
da apuração, e a proporcionalidade da medida. Citar que, em redes CGNAT
(Carrier-Grade NAT, RFC 6888), múltiplos assinantes compartilham o mesmo
endereço IPv4 público — sendo a identificação técnica possível APENAS com
a tupla (IP público + porta de origem + timestamp UTC preciso + segundos).]

PRESERVAÇÃO IMEDIATA (art. 13, §2º e §3º MCI)

Caso os registros de CGNAT translation log referentes à data e ao horário
indicados ainda estejam disponíveis (retenção legal mínima de 6 meses, nos
termos do art. 13 caput do MCI), requisito a PRESERVAÇÃO IMEDIATA enquanto
aguardam o atendimento desta requisição.

FORMATO DE ENTREGA

- Declaração formal, assinada pelo responsável técnico do provedor e
  acompanhada de assinatura digital ICP-Brasil (e-CNPJ)
- Indicação expressa de que os registros foram produzidos por sistema
  auditável e que a extração preserva sua integridade
- Hash SHA-256 dos registros entregues
- Encaminhamento por canal seguro: [portal / e-mail institucional]

PRAZO SOLICITADO: [15 dias úteis] a contar do recebimento.

Em caso de dúvida técnica, o contato institucional é:
  [Nome do responsável]
  [Cargo / matrícula]
  [E-mail institucional / telefone]

Ao ensejo, subscrevo-me respeitosamente.

Atenciosamente,

_________________________________________
[NOME DA AUTORIDADE]
[Cargo]
[Matrícula]
[Unidade]

ANEXOS:
- Cópia do Ofício nº [X] ao provedor de aplicação e da resposta
- Extrato dos fatos do IPL/PIC nº [número]
```

---

## Referências técnicas

| Referência | Aplicação |
|---|---|
| **RFC 6888** | Carrier-Grade NAT behavioral requirements |
| **RFC 7422** | Deterministic CGN — identificação sem porta em condições específicas |
| **Resolução Anatel 614/2013** | Obrigações de registro de conexão pelo ISP |
| **MCI art. 13** | Guarda de registros de conexão por 1 ano |
| **MCI art. 10** | Fornecimento mediante ordem judicial para conteúdo; dados cadastrais mediante requisição administrativa |
| `references/03-ip.md §3.5` | Detalhamento técnico CGNAT no KB v3.0/2026 |

## Observações operacionais críticas

- ❗ **Sem porta lógica, identificação inviável** em CGNAT. Nunca aceite resposta do provedor de aplicação que não inclua a porta.
- ❗ **Timestamp em UTC obrigatório** — com precisão de segundos. Jamais usar horário local sem offset.
- ❗ **Provedores regionais pequenos** podem ter retenção menor — priorize ofício urgente nestes casos.
- ❗ **Dual-stack IPv4/IPv6:** se a conexão foi via IPv6 nativo, CGNAT é dispensado — mas a identificação por prefixo IPv6 é igualmente possível.
- ❗ **Mobile (4G/5G):** operadoras móveis tipicamente usam CGNAT — IP + porta + timestamp é regra.

---

*Template conforme metodologia OSINT-Sentinel v1.0 e KB OSINT v3.0/2026 §3.5 e §25.*
