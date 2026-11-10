---
epistemic_grade: E3
---

# Metallurgy, Unit Operations, SHM Vibration & Industrial Instrumentation Standards (`sci-engineering` — `E3/E2`)

> **Epistemic Credibility Grade: `E3/E2` (Normative `ISO / EN / ASTM / IEC / NAMUR` Engineering Cut-Points & Safety Interlocks)**
>
> Quantitative reference tables for austenitic stainless steel metallurgy (`EN 10088`), `ISO 3310-1` granulometry, thermal/pressure unit-operation interlocks (`PED 2014/68/EU` / `RD 809/2021`), `ISO 20816-3` vibration severity, and `IEC 60751` / `NAMUR NE 43` sensor telemetry consumed via `make consult LAYER=sci-engineering` ([01_engineering_disciplines_and_systems_taxonomy.md](../architecture/01_engineering_disciplines_and_systems_taxonomy.md)).

---

## 1. Austenitic Stainless Steel Metallurgy & Sanitary Contact Surfaces (`ENG-SCI-01`) [E2]

> **Summary [E2]:** *Process equipment contacting organic acids, polyphenols, chlorides, or food/biological media must enforce molybdenum-stabilized austenitic alloys (`AISI 316` / `AISI 316L`, $\text{PREN} \ge 24.0$) and sanitary surface roughness $R_a \le 0.8\,\mu\text{m}$ ([01_engineering_disciplines_and_systems_taxonomy.md](../architecture/01_engineering_disciplines_and_systems_taxonomy.md)).*

Alloy pitting resistance in halide/acidic media is governed by $\text{PREN} = \%\text{Cr} + 3.3\,\%\text{Mo} + 16\,\%\text{N}$:

| Alloy (`AISI` / `EN` / `UNS`) | Composition ($\text{wt}\%$ Cr / Ni / Mo) | $\text{PREN}$ Cut-Point | Max Carbon ($\text{wt}\%$) | Approved Engineering Scope & Constraints |
| :--- | :--- | :---: | :---: | :--- |
| **`AISI 316` (`EN 1.4401` / `S31600`)** | $16.5\text{–}18.5$ / $10.0\text{–}13.0$ / $2.0\text{–}2.5$ | `>= 24.0` | `0.07%` | **Mandatory baseline** for non-welded rotary milling blades, `ISO 3310-1` sieve meshes, and polyphenol/acidic wetted parts (`EC 1935/2004`). |
| **`AISI 316L` (`EN 1.4404` / `S31603`)** | $16.5\text{–}18.5$ / $10.0\text{–}13.0$ / $2.0\text{–}2.5$ | `>= 24.0` | **`<= 0.03%`** | **Mandatory for welded vessels, bioreactors, and pyrolysis retorts** (`425–850 °C` weld zone) to prevent $\text{Cr}_{23}\text{C}_6$ intergranular sensitization. |
| **`AISI 304` (`EN 1.4301` / `S30400`)** | $17.5\text{–}19.5$ / $8.0\text{–}10.5$ / $0.0$ | `~17.5 – 19.5` | `0.07%` | Dry external frames, guards, and non-corrosive structural supports; **prohibited** for chloride/acidic maceration or high-shear blades. |
| **Carbon Steel / Uncoated Cast Iron** | Fe-C (`< 10.5% Cr`, non-passivating) | `< 2.0` | `> 0.15%` | **Strictly prohibited** on wetted biomass/food surfaces (`Fe²⁺/Fe³⁺` Fenton catalysis degrades lipids and polyphenols). |

- **Sanitary Surface Roughness (`ISO 4287` / `EHEDG`, `E2`)**: Product-contact surfaces require arithmetical mean roughness $R_a \le 0.80\,\mu\text{m}$ (electropolished sterile/pharmaceutical grade $R_a \le 0.40\,\mu\text{m}$) to prevent biofilm anchorage during Clean-in-Place (`CIP`).

---

