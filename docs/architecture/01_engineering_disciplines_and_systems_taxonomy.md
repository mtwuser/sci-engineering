---
epistemic_grade: E3
---

# Engineering Disciplines, Systems V-Model & Functional Safety Taxonomy (`sci-engineering` — `E3/E2`)

> **Epistemic Credibility Grade: `E3/E2` (UNESCO/Frascati Trunk 4 Engineering Taxonomy & `IEC 61508/61511` Safety Architecture)**
>
> This architecture specification structures **`sci-engineering`** (`canonical_trunk: "engineering"`) across six orthogonal engineering disciplines (`ENG-BR-01..06`), codifies the quantitative Systems Engineering `V-Model` and Factor-of-Safety (`FoS`) governance, and defines `IEC 61508 / IEC 61511` Safety Integrity Level (`SIL 1..4`) cut-points ([01_materials_metallurgy_unit_operations_and_shm_standards.md](../reference/01_materials_metallurgy_unit_operations_and_shm_standards.md)).

---

## 1. The 6 Canonical Branches of `sci-engineering` (`ENG-BR-01..06`) [E3]

> **Summary [E3]:** *`sci-engineering` translates fundamental formal and natural laws (`sci-maths`, `sci-physics`, `sci-biology`) into six applied engineering branches governed by international `ISO`, `IEC`, `EN`, and `ASTM` standards ([01_materials_metallurgy_unit_operations_and_shm_standards.md](../reference/01_materials_metallurgy_unit_operations_and_shm_standards.md)).*

The table below maps each engineering branch to its scientific substrate, governing standards, and industrial scope:

| Branch ID & Discipline | Primary Scientific Substrate | Normative `ISO / IEC / EN / ASTM` Standards | Industrial & Cyber-Physical Scope |
| :--- | :--- | :--- | :--- |
| **`ENG-BR-01`: Materials Science & Metallurgy** | Solid-state physics, phase diagrams, electrochemistry (`sci-physics`). | `EN 10088`, `ASTM A240`, `ISO 4287` ($R_a$), `EC 1935/2004`. | `AISI 316/316L` passivated alloys ($\text{PREN} \ge 24.0$), carbide sensitization prevention, sanitary surface finish ($R_a \le 0.8\,\mu\text{m}$). |
| **`ENG-BR-02`: Chemical, Process & Bioprocess Engineering** | Coupled Fourier/Fick transport (`sci-physics`), enzyme/$a_w$ kinetics (`sci-biology`). | `ISO 3310-1` (test sieves), `PED 2014/68/EU` (`RD 809/2021`), `ATEX 2014/34/EU`. | Convective drying (`[35.0 °C, 40.0 °C]`), micronization ($d_{90} < 300\,\mu\text{m}$), anoxic pyrolysis retorts (`450–650 °C`, `< 40.0 °C` hatch lock). |
| **`ENG-BR-03`: Mechanical, Thermal & Fluid Systems** | Continuum mechanics, Navier-Stokes, turbomachinery thermodynamics. | `ISO 5167` (flow metering), `DIN 32676` (tri-clamp), `ASME VIII` / `EN 13445`. | Heat exchangers, rotary/hammer mills, vacuum/pressure vessels, pneumatic and sanitary piping networks. |
| **`ENG-BR-04`: Civil, Structural & SHM Engineering** | Linear elasticity, Euler-Bernoulli/Timoshenko beams, spectral eigenvalue theory (`sci-maths`). | `Eurocodes EN 1990..1999`, `ISO 20816-1..3` (machine & structural vibration). | Structural Health Monitoring (`SHM`), modal natural frequencies ($f_n$), damping ($\zeta_n$), RMS vibration severity zones (`Zone A..D`). |
| **`ENG-BR-05`: Electrical, Instrumentation & Signal Acquisition** | Maxwell electrodynamics, semiconductor physics, Nyquist-Shannon sampling. | `IEC 60751` (`PT100`), `NAMUR NE 43` (`4–20 mA`), `IEC 61010-1`. | RTD/thermocouple conditioning, `4–20 mA` fault detection, `IEPE` accelerometers, anti-aliased `ADC` acquisition ($f_s \ge 2.56\,f_{\max}$). |
| **`ENG-BR-06`: Control Systems, Mechatronics & Functional Safety** | Dynamical systems, Lyapunov stability, Kalman estimation (`sci-maths`). | `IEC 61508`, `IEC 61511` (process `SIL`), `IEC 61131-3` (`PLC`), `ISO 13849-1`. | Cascade `PID`/`MPC` loops, hardware-wired safety instrumented functions (`SIF`), fail-safe valves/locks (`de-energize-to-trip`). |

