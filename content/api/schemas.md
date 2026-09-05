---
title: "JSON Schemas Specification"
description: "Formal JSON schema specifications for RPDev Feed card rendering and module manifests."
---

# JSON Schemas Specification

RPDev Feed modules and card layouts are formally defined using JSON Schema (Draft 7).

---

## 1. Card Rendering Schema (`card-v1.schema.json`)

Validates dynamic card payloads delivered by feed modules:

- **JSON Schema Endpoint**: [`/schemas/card-v1.schema.json`](../schemas/card-v1.schema.json)
- **CDN Global Mirror**: `https://cdn.iamrp.dev/feed/schemas/card-v1.schema.json`

### Supported Layout Types:
- `single_metric`: Large numerical value with unit, sparkline, and status color.
- `grid_metric`: 2 to 4 key-value diagnostic pairs.
- `news_list`: Article headline, source metadata, timestamp, and optional thumbnail.
- `weather_summary`: Temperature, condition icon, high/low, and hourly forecast pills.

---

## 2. Module Manifest Schema (`module-manifest.schema.json`)

Validates the `modules.json` catalog index and standalone APK metadata:

- **JSON Schema Endpoint**: [`/schemas/module-manifest.schema.json`](../schemas/module-manifest.schema.json)
- **CDN Global Mirror**: `https://cdn.iamrp.dev/feed/schemas/module-manifest.schema.json`

### Key Manifest Properties:
- `id` (`string`, pattern: `^[a-z0-9_]+$`): Unique identifier (e.g. `plugin_weather`).
- `name` (`string`): User-facing display title.
- `version` (`string`, semver): Release version string.
- `author` (`string`): Developer or organization credit.
- `isDefaultInstalled` (`boolean`): Flags pre-bundled activation.
- `configFields` (`array`): Declarative setting preferences rendered in Feed Settings UI.
