<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 20
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 20. Inteligência Artificial Aplicada à Investigação

### 20.1 LLMs em Nuvem (Uso com Cautela de Dados)

⚠️ **Atenção LGPD/sigilo**: nunca submeta dados pessoais de investigados, conteúdo sob segredo de justiça ou documentos classificados a APIs comerciais sem contrato com cláusulas de não-treinamento e residência de dados compatível. Para dados sensíveis, prefira **soluções locais** (seção 20.2).

| Plataforma | URL | Observações |
|---|---|---|
| Claude (Anthropic) | https://claude.ai | Excelente em análise textual e raciocínio |
| ChatGPT | https://chat.openai.com | GPT-4o/o1 para raciocínio |
| Gemini | https://gemini.google.com | Multimodal + integração Google |
| Perplexity | https://www.perplexity.ai | Busca com citações |
| Mistral Le Chat | https://chat.mistral.ai | Empresa europeia (GDPR) |
| DeepSeek | https://chat.deepseek.com | Raciocínio chinês |
| Kagi Assistant | https://kagi.com/assistant | Busca + LLMs |

### 20.2 LLMs Locais (Ollama / LM Studio / vLLM / llama.cpp)

🎯 **Recomendado para investigação com dados sensíveis** — processamento 100% offline, sem envio a terceiros. Abaixo sugestões considerando hardware com ~16–24 GB VRAM.

#### 20.2.1 Modelos para Análise Textual em Português

| Modelo | Tamanho / Quant | VRAM aprox. | Uso |
|---|---|---|---|
| Llama 3.3 70B | Q4_K_M | ~42 GB (offload necessário) | Topo de linha; exige CPU+VRAM |
| Llama 3.1 70B | Q4_K_M | ~42 GB | Alternativa estável |
| Llama 3.1 8B | Q8_0 | ~9 GB | Ótima para 16 GB VRAM |
| Qwen 2.5 72B | Q4_K_M | ~44 GB | Forte em português, matemática |
| Qwen 2.5 32B | Q4_K_M / Q5_K_M | ~20–24 GB | **Sweet spot para RTX ADA 24GB** |
| Qwen 2.5 14B | Q8_0 | ~16 GB | Excelente custo-benefício |
| Qwen 2.5 7B | Q8_0 | ~8 GB | Rápido para triagem |
| Qwen3 14B / 32B | Q4/Q5 | 14–24 GB | Geração recente |
| Mistral Large 2411 | Q4 | ~70 GB (offload) | Topo com licença restrita |
| Mistral Small 24B (2501) | Q4_K_M | ~15 GB | **Ótimo p/ 16 GB** |
| Mistral Nemo 12B | Q6_K | ~10 GB | Eficiente |
| Gemma 3 27B | Q4_K_M | ~18 GB | **Forte em PT-BR** |
| Gemma 3 12B | Q6_K | ~10 GB | Rápido |
| Gemma 3 4B | Q8_0 | ~5 GB | Extração leve |
| Phi-4 14B | Q6_K | ~12 GB | Raciocínio denso |
| Command R+ 104B | Q4 | ~64 GB | RAG especializado |
| Command R 35B | Q4_K_M | ~22 GB | RAG com boa PT |
| DeepSeek-R1-Distill 32B / 14B | Q4/Q6 | 12–22 GB | Raciocínio (cuidado: verboso) |
| Sabiá / Maritaca (comercial PT-BR) | API BR | — | Alternativa nacional |

#### 20.2.2 Modelos de Visão (VLM) para OCR / Relatórios / Tabelas

