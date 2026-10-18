# Chapter 10 — Project Planning, Design and Implementation (Common to all faculties)
*(Code AALL10 — 10 questions)*

---

## 10.1 Engineering Drawings and Its Concepts

### Standard drawing sheets
- Standard sizes (ISO A-series): **A0 (841×1189), A1, A2, A3, A4** — each size = half of previous (same ratio √2:1).
- **Border, title block** (bottom right): contains drawing number, title, scale, drawn by, date, sheet number.
- Line types: continuous thick (visible outline), thin (dimension/extension/hidden...), **dashed (hidden)**.

### Dimensions & scales
- **Dimensioning:** extension lines, dimension lines, arrows, leader lines; units mm in civil/mech drawings.
- **Scale:** ratio of drawing size to actual size.
  - **Full scale 1:1**, reduced scale (1:2, 1:100), enlarged scale (2:1, 5:1).
  - Scale notation: (1:50) means drawn 50× smaller.

### Projections (views)
- **Orthographic projection:** object projected on mutually perpendicular planes (top, front, side). Projectors perpendicular to drawing plane. Multi-view drawing system (First-angle/EU & Third-angle/US projection symbols).
- **Isometric projection/view:** 3D representation; three axes equally inclined (each 120°), edges drawn along axes; **foreshortened uniformly ~0.82** for true size (isometric scale). Common "3D" engineering view.
- **Pictorial views:** include isometric, oblique, perspective — show object "as seen".
- **Sectional drawing:** pretend to cut object, show internal details with **hatching/cross-section lines (45°)**, cutting plane line (thick dashes + arrows).

---

## 10.2 Engineering Economics

### Money & time
- **Cash flow:** inflows (+) and outflows (−) over time on a diagram.
- **Interest:** cost of money. **Simple:** `I = P·r·t`. **Compound:** `F = P(1+i)^n`.
- **Time value of money:** a rupee today is worth more than a rupee tomorrow (can earn interest).
- **Discount rate:** rate used to bring future cash flows to present value.
- **Present worth of future amount:** `P = F / (1+i)^n = F·(P/F,i,n)`.

### Economic analysis methods
| Method | Definition | Decision rule |
|---|---|---|
| **Payback period** | Time to recover initial investment | Shorter is better (ignore time value in simple version) |
| **Discounted Payback** | Payback using discounted cash flows | Meets threshold → accept |
| **NPV (Net Present Value)** | `Σ (CFₜ/(1+i)ᵗ) − Initial cost` | **Accept if NPV > 0**; project adds value |
| **IRR (Internal Rate of Return)** | Discount rate where **NPV = 0** | Accept if IRR ≥ MARR |
| **MARR (Minimum Attractive Rate of Return)** | Minimum return acceptable to firm (hurdle rate) | — |

- **Comparison of alternatives:** use present worth (PW), annual worth (AW), IRR comparison; select alternative with highest PW/AW or lowest cost (revenue vs cost projects).

### Depreciation & taxation
- **Depreciation:** allocation of asset cost over useful life.
  - **Straight-line (SL):** `D = (C − S)/n` (cost − salvage over life).
  - **Declining balance (DB), Sum-of-Years-Digits (SOYD), MACRS.**
- **Taxation system in Nepal:** corporate income tax, VAT (13% standard), TDS, property tax; depreciation affects taxable income, hence cash flows. Projects evaluated after-tax.

---

## 10.3 Project Planning and Scheduling

### Project concepts
- **Project:** temporary endeavor with a definite objective, schedule, budget; unique output.
- **Project classifications:** by size/cost, by industry (construction, IT, infrastructure), by complexity/risk.

### Project life cycle phases
1. **Initiation/Concept** — define need, feasibility.
2. **Planning** — scope, schedule (WBS), budget, risk, quality.
3. **Execution/Implementation** — perform the work.
4. **Monitoring & Controlling** — track, report, correct.
5. **Closing** — handover, lessons learned.
(Feasibility → design → construction → operation ≈ for engineering projects.)

### Planning process
- Define objectives → **WBS (work breakdown structure)** → activities → dependencies → estimate durations/resources → schedule.

### Scheduling tools
| Tool | Features |
|---|---|
| **Bar chart (Gantt)** | Activities vs time bars; simple; **doesn't clearly show dependencies** |
| **CPM (Critical Path Method)** | Deterministic durations; **critical path** = longest path & zero float; used for construction |
| **PERT (Program Evaluation & Review Technique)** | **Probabilistic** durations (optimistic a, most likely m, pessimistic b); `te = (a+4m+b)/6`; variance = ((b−a)/6)²; used for uncertain/R&D projects |

- **Critical path:** sequence of activities determining project duration; delays there delay the project. **Float/slack:** spare time an activity can be delayed without delaying project (total float; free float).
- **Network diagram:** AOA (activity on arrow) / AON (activity on node); forward & backward passes to compute ES, EF, LS, LF, float.

### Resource management
- **Resource leveling:** adjust schedule to keep resource usage within limits (delay non-critical activities).
- **Resource smoothing:** leveling within float without changing project duration.

### Monitoring/evaluation/controlling
- **Earned value analysis:** BCWS (planned), ACWP (actual), **EV (earned value)**; indicators: **CV = EV−AC**, **SV = EV−PV**, **CPI, SPI** (<1 = over budget/behind).
- Reports, meetings, corrective action, change control.

---

## 10.4 Project Management

