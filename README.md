# sci-engineering — Sovereign Epistemic Knowledge Corpus (`v1.0.0`)

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](VERSION)
[![ZeroCloudGravity](https://img.shields.io/badge/ZeroCloudGravity-v1.0.0-0F766E.svg)](https://github.com/mtwuser/zero-cloud-gravity)
[![Epistemic Grade](https://img.shields.io/badge/epistemic_grade-E3..E1-1D4ED8.svg)](docs/README.md)
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

> **Applied Engineering Sciences Corpus (`EN 10088` Metallurgy, `ISO 3310-1` Unit Operations, `IEC 61508/61511` `SIL` & `ISO 20816-3` SHM)** (`layer_role: knowledge`, `precedence: 20`, `stewardship_stage: public-community`).

## 1. Epistemic Corpus Index (`1:1:1` Progressive Disclosure)

All sections expose deterministic `rcap1` (`L0 -> L3`) capsules and cryptographic `citation_receipt` anchors (`<layer>::<file>#<slug>@<sha256_16>:<E3..E0>`):

| Tier | Credibility | Document |
| :--- | :--- | :--- |
| **Index** | `E2` | [`docs/README.md`](docs/README.md) |
| **Guide (`M1 -> M4`)** | `E1` | [Applied Engineering Design, Scaling & AAA Interlock Verification Guide (`M1 -> M4` — `E1`)](docs/guides/01_applied_engineering_design_and_verification_guide.md) |
| **Architecture & Taxonomy** | `E3` | [Engineering Disciplines, Systems V-Model & Functional Safety Taxonomy (`E3/E2`)](docs/architecture/01_engineering_disciplines_and_systems_taxonomy.md) |
| **Primary Reference** | `E3/E2` | [Metallurgy, Unit Operations, SHM Vibration & Industrial Instrumentation Standards (`E3/E2`)](docs/reference/01_materials_metallurgy_unit_operations_and_shm_standards.md) |

## 2. Mounting & Querying from Any `ZeroCloudGravity` Node

Link or mount this corpus into a personal (`<persona>-pc`, `<persona>-tutor`), research, or enterprise node without cloud dependencies:

```bash
zcg link <your-node-dir> --target https://github.com/mtwuser/sci-engineering.git --relation knowledge-feed
zcg consult-layer <your-node-dir> --layer sci-engineering --query "<topic>" --tier flash
```

## 3. Layer Setup Blueprint (`State U2: configured`)

- **Node ID & Role**: `sci-engineering` (`knowledge`, `precedence: 20`, `surface_veracity_mode: full-open-source`)
- **1-Hop Upstream Engine**: [`mtwuser/zero-cloud-gravity`](https://github.com/mtwuser/zero-cloud-gravity)
- **Active Template Packs**: `science-base`, `scientific-methodology`, `sci-engineering`, `knowledge-stewardship-portal`
- **Mission, Scope & Core Invariants**: Applied engineering and systems verification corpus (`E3..E1`) covering `ISO/IEC/IEEE 15288` V-model, `EN 10088` stainless metallurgy, `ISO 3310-1` unit operations, `IEC 61508` `SIL`, and `ISO 20816-3` vibration cut-points.
- **Downstream Topology**: Consumed read-only via `knowledge-feed` links or `layers/*` subtrees across academic, scientific, public-sector, and enterprise nodes.
- **Authorized Layer Steward**: `sci-engineering Knowledge Steward <mtwuser@users.noreply.github.com>`
