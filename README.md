# Mehdi El Bakkali

I build free, open-source tools that help engineers troubleshoot Azure cloud monitoring and web security — turning hours of investigation into seconds of answers.

I work across cloud observability, edge security, and IoT hardware — building offline-first diagnostic tools, serverless security layers, and DIY smart home devices. Everything I ship is open source, privacy-first, and designed to run at zero cost.

...troubleshooting, fixing things, and building what should already exist.

---

## Featured

> [!NOTE]
> <a href="https://github.com/stars/el-bakkali/lists/azure-monitor-tools"><img src="https://img.shields.io/badge/Azure%20Monitor%20Tools-View%20Collection%20→-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" alt="Azure Monitor Tools"></a>
>
> A curated collection of diagnostic and validation tools for Azure Monitor data collection pipelines — DCR validation, syslog/CEF analysis, AMA network diagnostics, log ingestion troubleshooting, and AI-powered threat hunting.
>
> $\color{#00C853}{\textsf{All free.}}$ $\color{#0078D4}{\textsf{All offline.}}$ $\color{#FF6D00}{\textsf{All open source.}}$

---

## Summary

> [!IMPORTANT]
> - 15 open-source projects across cloud monitoring, edge security, and IoT hardware
> - Privacy and security by default — offline processing, no telemetry, no credentials in code, validated inputs at every boundary
> - Offline-first — every desktop tool works without an internet connection, zero telemetry
> - Zero-dependency builds — custom pcap parsers, syslog/CEF parsers, and packet dissectors from scratch
> - Free tier friendly — Cloudflare Workers, Azure Flex Consumption, and ESP32 boards
>
> <a href="https://www.rust-lang.org"><img src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white" alt="Rust"></a> <a href="https://dotnet.microsoft.com"><img src="https://img.shields.io/badge/C%23-.NET-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt="C#"></a> <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript"><img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JS"></a> <a href="https://www.python.org"><img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"></a> <a href="https://learn.microsoft.com/powershell"><img src="https://img.shields.io/badge/PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white" alt="PowerShell"></a> <a href="https://learn.microsoft.com/azure/data-explorer/kusto/query"><img src="https://img.shields.io/badge/KQL-0078D4?style=flat-square&logo=microsoftazure&logoColor=white" alt="KQL"></a> <a href="https://learn.microsoft.com/azure/azure-resource-manager/bicep"><img src="https://img.shields.io/badge/Bicep-0078D4?style=flat-square&logo=microsoftazure&logoColor=white" alt="Bicep"></a>

---

## Selected Work

<details>
<summary><strong>Azure Monitor & Sentinel</strong> — Diagnostic and validation tools for Azure's data collection pipeline</summary>
<br>

When syslog messages aren't arriving, DCRs are silently dropping data, or the Azure Monitor Agent can't connect — these tools tell you exactly what's wrong.

- **[dcr-kql-validator](https://github.com/el-bakkali/dcr-kql-validator)** — DCR & KQL Transformation Validator

  - Offline desktop tool for validating Data Collection Rules and KQL transformation queries before deployment.
  - Built with Rust + Tauri. ~8 MB binary, 3 direct dependencies, zero network calls.
  - Validates ~90 allowed KQL scalar functions, detects blocked operators, checks `TimeGenerated` output.

- **[SyslogCEFAnalyzer](https://github.com/el-bakkali/SyslogCEFAnalyzer)** — Syslog & CEF Message Format Analyzer

  - Drop a `.pcap` or log file — instantly see which messages are valid, malformed, or missing fields.
  - 8 automated diagnostic rules: format detection, PRI validation, RFC 3164/5424, CEF, Cisco ASA/FTD, encoding, transport.
  - TCP stream reassembly, streaming pcap reader (up to 2 GB), drill-down UI. Zero NuGet packages.

- **[AMANetworkAnalyzer](https://github.com/el-bakkali/AMANetworkAnalyzer)** — AMA Network Trace Analyzer

  - Diagnose Azure Monitor Agent connectivity issues from pcap/pcapng/etl/cab captures.
  - 7 diagnostic rules: endpoint connectivity, DNS resolution, firewall blocking, proxy detection, TLS/cipher compliance, Private Link/AMPLS detection.
  - Supports Azure Commercial, Government, and China sovereign clouds.

- **[azure-logs-ingestion-api-troubleshooter](https://github.com/el-bakkali/azure-logs-ingestion-api-troubleshooter)** — Logs Ingestion API Troubleshooter

  - Step-by-step Bruno API collection for diagnosing DCR stream declaration mismatches, column misalignments, and ingestion failures.
  - Pre-flight schema diff compares your JSON payload against the DCR before sending.
  - Includes a one-command demo environment deployment script.

- **[azure-bruteforce-defense](https://github.com/el-bakkali/azure-bruteforce-defense)** — AI-Powered SSH Threat Hunting

  - Conversational threat hunting — ask "Who's attacking my server?" and Azure OpenAI queries your logs and responds with structured analysis.
  - Full-stack: Ubuntu VM with Fail2ban + Azure Functions + Microsoft Sentinel + GPT-4o-mini.
  - Zero hardcoded secrets — all auth via managed identity.

- **[cf-log-ingestion](https://github.com/el-bakkali/cf-log-ingestion)** — Cloudflare WAF to Azure Log Analytics

  - Automated pipeline: Cloudflare GraphQL API, Python Azure Function, DCR, custom table (23 columns).
  - 42 ready-to-use KQL queries (dashboard, alerts, threat hunting, ML anomaly detection) and a deployable Azure Monitor Workbook.
  - Runs within Azure free tier for low-traffic sites.

</details>

<details>
<summary><strong>Cloudflare Edge Security</strong> — Lightweight security tools on Cloudflare Workers (free tier)</summary>
<br>

Zero JavaScript on the client, zero cookies, zero tracking.

- **[cf-bot-guard](https://github.com/el-bakkali/cf-bot-guard)** — Bot Detection & Analytics

  - Scores every visitor 0-100 using 16 detection signals. Classifies ISPs by type (hosting, mobile, residential, education, corporate).
  - Privacy-respecting analytics stored in KV with a built-in 22-panel HTML dashboard. No cookies, no JS, no PII.
  - Transparent proxy — adds intelligence headers (`x-bot-score`, `x-isp-type`) without blocking.

- **[cf-email-domain-decoy](https://github.com/el-bakkali/cf-email-domain-decoy)** — Decoy Landing Page

  - Cryptic, minimal page for email-only domains with Moroccan geometric CSS art and bot fingerprinting.
  - Zero JavaScript, zero external resources, zero PII exposure. Every path returns identical content.

- **[blog-guard](https://github.com/el-bakkali/blog-guard)** — Static Site Path Allowlist

  - Allowlists valid paths via KV and redirects everything else to the homepage — a silent bot trap through the rate limiter.
  - Defence-in-depth: WAF, Bot Fight Mode, Rate Limiting, blog-guard.

</details>

<details>
<summary><strong>ESP32 & Smart Home</strong> — DIY hardware projects using ESPHome and Home Assistant</summary>
<br>

Because paying shop prices for smart home gear is daft.

- **[esp32-a1s-sendspin](https://github.com/el-bakkali/esp32-a1s-sendspin)** — Multi-Room Audio (11 stars)

  - Working ESPHome config for the ESP32-A1S Audio Kit with Sendspin protocol for synchronised multi-room playback via Music Assistant.

- **[esphome-air-quality-monitor](https://github.com/el-bakkali/esphome-air-quality-monitor)** — Air Quality Monitor

  - CO2, temperature, humidity & VOC monitoring on the Cheap Yellow Display (ESP32-2432S028) with a custom LVGL touchscreen UI.
  - Memory-optimised for ESP32 without PSRAM (~45-50 KB LVGL footprint).

- **[esp-thread-border-router](https://github.com/el-bakkali/esp-thread-border-router)** — Thread Border Router

  - ESP32-S3 + W5500 Ethernet module = a Thread Border Router with wired backhaul for about £15.
  - Replaces a £130 Apple HomePod or Google Nest Hub for Matter-over-Thread devices.

- **[diy-streaming-key-light](https://github.com/el-bakkali/diy-streaming-key-light)** — Streaming Key Light

  - A ~£25 bi-colour LED panel with full CCT control (3200K-5600K), Home Assistant integration, and a local web UI.
  - Replaces a £200 Elgato Key Light.

</details>

---

## Languages & Tools

<a href="https://www.rust-lang.org"><img src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white" alt="Rust"></a> <a href="https://dotnet.microsoft.com"><img src="https://img.shields.io/badge/C%23-.NET-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt="C#"></a> <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript"><img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JS"></a> <a href="https://www.python.org"><img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"></a> <a href="https://learn.microsoft.com/powershell"><img src="https://img.shields.io/badge/PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white" alt="PowerShell"></a> <a href="https://learn.microsoft.com/azure/data-explorer/kusto/query"><img src="https://img.shields.io/badge/KQL-0078D4?style=flat-square&logo=microsoftazure&logoColor=white" alt="KQL"></a> <a href="https://learn.microsoft.com/azure/azure-resource-manager/bicep"><img src="https://img.shields.io/badge/Bicep-0078D4?style=flat-square&logo=microsoftazure&logoColor=white" alt="Bicep"></a>

<a href="https://tauri.app"><img src="https://img.shields.io/badge/Tauri-24C8D8?style=flat-square&logo=tauri&logoColor=white" alt="Tauri"></a> <a href="https://workers.cloudflare.com"><img src="https://img.shields.io/badge/Cloudflare%20Workers-F38020?style=flat-square&logo=cloudflare&logoColor=white" alt="Cloudflare Workers"></a> <a href="https://learn.microsoft.com/azure/azure-functions"><img src="https://img.shields.io/badge/Azure%20Functions-0062AD?style=flat-square&logo=azurefunctions&logoColor=white" alt="Azure Functions"></a> <a href="https://esphome.io"><img src="https://img.shields.io/badge/ESPHome-000000?style=flat-square&logo=esphome&logoColor=white" alt="ESPHome"></a> <a href="https://www.home-assistant.io"><img src="https://img.shields.io/badge/Home%20Assistant-41BDF5?style=flat-square&logo=homeassistant&logoColor=white" alt="Home Assistant"></a> <a href="https://www.usebruno.com"><img src="https://img.shields.io/badge/Bruno-F4A83D?style=flat-square&logo=bruno&logoColor=white" alt="Bruno"></a>

<a href="https://www.kali.org"><img src="https://img.shields.io/badge/Kali%20Linux-557C94?style=flat-square&logo=kalilinux&logoColor=white" alt="Kali Linux"></a> <a href="https://ubuntu.com"><img src="https://img.shields.io/badge/Ubuntu-E95420?style=flat-square&logo=ubuntu&logoColor=white" alt="Ubuntu"></a> <a href="https://www.debian.org"><img src="https://img.shields.io/badge/Debian-A81D33?style=flat-square&logo=debian&logoColor=white" alt="Debian"></a> <a href="https://www.pfsense.org"><img src="https://img.shields.io/badge/pfSense-212121?style=flat-square&logo=pfsense&logoColor=white" alt="pfSense"></a> <a href="https://www.docker.com"><img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker"></a> <a href="https://www.proxmox.com"><img src="https://img.shields.io/badge/Proxmox-E57000?style=flat-square&logo=proxmox&logoColor=white" alt="Proxmox"></a> <a href="https://gethomepage.dev"><img src="https://img.shields.io/badge/Homepage-3174F1?style=flat-square&logo=homepage&logoColor=white" alt="Homepage"></a> <a href="https://openwrt.org"><img src="https://img.shields.io/badge/OpenWrt-00B5E2?style=flat-square&logo=openwrt&logoColor=white" alt="OpenWrt"></a> <a href="https://linuxcontainers.org"><img src="https://img.shields.io/badge/LXC-333333?style=flat-square&logo=linuxcontainers&logoColor=white" alt="Linux Containers"></a> <a href="https://kubernetes.io"><img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white" alt="Kubernetes"></a>

---

<sub>All projects are MIT licensed. Everything runs offline or on free tiers. No telemetry, ever.</sub>
