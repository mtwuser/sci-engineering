# sci-engineering (`knowledge`, `precedence: 20`)

## Layer Setup Blueprint (Epistemic Knowledge Atlas Node (gov-*, sci-*, geo-*, org-*))

- **Node ID & Role**: `sci-engineering` (`knowledge`, `precedence: 20`)
- **1-Hop Upstream Parent**: `mtwuser/zero-cloud-gravity`
- **Active Template Packs**: `science-base`, `scientific-methodology`, `sci-engineering`, `node-work-cockpit`
- **Branch & Promotion Pipeline (`promotion_pipeline`)**: `staged` (`['dev', 'tst', 'pre', 'pro']` — `master` = enacted `pro` baseline + optional `context_branches` (`specialty/*`, `hat/*`, `machine/*`); work promotes via `feature/*` or `directive/*` (`dev`) -> `env/tst` -> `env/pre` -> `master` (`pro`))
- **Human-Stack Profile (Optional)**: [Optional: leave blank for default, or compose Human-Stack facets: domain-<area>:M1..M4 | bridge-* | soft-* | hat-*]
- **Interaction Language (`--lang`)**: `en` (`English (en)` — repo artifacts 100% English)
- **Mission, Scope & Core Invariants**: [Fill: Epistemic domain, E3..E0 credibility invariants, and citation_receipt scope]
- **Downstream Topology (Next Tier)**: [Fill: Consumer nodes mounting this knowledge corpus]
- **Authorized Layer Owner (`set-authority`)**: [Fill: Role title & owner email]

## Initial Chat Kickoff Prompt (4-Phase Customizable Progression)

```text
Phase A (Setup & Purpose Alignment): Read the filled Layer Setup Blueprint in README.md, system/zcg-node.json, and .agents/LAYER_LINEAGE.md. Tailor antigravity/.gemini/config/AGENTS.md and templates/sci-engineering/rules/sci-engineering.md with our mission and invariants without duplicating upstream rules, then run make sync && make diff and update the Node Work & Sprint Ledger (WORKROAD.md / WORKTASK.md).
Phase B (Epistemic Knowledge & Spec Atlas): Structure docs/{reference,architecture,guides}/ (< 465 lines) with E3..E0 epistemic grades and citation_receipt anchors.
Phase C (Daily Bounded-Lot Execution & Verification): Claim work via make task TASK="<id>", execute 1 bounded lot per turn (3-5 files) with active-layer verification, and checkpoint via /continue.
Phase D (Upward Enrichment & Sync Reconciliation): Reconcile upstream updates via make sync STRATEGY=reconcile (make upstream-diff), verify make env-gate ENV=tst|pre|pro, and promote reusable rules upward via /enrich and make promote before /sclose.
```

## Upstream Upgrade & Version Reconciliation Prompt (4-Step Guided Flow)

```text
Step 1 (Topology & Horizon Audit): /sopen — Run make status (inspect sync_topology 4-stage DAG & promotion_pipeline), make horizon, and make upstream-diff against `mtwuser/zero-cloud-gravity`.
Step 2 (Zero-Loss Node & Schema Reconciliation): Run make sync STRATEGY=reconcile (or STRATEGY=merge) to upgrade Makefile, system/zcg-node.json, and inherited templates while preserving sovereign rules in templates/sci-engineering/rules/sci-engineering.md.
Step 3 (Selective Stack & Node Plugin Review): Evaluate whether any newly available context-stack, framework-stack, or plugin-stack pack adds genuine value without saturating context, then verify make diff (0 drift).
Step 4 (Environment / Mastery Gate & Closure): Validate make env-gate ENV=pro (or ENV=tst|pre|pro on staged enterprise nodes) and close via /sclose.
```
