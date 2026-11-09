# Engineering Disciplines, Unit Operations & Cyber-Physical Systems Taxonomy (`sci-engineering` — `E3`)

> **Epistemic Credibility Grade: `E3` (UNESCO/Frascati Trunk 4: Engineering & Technology Classification)**
>
> Canonical arboreal taxonomy mapping fundamental laws (`sci-physics`, `sci-maths`, `sci-biology`) to applied materials, chemical/bioprocess unit operations, mechanical/structural systems, and control engineering (`make consult LAYER=sci-engineering`).

---

## 1. Canonical 6-Branch Engineering Taxonomy (`ENG-BR-01..06` — `E3`)

`sci-engineering` structures applied engineering knowledge into six orthogonal branches bridging pure science (`nature` and `formal` trunks) with industrial and software execution:

| Branch ID | Engineering Discipline | Core Scientific Substrate | Canonical Standards & Industrial Scope |
| :--- | :--- | :--- | :--- |
| **`ENG-BR-01`** | **Materials Science & Metallurgy** | Solid-state physics, phase thermodynamics, electrochemistry | `EN 10088` / `ASTM A240` stainless steels (`AISI 304`, `AISI 316/316L`), `PREN` pitting resistance, polymer glass-transition ($T_g$), sanitary surface finish ($R_a \le 0.8\,\mu\text{m}$) |
| **`ENG-BR-02`** | **Chemical, Process & Bioprocess Engineering** | Coupled Fourier/Fick transport (`sci-physics`), enzyme/microbial kinetics (`sci-biology`) | Unit operations: size reduction, `ISO 3310-1` sieving/granulometry, convective drying (`35–40 °C`), solid-liquid extraction, anoxic pyrolysis retorts (`450–650 °C`), `ATEX` / `RD 809/2021` pressure/thermal interlocks |
| **`ENG-BR-03`** | **Mechanical, Thermal & Fluid Systems** | Continuum mechanics, Navier-Stokes, turbomachinery thermodynamics | Heat exchangers, pneumatic/hydraulic conveying, vacuum vessels, sanitary tri-clamp piping (`DIN 32676`), rotary knife and hammer mills |
| **`ENG-BR-04`** | **Civil, Structural & SHM Engineering** | Linear elasticity, Euler-Bernoulli beam dynamics, modal analysis (`sci-maths` `MATH-01..02`) | Structural Health Monitoring (`SHM`), modal natural frequencies ($f_n$), damping ratios ($\zeta_n$), accelerometer/strain-gauge arrays, `ISO 10816 / ISO 20816` vibration severity |
| **`ENG-BR-05`** | **Electrical, Electronics & Instrumentation** | Maxwell electrodynamics, semiconductor physics, signal theory | Industrial sensor conditioning (`PT100/PT1000` RTDs, `4–20 mA` current loops, `IEPE` piezoelectric accelerometers), ADC Nyquist sampling ($f_s > 2.56\,f_{\max}$), `IEC 61010` safety |
| **`ENG-BR-06`** | **Control Systems, Mechatronics & Safety (`SIL`)** | Dynamical systems, Lyapunov stability, stochastic filtering (`Kalman`) | PID/MPC thermal loop control, PLC hardware interlocks, functional safety (`IEC 61508` / `IEC 61511` `SIL 1..3`), fail-safe valve states |

---

## 2. Epistemic Bridge Between Pure Science (`nature` / `formal`) and Engineering (`engineering`)

1. **Law (`sci-physics` / `sci-maths` `E3`) $\rightarrow$ Constitutive Design Equation (`sci-engineering` `E3/E2`)**:
   - Pure physics establishes conservation of energy and Fourier/Fick transport PDEs (`sci-physics`); `sci-engineering` translates them into equipment sizing equations, Nusselt/Sherwood correlations, and safety factor margins ($\text{FoS} \ge 1.5$).
2. **Biological Threshold (`sci-biology` `E3`) $\rightarrow$ Unit Operation Window (`sci-engineering` `E2`)**:
   - Pure biology establishes protein/polyphenol thermal denaturation above $42.0\,^\circ\text{C}$ and microbial stasis at $a_w < 0.60$ (`sci-biology`); `sci-engineering` specifies the forced-convection dehydrator airflow, tray loading density, and `[35.0 °C, 40.0 °C]` PID control loop (`ENG-SCI-02`).
