# El Bakkali

Building tools that make cloud monitoring and web security less painful, plus the occasional DIY smart home project. Everything open source, everything free.

---

### What I Build

**[Azure Monitor & Sentinel](https://github.com/stars/el-bakkali/lists/azure-monitor-tools)** — Diagnostic and validation tools for engineers working with Azure's data collection pipeline. When syslog messages aren't arriving, data collection rules are silently dropping data, or the Azure Monitor Agent can't connect — these tools tell you exactly what's wrong.

| Project | What it does |
|---|---|
| [DCR & KQL Validator](https://github.com/el-bakkali/dcr-kql-validator) | Offline desktop tool for validating Data Collection Rules and KQL transformation queries before deployment. Built with Rust + Tauri. |
| [Syslog CEF Analyzer](https://github.com/el-bakkali/SyslogCEFAnalyzer) | Drop a pcap or log file → instantly see which syslog and CEF messages are valid, malformed, or missing fields. 8 automated diagnostic rules. |
| [AMA Network Analyzer](https://github.com/el-bakkali/AMANetworkAnalyzer) | Diagnose Azure Monitor Agent connectivity issues from packet captures. 7 diagnostic rules covering DNS, TLS, firewalls, proxies, and Private Link. |
| [Logs Ingestion API Troubleshooter](https://github.com/el-bakkali/azure-logs-ingestion-api-troubleshooter) | Step-by-step Bruno API collection for diagnosing DCR stream mismatches, column misalignments, and ingestion failures. |
| [Azure Brute-Force Defense](https://github.com/el-bakkali/azure-bruteforce-defense) | AI-powered SSH threat hunting with Azure OpenAI — ask questions about your security logs in plain English. |
| [Cloudflare Log Ingestion](https://github.com/el-bakkali/cf-log-ingestion) | Automated Cloudflare WAF firewall log ingestion into Azure Log Analytics. 42 KQL queries and a full workbook included. |

**Cloudflare Edge Security** — Lightweight security tools that run entirely on Cloudflare Workers (free tier), with zero JavaScript on the client, zero cookies, and zero tracking.

| Project | What it does |
|---|---|
| [CF Bot Guard](https://github.com/el-bakkali/cf-bot-guard) | 16-signal bot detection + privacy-respecting analytics with a built-in dashboard. All at the edge, no cookies, no JS. |
| [CF Email Domain Decoy](https://github.com/el-bakkali/cf-email-domain-decoy) | Cryptic decoy landing page for email-only domains with bot fingerprinting and Moroccan geometric CSS art. |
| [Blog Guard](https://github.com/el-bakkali/blog-guard) | Path allowlist for static sites — redirects scanners to the homepage as a silent bot trap. |

**ESP32 & Smart Home** — DIY hardware projects using ESPHome and Home Assistant, because paying shop prices for smart home gear is daft.

| Project | What it does |
|---|---|
| [ESP32-A1S Sendspin](https://github.com/el-bakkali/esp32-a1s-sendspin) | Multi-room audio with the ESP32-A1S Audio Kit and Music Assistant. ⭐ 11 stars |
| [Air Quality Monitor](https://github.com/el-bakkali/esphome-air-quality-monitor) | CO2, temperature, humidity & VOC monitoring on the Cheap Yellow Display with a custom LVGL UI. |
| [Thread Border Router](https://github.com/el-bakkali/esp-thread-border-router) | A £15 Thread Border Router with Ethernet backhaul — replaces a £130 Apple HomePod or Google Hub. |
| [DIY Streaming Key Light](https://github.com/el-bakkali/diy-streaming-key-light) | A ~£25 bi-colour streaming panel that replaces a £200 Elgato Key Light. |

---

### How I Build

- **Offline-first** — Every desktop tool works without an internet connection. No telemetry, no phone-home.
- **Zero dependencies where possible** — Custom pcap parsers, syslog/CEF parsers, and packet dissectors built from scratch in pure .NET and Rust.
- **Security-conscious** — Audited against OWASP ASVS, NIST CSF, and CIS Controls. Managed identity over API keys. Input validation at every boundary.
- **Free tier friendly** — Cloudflare Workers, Azure Functions on Flex Consumption, and ESP32 microcontrollers. If it can run for free, it does.

---

### Languages & Tools

`Rust` · `C#` · `JavaScript` · `Python` · `PowerShell` · `Bicep` · `KQL` · `YAML`

Tauri · .NET · Cloudflare Workers · Azure Functions · ESPHome · Home Assistant · Bruno API Client

---

*All projects are MIT licensed.*