## 2. Granulometry (`ISO 3310-1`), Drying & Pressure/Pyrolysis Interlocks (`ENG-SCI-02`) [E2]

> **Summary [E2]:** *Thermal dehydration, high-shear milling, and anoxic pyrolysis retorts enforce hard hardware/PLC cut-points (`N` vs. `N ± 1`) on temperature, `ISO 3310-1` particle size, `PED 2014/68/EU` `0.50 bar(g)` gauge pressure, and pyrophoric hatch unlocking (`T_core < 40.0 °C`) ([01_applied_engineering_design_and_verification_guide.md](../guides/01_applied_engineering_design_and_verification_guide.md)).*

The table below codifies unit-operation governing equations and exact boundary interlocks:

| Unit Operation & Standard | Nominal Operating Window | Exact Cut-Point (`N` vs. `N ± 1`) | Safety / Quality Interlock Action |
| :--- | :--- | :--- | :--- |
| **Convective Dehydration (`ENG-OP-01`)** | $T_{\text{air}} \in [35.0\,^\circ\text{C}, 40.0\,^\circ\text{C}]$ (`308.15–313.15 K`), product $X_w < 10.0\%\text{ w/w}$ ($a_w < 0.60$) | $T_{\text{air}} = 40.0\,^\circ\text{C}$ (`NOMINAL`) vs. $T_{\text{air}} \ge 40.5\,^\circ\text{C}$ (`HIGH-TEMP TRIP`) | Cuts heater power while maintaining blower airflow to protect thermolabile compounds (`sci-biology`). |
| **High-Shear Milling & `ISO 3310-1` Sieving (`ENG-OP-02`)** | `AISI 316` blades (`>= 24 000 RPM`), duty cycle $\le 60\text{ s}$, bed $T_{\text{bed}} \le 45.0\,^\circ\text{C}$ | Sieve aperture $d_{90} < 300\,\mu\text{m}$ (`PASS`) vs. $d_{90} \ge 300\,\mu\text{m}$ (`RE-MILL` oversize recycle) | Bond grinding work $W = 10\,W_i(d_{80,p}^{-1/2} - d_{80,f}^{-1/2})$; `ATEX` earthing $< 10\,\Omega$ prevents dust electrostatic ignition. |
| **Pressure Equipment Boundary (`PED 2014/68/EU` / `RD 809/2021`)** | Atmospheric / low-pressure retort $P_s \le 0.45\text{ bar(g)}$ (`45 kPa(g)`) | $P_{s,\max} \le 0.50\text{ bar(g)}$ (`Art. 4.3 SEP`) vs. $P_{s,\max} > 0.50\text{ bar(g)}$ (`PED Cat. I–IV` mandatory CE notified-body stamp) | Mechanical spring relief valve set at $P_{\text{rel}} = 0.45\text{ bar(g)}$ ensures statutory `<= 0.50 bar(g)` envelope. |
| **Anoxic Pyrolysis Retort Hatch Interlock (`ENG-OP-03`)** | Carbonization $T \in [450\,^\circ\text{C}, 650\,^\circ\text{C}]$, head-space $\text{O}_2 < 1.5\%\text{ v/v}$ | Core quench $T_{\text{core}} = 39.9\,^\circ\text{C}$ (`UNLOCK_ALLOWED`) vs. **$T_{\text{core}} \ge 40.0\,^\circ\text{C}$ (`HATCH_LOCKED`)** | Electromechanical `SIL 2` bolt blocks $\text{O}_2$ ingress to prevent pyrophoric biochar auto-ignition. |

---

## 3. Structural Health Monitoring (`SHM`) & `ISO 20816-3` Vibration Cut-Points (`ENG-SCI-03`) [E2]

> **Summary [E2]:** *Modal structural dynamics ($\det(\mathbf{K} - \omega_n^2\mathbf{M}) = 0$) and rotating machinery diagnostics require anti-aliased Nyquist sampling ($f_s \ge 2.56\,f_{\max}$) and `ISO 20816-3` broadband RMS velocity thresholds (`Zone A..D`).*

