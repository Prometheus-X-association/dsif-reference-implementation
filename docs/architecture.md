# DSIF Catalogue Federation — Architecture Overview

> Full specification: [DSIF Wiki](https://github.com/Prometheus-X-association/data-space-interoperability-framework)

## Overview

The Catalogue Federation layer implements a **hierarchical DNS-inspired discovery architecture** for federated data catalogs. The hierarchy has three tiers:

1. **Root Authority (RA)** — bootstraps the federation; authoritative registry of all Sector Authorities
2. **Sector Authority (SA)** — manages discovery within a domain sector; aggregates Independent Catalogs
3. **Independent Catalog (IC)** — the leaf nodes; serve DCAT-AP metadata and a search endpoint

```
Root Authority
     │  GET /sectors → list of Sector Authorities
     │
     ├── Sector Authority (Health)
     │        │  GET /discovery → list of IC connection profiles
     │        ├── Independent Catalog A  (DCAT-AP + search)
     │        └── Independent Catalog B  (DCAT-AP + search)
     │
     └── Sector Authority (Skills)
              │  GET /discovery → list of IC connection profiles
              ├── Independent Catalog C  (DCAT-AP + search)
              └── Independent Catalog D  (DCAT-AP + search)
```

---

## Component Responsibilities

### Root Authority (RA)

- **Single source of truth** for the mapping: `sector name → Sector Authority endpoint`
- Read-only public API; write operations protected by an admin token
- `sectorName` is a lowercase slug (`^[a-z0-9-]+$`); RA is authoritative for uniqueness

### Sector Authority (SA)

- Registers Independent Catalogs within its sector
- Provides **federated search** across all ICs in the sector via reference aggregation (not content aggregation)
- Optionally proxies cross-sector queries through the RA (hop limit applies)
- Exposes a self-describing `/.well-known/dataspace-catalog.json` Manifest

### Independent Catalog (IC)

- Serves **DCAT-AP JSON-LD** compatible with the CKAN DCAT extension
- Publishes a **Federation Manifest** and a **Connection Profile**
- Exposes a minimal search endpoint
