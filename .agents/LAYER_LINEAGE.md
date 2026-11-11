# Zero-Cloud Node Governance Lineage (`zero-cloud-gravity`)

- **Applied Template Pack**: `science-base,scientific-methodology,sci-engineering,knowledge-stewardship-portal`

## Participating Layers (Ordered by Precedence `0..100`)

| Precedence | Layer | Layer ID | Role | Surface Bindings |
|---:|---|---|---|---:|
| `20` | `root` | `sci-engineering` | `knowledge` | `1` |

## Project Setup Blueprint (Level 4 — Project & Consumer Workspace)
- **Applied Template Packs**: `science-base,scientific-methodology,sci-engineering,knowledge-stewardship-portal`
- **Branch & Promotion Pipeline (`promotion_pipeline`)**: `staged` (`['dev', 'tst', 'pre', 'pro']` — `master` = enacted `pro` baseline; `dev` is ephemeral `feature/<TICKET>-*` -> `env/tst` -> `env/pre` -> `master` (`pro`))
- **Human-Stack Profile (Optional)**: [Optional: leave blank for default, or compose Human-Stack facets: domain-<area>:M1..M4 | bridge-* | soft-* | hat-*]
- **Interaction Language (`--lang`)**: `en` (`English (en)` — repo artifacts 100% English)
- **Project / Service Purpose**: [Fill: Core product/service mission and bounded context]
- **Architecture & Integrations**: [Fill: Domain modules, stores, and UI/CLI surface]
- **Phase 1 Milestone Goal**: [Fill: Initial vertical slice or MVP deliverable]

## Initial Chat Kickoff Prompt (4-Phase Customizable Progression)
```text
Phase A (Setup & Purpose Alignment): /sopen — Read .agents/LAYER_LINEAGE.md, all inherited .agents/rules/*.md, and our Project Setup Blueprint.
Phase B (Epistemic Knowledge Atlas & Sprint Ledger): Initialize README.md, docs/architecture/ (1:1:1 specs or SYLLABUS.md M1..M4), WORKROAD.md, and WORKTASK.md.
Phase C (Daily Bounded-Lot Execution & Verification): Claim Task 1 via make task, propose the Pre-Edit Scope Blueprint (1 lot/turn), and verify with make verify.
Phase D (Promotion & Reconciliation): Run make sync && make diff, validate make env-gate ENV=tst|pre|pro, and promote reusable discoveries via /enrich and make promote before /sclose.
```
