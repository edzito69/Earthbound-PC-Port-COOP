# Experimental online — design, limits and safety

**BE CAREFUL: forwarding a router port exposes the game service to the Internet. A room code does not encrypt the connection. Absolute security cannot be guaranteed.**

This document accompanies **4.20 FPS experimental** for Windows, Linux and Android. The **4.20 stable** snapshot remains separate. Both original custom Read Mes are preserved.

## How online was built

- The host runs the campaign and native player simulations. Guests send controls and receive their individual view and corresponding audio commands.
- Desktop and Android use the same implementation. Cameras and zoom are personal; players sharing one device can use split screen.
- Joint battles reuse native COOP simultaneous command selection. The host resolves the original battle rules and turns.
- Each guest plays music through its local SPC/DSP engine according to its own game situation. Music is not accelerated to improve FPS.
- The protocol does not provide operating-system command execution, ROM transfer, file uploads or native RAM snapshot transfer. This reduces exposure but does not prove the absence of vulnerabilities.
- The native foundation is Brian Pugh and contributors' BrianPugh/earthbound work. LakeSnes, SDL2 and other projects and contributors are credited in CREDITS.md and licenses/. The adaptation includes Edzito's work with AI/Codex assistance. Online is experimental and has not received an independent security audit.

## Implemented safeguards

- Six-digit room codes generated from the operating system's random source, with per-address attempt limits.
- Bounded pending connections, packet sizes, queues, images and handshake/inactivity timeouts.
- Early rejection of invalid packet types and lengths. Guests can send only the expected handshake, input or heartbeat formats.
- A limit of 240 complete messages per second per client and packet-sequence validation.
- CRC32 corruption checks and bounded image decoding. **CRC32 is not cryptographic authentication.**
- LAN discovery does not advertise the room code, limits responses, filters local/VPN sources and never automatically joins a room.
- The game does not automatically configure router port forwarding.

## LAN precautions

Prefer a trusted home network, updated devices and a strong Wi-Fi password. Share room codes only with people you know. A person on the same network may still be able to observe or interfere with unencrypted traffic, depending on network conditions.

Allow the application through the firewall on the private profile only and restrict access to the local subnet where possible. Do not disable the entire firewall. LAN discovery normally uses UDP port 32176; gameplay normally uses TCP on the same port. Check the Online menu if the port has changed.

Discovery supports private IPv4, loopback, link-local, shared VPN address ranges and Hamachi addresses. Unusual networks may need explicit IP/port entry. Do not forward UDP discovery to the Internet.

## Internet play and open ports: extra care

1. Prefer a trusted VPN tunnel configured with encryption between known players. The game does not establish that tunnel or verify the provider's security.
2. Manual port forwarding makes the service reachable by others. If you choose it, forward only the necessary gameplay TCP port; do not expose UDP discovery, remote desktop or unrelated services.
3. Do not publicly post your IP, room code, connection-menu screenshots or network files. Anyone receiving a game view can record it.
4. Stop hosting when finished. Also remove unneeded router forwarding and firewall exceptions: closing the game does not delete manually created rules.
5. Use trusted builds. Do not run as administrator/root merely to bypass connection problems. Back up saves before testing updates.

**There is no TLS, end-to-end encryption, identity authentication, server certificate, anticheat or comprehensive denial-of-service protection.** The code gates admission; it does not protect against a network observer. This project is not a hardened public server.

## Performance and other limits

- The video target is up to 60 FPS. Actual performance depends on host CPU/GPU, phone, audio, player count and network. Neither 50 nor 60 FPS is guaranteed.
- Native rendering and received video are measured separately. Repeated pictures must not be presented as an actual rendering improvement.
- Most simulation work runs on the host. Latency, disconnects, weak Wi-Fi and congested queues can reduce responsiveness and smoothness.
- Every campaign/character combination has not been played through. Automated tests do not replace physical-phone and real-network testing.
- CGNAT, Wi-Fi client isolation, guest networks and firewall rules can prevent connections. The game does not automatically bypass these restrictions.
- Session saves belong to the host. Back them up before upgrading; do not assume unrestricted compatibility between experimental versions.

## Local checks in this version

Tests exercise discovery without exposing the code, incorrect room codes, oversized framing, forbidden bulk-message headers and invalid sequence numbers. They also compare command-window pixels, check codec/checksum behavior and validate battles, input, zoom and audio using separate processes. These checks are not an independent audit, a complete penetration test or a real-network security guarantee.

Join notices appear over gameplay: “Player connecting...” and “Connected!”, with Portuguese equivalents.

## If something looks wrong

Disconnect, stop hosting and preserve your saves. Record the version, player count, devices and triggering action. Remove IPs, room codes, usernames and personal paths before sharing logs or screenshots. Never include ROMs or signing keys.

Updated October 30, 2026. Full credits and licenses: CREDITS.md and licenses/.
