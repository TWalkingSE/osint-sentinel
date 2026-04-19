<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 12
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 12. FAVICONS COMO IDENTIFICADORES

### 12.1 Conceito

O hash MurmurHash3 do arquivo `favicon.ico` de um site pode ser usado como impressão digital para encontrar outros sites com a mesma infraestrutura ou pertencentes ao mesmo operador. Útil especialmente para identificar painéis de phishing idênticos em domínios diferentes, fazendas de sites de fraude e infraestrutura compartilhada de grupos criminosos.

### 12.2 Processo de Investigação

**Passo 1 — Obter o favicon:**
```
https://www.google.com/s2/favicons?domain=alvo.com
https://icon.horse/icon/alvo.com
https://alvo.com/favicon.ico
```

**Passo 2 — Calcular o hash (Python):**
```python
import mmh3, base64, requests

resp = requests.get("https://alvo.com/favicon.ico")
favicon_b64 = base64.encodebytes(resp.content)
hash_value = mmh3.hash(favicon_b64)
print(hash_value)
```

**Passo 3 — Buscar no Shodan:**
```
http.favicon.hash:HASH_CALCULADO
```

**Passo 4 — Buscar no Censys:**
```
services.http.response.favicons.md5_hash:HASH
```

### 12.3 Ferramentas

| Ferramenta | URL / Comando |
|---|---|
| FaviHunter | https://github.com/eremit4/favihunter |
| Shodan | `http.favicon.hash:HASH` |
| Censys | `services.http.response.favicons.md5_hash:HASH` |
| FavFreak | https://github.com/devanshbatham/FavFreak |
| FaviconFinder | https://github.com/will-hart/FaviconFinder |
| Hunter.how Favicon | https://hunter.how/ | Query `web.favicon.data` |
| FOFA Favicon | `icon_hash="HASH"` | Alternativa chinesa |
| ZoomEye Favicon | `iconhash:"HASH"` | |
| Netlas Favicon | `favicon.hash_murmur:HASH` | |

### 12.4 Dorks úteis

```
# Encontrar painéis C2 com favicon padrão do Cobalt Strike
http.favicon.hash:989289239 (Shodan)

# Identificar phishing kits com favicon idêntico
http.favicon.hash:HASH_DO_FAVICON_LEGITIMO -ssl.cert.subject.cn:*.dominio-real.com
```



