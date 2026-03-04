# Domain Profile

## Field

**Primary:** Education Economics (learning loss, COVID-19, primary education)
**Adjacent subfields:** Development Economics, Labor Economics, Public Economics
**Geographic focus:** Ukraine (upper-middle-income, Eastern Europe)

---

## Target Journals (ranked by tier)

| Tier | Journals |
|------|----------|
| Top-5 | AER, QJE, JPE, REStud |
| Top field | AEJ:Applied, Journal of Human Resources (JHR), Journal of Development Economics |
| Strong field | Economics of Education Review, Journal of Public Economics, Journal of Policy Analysis and Management |
| Specialty | International Journal of Educational Development, Education Finance and Policy |

---

## This Paper's Data

| Dataset | Type | Access | Notes |
|---------|------|--------|-------|
| Ukraine State Monitoring of Quality of Primary Education (UCEQA) | Two cross-sections (2018, 2021) | restricted | 4th grade; math + reading; IRT-scaled 100-300 pts; ~9,000 students per wave |
| Teacher questionnaires (linked) | Class-level | same as above | Reports remote learning duration per class; key heterogeneity variable |

**Key data facts:**
- 2018 wave: 366 schools, 486 classes, 9,007 valid pupil records
- 2021 wave: 355 schools, 475 classes, 7,924 valid pupil records
- Scores on common IRT scale → directly comparable across waves
- Survey design weights available; cluster at school level (PSU)
- SES index: PCA asset-based, grouped into tertiles

---

## Identification Strategy

**Design:** Cross-cohort comparison (repeated cross-sections, NOT panel)

**Estimating equation:**
`Y_irt = α_r + β₁·May2021_t + X'_irt·β₂ + ε_irt`

**Key assumption:** Absent COVID-19, the 2021 cohort would have performed similarly to the 2018 cohort after conditioning on region FEs and observables.

**Main threat:** Differential test participation and compositional change across waves
- Math participation: 90.8% (2018) → 85.8% (2021)
- SES composition shifted: high-SES share increased 21% → 35%
- Suggests positive selection in 2021 → estimates may understate true losses

**Key results (preferred spec, column 3):**
- Mathematics: β₁ = −0.091 SD (p < 0.10)
- Reading: β₁ = −0.099 SD (p < 0.05)
- ≈ 0.21 school years math loss; ≈ 0.28 school years reading loss

---

## Field Conventions

- Report effect sizes in SD units of the 2018 pre-COVID distribution
- Convert to school-year equivalents using Hill et al. (2008) benchmarks (0.52 SD/year math; 0.36 SD/year reading) — treat as illustrative, not definitive
- Cluster standard errors at school level (primary sampling unit)
- Use survey design weights in all regressions
- Report SMDs for balance checks (threshold: >0.10 = imbalance, >0.25 = substantial)
- Cross-cohort design requires explicit attrition/selection discussion

---

## Notation Conventions

| Symbol | Meaning | Anti-pattern |
|--------|---------|-------------|
| $Y_{irt}$ | Test score for student $i$ in region $r$ at time $t$ | Don't drop region subscript |
| $\beta_1$ | Cross-cohort difference (main estimand) | Call it ATT — it's not causal without stronger assumption |
| $\alpha_r$ | Region fixed effects | |
| May2021$_t$ | Indicator = 1 for 2021 wave | |
| $\mathbf{X}_{irt}$ | Controls: age, gender, rural, school type, books, SES | |

---

## Seminal References (already in paper)

| Reference | Role |
|-----------|------|
| Betthäuser et al. (2023, *Nature Human Behaviour*) | Meta-analysis: avg loss 0.14 SD, 42 studies, 15 countries |
| Patrinos et al. (2022, World Bank) | 0.17 SD mean shortfall; 36 evaluations |
| Dela Cruz et al. (2024, ADB) | 1.1 years loss per year closure; developing countries |
| Hill et al. (2008, *Child Dev Perspectives*) | Learning growth benchmarks for SD-to-school-year conversion |
| Lichand et al. (2022, *Nature Human Behaviour*) | Secondary education, Brazil — closest comparable |
| Singh, Romero, Muralidharan (2024) | Panel evidence, India |
| Hevia et al. (2022) | Mexico, cross-section |
| Ardington et al. (2021) | South Africa, early grade reading |

---

## Sections Still Needed

| Section | Status | Key Content Required |
|---------|--------|---------------------|
| Robustness | Missing | Reweighting/IPW for SES shift; bounding exercises for differential attrition; alternative control sets |
| Heterogeneity | Missing | By remote learning duration (Table 2 categories); by rural/urban; by SES tertile; by gender |
| Discussion/Conclusion | Missing | Situate 0.09 SD in global benchmarks; policy implications; limitations; war caveat |

---

## Field-Specific Referee Concerns

- "Cross-cohort ≠ causal" — must clearly state assumption and its plausibility; not oversell as DiD
- "Differential attrition" — SES shift (SMD=0.34) is substantial; requires serious robustness analysis
- "Why not use school-level panel?" — need to explain why cross-section is the only feasible design with this data
- "School closures policy vs. realized exposure" — paper has teacher-reported remote duration; use it for heterogeneity
- "War context" — 2022 invasion changes things; be clear the 2021 data precedes full-scale invasion
- "Ukraine PISA 2018 baseline" — already mentioned; good to acknowledge pre-existing deficits vs. pandemic losses
- "Learning growth benchmarks not Ukraine-specific" — already acknowledged; maintain this caveat
