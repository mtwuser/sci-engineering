# Applied Engineering Design, Scaling & Verification Guide (`sci-engineering` — `E1`)

> **Epistemic Credibility Grade: `E1` (Pedagogical & Industrial Design Methodology across `M1..M4`)**
>
> Practical guide for sizing unit operations, selecting `AISI 316/316L` materials, designing sensor/SHM telemetry pipelines, and verifying safety interlocks (`make consult LAYER=sci-engineering`).

---

## 1. Progressive Mastery Adaptation (`human_stack: domain-engineering:M1..M4`)

| Mastery Level | Pedagogical & Operational Focus | Verification Deliverable |
| :--- | :--- | :--- |
| **`M1` (Novice / Undergraduate)** | Control-volume mass/energy balances, unit conversions, `AISI 304` vs `AISI 316` corrosion basics, Nyquist sampling intuition | Solved mass/energy balance sheet with explicit SI units (`kg`, `W`, `Pa`, `K`) |
| **`M2` (Intermediate / Lab Engineer)** | Coupled drying/milling calculations (`ISO 3310-1` $d_{90} < 300\,\mu\text{m}$), PID temperature loop tuning, FFT modal frequency extraction | SOP & P&ID verification table with `N vs N±1` boundary test cases |
| **`M3` (Senior Process / Mechatronics Engineer)** | Scale-up similarity (`Bi`, `Fo`, `Re`), pyrolysis retort pressure/thermal relief sizing (`RD 809/2021`), `ISO 20816` SHM anomaly thresholds | Full equipment specification and `AAA` automated interlock test suite |
| **`M4` (Principal Systems Architect)** | Multi-plant digital twin telemetry, `IEC 61511` `SIL` safety certification, cross-layer `citation_receipt` governance | Signed engineering design dossier with `E3/E2` statutory/standard receipts |

---

## 2. 4-Step Engineering Verification Checklist (`AAA` Boundary Protocol)

1. **Material & Surface Audit (`ENG-SCI-01`)**: Confirm alloy certificate ($\text{PREN} \ge 24.0$, `AISI 316/316L`) for all corrosive/food-grade wetted parts.
2. **Steady-State & Transient Balance (`ENG-SCI-02`)**: Close mass ($\sum \dot{m}_{\text{in}} = \sum \dot{m}_{\text{out}}$) and enthalpy balances within $\le 0.5\%$ residual error.
3. **Hard Interlock Cut-Point Test (`N vs N±1`)**: Verify both nominal acceptance ($T_{\text{core}} = 39.9\,^\circ\text{C} \to \text{UNLOCK}$) and boundary rejection ($T_{\text{core}} = 40.0\,^\circ\text{C} \to \text{LOCKED}$).
4. **Telemetry & Provenance Seal (`ENG-SCI-03`)**: Attach `sci-engineering::docs/reference/01_materials_metallurgy_unit_operations_and_shm_standards.md#<slug>@<digest16>:E3`.