$$\mathbf{M}\ddot{\mathbf{u}}(t) + \mathbf{C}\dot{\mathbf{u}}(t) + \mathbf{K}\mathbf{u}(t) = \mathbf{f}(t), \qquad v_{\text{RMS}} = \sqrt{\frac{1}{T}\int_0^T v^2(t)\,dt} \quad (10\text{ Hz} \le f \le 1\,000\text{ Hz})$$

The table below lists `ISO 20816-3` broadband RMS vibration velocity cut-points for Group 2 medium-sized industrial machines (`15 kW – 300 kW`) on rigid foundations:

| `ISO 20816-3` Zone | RMS Velocity Range $v_{\text{RMS}}$ ($\text{mm}\cdot\text{s}^{-1}$) | Machine Health & Operational Action |
| :--- | :---: | :--- |
| **`Zone A` (Newly Commissioned)** | $v_{\text{RMS}} \le 1.4$ (`<= 2.3` flexible mount) | Optimal baseline after rotor balancing and shaft alignment. |
| **`Zone B` (Unrestricted Long-Term)** | $1.4 < v_{\text{RMS}} \le 2.8$ (`<= 4.5` flexible) | Acceptable continuous industrial operation; log spectral trend. |
| **`Zone C` (Restricted / Alert)** | $2.8 < v_{\text{RMS}} \le 4.5$ (`<= 7.1` flexible) | **Maintenance Alert**: Schedule bearing/imbalance inspection; restrict continuous duty. |
| **`Zone D` (Damage / Emergency Trip)** | **$v_{\text{RMS}} > 4.5$ (`> 7.1` flexible)** | **Automatic `TRIP` Shutdown**: Severe vibration capable of bearing seizure or structural fatigue failure. |

---

## 4. Industrial Sensor Loops (`NAMUR NE 43` `4–20 mA` & `IEC 60751` `PT100`) (`ENG-SCI-04`) [E2]

> **Summary [E2]:** *Analog `4–20 mA` current loops (`NAMUR NE 43`) encode live-zero wire-break and saturation diagnostics outside `[3.8 mA, 20.5 mA]`, while `IEC 60751` `PT100` platinum RTDs provide deterministic resistance-temperature calibration.*

The table below defines exact `NAMUR NE 43` current-loop diagnostic cut-points and `IEC 60751` `PT100` ($R_0 = 100.00\,\Omega$ at $0\,^\circ\text{C}$, $\alpha = 0.00385\,\Omega\cdot\Omega^{-1}\cdot{}^\circ\text{C}^{-1}$) accuracy classes:

| Standard & Signal | Nominal Measurement / Tolerance | Exact Fault / Class Cut-Point (`N` vs. `N ± 1`) | Controller / Safety Action |
| :--- | :--- | :--- | :--- |
| **`NAMUR NE 43` `4–20 mA` Loop** | `4.00 mA` (`0%` EU) to `20.00 mA` (`100%` EU); extended linear `[3.80 mA, 20.50 mA]` | **`I <= 3.60 mA`** (burnout low / wire break) or **`I >= 21.00 mA`** (burnout high / short) | Assert `SENSOR_FAULT` quality flag immediately and drive actuator to fail-safe state (`never` clamp `0 mA` as `-25%` EU!). |
| **`IEC 60751` `PT100` RTD Tolerance** | Callendar-Van Dusen $R(T) = R_0(1 + AT + BT^2)$ ($T \ge 0\,^\circ\text{C}$) | **Class AA**: $\pm(0.10 + 0.0017|T|)\,^\circ\text{C}$ · **Class A**: $\pm(0.15 + 0.002|T|)\,^\circ\text{C}$ · **Class B**: $\pm(0.30 + 0.005|T|)\,^\circ\text{C}$ | Use 4-wire Kelvin connection on Class AA/A probes (`<= ±0.23 °C` at `40.0 °C`) to eliminate lead-wire resistance offset. |
