---
title: "Custom REST / JSON Endpoint Module"
description: "Declarative JSON REST client polling arbitrary HTTP endpoints with dot-notation field mapping into feed cards."
---

# ☁️ Custom REST / JSON Endpoint Module

> **ID**: `plugin_dynamic_rest`  
> **Category**: Custom REST / Webhooks  
> **Version**: `1.0.1`  
> **Author**: RPDevs  
> **Default Installed**: No (Install via Repository or In-App Creator)  
> **Icon**: `Cloud`

The **Custom REST / JSON Endpoint** module is the universal adapter for RPDev Feed. It allows power users to connect *any* internal or external HTTP REST API (Docker, Gotify, Node-RED, self-hosted dashboards) and map the response fields into status badges, timeline rows, and composite cards using intuitive dot-notation syntax.

---

## 🏗️ Architecture & Data Ingestion

```mermaid
graph LR
    API["Any HTTP/JSON Endpoint<br/>(e.g., https://api.github.com/zen)"]
    Client["DynamicRestPlugin.kt"]
    Card["Rendered HubCardData"]

    Client -->|HTTP GET with Custom Headers| API
    API -->|Raw JSON Response| Client
    Client -->|JSON Pointer Extraction (e.g. 'data.status')| Card
```

---

## ⚙️ Configuration Reference

| Parameter Key | Label | Type | Default Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `rest_url` | REST Endpoint URL | String | `"https://api.github.com/zen"` | HTTP/HTTPS URL returning JSON or plain text. |
| `auth_header` | Authorization Header | String | `""` | Optional HTTP Authorization header (e.g. `"Bearer my_token"`). |
| `json_title_path` | JSON Path for Title / Message | String | `"message"` | JSON key name or dot-notation path to extract for card text. |
| `display_title` | Module Title | String | `"REST Monitor"` | Title shown on the card header. |

---

## 🛡️ Privacy & Security Audit

- **Permissions Required**: `android.permission.INTERNET`.
- **Local Authentication**: Secrets and tokens remain encrypted in Android SharedPreferences and are only transmitted to the configured endpoint URL.

---

## 📋 Sample HubCardData JSON Output

```json
{
  "id": "card_dynamic_rest",
  "pluginId": "plugin_dynamic_rest",
  "title": "REST Monitor • Production Status",
  "summary": "All systems operational (100% uptime)",
  "iconName": "Cloud",
  "priority": 75,
  "chips": [
    { "label": "HTTP 200 OK", "color": "green" },
    { "label": "Latency 42ms", "color": "gray" }
  ]
}
```
