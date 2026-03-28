# Executive Summary
## Evil Twin Attack Defense: Practical Guidelines for Public Wi-Fi Users

**Author:** Saveliy Golubev | MAOU Gymnasium №16, Tyumen, Russia | 2026  
**Research Type:** Individual Applied Security Research  
**Full Paper:** Available upon request (Russian, 30+ pages)

---

## What Is the Problem?

Every time you connect to "Free_Airport_WiFi" or "Cafe_Guest", you may be connecting to an attacker's laptop, not a real router. This is the **Evil Twin attack** — a rogue access point that perfectly mimics a legitimate one.

The attacker does not need to break any encryption. They simply create a more convincing copy of the network and wait for your device to connect automatically.

**Time to execute a full attack from scratch: ~15 minutes.**  
**Equipment cost: a laptop running free, open-source software.**

---

## What Was Researched

This project conducted a complete, three-phase investigation:

**Phase 1 — Theory:** How public 802.11 Wi-Fi networks work, where their vulnerabilities lie, and how an Evil Twin attack unfolds across five stages (reconnaissance → rogue AP → deauth → interception → phishing portal).

**Phase 2 — Lab Simulation:** The attack was reproduced end-to-end in a fully isolated virtual environment (Kali Linux + VirtualBox, Internal Network mode). Using the open-source `airgeddon` framework, a rogue access point with a captive phishing portal was deployed. A test Android device connected to it and submitted test credentials — which were captured instantly on the attacker's terminal.

**Phase 3 — Defense Guidelines:** Based on the experiment's findings, a structured 6-rule protection framework was developed, targeting everyday users without technical backgrounds.

---

## Key Findings

- The attack bypasses cryptography entirely — it exploits **human behavior**, not code
- **Auto-connect** to known Wi-Fi networks is the primary technical enabler
- **HTTPS alone is not sufficient protection** — phishing portals can carry valid SSL certificates
- The attack is equally effective against **open networks** and **WPA2 password-protected** shared networks
- Adequate protection is achievable with simple, free, accessible tools (VPN, 2FA)

---

## The 6-Rule Defense Framework

| Priority | Rule | Core Action |
|---|---|---|
| 🔴 Critical | **Use a VPN** | Encrypts all traffic before it leaves your device |
| 🔴 Critical | **Disable auto-connect** | Prevents automatic connection to rogue APs |
| 🟠 High | **Avoid sensitive actions on public Wi-Fi** | Use mobile data (4G/5G) for banking, email |
| 🟠 High | **Enable 2FA on all accounts** | Captured passwords become useless without OTP |
| 🟡 Medium | **Verify SSID with staff** | Confirm exact network name before connecting |
| 🟡 Medium | **Keep software updated** | Closes browser/OS vulnerabilities exploitable via MitM |

---

## Practical Impact

The primary deliverable of this research is not a technical tool — it is **educational material that changes user behavior**. The live demonstration format proved that seeing credentials captured in real time produces stronger security awareness than abstract warnings.

Target audience: general public, students, corporate employees — anyone who uses public Wi-Fi.

---

*This research was conducted entirely in an isolated environment on researcher-owned equipment. No real networks, users, or credentials were involved.*
