# Evil Twin Attack Chain — 5-Stage Flow

```mermaid
flowchart TD
    A["Stage 1: Reconnaissance\n──────────────────────\nWireless adapter → monitor mode\nairodump-ng scans air\nTarget SSID identified\n(e.g. Free_Public_Lab)"]

    B["Stage 2: Evil Twin Deployment\n──────────────────────\nRogue AP created with identical SSID\nEncryption disabled (Open network)\nSignal boosted to appear more attractive\nhostapd manages the fake AP"]

    C["Stage 3: Deauthentication Attack\n──────────────────────\naireplay-ng sends spoofed deauth frames\nVictim device disconnects from real AP\nDevice auto-connects to strongest signal\n→ lands on Evil Twin"]

    D["Stage 4: Traffic Interception\n──────────────────────\nAll victim traffic routed through attacker\ndnsmasq hijacks all DNS queries\niptables redirects HTTP (port 80)\nlighttpd serves phishing page"]

    E["Stage 5: Credential Capture\n──────────────────────\nVictim opens any website\nBrowser gets phishing captive portal\nCredentials submitted via POST form\nairgeddon logs: 'Credentials captured!'"]

    A --> B --> C --> D --> E

    style A fill:#1a1a2e,color:#e0e0e0,stroke:#4a9eff
    style B fill:#16213e,color:#e0e0e0,stroke:#4a9eff
    style C fill:#c0392b,color:#ffffff,stroke:#e74c3c
    style D fill:#8e44ad,color:#ffffff,stroke:#9b59b6
    style E fill:#c0392b,color:#ffffff,stroke:#e74c3c
```

## Key Insight

> The attack does **not** break any cryptography.  
> It creates a new, trusted-looking network that the victim **chooses to join**.  
> The vulnerability is behavioral, not technical.
