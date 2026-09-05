---
title: "Submitting Community Modules"
description: "Guidelines and verification procedures for publishing modules to the RPDev Repository."
---

# Submitting Community Modules

The RPDev Repository welcomes community-authored feed modules that respect user sovereignty and adhere to security standards.

---

## 1. Submission Requirements

Before opening a pull request to add your module to `modules.json`:

1. **Manifest Validation**: Ensure your module manifest adheres strictly to [`module-manifest.schema.json`](../schemas/module-manifest.schema.json).
2. **Permission Audit**: Modules requesting sensitive permissions (`READ_SMS`, `ACCESS_FINE_LOCATION`) must justify rationale.
3. **Reproducible Builds**: Provide an open GitHub repository with automated release tags.
4. **Offline Capability**: Modules must gracefully handle network disconnects and cache state locally.

---

## 2. Review Checklist

- [ ] Valid JSON schema metadata
- [ ] High-resolution vector icon (SVG or 512x512 PNG)
- [ ] Zero third-party ad networks or analytics trackers
- [ ] Tested against Android 9 through Android 16
