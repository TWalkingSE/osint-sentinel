<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 06
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 6. IMAGENS E VÍDEOS (IMINT)

### 6.1 Pré-processamento de Imagens

| Necessidade | Ferramenta | URL |
|---|---|---|
| Extrair frame de vídeo | VLC / FFmpeg | Locais |
| Melhorar qualidade | LetsEnhance | https://letsenhance.io/ |
| Melhorar qualidade | PicWish | https://picwish.com/ |
| Melhorar qualidade | UpscaleMedia | https://www.upscale.media/ |
| Melhorar qualidade | Topaz Gigapixel | https://www.topazlabs.com/ |
| Melhorar qualidade | Real-ESRGAN (local) | https://github.com/xinntao/Real-ESRGAN |
| Remover fundo | Remove.bg | https://www.remove.bg/ |
| Remover fundo | Pixlr | https://pixlr.com/ |
| Remover fundo | BRIA (HF) | https://huggingface.co/briaai/RMBG-1.4 |
| Remover objeto | Cleanup.pictures | https://cleanup.pictures/ |
| Remover objeto | Inpaint-web | https://www.inpaint-web.com/ |
| Remover marca d'água | WatermarkRemover | https://www.watermarkremover.io/ |
| Desfocagem reversa | SmartDeblur | http://smartdeblur.net/ |
| Desfocagem reversa | ImageJ + plugin | https://imagej.nih.gov/ |
| Análise forense | FotoForensics | https://fotoforensics.com/ |
| Análise de JPG | JPEGSnoop | https://jpegsnoop.softonic.com.br/ |
| ELA (Error Level Analysis) | https://fotoforensics.com/ | Detectar edição |
| Clone Detection | Forensically | https://29a.ch/photo-forensics/ |
| Noise Analysis | Forensically | https://29a.ch/photo-forensics/ |
| Deblur (stable) | https://deblur.app/ | Online |
| OCR (Tesseract) | https://github.com/tesseract-ocr/tesseract | CLI |
| OCR online | https://www.onlineocr.net/ | Web |
| OCR (PaddleOCR) | https://github.com/PaddlePaddle/PaddleOCR | Open source |
| OCR (docTR / OnnxTR) | https://github.com/mindee/doctr | Por deep learning |

### 6.2 Busca Reversa de Imagem

| Ferramenta | URL | Especialidade |
|---|---|---|
| Google Images | https://images.google.com/ | Indexação global |
| Google Lens | https://lens.google.com/ | Mobile + desktop |
| Yandex Images | https://yandex.com/images/ | Melhor para rostos |
| Bing Images | https://www.bing.com/?scope=images | Alternativo |
| TinEye | https://tineye.com/ | Correspondência exata |
| PimEyes | https://pimeyes.com/ | Reconhecimento facial (pago) |
| FaceCheck.id | https://facecheck.id/ | Facial em redes sociais |
| Search4Faces | https://search4faces.com/ | Redes sociais russas |
| Reverse Image Search | https://www.reverse-image-search.org/ | Multi-motor |
| Duplichecker | https://www.duplichecker.com/ | Multi-busca |
| Jimpl | https://jimpl.com/ | Metadados + busca |
| RootAbout | https://rootabout.com/ | Alternativo |
| ImgOps | https://imgops.com/ | Hub de ferramentas |
| KarmaDecay | http://karmadecay.com/ | Busca no Reddit |
| Imgur | https://imgur.com/ | Tags e usuários |
| ImageIdentify | https://www.imageidentify.com/ | Classificação por IA |
| Lenso.ai | https://lenso.ai/ | Busca reversa IA |
| Labnol Reverse Search | https://labnol.org/reverse/ | Agregador |
| Photutorial Reverse | https://photutorial.com/tools/ | Agregador |
| SauceNAO | https://saucenao.com/ | Anime/manga/art |
| IQDB | https://iqdb.org/ | Anime focused |
| Ascii2D | https://ascii2d.net/ | Japonês (manga) |
| Google Photos Reverse (SerpAPI) | https://serpapi.com/ | API comercial |
| Social Catfish | https://socialcatfish.com/ | Reverse por pessoa |

