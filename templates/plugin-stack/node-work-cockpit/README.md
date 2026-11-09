# `node-work-cockpit` (`plugin-stack`) — Tier 2 Sovereign Project & Knowledge Node Surface

> Tier 2 runtime surface plugin extending `software-engineering` for standard `node` and `subnode` repositories, `WORKTASK.md` lifecycle automation, and local HTML cockpit rendering.

---

## 1. Template Identity & Service Contract (`template.json` & `service_contract.json`)

The following table summarizes the canonical metadata declared in [`template.json`](template.json), [`assets/service_contract.json`](assets/service_contract.json), and [`rules/node-work-cockpit.md`](rules/node-work-cockpit.md):

| Attribute | Canonical Value | Verification & Runtime Role |
| :--- | :--- | :--- |
| **`id`** | `node-work-cockpit` | Runtime surface in `VALID_PLUGIN_STACK_IDS` (`constants.py`) |
| **`stack_group`** | `plugin-stack` | Runtime Surface & Cockpit Capability Axis |
| **`extends`** | `["software-engineering"]` | Inherits engineering and verification gates from `software-engineering` |
| **`service_contract`** | [`assets/service_contract.json`](assets/service_contract.json) | Declares `node`/`subnode` work-ledger cards, `1:1:1` audit views, and MCP hooks |
| **`rules_file`** | [`rules/node-work-cockpit.md`](rules/node-work-cockpit.md) | `make status|task|complete|verify` discipline and cockpit artifact hygiene |

---

## 2. Core Node Cockpit Capabilities

The `node-work-cockpit` plugin provides the standard operational surface for engineering, infrastructure, and knowledge (`osa-*`) nodes:

1. **Deterministic Task Lifecycle (`make task -> make verify -> make complete`)**: Wires the node's `Makefile` to `zcg` work-ledger state transitions (`WORKTASK.md`, `WORKROAD.md`, `BACKLOG.md`, `CHANGELOG.md`).
2. **Self-Contained Intranet Cockpit (`zcg generate-intranet`)**: Renders a static, zero-dependency HTML dashboard summarizing node identity, mounted stack lineage, active `WORKTASK.md` lots, and verification status (`ZCG_NO_BROWSER=1`).
3. **Contextual MCP Capsule Exposure**: Exposes the node's `docs/` and `.agents/rules/` surfaces to `zcg-mcp` (`get_layer_overview`, `audit_node_drift`, `unfold_context_capsule`).

---

## 3. Mounting & Cross-References

Declare `node-work-cockpit` in `system/zcg-node.json` under `stack_groups.plugin_stack` and synchronize the node:

```bash
zcg sync-layer /path/to/project-node
```

- **Parent Context Stack**: `templates/context-stack/software-engineering/README.md`
- **Cockpit Architecture**: `docs/architecture/04_cockpit_and_intranet_surfaces.md`
- **Catalog Reference**: `docs/reference/01_stack_and_plugin_matrix.md`
