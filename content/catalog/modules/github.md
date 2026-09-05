---
title: "GitHub Pulse Module"
description: "Live GitHub pull request review requests, Actions CI workflow states, assigned issues, and commit activity."
---

# 🐙 GitHub Pulse Module

> **ID**: `plugin_github`  
> **Category**: Developer & Code  
> **Version**: `1.0.1`  
> **Author**: RPDevs  
> **Default Installed**: No (Install via Repository)  
> **Icon**: `GitBranch`

The **GitHub Pulse** module is designed for software developers, maintaining real-time visibility over open pull requests awaiting review, continuous integration workflow results across key repositories, and pending issue assignments.

---

## 🏗️ Architecture & Data Ingestion

```mermaid
graph LR
    Feed["RPDev Feed Engine"]
    API["https://api.github.com/"]
    
    Feed -->|HTTPS GET with Authorization: Bearer PAT| API
    API -->|/user/issues?filter=assigned| Feed
    API -->|/repos/{owner}/{repo}/actions/runs| Feed
    API -->|/notifications?participating=true| Feed
```

---

## ⚙️ Configuration Reference

| Parameter Key | Label | Type | Default Value | Description |
| :--- | :--- | :--- | :--- | :--- |
| `username` | GitHub Username / Org | String | `"RPDevs-Builds"` | GitHub account or organization handle to monitor. |
| `token` | GitHub Personal Access Token | Secret String | `""` | GitHub Personal Access Token (`repo`, `workflow`, `notifications` scopes). |
| `tracked_repos` | Tracked Repositories | String | `"RPDevs-Builds/RPDev-Feed, RPDevs-Builds/RPDev-Feed-Modules"` | Comma-delimited repository list for workflow telemetry. |

---

## 🛡️ Privacy & Security Audit

- **Permissions Required**: `android.permission.INTERNET`.
- **Token Security**: Tokens are stored strictly in Android EncryptedSharedPreferences / Private App DataStore. No external servers or telemetry intermediaries ever receive your credential.

---

## 📋 Sample HubCardData JSON Output

```json
{
  "id": "card_github",
  "pluginId": "plugin_github",
  "title": "GitHub Pulse • RPDevs-Builds",
  "summary": "All CI Workflows Passing • 1 PR Needs Review",
  "iconName": "GitBranch",
  "priority": 85,
  "chips": [
    { "label": "CI: Passed", "color": "green" },
    { "label": "PR #14: Ready", "color": "blue" }
  ]
}
```
