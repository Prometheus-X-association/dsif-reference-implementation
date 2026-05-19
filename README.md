# Prometheus-X - DSIF Reference Implementation

This repository is the **meta-directory** for [Prometheus-X](https://prometheus-x.org)'s reference implementations of the **Data Space Interoperability Framework (DSIF)** specifications.

It does not contain implementation code itself. Instead, it aggregates the individual implementation repositories as Git submodules, providing a single entry point for navigating the full PTX DSIF implementation landscape.

---

## What is the DSIF?

The **Data Space Interoperability Framework** is a set of open specifications that aim to enable seamless interaction between different dataspace ecosystems (Prometheus-X, EDC, FIWARE, Gaia-X, Simpl, Pontus-X, and others). It defines standardised APIs and data models across five federation layers:

| Layer | Description |
|---|---|
| **Catalogue Federation** | Hierarchical DNS-like discovery and aggregation of data offerings across catalogs |
| **Contract Federation** | Interoperable contract negotiation across dataspace ecosystems |
| **Identity Federation** | Bridging centralised and decentralised identity models |
| **Consent Federation** | Cross-dataspace consent management with GDPR compliance |
| **Service Chain Protocol** | Orchestrating distributed data processing workflows |

The DSIF builds on established open standards: **W3C DCAT v3**, **W3C DID**, **W3C ODRL v2.2**, **W3C Verifiable Credentials**, and **ISO/IEC TS 27560:2023**.

> Full specification: [DSIF Wiki](https://github.com/Prometheus-X-association/data-space-interoperability-framework)

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
