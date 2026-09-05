---
title: "Module Catalog Index"
description: "Browse, inspect, and install all 9 official and community modules available in the RPDev Repository."
---

# 📦 RPDev Module Catalog Index

The **RPDev Feed** ecosystem features **9 modular context plugins**, giving you complete control over your home screen minus-one experience. Whether you want zero-telemetry weather, battery hardware diagnostics, developer GitHub activity, smart home control, or self-hosted server monitoring, every module is fully documented and reviewed below.

---

## 📊 Quick Catalog Overview

| Module Name | Identifier | Category | Default | Deep Technical Specs |
| :--- | :--- | :--- | :---: | :--- |
| **Privacy Weather** | `plugin_weather` | Weather & Environment | ✅ Yes | [Documentation](modules/weather.md) |
| **Hardware & Battery Telemetry** | `plugin_sensors` | System & Hardware | ✅ Yes | [Documentation](modules/sensors.md) |
| **Calendar Agenda** | `plugin_calendar` | Productivity & Calendar | 📥 Store | [Documentation](modules/calendar.md) |
| **GitHub Pulse** | `plugin_github` | Developer & Code | 📥 Store | [Documentation](modules/github.md) |
| **Webpage Monitor & Keyword Scraper** | `plugin_web_scraper` | Developer & Code | 📥 Store | [Documentation](modules/web-scraper.md) |
| **Custom REST / JSON Endpoint** | `plugin_dynamic_rest` | Custom REST / Webhooks | 📥 Store | [Documentation](modules/dynamic-rest.md) |
| **Home Assistant State Monitor** | `module_home_assistant` | Smart Home & IoT | 📥 Store | [Documentation](modules/home-assistant.md) |
| **Docker & Fleet Health Monitor** | `module_docker_telemetry` | DevOps & Infrastructure | 📥 Store | [Documentation](modules/docker-telemetry.md) |
| **Uptime Kuma Status Monitor** | `module_uptime_kuma` | DevOps & Infrastructure | 📥 Store | [Documentation](modules/uptime-kuma.md) |

---

## 🗂️ Module Categories

### ☀️ Weather & Environment
- **[Privacy Weather](modules/weather.md)** (`plugin_weather`): Real-time weather, radar, high/low curves, and hourly precipitation forecasts powered by Open-Meteo with zero tracking.

### 🔋 System & Diagnostics
- **[Hardware & Battery Telemetry](modules/sensors.md)** (`plugin_sensors`): Real-time battery wattage, voltage, temperature, internal storage, and RAM memory pressure directly from kernel APIs.

### 📅 Productivity & Organization
- **[Calendar Agenda](modules/calendar.md)** (`plugin_calendar`): On-device upcoming 24-hour schedule reader querying Android's `CalendarContract` with complete privacy isolation.

### 💻 Developer Tools
- **[GitHub Pulse](modules/github.md)** (`plugin_github`): Real-time pull request review requests, GitHub Actions CI workflow results, and assigned notifications.
- **[Webpage Monitor & Keyword Scraper](modules/web-scraper.md)** (`plugin_web_scraper`): Periodic HTML scraper utilizing Jsoup and MD5 content diffs to alert on keyword matches.

### ☁️ Integrations & Self-Hosted Infrastructure
- **[Custom REST / JSON Endpoint](modules/dynamic-rest.md)** (`plugin_dynamic_rest`): Universal REST adapter polling any HTTP JSON API with dot-notation field mapping.
- **[Home Assistant State Monitor](modules/home-assistant.md)** (`module_home_assistant`): Real-time smart home sensor values, presence detection, and climate telemetry.
- **[Docker & Fleet Health Monitor](modules/docker-telemetry.md)** (`module_docker_telemetry`): Container lifecycle states, CPU/memory pressure, and daemon health checks.
- **[Uptime Kuma Status Monitor](modules/uptime-kuma.md)** (`module_uptime_kuma`): Live service uptime percentages, heartbeat graphs, and incident notices.

---

## 📡 Live In-App Store & Manifest Sync

RPDev Feed queries this repository live at:
```
https://repo.launcher.iamrp.dev/catalog/modules.json
```
To contribute a new module or update an existing module schema, review our **[Module Submission Guidelines](../submitting-modules.md)**.
