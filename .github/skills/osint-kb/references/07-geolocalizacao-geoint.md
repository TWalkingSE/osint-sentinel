<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 07
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 7. GEOLOCALIZAÇÃO E GEOINT

### 7.1 Ferramentas de Geolocalização

| Ferramenta | URL | Função |
|---|---|---|
| Google Earth | https://earth.google.com/ | Visualização 3D |
| Google Maps | https://maps.google.com/ | Street View + satélite |
| Bing Maps | https://www.bing.com/maps | Alternativa |
| Yandex Maps | https://yandex.com/maps/ | Boa cobertura Europa/CIS |
| OpenStreetMap | https://www.openstreetmap.org/ | Dados abertos |
| ArcGIS | https://www.arcgis.com/ | Profissional |
| Mapillary | https://www.mapillary.com/ | Fotos em nível de rua colaborativas |
| KartaView | https://kartaview.org/ | Alternativa ao Street View |
| What3Words | https://what3words.com/ | Localização em 3 palavras |
| Wikimapia | http://wikimapia.org/ | Locais com descrição colaborativa |
| Overpass Turbo | https://overpass-turbo.eu/ | Consulta OSM avançada |
| OpenStreetCam (KartaView) | https://kartaview.org/ | Street-level fotos |
| BaiduMaps | https://map.baidu.com/ | China |
| Naver Maps | https://map.naver.com/ | Coreia do Sul |
| Kakao Maps | https://map.kakao.com/ | Coreia do Sul |
| 2GIS | https://2gis.com/ | Rússia + ex-URSS |
| Here Maps | https://wego.here.com/ | Alternativa profissional |
| MapCrunch | http://www.mapcrunch.com/ | Street View random |
| GeoGuessr | https://www.geoguessr.com/ | Treinamento GEOINT |

### 7.2 Estimativa de Localização por Imagem

| Ferramenta | URL | Método |
|---|---|---|
| GeoEstimation (TIB) | https://labs.tib.eu/geoestimation/ | IA — estimativa por imagem |
| GeoSpy | https://geospy.ai/ | IA — geolocalização |
| Picarta | https://picarta.ai/ | IA — localização |
| OSINT.SH Geolocate | https://osint.sh/images/ | Multi-busca |
| PlanetScope | https://www.planet.com/ | Imagens de satélite |
| Sentinel Hub | https://www.sentinel-hub.com/ | ESA — satélite gratuito |
| Immersal | https://immersal.com/ | Localização por AR |
| Loc8.ai | https://loc8.ai/ | Geoestimation IA |
| EarthKit | https://earthkit.ai/ | Multi-camada |
| GEOINT Search | https://geointsearch.com/ | Busca específica |
| StreetComplete | https://streetcomplete.app/ | Consulta OSM em campo |

### 7.3 Cronolocalização (Posição do Sol e Lua)

| Ferramenta | URL |
|---|---|
| SunCalc | https://www.suncalc.org/ |
| SunEarthTools | https://www.sunearthtools.com/ |
| FindMyShadow | https://findmyshadow.com/ |
| ShadowCalculator | http://shadowcalculator.eu/ |
| NOAA Solar Calculator | https://gml.noaa.gov/grad/solcalc/ |
| MoonCalc | https://www.mooncalc.org/ |
| In-The-Sky.org | https://in-the-sky.org/ |
| Stellarium Web | https://stellarium-web.org/ | Planetário online |
| Photographers' Ephemeris | https://photoephemeris.com/ | Posição celeste |

**Técnica de cronolocalização:**
1. Identifique sombras na imagem
2. Determine direção aproximada pelo contexto visual
3. Use o SunCalc para simular posição do sol em datas/horas diferentes
4. Compare com comprimento e direção das sombras na imagem
5. Refine até convergir em data/hora provável
6. Considere refração atmosférica se precisão alta for necessária

### 7.4 Câmeras Abertas e Vigilância

