# Online COOP — Ver.4.2.0 (experimental)

## English

### Compatible devices

macOS is excluded from this preview at the project owner's request.
Windows, Linux and Android builds use the same Online protocol. Any of these builds can host or join another supported build. Everyone must install **the same revised Ver.4.2.0 package (30 October 2026)** and supply their own compatible ROM. Real mixed-device and Internet play have not yet been verified on physical hardware.

### Host a session
1. Start or load your campaign and reach normal gameplay, outside battles and menus.
2. Open **F1 → Online** (Mr. Saturn → Online on Android).
3. Choose Ness/Mess, Paula, Jeff or Poo, and the port (default **32176**).
4. Select **Host a game**. Reopen Online to see your local IPv4 address and random six-digit room code.
5. Share the address, port and code with the other players. Keep the host game running.

### Join on the same Wi-Fi / LAN
1. Open **Online**, choose your character and enter the host's room code.
2. Select **Find LAN games**. Wait up to three seconds.
3. Select a discovered game (left/right or tap to cycle), then **Join selected LAN game**.
4. If discovery is blocked by the router, enter the host's local IPv4 address and port and use **Connect by IP** instead.

On Android, tapping the IP, port or room-code field opens a numeric keyboard; the IP keyboard includes a decimal point. The Done key finishes editing.

Guest Wi-Fi isolation can prevent devices from communicating. Discovery uses UDP on the selected port; gameplay uses TCP on that port.

### Join from another network
The host must be reachable through a public IPv4 address. Forward the chosen **TCP** port on the router to the host's local IPv4 address and allow the application through the host firewall. Guests enter the public IPv4 address, external port and room code. This build does not change router/firewall settings automatically, provide a relay, or bypass CGNAT. Where direct incoming connections are unavailable, direct-IP Internet hosting will not work without a network arrangement that makes the host reachable.

### Hamachi / routed VPN
1. Put host and guests on the same working VPN network using the VPN software supported by their devices.
2. Host normally in **Online**. The game listens on its chosen TCP port on all local interfaces, including VPN interfaces.
3. Guests enter the host's **VPN IPv4** in **Host IP / Hamachi IPv4**, the same port and the six-digit game room code, then choose **Connect by IP**.
4. LAN discovery is optional and may not cross VPN adapters; direct IP is the intended VPN path. The IP shown by the game may be the ordinary LAN address: copy the VPN address from the VPN client instead.

