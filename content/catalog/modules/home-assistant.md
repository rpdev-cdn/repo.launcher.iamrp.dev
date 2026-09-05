---
title: "Home Assistant State Monitor Module"
description: "Display smart home entity states, temperature sensors, lights, and climate controls from your Home Assistant instance."
---

# 🏠 Home Assistant State Monitor Module

> **ID**: `module_home_assistant`  
> **Category**: Smart Home & IoT  
> **Version**: `1.0.1`  
> **Author**: RPDevs  
> **Default Installed**: No (Install via Repository)  
> **Icon**: `House`

The **Home Assistant State Monitor** brings your local smart home automation dashboard directly to your Android home screen minus-one feed. Query light statuses, temperature sensors, climate zones, presence detection, and smart locks with instantaneous updates.

---

## 🏗️ Architecture & Data Ingestion

```mermaid
graph LR
    HA["Home Assistant Instance<br/>(Local LAN or Cloudflare Tunnel)"]
    Plugin["Home Assistant Module Adapter"]
    Card["Smart Home Status Card"]

    Plugin -->|GET /api/states/{entity_id}| HA
    HA -->|Entity State JSON (state, attributes)| Plugin
    Plugin -->|Format Temperature, Unit, Friendly Name| Card
```

---

## ⚙️ Configuration Reference

| Parameter Key | Label | Type | Default Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `ha_url` | Home Assistant Base URL | String | `"http://homeassistant.local:8123"` | The base URL of your Home Assistant server. |
| `ha_token` | Long-Lived Access Token | Secret String | `""` | Token generated from your Home Assistant Profile page. |
| `ha_entities` | Entity IDs (comma-separated) | String | `"sensor.living_room_temperature, climate.thermostat, light.desk"` | Entities to poll and render in the feed chips. |

---

## 🛡️ Privacy & Security Audit

- **Permissions Required**: `android.permission.INTERNET`.
- **Local Network Priority**: Supports local subnet discovery (`192.168.x.x` or `.local`), keeping your smart home data entirely contained within your private Wi-Fi network without routing through external servers.

---

## 📋 Sample HubCardData JSON Output

```json
{
  "id": "module_home_assistant",
  "pluginId": "module_home_assistant",
  "title": "Home Assistant • Living Space",
  "summary": "Climate: 21.5°C • 2 Lights Active",
  "iconName": "House",
  "priority": 70,
  "chips": [
    { "label": "Living Room: 21.5°C", "color": "blue" },
    { "label": "Desk Light: ON", "color": "yellow" },
    { "label": "Front Door: Locked", "color": "green" }
  ]
}
```