> ⚠️ **Ética e reconhecimento facial:** Ferramentas como PimEyes, FaceCheck.id e Clearview (policial) usam raspagem massiva de fotos públicas. O uso por agente público exige:
> - Autorização judicial/administrativa específica em investigações
> - Observância da LGPD (bases legais do art. 7º e 11)
> - Documentação robusta em cadeia de custódia
> - Conhecimento de que resultados podem gerar falsos positivos — **nunca basear prisão ou identificação formal apenas em match facial**
> Ver seção 26.

### 6.3 Reconhecimento e Comparação Facial

| Ferramenta | URL | Observação |
|---|---|---|
| Face++ | https://www.faceplusplus.com/ | API profissional |
| MxFace | https://mxface.ai/face-comparing | Comparação direta |
| FaceComparison | https://facecomparison.toolpie.com/ | Online gratuito |
| Pictriev | http://www.pictriev.com/ | Análise de semelhança |
| Kairos | https://www.kairos.com/ | API comercial |
| AWS Rekognition | https://aws.amazon.com/rekognition/ | Escala empresarial |
| Azure Face API | https://azure.microsoft.com/en-us/services/cognitive-services/face/ | Microsoft |
| BetaFace | https://www.betafaceapi.com/ | API gratuita |
| DeepFace (open-source) | https://github.com/serengil/deepface | Biblioteca Python |
| InsightFace | https://github.com/deepinsight/insightface | Biblioteca open-source |
| CompreFace | https://github.com/exadel-inc/CompreFace | Self-hosted |
| FaceNet | https://github.com/davidsandberg/facenet | Research |
| OpenCV Face | https://opencv.org/ | Biblioteca |
| ArcFace | https://arxiv.org/abs/1801.07698 | SOTA em research |

> ⚠️ O reconhecimento facial está sujeito a restrições legais em diversas jurisdições. Use apenas com autorização judicial e registros adequados. **No Brasil**, já há discussões sobre banimento em espaços públicos e normativas como as do Decreto 10.046/2019 e a ADI sobre videomonitoramento com reconhecimento facial. Ver guidance da ANPD.

### 6.4 Metadados EXIF de Imagens

| Ferramenta | URL / Comando |
|---|---|
| ExifTool | `exiftool imagem.jpg` (Linux/Windows) |
| FotoForensics | https://fotoforensics.com/ |
| ImgOps | https://imgops.com/ |
| ViewExifData | http://www.viewexifdata.com/ |
| ExifData | https://exifdata.com/ |
| Pic2Map | https://www.pic2map.com/ |
| Metadata2Go | https://www.metadata2go.com/ |
| OnlineExifViewer | https://onlineexifviewer.com/ |
| Verexif | https://www.verexif.com/ |
| Thexifer | https://www.thexifer.net/ |
| StolenCameraFinder | https://www.stolencamerafinder.com/ |
| Jimpl | https://jimpl.com/ |
| Metapicz | http://metapicz.com/ |
| Exif Pilot | https://www.colorpilot.com/exif.html |
| Extract Metadata (web) | https://www.extractmetadata.com/ |

**Dados extraíveis de EXIF:**
- Coordenadas GPS (latitude/longitude)
- Data e hora da captura
- Modelo e fabricante da câmera/celular
- Software de edição utilizado
- Orientação e configurações da câmera
- Número de série do dispositivo (em alguns casos)
- Owner/Copyright
- Lens used
- ISO, shutter speed, aperture
- Flash usage
- Software/firmware version
- Color profile

### 6.5 Detecção de Deepfake e Manipulação

