# Interview Q&A — VPN Fundamentals

## 1) What is a VPN?
- A Virtual Private Network creates an encrypted tunnel between your device and a VPN server. Traffic appears to come from the server’s IP, masking your source IP from local networks and ISPs. VPNs can be app‑ or system‑wide depending on the client.

## 2) How does a VPN protect privacy?
- It encrypts traffic between your device and the VPN server, preventing local eavesdroppers (e.g., on public Wi‑Fi) and ISPs from seeing your plaintext traffic and destination sites. Note: the VPN provider can see your exit traffic unless additional protections (HTTPS, DoH) are in use. VPNs don’t replace HTTPS or good browser hygiene.

## 3) Difference between VPN and proxy?
- VPN: system‑wide tunnel with encryption; routes most traffic through the server.
- Proxy: app‑specific forwarding, often without encryption (unless HTTPS/SOCKS5 with TLS); typically only the configured application uses it.

## 4) What is encryption in VPN?
- Data plane encryption (e.g., AES‑256‑GCM or ChaCha20‑Poly1305) protects confidentiality and integrity. Handshakes use protocols like TLS (OpenVPN) or Noise (WireGuard) for key exchange and authentication, commonly providing Perfect Forward Secrecy (PFS) via ephemeral keys.

## 5) Can VPN guarantee complete anonymity?
- No. VPNs shift trust to the provider. Websites can still track via cookies, fingerprinting, and logged‑in accounts. Legal requests, provider/server logs, and endpoint compromise can reveal activity. For stronger anonymity, separate tools (e.g., Tor) are used with different trade‑offs.

## 6) What protocols do VPNs use?
- WireGuard: modern, fast, lean codebase; often best performance; uses Noise‑based cryptography (ChaCha20‑Poly1305, Curve25519).
- OpenVPN: mature and flexible; runs over UDP/TCP; widely supported; uses TLS with ciphers like AES‑GCM/ChaCha20.
- IKEv2/IPsec: stable on mobile, quick re‑connects; good for roaming.

## 7) What are some VPN limitations?
- Speed/latency overhead; free tiers can be congested.
- Trust: provider can see exit traffic; policy/jurisdiction matters.
- Blocking: streaming sites, banks, or CDNs may block VPN ranges; captchas increase.
- Not a silver bullet: doesn’t prevent phishing/malware; endpoint security still required.
- Potential DNS/IPv6/WebRTC leaks if misconfigured.

## 8) How does a VPN affect network speed?
- Extra routing and encryption add latency and can reduce throughput. Impact depends on protocol (WireGuard vs OpenVPN), server distance/load, peering to target sites, and your device’s CPU/network quality. Nearest servers and modern protocols typically perform better.

Best Practices (quick list)
- Use reputable providers; install official clients only.
- Keep kill switch enabled; verify DNS/IPv6 leak protection.
- Prefer modern protocols (WireGuard/OpenVPN UDP) and nearby servers.
- Continue using HTTPS and good browser hygiene; a VPN is one layer of defense.

Bonus: VPN vs Tor (high‑level)
- VPN: single provider; faster; suitable for everyday privacy and public Wi‑Fi. Trust is centralized in provider.
- Tor: multi‑hop overlay; stronger anonymity model; slower; not ideal for streaming. Trust is distributed; exit nodes can see plaintext if not using HTTPS.
