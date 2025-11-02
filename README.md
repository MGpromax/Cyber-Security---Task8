# Cyber Security Internship — Task 8: VPN Setup and Privacy

Objective
- Understand the role of VPNs in protecting privacy and securing communication. Set up a free VPN, verify connection (IP/DNS/IPv6), evaluate performance, and document results with screenshots.

Scope & Tools
- Providers (free tier): ProtonVPN, Windscribe (or similar reputable services)
- Verification: whatismyipaddress.com, fast.com (or Speedtest), DNS leak tests

What this repo contains
- `task8/procedure.md` — step‑by‑step setup, verification (IP/DNS/IPv6/WebRTC), kill‑switch test, performance methodology, and troubleshooting
- `task8/report.md` — professional report template to record your results, averages, and screenshots
- `task8/interview-qa.md` — concise answers to likely interview questions with protocol/encryption notes

Executive Summary (fill after your hands‑on)
- Provider/tier: [ProtonVPN Free / Windscribe Free]
- Platform: [Windows/macOS/Linux/iOS/Android]
- Protocol used: [WireGuard/OpenVPN/IKEv2]
- Connected location: [Country/City]
- Observed IP change: [Old → New]
- Speed impact: [Baseline vs VPN]
- Key takeaways: [privacy improvements, limitations]

Threat Model — What VPNs Do vs Don’t
- Do: Encrypt traffic between your device and the VPN server; hide your source IP from local networks/ISPs; reduce risk on public Wi‑Fi; centralize DNS via the provider.
- Don’t: Make you fully anonymous; block tracking cookies/fingerprinting; replace HTTPS; bypass endpoint malware; prevent account‑linked tracking.

Provider Selection Checklist (Free tiers)
- Reputation and transparency (audits, ownership, jurisdiction, policy clarity)
- Privacy policy and logging claims (connection vs activity logs)
- Protocol support (WireGuard/OpenVPN), kill‑switch, DNS/IPv6 leak protection
- Server availability in your region; speed on free clusters; no shady bundling

Method Summary
1) Choose a reputable free VPN provider and sign up.
2) Install the official client and sign in.
3) Connect to a server (preferably the closest one for performance).
4) Verify IP change, DNS resolver, and IPv6/WebRTC leak status; confirm traffic is encrypted (HTTPS still required end‑to‑end).
5) Compare speed before vs after (3 runs each, average). Note latency/throughput changes.
6) Test the kill‑switch and optionally try another protocol/server; capture screenshots and complete `task8/report.md`.

Safety and Privacy
- Use only official apps from vendor sites/app stores. Avoid third‑party or cracked clients.
- VPNs shift trust to the provider. Review privacy policies and logging claims.
- VPNs do not make you fully anonymous; websites can still track via cookies/fingerprints.

Metrics to Capture (recommended)
- Public IP (before/after), Geo location
- DNS servers in use (before/after), DNS leak test result
- IPv6 leak status; WebRTC leak status (if using browser‑based apps)
- Speed: download, upload, latency (3 runs, averaged) for baseline and VPN
- Protocol/server used; kill‑switch setting and test outcome

How to reproduce
- Follow `procedure.md` on your system. Add redacted screenshots (no sensitive info) to a `screenshots/` folder.

Submission
- Fill `report.md` with your actual results and add at least one connection status screenshot.
- Commit/push to a new GitHub repo and submit the link per your program’s instructions.

Legal & Ethical
- Use VPNs responsibly and in accordance with local laws and provider terms. Do not attempt to evade lawful restrictions or violate network policies.
