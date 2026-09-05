---
title: "Repository API Endpoints"
description: "Live REST and static JSON endpoints for module catalog resolution, updates, and schemas."
---

# Repository API Endpoints

The repository provides high-availability HTTP/2 endpoints for mobile clients and automated CI/CD tooling.

---

## 1. Catalog Endpoints

### Master Catalog Index
- **URL**: `https://repo.launcher.iamrp.dev/catalog/modules.json`
- **Fallback URL**: `https://cdn.iamrp.dev/feed/modules.json`
- **Method**: `GET`
- **Headers**: `Accept: application/json`
- **Cache-Control**: `public, max-age=300, stale-while-revalidate=86400`

```bash
# Test catalog response
curl -s https://repo.launcher.iamrp.dev/catalog/modules.json | jq .
```

---

## 2. Schema Validation Endpoints

### Card Schema
- **URL**: `https://repo.launcher.iamrp.dev/schemas/card-v1.schema.json`
- **CDN**: `https://cdn.iamrp.dev/feed/schemas/card-v1.schema.json`

### Module Manifest Schema
- **URL**: `https://repo.launcher.iamrp.dev/schemas/module-manifest.schema.json`
- **CDN**: `https://cdn.iamrp.dev/feed/schemas/module-manifest.schema.json`

---

## 3. Launcher Updates Endpoint

- **URL**: `https://cdn.iamrp.dev/launcher/updates.json`
- **Method**: `GET`
- **Payload**: Version metadata, minimum SDK requirements, changelog, and direct APK download URLs.
