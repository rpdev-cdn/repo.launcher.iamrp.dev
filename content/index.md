---
title: "RPDev Repository"
description: "Central package registry, module catalog, and distribution hub for RPDev Launcher and RPDev Feed."
---

# RPDev Repository

> Sovereign package repository, JSON API catalogs, and module registry for the RPDev mobile application ecosystem.

```
  ██████╗ ███████╗██████╗  ██████╗ 
  ██╔══██╗██╔════╝██╔══██╗██╔═══██╗
  ██████╔╝█████╗  ██████╔╝██║   ██║
  ██╔══██╗██╔══╝  ██╔═══╝ ██║   ██║
  ██║  ██║███████╗██║     ╚██████╔╝
  ╚═╝  ╚═╝╚══════╝╚═╝      ╚═════╝ 
        R E P O S I T O R Y        
```

---

## What is RPDev Repository?

RPDev Repository serves as the central index and delivery engine for:
1. **[Module Catalog](catalog/index.md)**: Searchable registry of verified feed modules and launcher extensions.
2. **[API Specifications](api/endpoints.md)**: Live endpoints consumed by `HubModuleManager` in RPDev Feed.
3. **[JSON Schemas](api/schemas.md)**: Formal JSON schemas validating card payloads and module manifests.
4. **Binary Releases**: Hosted APK downloads, checksums, and update metadata.

---

## Live Endpoints

All repository endpoints are globally replicated across Cloudflare edge nodes with zero-downtime failover:

| Resource | Direct URL | Description |
|---|---|---|
| **Master Modules Catalog** | [`/catalog/modules.json`](catalog/modules.json) | Complete JSON metadata for all 9 feed modules |
| **Edge Feed Manifest** | [`https://cdn.iamrp.dev/feed/modules.json`](https://cdn.iamrp.dev/feed/modules.json) | Replicated edge delivery catalog |
| **Card Schema (v1)** | [`/schemas/card-v1.schema.json`](schemas/card-v1.schema.json) | JSON schema for feed card layouts |
| **Module Manifest Schema** | [`/schemas/module-manifest.schema.json`](schemas/module-manifest.schema.json) | JSON schema for module registration |
| **Launcher Updates** | [`https://cdn.iamrp.dev/launcher/updates.json`](https://cdn.iamrp.dev/launcher/updates.json) | Version update tracker for RPDev Launcher |

---

## Quick Navigation

- 📦 **[Browse Module Catalog](catalog/index.md)**
- 📐 **[API & JSON Schemas](api/schemas.md)**
- 🌐 **[Repository Endpoints](api/endpoints.md)**
- 🚀 **[Submit a Community Module](submitting-modules.md)**