| Ferramenta | URL |
|---|---|
| Photo Forensics | https://29a.ch/photo-forensics/ |
| FaceForensics++ | http://www.faceforensics.com/ |
| Deepware Scanner | https://deepware.ai/ |
| Hive Moderation | https://hivemoderation.com/ai-generated-content-detection |
| Illuminarty | https://illuminarty.ai/ |
| AI or Not | https://www.aiornot.com/ |
| InVID / WeVerify | https://weverify.eu/ |
| Sensity AI | https://sensity.ai/ |
| Intel FakeCatcher | https://www.intel.com/ | PPG analysis |
| Optic AI or Not | https://aiornot.com/ |
| Maybe's AI Art Detector | https://huggingface.co/spaces/umm-maybe/AI-image-detector |
| Duckduckgoose | https://www.duckduckgoose.ai/ |
| Reality Defender | https://www.realitydefender.com/ |
| DeepFake-o-meter (UB) | https://zinc.cse.buffalo.edu/ | Research |
| Content Credentials (C2PA) | https://c2pa.org/ | Autenticação |
| Truepic | https://truepic.com/ | Autenticação de captura |

### 6.6 Esteganografia

| Ferramenta | URL / Comando | Função |
|---|---|---|
| Steghide | `steghide extract -sf imagem.jpg` | Extrai dados ocultos |
| Hexed.it | https://hexed.it/ | Inspeção hexadecimal |
| Stegsolve | Java app | Análise de camadas |
| zsteg | `zsteg imagem.png` | Análise de PNG/BMP |
| OpenStego | https://www.openstego.com/ | Open-source |
| Aperisolve | https://www.aperisolve.com/ | Multi-análise online |
| Stegoveritas | https://github.com/bannsec/stegoVeritas | Automático |
| Outguess | https://github.com/resurrecting-open-source-projects/outguess | JPEG |
| Foremost | https://github.com/korczis/foremost | File carving |
| Binwalk | https://github.com/ReFirmLabs/binwalk | Firmware + arquivos embutidos |
| StegOnline | https://stegonline.georgeom.net/ | Web |
| DeepSound | http://jpinsoft.net/deepsound/ | Áudio |
| StegDetect | — | Detecção |

### 6.7 Análise de Vídeo

| Ferramenta | URL | Função |
|---|---|---|
| FFmpeg | https://ffmpeg.org/ | Multi-uso CLI |
| InVID Verification Plugin | https://www.invid-project.eu/tools-and-services/invid-verification-plugin/ | Browser extension |
| YouTube DataViewer | https://citizenevidence.amnestyusa.org/ | Hora real de upload |
| Montage | https://montage.meedan.com/ | Colaborativo |
| Checkmate (Meedan) | https://meedan.com/check/ | Verificação |
| ffprobe | FFmpeg suite | Metadados de vídeo |
| Exiftool (vídeo) | `exiftool video.mp4` | Metadados |
| MediaInfo | https://mediaarea.net/en/MediaInfo | Detalhes técnicos |
| ShotDeck | https://shotdeck.com/ | Bibliotecário de frames (cinema) |
| Video Forensic Analysis | https://video.forensafe.com/ | Análise forense |
| Amped Authenticate | https://ampedsoftware.com/authenticate | Perícia profissional |
| Reality Defender Video | https://www.realitydefender.com/ | Deepfake vídeo |

### 6.8 OSINT em Imagens AI-Generated

| Ferramenta | URL | Função |
|---|---|---|
| SDXL Detector | Hugging Face | Stable Diffusion |
| Maybe's AI Detector | https://huggingface.co/spaces/umm-maybe/AI-image-detector | Multi-model |
| Illuminarty | https://illuminarty.ai/ | Comercial |
| AI Image Detector (Huggingface) | https://huggingface.co/organizations/detect-ai | Vários |
| C2PA Verify | https://contentcredentials.org/verify | Padrão aberto |
| Imagen Detector (Google) | — | Interno Google |

---