The game does not install a VPN or change its firewall rules. VPN software/platform support must be checked separately, particularly on Android. Hamachi's virtual-address concept is described in [GoTo's documentation](https://lmi-documentation-origin.azurewebsites.net/webhelp/EN/CentralUserGuide/LogMeIn/c_hamachi_Virtual_IP.html). No external VPN session has been tested here.

### Gameplay
- Up to four players total, one player per device, with an individual full-window view.
- The host runs the shared native COOP campaign: progression, enemy encounters, inventories and native battle rules remain together.
- Players can explore separately and join another player's battle, using the existing COOP mechanics.
- Joint battles retain simultaneous native command selectors.
- Hold **L3 + left stick up/down** for personal zoom. Tap **L3** to choose an active player to teleport to. **R3** changes your color scheme.
- Keyboard controls follow your configured preset; PC mouse and Android gestures are routed to the remote player. Android adapts the transmitted view when the display rotates.
- Rendering/game language follow the host. Resolution, local volume, controller mappings and F1/F2 language remain local; the camera zoom entry sends a personal zoom request.
- The host F1 window pauses the simulation; a visitor's F1 window only stops that visitor's controls.
- The host manages campaign saves. Disconnect before loading states, changing chapters or returning to the title. Rewind is disabled during Online sessions.
- Use **Online → Disconnect / stop server** to leave. The visitor's own local campaign remains separate. The host retains the session's campaign and player inventories in host saves.

### How this first version works
The host is authoritative and streams each player's view. Native music/sound commands are sent to each listener's local SPC/DSP engine, using that listener's own compatible donor ROM. Remote devices send controls rather than run divergent campaign copies. The network carries no ROM, executable code or native memory snapshots. The view stream currently targets up to **30 pictures/second**; native gameplay still runs on the host's normal simulation clock. Upload bandwidth, latency and host performance affect responsiveness. Players in different rooms receive their own music and effects; participants in a shared battle receive that battle's sound. The guest's local SPC state is restored on disconnect. The first 4.2 preview used a shared audio mix; use the revised package on every device.

Failed entry attempts are limited per IPv4 address (six failures in 30 seconds cause a 30-second cooldown). Pending handshakes and UDP discovery replies are also bounded. The room code gates entry; the direct transport is **not encrypted**. Use sessions with people and networks you trust. No accounts, public server directory or third-party relay are involved. Physical Android/Linux and public-Internet sessions still need testing. Back up saves before testing experimental COOP.

### Validation performed
- Separate native host/client processes over real loopback TCP, with UDP room discovery.
- One host plus three remote clients, character selection, remote movement, individual zoom/colors, remote teleport into a joint battle and native victory.
- Non-silent local SPC/DSP output, distinct guest music commands, unchanged host music command state, video decoding, portrait view and a return to landscape.
- Battle command pixels and hit rectangles checked for every player; host zoom changed independently of guests.
- Client native campaign state remains unchanged by joining and leaving.
- Wrong room-code and oversized-frame rejection; bounded codec runs and CRC checks.
- These tests are not a substitute for a complete campaign or physical cross-platform play.

## Português

### Compatibilidade
As builds Windows, Linux e Android usam o mesmo protocolo. Qualquer uma pode hospedar ou entrar na partida de outra. Todos precisam da **Ver.4.2.0** e da própria ROM compatível. A combinação entre aparelhos reais e a conexão pública pela Internet ainda precisam de validação prática.

### Hospedar
1. Inicie ou carregue a campanha e chegue ao cenário normal, fora de batalhas e menus.
2. Abra **F1 → Online**, ou **Mr. Saturn → Online** no Android.
3. Escolha o personagem e a porta (padrão **32176**).
4. Selecione **Hospedar partida**. Reabra Online para consultar o IPv4 local e o código aleatório de seis dígitos.
5. Passe endereço, porta e código aos amigos e mantenha o jogo aberto.

### Entrar pela mesma rede
Escolha seu personagem, digite o código informado pelo anfitrião e use **Buscar na rede local**. Aguarde até três segundos. Selecione uma partida encontrada e use **Entrar na partida da rede**. Se a descoberta não funcionar, preencha o IPv4 local e a porta do anfitrião e selecione **Conectar por IP**. Redes de convidados podem isolar os aparelhos.

### Entrar pela Internet
É necessário que o anfitrião seja alcançável por IPv4 público: encaminhe a porta **TCP** escolhida no roteador para o IPv4 local do aparelho anfitrião e permita o aplicativo no firewall. O visitante informa IPv4 público, porta externa e código. Não há relay, configuração automática do roteador nem solução automática para CGNAT.

Ao tocar nos campos IP, porta e código no Android, abre o teclado numérico. O campo IP inclui ponto; o botão Concluir termina a edição.

### Hamachi / VPN
Conecte os aparelhos à mesma VPN compatível com seus sistemas. Hospede normalmente; no convidado informe o IPv4 virtual do anfitrião, a porta e o código da sala, e use **Conectar por IP**. O IP exibido pelo jogo pode ser o da LAN: copie o endereço virtual no programa da VPN. A descoberta LAN pode não atravessar a VPN. Não há instalação ou alteração automática de firewall/VPN; a disponibilidade no Android depende do software utilizado. Uma sessão externa por VPN ainda não foi testada aqui.

### Regras e limites
- Até quatro jogadores, um por aparelho, cada um com sua própria visão da partida.
- A campanha e as batalhas usam o COOP nativo do anfitrião; é possível explorar separado e participar de lutas conjuntas com seleção simultânea.
- **L3 + cima/baixo** ajusta o zoom pessoal. Um toque em **L3** escolhe um jogador para teleporte. **R3** muda as cores.
- Teclado/mouse seguem a predefinição configurada. Gestos do Android e rotação da tela são encaminhados pela sessão.
- Renderização e idioma do jogo seguem o anfitrião; resolução, volume local, controles e idioma de F1/F2 são locais. O zoom do menu ajusta a câmera pessoal.
- O F1 do anfitrião pausa a simulação; o F1 do visitante apenas interrompe os comandos desse visitante.
- Os saves da campanha ficam com o anfitrião. Desconecte antes de carregar estados, trocar capítulos ou voltar ao título. Rewind fica desabilitado no Online.
- A campanha local do visitante permanece separada. Os inventários da sessão fazem parte dos saves do anfitrião.
- Nesta revisão, o anfitrião transmite a visão de cada jogador e os comandos nativos de música e efeitos. O vídeo busca até **30 imagens por segundo**; a simulação nativa continua no relógio normal do anfitrião.
- Cada aparelho reproduz sua própria trilha pelo SPC/DSP local. Jogadores em ambientes diferentes recebem trilhas diferentes; participantes da mesma batalha recebem seus efeitos. Ao desconectar, o áudio local é restaurado. Todos devem usar o mesmo pacote 4.2 revisado de 30/10/2026.
- Seis falhas de entrada pelo mesmo IPv4 em 30 segundos provocam uma espera de 30 segundos. Solicitações pendentes e respostas de descoberta são limitadas.
- O código controla a entrada, mas a conexão direta **não é criptografada**. Use com pessoas e redes de confiança.
- Testes em processos locais passaram; ainda faltam aparelhos reais de sistemas diferentes e redes externas. Faça backup dos saves antes de testar.

## Platform network permissions

This Android build targets SDK 35 and declares INTERNET. Android's guidance grants local network access implicitly for this target level; it says not to request ACCESS_LOCAL_NETWORK before targeting SDK 37. See [Android's local network permission guidance](https://developer.android.com/privacy-and-security/local-network-permission). No location or contacts permission is added.

## Revised 4.2 interface and campaign notes
- Desktop defaults for fresh preferences: fullscreen, 1920 x 1080. Existing user preferences are kept.
- Mr. Saturn starts enabled on Android; Touch settings can disable it. The portrait F1 header includes an interactive Saturn.
- The obsolete floating KO button is removed. Online Android has a lower-left teleport shortcut; SMAASH remains in the native God Menu battle action.
- F2, F3 and F4 close their own open selector when pressed again.
- Mouse/touch selection uses logical UI coordinates; portrait equipment choices have a gray selection highlight.
- P1 uses the native window palette; other players retain their identifying tints. A single view has no split-screen border.
- Choosing Paula, Jeff or Poo keeps native story/script slots and progression. Original cutscene appearances are retained; this is not a rewrite of every cinematic. Complete campaigns with each protagonist have not been played through in validation.
- The desk bear in Ness's room offers a short bilingual community thank-you. The Apple Kid mouse dialogue now has a deliberate pause before its thanks.
- Frame targets are limits, not guaranteed device FPS. Physical PC/Android interoperation, phone performance and public Internet/VPN play still need hands-on validation.

Android: Gameplay → Vertical interface offers **New (default)** and **Old**. Touch → **Lock landscape** is **off by default**; enabling it keeps the phone sideways. Personal zoom supports **50–250%**, including pinch and remote sessions.

Android: Gameplay → Interface vertical oferece **Nova (padrão)** e **Antiga**. Touch → **Bloquear na horizontal** começa **desligado**; ao ativar, mantém o celular de lado. Zoom pessoal de **50–250%**, também por pinça e no Online.

Guests start with their own device zoom preference, including the Android 140% default. The host camera does not supply the guest zoom fallback. The portrait enemy/background framing grows for small encounters while keeping wide enemies within the native canvas. The desk uses the original stationary Teddy bear sprite from the donor assets.

## FPS experiment and security limits

This separate experiment targets up to 60 video frames per second. Actual host rendering and guest reception are measured independently; neither is guaranteed on phones or over the Internet. Native simulation and audio are not sped up.

Guest messages are restricted to a 32-byte handshake, 16-byte input, or empty heartbeat; invalid types/lengths are rejected before payload processing. Guest traffic is capped at 240 complete messages per second. Existing memory/queue/frame limits and room-code attempt limits still apply.

The direct transport remains **unencrypted**. A room code is admission control, and CRC32 detects corruption; neither provides encryption or protection against a network observer. Use trusted LAN peers or an encrypted VPN tunnel for Internet play. The game does not configure router forwarding automatically. Do not publish a room code. Do not treat these limits as protection against every possible denial-of-service attack.
