# Data Space Interoperability Framework (DSIF) - Technical Specifications

The DSIF provides specifications for enabling interoperability across different dataspace ecosystems.

## Overview

The Data Space Interoperability Framework addresses the critical challenge of enabling seamless interaction between different dataspace initiatives such as EDC, FIWARE, Prometheus-X, Gaia-X, Simpl, Pontus-X and more. 

## Core Components

The DSIF consists of five main federation layers:

### 1. [Catalogue Federation](Catalogue-Federation)
Enables discovery and aggregation of data offerings across multiple dataspace catalogs through a hierarchical DNS-like architecture.

### 2. [Contract Federation](Contract-Federation) 
Provides interoperable contract negotiation and management across different dataspace ecosystems, supporting both peer-to-peer and intermediated models.

### 3. [Identity Federation](Identity-Federation)
Bridges centralized and decentralized identity models to enable cross-dataspace participant and individual identification.

### 4. [Consent Federation](Consent-Federation)
Manages individual consent across dataspaces while ensuring GDPR compliance and legal enforceability.

### 5. [Service Chain Protocol](Service-Chain-Protocol)
Orchestrates distributed data processing workflows across multiple dataspace participants.

## Key Features

- **Cross-Dataspace Interoperability**: Seamless integration between different dataspace technologies
- **Standardized APIs**: Common interfaces based on DCAT, DSP, ODRL, and other open standards
- **Federated Architecture**: Hierarchical discovery model inspired by DNS
- **Legal Compliance**: Built-in support for GDPR, consent management, and auditability
- **Scalable Design**: Efficient crawling, caching, and synchronization mechanisms

## Getting Started

1. Start with [Catalogue Federation](Catalogue-Federation) to understand the foundational discovery architecture
2. Review [Technical Architecture](Technical-Architecture) for implementation details
3. Explore specific federation components based on your use case

## Reference Standards & Compliance

The DSIF builds upon established standards:
- **W3C DCAT** for metadata exchange
- **W3C DID** (Decentralized IDentifiers)
- **W3C ODRL v2.2** for policy and contract management
- **W3C Verifiable Credentials** for decentralized identity

## Specifications to reconcile/integrate

The DSIF will bring a vision on how to integrate implementations of relevant standards

- **DSP with OID4VC** (current connectors like EDC tie DSP with DCP) 
- **DSP with TM Forum Open APIs** for contract negotiation 
- **DCAT with TM Forum Open APIs** for catalogue management  
- **DSP with well-established DCAT APIs** (e.g., CKAN)
- **ISO/IEC TS 27560:2023 and ODRL-based authorization** for consent management

## Contributing

This specification is developed collaboratively across multiple dataspace initiatives. Comments and contributions are welcome.