### Information systems
- **Management information system (MIS):** provides data for planning, control, decision-making (reports, dashboards).
- **Project management information systems (PMIS):** software (MS Project, Primavera).

### Project risk analysis and management
- **Risk:** uncertain event that may affect project (positive = opportunity, negative = threat).
- **Risk management process:**
  1. **Identification** (checklists, brainstorming)
  2. **Qualitative analysis** (probability × impact matrix)
  3. **Quantitative analysis** (EMV = probability × impact; simulation/Monte Carlo)
  4. **Response planning** (avoid, transfer, mitigate, accept)
  5. **Monitoring & control**

### Project financing
- Sources: equity, debt (loans/bonds), grants, **public-private partnership (PPP)**, BOOT/BOT models.
- **Financing plan:** mix of debt/equity, repayment schedules, cash flow management.

### Tendering
- **Tender:** formal offer/invitation to bid for work.
- **Tendering process:** invitation → bid submission → **bid opening** → evaluation → **award of contract**.
- Tender types: open (any), selective/restricted (invited), negotiated, two-envelope (technical + financial).
- **Bid documents:** BOQ (bill of quantities), specifications, drawings, conditions of contract.

### Contract management
- **Contract:** legally binding agreement (scope, price, time, quality, terms & conditions).
- Contract types: lump-sum (fixed price), **unit-price (BOQ-based)**, cost-plus, design-build.
- Management: progress claims/measurement, variation orders, extension of time, claims & disputes, **payment (advance, running, retention, final)**, performance bond.

---

## 10.5 Engineering Professional Practice

### Environment and society
- Engineers must consider **environmental impact** (EIA), sustainability, and social responsibility in projects.
- Green engineering, waste management, renewable energy.

### Professional ethics
- **Ethics:** moral principles guiding professional conduct.
- Core ethical principles: honesty, integrity, competence, confidentiality, conflict-of-interest avoidance, public **safety & welfare first**.
- Codes of conduct: e.g., **NEA code of conduct**, rarely professional registration discipline.

### Regulatory environment
- Engineering practice in Nepal governed by laws, standards, building codes (NBC), Nepal Building Act, environmental law, **NEC Act/Regulations**; approval processes (DUDBC, municipality permits).

### Contemporary issues/problems in engineering
- Infrastructure deficit, disaster risk (earthquake resilience after 2015 Gorkha quake), climate change adaptation, energy crisis, technology & cyber issues, brain drain, corruption, safety lapses.

### Occupational health and safety (OHS)
- **OHS:** protecting workers from hazards (physical, chemical, biological, ergonomic, psychosocial).
- Measures: risk assessment, **PPE (helmet, gloves, goggles)**, safety training, emergency plans, accident reporting; legal duties under Labour/Occupational Safety Acts of Nepal.

### Nepal Engineers' Association (NEA)
- **NEA:** professional body of Nepalese engineers; promotes profession, organizes events, represents engineers' interests, licenses & ethical conduct support, capacity building.
- (Distinct from NEC — NEC is the statutory licensing/regulatory council; NEA is the professional association.)

---

## 10.6 Engineering Regulatory Body — Nepal Engineering Council (NEC)

### Establishment & purpose
- **NEC established 2055 B.S. (1999 AD)** under the **Nepal Engineering Council Act, 2055** — a **statutory autonomous body**.
- Purpose: **regulate and promote the engineering profession** in Nepal; maintain professional register.

### Key functions (as per Act)
1. Identify engineering institutions/programs for **recognition/accreditation**.
2. **Register engineers** (General, Professional, Non-Nepali categories).
3. Prepare **registration exam curriculum** and **conduct the license examination** (≥ 2 per year).
4. Maintain the **Register of Engineers** and publish it.
5. Determine qualifications to practice; issue registration certificates.
6. Regulate practice; **prohibition to practice without registration** (Section 11).
7. Amend curriculum, supervise engineering education quality (colleges/affiliation recognition).

### Registration categories
- **General Registered Engineer** (fresh graduate, passes registration exam).
- **Professional Engineer** (written + skill eval + interview; experience requirement).
- **Non-Nepali registered engineer** (foreign engineers).

### Important provisions
- Practicing engineering without NEC registration is **illegal** (prohibited by Act Section 11).
- **Rules/Regulations 2057 (2001)** govern procedure; amended 2080 (2023) — examination via committee under Section 14.
- **Rights:** only registered engineers can sign/submit engineering works, hold engineering posts.
- Code of professional conduct must be followed; violation → disciplinary action / removal from register.

---

## Formula Box (Chapter 10 — must memorize)
- A-series sheets: A0 → A4 (half each time)
- Scales: 1:1 full; reduced/enlarged
- Orthographic = perpendicular projectors, multi-view; Isometric = 3 axes at 120°
- Simple interest I=PrA; Compound F=P(1+i)^n
- NPV = Σ CF/(1+i)^t − I₀; accept if > 0; IRR = rate where NPV=0; accept if IRR ≥ MARR
- SL depreciation D = (C−S)/n
- CPM = deterministic, critical path; PERT = probabilistic, te=(a+4m+b)/6
- Float/slack: LS−ES (or LF−EF); critical path float = 0
- EVA: EV, CV=EV−AC, SPI=EV/PV; CPI=EV/AC
- Risk: EMV = probability × impact
- Tender → award → contract; BOQ
- PPE: safety; NBC building codes; NEA = professional association
- NEC: statutory, 2055 Act; General/Professional/Non-Nepali registers; exam ≥2×/year