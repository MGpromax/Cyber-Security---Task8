# Task 8 — Procedure: Set Up a VPN and Verify Privacy

Important: Only use official VPN clients. Do not share screenshots containing personal data, account details, or internal IPs.

Prerequisites
- A reputable free VPN account (e.g., ProtonVPN Free, Windscribe Free).
- System with admin rights to install software (Windows/macOS/Linux) or mobile (iOS/Android).
- A modern browser for testing (Chrome/Firefox/Edge/Safari/Brave).
- Optional: A second network (mobile hotspot) if your main network blocks VPNs.

1) Choose and Install
- Select a provider (consider privacy policy, supported platforms, protocols, and free‑tier limits).
- Download from the official website or app store only.
- Install the client and sign in.
- Example locations in apps:
  - ProtonVPN: enable Kill Switch (Settings → General), set Protocol (Settings → Connection), optionally enable “Smart Protocol”.
  - Windscribe: enable Firewall/Kill Switch, set Protocol to WireGuard/OpenVPN in Preferences.

2) Configure (recommended)
- Auto‑connect on startup: On (optional)
- Kill switch: On (prevents traffic leaks if VPN drops)
- Protocol: Provider default (often WireGuard or OpenVPN). Test both to compare performance.
- Split tunneling: Off by default; use only if required for specific apps; document any exceptions.
- IPv6 handling: Ensure the client supports IPv6 or disables it to avoid leaks.

3) Connect to a Server
- Prefer the nearest/lowest‑latency server for better speed (free tiers may limit choices).
- Wait for the client to show “Connected” with server name and new IP.
- Capture a connection status screenshot for the report.

4) Verify Connection (Privacy Checks)
- Public IP: Open `https://whatismyipaddress.com/` and note your new IP and city/country.
- DNS Leak Test: Visit `https://dnsleaktest.com/` and run “Standard” then “Extended Test”. Expected: DNS resolvers should belong to the VPN provider/location, not your ISP.
- IPv6 Leak: If you have IPv6, check `https://ipleak.net/` and confirm IPv6 queries go through the tunnel or are disabled.
- WebRTC Leak (browser): On `https://browserleaks.com/webrtc`, ensure local/public IPs aren’t exposed when on VPN. If they are, consider disabling WebRTC (may break video calls) or keep this risk in mind.
- Encryption in transit: Remember HTTPS provides end‑to‑end security; the VPN encrypts traffic only between your device and the VPN server.

5) Validate Performance (Methodology)
- Baseline speed: Disconnect VPN and measure at `https://fast.com` or Speedtest (3 runs). Record download, upload, latency; compute average.
- VPN speed: Reconnect VPN and measure again (3 runs). Record and average.
- Optional: Repeat using another protocol (WireGuard vs OpenVPN) or a second server.
- Note any site blocks, captchas, or streaming issues while on VPN.

6) Collect Evidence
- Screenshot the VPN client “Connected” view (server/location/protocol visible if possible).
- Screenshot IP verification from whatismyipaddress.com (redact if needed).
- Screenshot DNS leak test results; optional IPv6/WebRTC leak test screenshots.
- Save filenames under `screenshots/` and reference them in `task8/report.md`.

7) Document Results
- Complete `task8/report.md` with provider, protocol, server, IP/DNS/IPv6/WebRTC results, speed comparisons (averages), kill‑switch behavior, and notes on benefits/limitations.

8) Optional Checks
- Protocol comparison: WireGuard vs OpenVPN (UDP). Note performance and stability differences.
- Kill switch test: Start a continuous ping (e.g., `ping 1.1.1.1`). While connected to the VPN, disable your network adapter or unplug the cable/Wi‑Fi briefly; confirm traffic is blocked until VPN reconnects.
- Split tunneling: If used, document which apps bypass the VPN and why.
- App compatibility: Verify critical apps still work; if blocked, change server/location.

Troubleshooting
- Can’t connect: Try a different protocol (UDP→TCP), another server, or another network; check for local firewalls.
- DNS fails after connect: Toggle the client’s DNS leak protection, flush DNS cache, or restart the client.
- Slow speeds: Choose a nearer/less‑loaded server; try WireGuard; close bandwidth‑heavy apps; retest at a different time.
- Captive portals (public Wi‑Fi): Connect without VPN, complete the portal login, then enable the VPN.
- WebRTC leaks: Consider disabling WebRTC or use browsers with built‑in leak protections; expect possible breakage of video calls.

Post‑Setup Notes
- VPNs improve privacy on untrusted networks (e.g., public Wi‑Fi) and hide your IP from local networks/ISPs.
- They do not make you fully anonymous and do not remove the need for HTTPS, good browser hygiene, or endpoint security.

Uninstall & Cleanup (if needed)
- Disconnect and quit the client. Uninstall using OS procedures.
- Remove residual TAP/WireGuard adapters (Windows) if left behind.
- Re‑enable any OS DNS/IPv6 settings you changed for testing.
