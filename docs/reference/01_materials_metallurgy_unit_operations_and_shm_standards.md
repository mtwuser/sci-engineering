# Materials Metallurgy, Unit Operations & SHM Telemetry Standards (`sci-engineering` — `E3/E2`)

> **Epistemic Credibility Grade: `E3/E2` (Canonical ISO/EN/ASTM Engineering Standards & Safety Interlocks)**
>
> Normative reference tables for surgical/food-grade metallurgy, `ISO 3310-1` granulometry, biorefinery thermal unit operations, and Structural Health Monitoring (`SHM`) vibration telemetry (`make consult LAYER=sci-engineering`).

---

## 1. Austenitic Stainless Steel Metallurgy & Sanitary Contact Surfaces (`ENG-SCI-01` — `E3/E2`)

Process equipment contacting organic acids, polyphenols, chloride-bearing biomass, or biological media must select alloys by their **Pitting Resistance Equivalent Number** ($\text{PREN} = \%\text{Cr} + 3.3\,\%\text{Mo} + 16\,\%\text{N}$):

| Alloy Designation (`AISI` / `EN` / `UNS`) | Nominal Composition ($\text{wt}\%$) | Minimum $\text{PREN}$ | Max Carbon ($\text{wt}\%$) | Approved Engineering Application & Constraints |
| :--- | :--- | :--- | :--- | :--- |
| **`AISI 316` (`EN 1.4401` / `UNS S31600`)** | $16.5\text{–}18.5\%\text{ Cr}$, $10\text{–}13\%\text{ Ni}$, $2.0\text{–}2.5\%\text{ Mo}$ | `>= 24.0` | `0.07%` | **Mandatory baseline** for rotary milling blades (`dept-iso-bio` `BIO-01`), sieve meshes, and acidic/polyphenol wetted extractors (`EC 1935/2004`). |
| **`AISI 316L` (`EN 1.4404` / `UNS S31603`)** | $16.5\text{–}18.5\%\text{ Cr}$, $10\text{–}13\%\text{ Ni}$, $2.0\text{–}2.5\%\text{ Mo}$ | `>= 24.0` | `0.03%` | **Mandatory for welded vessels, bioreactors, and pyrolysis retorts** (`< 450 °C` continuous wet / `< 650 °C` anoxic dry) to prevent intergranular carbide precipitation (`sensitization`). |
| **`AISI 304` (`EN 1.4301` / `UNS S30400`)** | $17.5\text{–}19.5\%\text{ Cr}$, $8\text{–}10.5\%\text{ Ni}$, $0\%\text{ Mo}$ | `~18.0` | `0.07%` | External frames and non-acidic dry structural housings only; **prohibited** for acidic organic maceration or high-shear milling blades. |
| **Plain Carbon Steel / Cast Iron** | Fe-C without Cr/Ni passivation | `< 2.0` | `> 0.15%` | **Strictly prohibited** on wetted or food/biomass contact surfaces due to $\text{Fe}^{2+}/\text{Fe}^{3+}$ Fenton catalytic oxidation of lipids and polyphenols. |

---

## 2. Granulometry (`ISO 3310-1`) & Thermal/Pyrolysis Unit Operations (`ENG-SCI-02` — `E3/E2`)

| Unit Operation & Standard | Operational Parameter & Cut-Point (`N vs N±1`) | Engineering Governing Equation / Control Interlock |
| :--- | :--- | :--- |
| **Convective Tray/Belt Dehydration (`ENG-OP-01`)** | Air temperature $T_{\text{air}} \in [35.0\,^\circ\text{C}, 40.0\,^\circ\text{C}]$ (`308.15–313.15 K`); target moisture $X_w < 10.0\%\text{ w/w}$ ($a_w < 0.60$). Hard alarm at $T_{\text{air}} \ge 40.5\,^\circ\text{C}$. | Drying rate $\dot{m}_{\text{evap}} = k_g A (p_w^*(T_s) - \varphi p_w^*(T_{\text{air}}))$; preserves heat-labile phytochemicals (`sci-biology` `BIO-SCI-02`). |
| **High-Shear Milling & `ISO 3310-1` Sieving (`ENG-OP-02`)** | `AISI 316` blades (`>= 24 000 RPM`), batch duty cycle $\le 60\text{ s}$ (`T_bed <= 45.0 °C`), calibrated `ISO 3310-1` woven wire sieve aperture $d_{90} < 300\,\mu\text{m}$ (`< 0.30 mm`, `No. 50 Mesh`). | Specific grinding energy $E_m = C_K (d_{80,\text{prod}}^{-1/2} - d_{80,\text{feed}}^{-1/2})$ (Bond's Law); specific surface area $a_s = 6 / (\rho_p d_{32})$. |
| **Anoxic Pyrolysis Retort & Quench Interlock (`ENG-OP-03`, `RD 809/2021`)** | Carbonization window $T_{\text{retort}} \in [450\,^\circ\text{C}, 650\,^\circ\text{C}]$, head-space $\text{O}_2 < 1.5\%\text{ v/v}$, pressure relief valve at $P_{\text{rel}} = 0.45\text{ bar(g)}$ (`< 0.50 bar(g)` statutory limit). **Hatch interlock locked until $T_{\text{core}} < 40.0\,^\circ\text{C}$ (`313.15 K`)**. | Prevents pyrophoric auto-ignition of high-porosity biochar upon atmospheric $\text{O}_2$ admission ($T_{\text{core}} = 40.0\,^\circ\text{C}$ is `BLOCKED`). |

---

## 3. Structural Health Monitoring (`SHM`) & Modal Vibration Telemetry (`ENG-SCI-03` — `E2`)

- **Multi-Degree-of-Freedom (`MDOF`) Structural Dynamics (`sci-maths` `MATH-01`)**:
  $$\mathbf{M}\ddot{\mathbf{u}}(t) + \mathbf{C}\dot{\mathbf{u}}(t) + \mathbf{K}\mathbf{u}(t) = \mathbf{f}(t), \qquad \det\!\left(\mathbf{K} - \omega_n^2 \mathbf{M}\right) = 0 \implies f_n = \frac{\omega_n}{2\pi}$$
- **Nyquist-Shannon Telemetry & `ISO 10816 / ISO 20816` Vibration Severity Cut-Points**:
  - Sampling frequency must satisfy $f_s \ge 2.56\,f_{\max}$ with anti-aliasing low-pass filtering at $f_c \le 0.40\,f_s$.
  - Broadband RMS velocity $v_{\text{RMS}}$ (`10 Hz – 1 000 Hz`) for Class II industrial machines: **Good** ($v_{\text{RMS}} \le 1.8\text{ mm}\cdot\text{s}^{-1}$), **Alert** ($1.8 < v_{\text{RMS}} \le 4.5\text{ mm}\cdot\text{s}^{-1}$), **Trip / Emergency Shutdown** ($v_{\text{RMS}} > 7.1\text{ mm}\cdot\text{s}^{-1}$).