| Modelo | Uso | Observações |
|---|---|---|
| Qwen2-VL 7B / 72B | OCR + raciocínio visual | Excelente em tabelas e documentos PT-BR |
| Qwen2.5-VL 7B / 32B / 72B | Versão mais recente | Ganho em OCR estruturado |
| MiniCPM-V 2.6 (8B) | OCR multilíngue | Rápido, roda em 16 GB |
| MiniCPM-o 2.6 | Multimodal + áudio | Leve |
| InternVL 2.5 / 3 (até 78B) | Documentos complexos | Forte em charts/formulários |
| LLaVA 1.6 / NeXT | Base clássica | Mais leve, menor qualidade atual |
| Llama 3.2 Vision 11B / 90B | Visão Meta | Integra bem com Ollama |
| Pixtral 12B (Mistral) | Visão europeia | Contexto longo |
| docTR / Nougat (Meta) | OCR acadêmico/científico | Especializado em layout |
| PaddleOCR | OCR tradicional | Muito bom em PT; rápido em GPU |
| Tesseract 5 + LSTM | OCR clássico | Fallback confiável |
| Surya OCR | OCR multilíngue moderno | Layout + linhas |
| EasyOCR | OCR leve | Quando não precisa de raciocínio |

#### 20.2.3 Transcrição de Áudio (Interceptações, Escutas, Vídeos)

| Ferramenta | Uso |
|---|---|
| OpenAI Whisper (large-v3) | Padrão; roda local |
| Faster-Whisper (CTranslate2) | 4–10× mais rápido |
| WhisperX | Diarização (separar falantes) + alinhamento |
| Whisper.cpp | CPU/metal/CUDA leve |
| Pyannote | Diarização profissional |
| NeMo (NVIDIA) | Pipelines ASR + diarização |
| SpeechBrain | Toolkit acadêmico |
| Vosk | Offline leve |

#### 20.2.4 Embeddings e RAG Investigativo

| Ferramenta | Função |
|---|---|
| nomic-embed-text | Embeddings locais |
| bge-m3 (BAAI) | Multilíngue, forte em PT |
| multilingual-e5-large | Baseline sólido |
| Jina Embeddings v3 | Contexto longo |
| Qdrant / Milvus / Weaviate / Chroma | Vector DBs |
| LangChain / LlamaIndex / Haystack | Orquestração RAG |
| AnythingLLM / LibreChat / Open WebUI | Front-ends p/ LLMs locais |
| Msty | UI desktop + multi-provider |
| GPT4All | Desktop offline |

### 20.3 Casos de Uso Investigativos (Local-First)

| Tarefa | Modelo Sugerido |
|---|---|
| Revisão ortográfica/gramatical de relatórios em PT | Qwen 2.5 14B/32B, Gemma 3 12B/27B |
| Sumarização de autos processuais volumosos | Qwen 2.5 32B / Mistral Small 24B |
| Extração estruturada de entidades (CPF, CNPJ, IP, valores) | Qwen 2.5 7B/14B + prompt JSON |
| OCR de relatórios digitalizados com tabelas | Qwen2.5-VL 7B/32B, MiniCPM-V 2.6 |
| Tradução PT↔EN↔ES de mensagens apreendidas | Gemma 3, Qwen 2.5 |
| Transcrição de mídia apreendida | WhisperX (diarizado) |
| Análise de logs (firewall, proxy, auth) | Qwen 2.5 7B + regex + scripts |
| Comparação de estilos (stylometry) | Embeddings BGE-m3 + cosine |
| Classificação de conteúdo (golpe, pornografia etc.) | Classificadores ad-hoc via prompt |
| RAG sobre jurisprudência BR | bge-m3 + Qdrant + Qwen/Gemma |

### 20.4 Deepfakes e Mídia Sintética — Detecção

| Ferramenta | Função |
|---|---|
| Sensity AI | Comercial, detecção multimodal |
| Intel FakeCatcher | Biossinais (PPG) |
| Reality Defender | Comercial |
| Truepic / C2PA | Proveniência (autenticação de origem) |
| Microsoft Video Authenticator | Análise de frames |
| DeepFake-o-Meter | Agregador acadêmico |
| FakeImageDetector | Web |
| Hugging Face deepfake-detector models | Open |
| Faceforensics++ | Dataset/referência |
| AI or Not | Classificador geral |
| Hive Moderation | API comercial |
| Photo Forensics (Foto Forensics) | ELA |



