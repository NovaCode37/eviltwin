# Public Wi-Fi Security Checklist
### Protection Against Evil Twin & Man-in-the-Middle Attacks

*Based on research: "Evil Twin Attack Defense: Practical Guidelines for Public Wi-Fi Users" (2026)*

---

## Before Connecting to Any Public Wi-Fi

- [ ] **Activate your VPN** before connecting (WireGuard or OpenVPN-based provider recommended)
- [ ] **Verify the exact SSID** with a staff member — do not guess or pick from a list
- [ ] **Check for duplicate networks** — two entries with the same name is a red flag
- [ ] Confirm auto-connect to open networks is **disabled** in your device settings

---

## While Connected

- [ ] VPN status shows **active and connected** — if it dropped, reconnect before doing anything
- [ ] Avoid logging into **email, banking, social media** without VPN
- [ ] Prefer **mobile data (4G/5G)** for sensitive operations if data plan allows
- [ ] Do **not** enter passwords if a captive portal asks for your social media or email login

---

## Account Hardening (Do Once, Protects Always)

- [ ] **2FA enabled** on email, banking, social media, and work accounts
- [ ] Using a **password manager** — unique password for every service
- [ ] Auto-updates enabled for OS, browser, and apps
- [ ] Old public Wi-Fi networks **removed** from saved networks list

---

## Warning Signs of an Active Attack

| Sign | What It Means |
|---|---|
| Two networks with the same name, different signal strength | Possible Evil Twin AP nearby |
| Captive portal asks for email/social media password | Phishing portal — disconnect immediately |
| VPN active but a login page still appears | DNS hijacking in progress |
| Sudden disconnection from a known network | Possible deauth attack — do not reconnect without VPN |
| Browser shows HTTP on a site you know uses HTTPS | Possible SSL stripping attack |

---

## Quick Reference: Which Protection to Use

| Situation | Recommended Action |
|---|---|
| Cafe / airport / hotel Wi-Fi | VPN always on |
| Banking or work email | Mobile data only |
| Not sure if network is real | Ask staff, check BSSID |
| Traveling, limited mobile data | Personal hotspot from phone |
| Credentials possibly exposed | Change password + revoke sessions immediately |

---

## Technical Detection (Advanced)

```
# Check for duplicate SSIDs on Linux/Mac
sudo iwlist scan | grep -E "ESSID|Address"

# Or use a Wi-Fi Analyzer app on Android to visualize all APs and their BSSIDs
```

Legitimate AP BSSID format: matches the MAC address on the router sticker or venue's IT documentation.  
Any second AP with the same SSID but a **different BSSID** = investigate before connecting.

---

*For the full research paper and lab methodology, see the main [README](../README.md) and [Executive Summary](../docs/executive-summary.md).*
