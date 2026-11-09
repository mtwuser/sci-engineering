---
trigger: always_on
description: "Materials/Metallurgy Standards, Chemical/Bioprocess Unit Operations, and Mechanical/SHM Safety Cut-Points (sci-engineering)"
---

# Applied Engineering Sciences Corpus Rules (`sci-engineering`)

## Scope & Surface Target
- **Template Pack**: `templates/sci-engineering/` (`context-stack`).
- **Knowledge Domain**: `scientific-epistemic` (`canonical_trunk: "engineering"`, `E3..E1`).

## Normative Invariants (`ENG-SCI-01..03`)

1. **`ENG-SCI-01` (Materials, Metallurgy & Corrosion-Resistance Standards — `E3/E2`)**:
   - Every wetted, food-contact, or reactive process surface must declare its exact alloy designation (`EN 10088` / `ASTM A240`), Pitting Resistance Equivalent Number ($\text{PREN} = \%\text{Cr} + 3.3\,\%\text{Mo} + 16\,\%\text{N} \ge 24.0$ for `AISI 316 / 316L`, `EN 1.4401 / 1.4404`), and maximum surface roughness ($R_a \le 0.8\,\mu\text{m}$ sanitary finish).
2. **`ENG-SCI-02` (Unit Operations, Granulometry & Thermal/Pressure Safety Interlocks — `E3/E2`)**:
   - Process flowsheets and equipment specs must enforce exact particle-size distributions (`ISO 3310-1` test sieves), coupled heat/mass balances (`sci-physics` `PHYS-02..03`), and hard hardware/PLC safety cut-points (`N vs N±1`), including convective dehydration windows (`[35.0 °C, 40.0 °C]`) and anoxic pyrolysis retort opening interlocks ($T_{\text{core}} < 40.0\,^\circ\text{C}$, $\text{O}_2 < 1.5\%\text{ v/v}$).
3. **`ENG-SCI-03` (Structural Health Monitoring `SHM`, Mechatronics & `citation_receipt` Provenance — `E2`)**:
   - Mechanical structures, rotating machinery, and sensor telemetry pipelines must specify modal natural frequencies ($f_n$), damping ratios ($\zeta_n$), RMS vibration velocity bounds (`ISO 10816 / ISO 20816`), and cite `sci-engineering::docs/...#<slug>@<digest16>:E3`.

## Verification & Sign-Off Gates
- [ ] Verify zero drift via `zcg diff-project`.
- [ ] Confirm all engineering tolerances, alloy grades, and safety cut-points use exact SI/ISO units.
