<!--
Origem: KB OSINT v3.0/2026, seÃ§Ã£o 19
Arquivo canÃ´nico â€” carregar sob demanda via skill /osint-kb conforme identificador.
-->
## 19. OPSEC para Investigadores

### 19.1 Princípios

1. **Assuma compromisso permanente**: o alvo PODE estar monitorando.
2. **Compartimentação**: separe persona real, persona investigativa e infraestrutura operacional.
3. **Minimização**: colete o mínimo necessário; não "stalkeie" além do escopo legal.
4. **Documentação**: cadeia de custódia desde o primeiro acesso (Hunchly, ata notarial).
5. **Anti-atribuição**: IP, DNS, timezone, idioma, fingerprint, padrões comportamentais — todos coerentes com a legenda.

### 19.2 Infraestrutura Mínima

| Camada | Ferramenta |
|---|---|
| Host | Máquina física dedicada OU VM descartável (VMware/VirtualBox/Proxmox/Qubes) |
| SO operacional | Linux hardened, Tails (live), Whonix (Tor-gated) |
| Navegador | Firefox com user.js hardening OU Brave privado OU Tor Browser (quando apropriado) |
| Container de sessão | Firefox Multi-Account Containers / Temporary Containers |
| Anti-fingerprint | CanvasBlocker, FingerprintDefender, JShelter, LibreWolf, Mullvad Browser |
| DNS | DoH via Cloudflare 1.1.1.1, Quad9, Mullvad DNS, DNSCrypt |
| VPN | Mullvad, IVPN, ProtonVPN, Windscribe (com pagamento anônimo quando operacional) |
| Tor | Tor Browser, tor + obfs4/meek-azure para redes restritivas |
| E-mail | ProtonMail, Tutanota, Mailfence (contas operacionais) |
| Armazenamento | Cryptomator, VeraCrypt, LUKS (containers encriptados) |
| Comunicação | Signal, SimpleX (com cuidados de OPSEC do device) |
| Senhas | KeePassXC / Bitwarden self-hosted |
| 2FA | Hardware (YubiKey, Solo) — evitar SMS |

### 19.3 Checklist Pré-Operação

- [ ] VM com snapshot limpo
- [ ] VPN conectada ANTES de qualquer app
- [ ] Kill switch de VPN ativo
- [ ] DNS leak test (browserleaks.com)
- [ ] WebRTC leak test
- [ ] Fingerprint test (amiunique.org, creepjs)
- [ ] Timezone/locale coerentes com legenda
- [ ] JavaScript/cookies conforme política do caso
- [ ] Hunchly ativo (captura forense)
- [ ] Comando/MP/ordem judicial em mãos (quando necessário)
- [ ] Registro formal início: data, hora, investigador, caso

### 19.4 Armadilhas Comuns

- **Canary tokens**: links/imagens que notificam o alvo quando você acessa (use Thinkst Canary para PROTEGER; saiba que alvos podem usar contra você).
- **Referer leak**: hyperlinks vazam origem; use `rel="noreferrer"`.
- **Browser fingerprint único**: navegador padrão + extensões delatam identidade.
- **Retweet/like acidental**: manter conta logada em dispositivo errado.
- **Metadados em ofícios/laudos**: limpar EXIF/autor antes de compartilhar.
- **Reutilização de screenshots**: Hunchly adiciona hash + timestamp forense; prints soltos não.
- **Google account persistente**: pesquisas logado vs anônimo = resultados diferentes + expõe investigador.

### 19.5 Firefox user.js — Endereços de Referência

- **arkenfox/user.js**: github.com/arkenfox/user.js (hardening validado pela comunidade)
- **Betterfox**: github.com/yokoffing/Betterfox (balanceado)
- Configurações críticas:
  - `privacy.resistFingerprinting = true`
  - `media.peerconnection.enabled = false` (WebRTC)
  - `network.dns.disablePrefetch = true`
  - `network.prefetch-next = false`
  - `browser.safebrowsing.*` conforme necessidade



