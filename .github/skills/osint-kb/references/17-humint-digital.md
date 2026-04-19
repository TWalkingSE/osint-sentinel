<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 17
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 17. HUMINT Digital (Sockpuppets e Engenharia Social)

⚠️ **Uso estritamente profissional, autorizado e documentado.** Operações encobertas em ambiente digital devem estar previstas em MP/ordem judicial quando cabível, nos termos da **Lei 12.850/2013 (arts. 10 a 10-C)** — infiltração de agentes. Fora desses contextos, sockpuppets podem configurar **estelionato (art. 171 CP)**, **falsa identidade (art. 307 CP)** ou **violação de ToS** com repercussões probatórias.

### 17.1 Princípios Operacionais

- **Compartimentação total**: nunca use o mesmo endpoint/IP para persona real e sockpuppet.
- **Legend consistency**: backstopping — perfil precisa ter histórico plausível (fotos EXIF-limpas, atividade temporal distribuída, pegada digital em múltiplas plataformas).
- **Device hygiene**: VM dedicada, navegador com perfil limpo, fingerprint distinto, anti-canvas/WebGL.
- **Rede**: VPN comercial + Tor quando aplicável + residencial proxy para evitar detecção de data center.
- **OPSEC temporal**: horário de atividade coerente com fuso declarado da persona.
- **Financeiro**: se a persona precisar de pagamentos, usar pré-pago não rastreável — mas apenas em operações autorizadas.

### 17.2 Ferramentas de Apoio a Personas

| Ferramenta | URL | Função |
|---|---|---|
| This Person Does Not Exist | https://thispersondoesnotexist.com/ | Avatar GAN (⚠️ facialmente detectável) |
| Generated.Photos | https://generated.photos/ | Bancos de avatares IA |
| Fake Name Generator | https://www.fakenamegenerator.com/ | Identidade sintética |
| BrowserLeaks | https://browserleaks.com/ | Checar fingerprint |
| AmIUnique | https://amiunique.org/ | Unicidade navegador |
| CreepJS | https://abrahamjuliot.github.io/creepjs/ | Detecção anti-bot |
| Multilogin / GoLogin / Incogniton | Comerciais | Anti-detect browsers |
| Kameleo / AdsPower | Comerciais | Gestão multi-perfil |

### 17.3 Detecção de Sockpuppets Adversários

| Sinal | Indicador |
|---|---|
| Metadados avatar | EXIF intacto revela câmera/app/IA |
| Temporal | Atividade 24/7, picos fora do fuso declarado |
| Conteúdo | Poucos posts originais, muito repost/like |
| Rede social | Poucos seguidores com interação real; clusters recíprocos |
| Stylometry | Estilo de escrita inconsistente entre posts |
| Erros linguísticos | Tradução automática/IA detectável |
| Comportamento | Responde em segundos; nunca foge do roteiro |
| Face GAN | Olhos assimétricos, cenário desfocado, acessórios quebrados |

### 17.4 Frameworks Defensivos

- **Sockpuppet Detection** (várias heurísticas acadêmicas)
- **Botometer** (X/Twitter)
- **Hoaxy** (difusão de desinformação)
- **DFRLab Open-Source Tools**
- **Graphika** (análise de redes coordenadas)



