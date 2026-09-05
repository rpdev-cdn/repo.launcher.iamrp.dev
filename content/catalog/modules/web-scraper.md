---
title: "Webpage Monitor & Keyword Scraper Module"
description: "Periodic HTML scraper engine tracking webpage changes via MD5 content diffs and keyword alert triggers."
---

# 🌐 Webpage Monitor & Keyword Scraper Module

> **ID**: `plugin_web_scraper`  
> **Category**: Developer & Code  
> **Version**: `1.0.1`  
> **Author**: RPDevs  
> **Default Installed**: No (Install via Repository)  
> **Icon**: `Globe`

The **Webpage Monitor & Keyword Scraper** turns RPDev Feed into an autonomous website watchtower. It periodically inspects targeted HTML pages, scopes content extraction using CSS selectors via Jsoup, calculates cryptographic MD5 hashes to detect structural changes, and alerts you when critical keywords appear.

---

## 🏗️ Architecture & Data Ingestion

```mermaid
graph TD
    Target["Target Webpage URL"]
    Jsoup["Jsoup Parser Engine"]
    HashEngine["MD5 Hasher & Regex Matcher"]
    Cache["Local Hash Store"]
    Card["Scraper Status Card"]

    Target -->|HTTP GET (Direct On-Device)| Jsoup
    Jsoup -->|CSS Selector Scoped Nodes| HashEngine
    HashEngine <-->|Compare against Last State| Cache
    HashEngine -->|Matched Keywords & Change Notice| Card
```

---

## ⚙️ Configuration Reference

| Parameter Key | Label | Type | Default Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `scrape_url` | Target Webpage URL | String | `"https://github.blog/news-insights/product-news/"` | Complete HTTP/HTTPS URL of the site to monitor. |
| `keywords` | Monitored Keywords | String | `"release, update, android, security"` | Comma-separated search terms that trigger high-priority alerts. |
| `css_selector` | CSS Selector | String | `"article, main, .content, body"` | Optional CSS selector to isolate target text nodes. |
| `display_title` | Card Display Title | String | `"Webpage Monitor"` | Title banner for the feed card. |

---

## 🛡️ Privacy & Security Audit

- **Permissions Required**: `android.permission.INTERNET`.
- **Zero Intermediaries**: The connection is made directly between your Android phone and the target web server. No scraping proxy or cloud middleman is used.

---

## 📋 Sample HubCardData JSON Output

```json
{
  "id": "card_web_scraper",
  "pluginId": "plugin_web_scraper",
  "title": "Webpage Monitor • GitHub Blog",
  "summary": "Keyword 'android' detected in latest article",
  "iconName": "Globe",
  "priority": 80,
  "chips": [
    { "label": "Matched: android", "color": "orange" },
    { "label": "Status: Modified", "color": "blue" }
  ]
}
```