---

## 2. Systems Engineering `V-Model`, Tolerances & Factor-of-Safety (`FoS`) Governance [E3]

> **Summary [E3]:** *Every physical or cyber-physical engineering design must close mass/energy conservation (`E3`), apply explicit statutory Factor-of-Safety (`FoS > 1.0`) margins over yield/buckling/pressure limits, and pair every requirement on the left of the `V-Model` with an objective `AAA` verification test on the right ([01_applied_engineering_design_and_verification_guide.md](../guides/01_applied_engineering_design_and_verification_guide.md)).*

1. **Allowable Stress & Factor of Safety (`ENG-ARCH-01`)**: Design load or stress $\sigma_{\text{design}}$ must satisfy $\sigma_{\text{design}} \le \sigma_{\text{allow}} = \sigma_{\text{limit}} / \text{FoS}$, with minimum $\text{FoS} \ge 1.50$ against ductile `0.2%` offset yield ($R_{p0.2}$) under `EN 13445` pressure-vessel design and $\text{FoS} \ge 2.40\text{–}3.50$ against ultimate tensile strength ($R_m$) or brittle fracture.
2. **Independent Protection Layers (`IPL` / Defense-in-Depth, `ENG-ARCH-02`)**: Process control (`BPCS`, e.g., `PID` temperature loop) and Safety Instrumented Systems (`SIS`, e.g., independent high-temperature thermal cut-out + mechanical pressure relief valve) **must never share sensors, logic solvers, or final switching elements** (`0` common-cause single points of failure).

---

## 3. Functional Safety Integrity Levels (`IEC 61508 / IEC 61511` `SIL 1..4` Cut-Points) [E2]

> **Summary [E2]:** *`IEC 61508` and `IEC 61511` classify Safety Instrumented Functions (`SIF`) into four discrete Safety Integrity Levels (`SIL 1..4`) bounded by exact order-of-magnitude cut-points on average Probability of Failure on Demand ($\text{PFD}_{\text{avg}}$) and dangerous failure frequency ($\text{PFH}$).*

The table below specifies the exact `IEC 61508` quantitative cut-points for Low-Demand and High-Demand/Continuous safety functions:

| Safety Integrity Level (`SIL`) | Low-Demand Mode $\text{PFD}_{\text{avg}}$ (`<= 1/year`) | Risk Reduction Factor ($\text{RRF} = 1/\text{PFD}_{\text{avg}}$) | High-Demand / Continuous Mode $\text{PFH}$ ($\text{h}^{-1}$) | Typical Industrial Application |
| :---: | :---: | :---: | :---: | :--- |
| **`SIL 1`** | $[10^{-2}, 10^{-1})$ | `10 – 100` | $[10^{-6}, 10^{-5})$ | Secondary equipment protection, batch dehydration over-temperature cut-off (`>= 40.5 °C`). |
| **`SIL 2`** | $[10^{-3}, 10^{-2})$ | `100 – 1 000` | $[10^{-7}, 10^{-6})$ | Pyrolysis retort hatch lock (`T_core < 40.0 °C`), `ATEX` dust-milling inerting/earthing interlocks. |
| **`SIL 3`** | $[10^{-4}, 10^{-3})$ | `1 000 – 10 000` | $[10^{-8}, 10^{-7})$ | High-pressure exothermic runaway emergency depressurization (`HIPPS`), toxic gas shutdown. |
| **`SIL 4`** | $[10^{-5}, 10^{-4})$ | `10 000 – 100 000` | $[10^{-9}, 10^{-8})$ | Nuclear reactor protection, primary railway/aviation fly-by-wire critical systems. |