| Ferramenta | URL |
|---|---|
| Insecam | http://www.insecam.org/ |
| EarthCam | https://www.earthcam.com/ |
| WorldCam | https://worldcam.eu/ |
| OpenTopia | http://www.opentopia.com/ |
| Pictimo | https://www.pictimo.com/ |
| AirportWebcam | https://airportwebcams.net/ |
| Shodan (câmeras) | `product:"webcam"` no Shodan |
| Camarize | https://www.camarize.com/ | CCTV comercial |
| Look4.cam | https://look4.cam/ | Webcams públicas |

> ⚠️ **Alerta:** Muitas dessas câmeras estão expostas por falha de configuração. Apenas observe — nunca tente acessar câmeras internas de locais privados sem autorização judicial (invasão de dispositivo, art. 154-A CP).

### 7.5 Imagens de Satélite Históricas

| Ferramenta | URL |
|---|---|
| World Imagery Wayback | https://livingatlas.arcgis.com/ |
| Google Earth Engine | https://earthengine.google.com/ |
| Copernicus Open Access Hub | https://scihub.copernicus.eu/ |
| USGS EarthExplorer | https://earthexplorer.usgs.gov/ |
| NASA Worldview | https://worldview.earthdata.nasa.gov/ |
| Zoom Earth | https://zoom.earth/ |
| Sentinel Hub EO Browser | https://apps.sentinel-hub.com/eo-browser/ |
| Terraserver | https://terraserver.com/ | Alta resolução paga |
| Maxar Open Data | https://www.maxar.com/open-data | Eventos de crise |
| Airbus OneAtlas | https://www.intelligence-airbusds.com/ | Comercial |
| Descartes Labs Search | https://search.descarteslabs.com/ | Plataforma |
| Bing Maps Birds Eye | https://www.bing.com/maps | Vista oblíqua |
| HOT OSM (Humanitarian) | https://www.hotosm.org/ | Emergências |

### 7.6 Mapas e Análise Geoespacial

| Ferramenta | URL | Função |
|---|---|---|
| QGIS | https://www.qgis.org/ | SIG profissional open-source |
| Google My Maps | https://mymaps.google.com/ | Mapas personalizados |
| Felt | https://felt.com/ | Colaborativo online |
| Kepler.gl | https://kepler.gl/ | Visualização de dados geo |
| uMap | https://umap.openstreetmap.fr/ | Open-source |
| Palladio | https://hdlab.stanford.edu/palladio/ | Análise histórica |
| Mapbox Studio | https://www.mapbox.com/mapbox-studio | Customização |
| Leaflet.js | https://leafletjs.com/ | Biblioteca |
| Deck.gl | https://deck.gl/ | Viz de dados geo |
| CartoDB | https://carto.com/ | SaaS |
| MapServer | https://mapserver.org/ | Server GIS |
| PostGIS | https://postgis.net/ | Banco geoespacial |

### 7.7 Análise de IP e ERB (GSM)

**Estação Rádio Base (ERB):**
- Cada antena da operadora tem um identificador (Cell ID + LAC + MCC + MNC)
- A análise de CDR (Call Detail Record) revela localização aproximada
- Pedido via ofício à operadora com período específico

| Ferramenta | URL | Função |
|---|---|---|
| CellMapper | https://www.cellmapper.net/ | Mapa de antenas colaborativo |
| OpenCellID | https://opencellid.org/ | Base aberta de ERBs |
| Mozilla Location Service | https://location.services.mozilla.com/ | Descontinuado mas histórico |
| UnwiredLabs | https://unwiredlabs.com/ | API comercial |
| LocationAPI | https://www.locationapi.org/ | Multi-source |
| Google Geolocation API | https://developers.google.com/maps/documentation/geolocation | Resolver por WiFi/Cell |
| WiGLE | https://wigle.net/ | WiFi + Cell global |
| BTSearch | https://btsearch.pl/ | Foco em Polônia/EU |

**Referências técnicas:**
- Padrão 3GPP para CDR
- Lei 9.472/1997 (LGT) para acesso a dados de localização
- RFC sobre CGI (Cell Global Identity)



