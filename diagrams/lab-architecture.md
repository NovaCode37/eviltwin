# Isolated Lab Architecture

```mermaid
flowchart TD
    subgraph HOST["🖥️ Physical Host — Windows 10/11"]
        subgraph VBOX["Oracle VM VirtualBox 7.0"]
            subgraph INTERNAL["🔒 Internal Network (air-gapped)"]
                KALI["Kali Linux 2024.1\n─────────────────\nairgeddon v11.22\nhostapd\ndnsmasq\nlighttpd\niptables\n\n[ATTACKER]"]
            end
        end
        WIFI["Physical Wi-Fi adapter\n(host network)"]
    end

    ANDROID["📱 Android Device\n[VICTIM]\n\nManual connection\nto rogue AP only"]

    INTERNET(("🌐 Internet"))

    KALI <-->|"Internal Network ONLY\nNo bridge to host"| ANDROID
    HOST -.- WIFI
    WIFI -.- INTERNET

    KALI -.->|"❌ NO ACCESS"| INTERNET
    ANDROID -.->|"❌ NO ACCESS"| INTERNET

    style HOST fill:#1a1a2e,color:#e0e0e0,stroke:#4a9eff
    style VBOX fill:#16213e,color:#e0e0e0,stroke:#2980b9
    style INTERNAL fill:#0f3460,color:#ffffff,stroke:#27ae60
    style KALI fill:#c0392b,color:#ffffff,stroke:#e74c3c
    style ANDROID fill:#2c3e50,color:#e0e0e0,stroke:#7f8c8d
    style INTERNET fill:#1a1a2e,color:#7f8c8d,stroke:#7f8c8d
```

## Why This Matters

| Property | Value |
|---|---|
| External network access | ❌ None — VirtualBox Internal Network mode |
| Real users affected | ❌ Zero — physically isolated environment |
| Legal status | ✅ Fully compliant — researcher-owned equipment only |
| Internet reachability | ❌ Blocked at hypervisor level |
