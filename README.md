# Prometheus-X — DSIF Reference Implementation

This repository is the **meta-directory** for [Prometheus-X](https://prometheus-x.org)'s reference implementations of the **Data Space Interoperability Framework (DSIF)** specifications.

It does not contain implementation code itself. Instead, it aggregates the individual implementation repositories as [Git submodules](#cloning-this-repository), providing a single entry point for navigating the full PTX DSIF implementation landscape.

---

## What is the DSIF?

The **Data Space Interoperability Framework** is a set of open specifications that enable seamless interaction between different dataspace ecosystems (Prometheus-X, EDC, FIWARE, Gaia-X, Simpl, Pontus-X, and others). It defines standardised APIs and data models across five federation layers:

| Layer | Description |
|---|---|
| **Catalogue Federation** | Hierarchical DNS-like discovery and aggregation of data offerings across catalogs |
| **Contract Federation** | Interoperable contract negotiation across dataspace ecosystems |
| **Identity Federation** | Bridging centralised and decentralised identity models |
| **Consent Federation** | Cross-dataspace consent management with GDPR compliance |
| **Service Chain Protocol** | Orchestrating distributed data processing workflows |

The DSIF builds on established open standards: **W3C DCAT v3**, **W3C DID**, **W3C ODRL v2.2**, **W3C Verifiable Credentials**, and **ISO/IEC TS 27560:2023**.

> Full specification: [DSIF Wiki](https://github.com/Prometheus-X-association/data-space-interoperability-framework)

---

## Implementation Status

The current work focuses on the **Catalogue Federation** layer — specifically the hierarchical authority model that underpins federated catalog discovery.

### Catalogue Federation — Hierarchy

```
Root Authority (RA)
├── Sector Authority 1  (e.g. Health)
│   ├── Independent Catalog A
│   └── Independent Catalog B
└── Sector Authority 2  (e.g. Skills)
    ├── Independent Catalog C
    └── Independent Catalog D
```

| Component | Repository | Status | Description |
|---|---|---|---|
| **Root Authority** | [root-authority](implementations/root-authority) | 🟡 In Progress | Source of truth for sectors → SA endpoints. Bootstraps the federation. |
| **Sector Authority** | [sector-authority](implementations/sector-authority) | 🟡 In Progress | Registers Independent Catalogs; provides discovery and cross-IC aggregation within a sector. |
| Independent Catalog | *(planned)* | 🔵 Planned | DCAT-AP JSON-LD endpoint + federation manifest. |

---

## Architecture Overview

See [docs/architecture.md](docs/architecture.md) for a detailed description of the Catalogue Federation PoC architecture, API surfaces, and component responsibilities.

---

## Cloning this Repository

This repo uses [Git submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules). To clone everything in one step:

```bash
git clone --recurse-submodules https://github.com/Prometheus-X-association/meta-implementation-dsif.git
```

If you have already cloned without submodules:

```bash
git submodule update --init --recursive
```

To update all submodules to their latest tracked commits:

```bash
git submodule update --remote --merge
```

---

## Repository Structure

```
meta-implementation-dsif/
├── README.md                   # This file
├── docs/
│   └── architecture.md         # Architecture overview & API reference
├── implementations/
│   ├── root-authority/         # Submodule → Prometheus-X-association/root-authority
│   └── sector-authority/       # Submodule → Prometheus-X-association/sector-authority
└── context/                    # Working documents & PoC specifications
```

---

## Contributing

Contributions to the individual implementation repositories should be made directly in those repos. For cross-cutting concerns, specifications, or meta-repo structure changes, open an issue or PR here.

All implementations follow the DSIF PoC specification (`dsif-poc-v0.2`). See [context/](context/) for the working documents.

---

## License

Apache 2.0 — see individual implementation repositories for their own license files.
