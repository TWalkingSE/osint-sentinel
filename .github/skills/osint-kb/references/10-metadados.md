<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 10
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 10. METADADOS (EXIF E DOCUMENTOS)

### 10.1 Metadados em Documentos Office/PDF

| Ferramenta | URL / Comando | Função |
|---|---|---|
| ExifTool | `exiftool documento.pdf` | Autor, software, data |
| FOCA | https://github.com/ElevenPaths/FOCA | Automação para sites |
| Metagoofil | `metagoofil -d dominio.com -t pdf` | Extração em massa |
| PDF-Parser | `pdf-parser documento.pdf` | Análise estrutural |
| PDF Examiner | https://www.pdf-examiner.com/ | Análise online |
| OfficeMalScanner | Windows | Análise de Office |
| olevba (oletools) | https://github.com/decalage2/oletools | Macros em Office |
| oleid | oletools | Identificação |
| oledump | DidierStevens | Dump de streams OLE |
| peepdf | https://github.com/jesparza/peepdf | Análise PDF |
| PyMuPDF (fitz) | Python | Extração programática |
| LibreOffice Reviewer | Manual | Comentários e histórico |
| PDF Stream Dumper | Ferramenta Windows | Análise profunda |
| Didier Stevens Suite | https://blog.didierstevens.com/ | Vários utilitários |

**Metadados extraíveis de documentos:**
- Nome do autor e coautor
- Organização/empresa
- Software utilizado (versão)
- Data de criação e última modificação
- Número de revisões
- Comentários e anotações ocultas
- Impressoras utilizadas
- Nomes de usuário internos
- Caminhos de arquivo (path) no sistema de origem
- Templates utilizados
- GUIDs de documento
- E-mails em hiperlinks ocultos

### 10.2 Metadados em Imagens (EXIF Completo)

**Campos mais relevantes para investigação:**

| Campo EXIF | Valor de Inteligência |
|---|---|
| `GPS.GPSLatitude` / `GPS.GPSLongitude` | Localização exata |
| `DateTimeOriginal` | Hora real da captura |
| `Make` / `Model` | Modelo do dispositivo |
| `Software` | App de câmera ou edição |
| `SerialNumber` | Número de série do dispositivo |
| `LensModel` | Identifica câmera profissional |
| `UserComment` | Comentários embutidos |
| `ThumbnailImage` | Miniatura original (antes de edição) |
| `Artist` / `Copyright` | Autoria declarada |
| `GPSAltitude` | Altitude (útil para indoor vs outdoor) |
| `GPSImgDirection` | Direção em que a foto foi tirada |
| `HostComputer` | Nome do equipamento |
| `DocumentName` | Nome do documento original |
| `Keywords` | Tags atribuídas |
| `OwnerName` | Proprietário declarado |
| `InternalSerialNumber` | ID profundo (Canon, Nikon) |
| `FirmwareVersion` | Versão do firmware |
| `ShutterCount` | Contagem de disparos (DSLR) |

### 10.3 Metadados em Vídeo

| Campo | Função |
|---|---|
| `creation_time` | Data/hora de criação |
| `encoder` | Software usado |
| `location` (QuickTime) | GPS embutido em iPhone |
| `make` / `model` | Dispositivo |
| `duration` | Tempo de vídeo |
| `frame_rate` | Taxa de quadros |
| `codec` | Codec usado |
| `title` / `comment` | Metadados descritivos |

**Ferramentas:**
- `exiftool video.mp4`
- `ffprobe video.mp4 -show_format -show_streams`
- `mediainfo video.mp4`

### 10.4 Metadados em Áudio

| Campo | Função |
|---|---|
| `artist` / `album` / `title` | ID3 tags |
| `encoder` | Software de captura |
| `date` | Data de criação |
| `GPS` (em alguns apps) | Localização |
| `channel_layout` | Mono/estéreo/5.1 |

### 10.5 Remoção (Anti-Forense) e Detecção de Remoção

- Serviços que removem EXIF: Imgur, Facebook, Twitter (na maioria dos casos)
- Serviços que MANTÉM: Flickr, Google Drive (compartilhado), WeTransfer (parcial)
- Técnica: se um arquivo "puro" teve EXIF removido, isso pode ser um indicador de consciência anti-forense
- Ferramentas de limpeza: MAT2, ExifTool com `-all=`

---


