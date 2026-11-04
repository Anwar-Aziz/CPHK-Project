# Maternal and Neonatal Health in Pemba, Zanzibar

**Frequency, Socio-Demographic and Host Characteristics, and Access to Care via Geo-Spatial Analysis of Maternal Morbidity, Mortality, and Neonatal Death in Four Districts of Pemba**

## Overview

This report presents a comprehensive retrospective analysis of maternal morbidity, maternal mortality, stillbirths, and neonatal deaths across four districts of Pemba Island, Zanzibar. Using the AMANHI cohort database of **4,501 pregnancies (2014–2018)**, the study examines socio-demographic factors (maternal age, education), host characteristics (maternal weight, health conditions), and access-to-care indicators through geospatial analysis.

## Summary of Key Findings

- **Maternal mortality:** Effectively absent in the dataset (0 maternal deaths recorded).
- **Maternal complications:** Hypertensive disorders (2.5%), prolonged labor (2.1%), antepartum hemorrhage (3.9%).
- **Stillbirths:** 106 recorded — approximately **2.4% of all births** (~24 per 1,000 births).
- **Neonatal mortality:** 78 neonatal deaths among 4,395 live births — **1.77%** (~17.7 per 1,000 live births).

Adverse outcomes disproportionately affected older and obese mothers, preterm infants, and those living farther from health facilities.

## Methods

### Study Design and Data Sources

Retrospective analysis of pregnancy outcomes in four Pemba districts. Data compiled and cleaned from the **AMANHI cohort database**, covering 4,501 pregnancies (2014–2018). Key variables:
- Maternal socio-demographics (age, education)
- Clinical history and complications (hypertension in pregnancy, prolonged labor, antepartum hemorrhage)
- Birth outcomes (live birth vs. stillbirth)
- Neonatal survival status
- Geospatial coordinates of maternal residences and health facilities

### Data Processing and Analysis

- **Cleaning:** Invalid/placeholder values (e.g., −88) replaced with NA; mean/mode imputation applied where appropriate.
- **Categorization:**
  - Maternal age: Under 20, 20–25, 26–30, 31–35, Over 35
  - Education: Primary, Secondary, Advanced Level, Higher Education
  - Gestational age: Preterm (<37 wks), Term (37–42 wks), Post-term (>42 wks)
  - Maternal weight: Underweight, Normal, Overweight, Obese (BMI-related cutoffs)
- **Statistics:** Descriptive frequencies; neonatal mortality rate (NMR) per 1,000 live births.
- **Spatial analysis:** Village coordinates mapped to estimate each mother's distance to the nearest facility; association with adverse outcomes examined.
- **Bivariate analyses:** Outcomes tabulated by age, education, gestational age, and weight group; chi-square tests for significance.
- **Modeling:** Correlation matrices and logistic regression (odds ratios, accuracy, AUC) for neonatal death predictors — primarily descriptive given low event rates.
- **Tools:** Python (pandas, seaborn/matplotlib, scikit-learn), GIS tools, LaTeX for reporting.

## Findings Part I: Maternal Morbidity and Mortality

### Frequency of Complications and Outcomes

| Outcome | Count | Rate |
|---|---|---|
| Maternal deaths | 0 | 0 per 100,000 live births |
| Hypertensive disorders | 111 | 2.5% |
| Prolonged labor (>24 hrs) | 93 | 2.1% |
| Antepartum hemorrhage (APH) | 176 | 3.9% |
| Stillbirths | 106 | 2.4% (~24 per 1,000 births) |

Areas farther from health facilities tended to show slightly higher incidences of complications and stillbirths.

### Maternal Characteristics and Adverse Outcomes

**Maternal Age**
- Oldest group (Over 35): 4.2% hypertensive complications (vs. 0.7% for under-20); 4.3% APH (vs. 2.7%); stillbirth rate 3.1% (~double the ~1.8% of mid-20s mothers).
- Teenagers (Under 20): highest prolonged labor incidence (3.4% vs. ~2% other groups).

**Education**
- No strong or linear correlation with adverse outcomes.
- Hypertension: ~2.3% primary vs. ~2.5% secondary educated.
- Stillbirth: ~2.4% primary vs. ~2.2% secondary.
- Advanced/higher education groups too small for firm conclusions.
- Lower education groups had wider age ranges, including more teenage and older mothers (higher-risk profiles).

**Gestational Age**
- Preterm (<37 weeks): 524 births; 13.4% APH; 60 stillbirths (~11.5% stillbirth rate); 4.0% hypertension.
- Term (37–42 weeks): stillbirth ~1%; APH 2.7%.
- Post-term (>42 weeks): 124 cases; lowest complication rates; virtually no prolonged labors (likely active management).

**Maternal Weight**
- Hypertension: 5.0% overweight, 6.3% obese vs. 1.7% underweight, 1.9% normal.
- APH: highest in obese women (4.2%).
- Stillbirth: 3.6% overweight, 4.9% obese vs. ~2% underweight/normal.

### Access to Care (Geospatial Findings)

- Mothers with stillbirth or life-threatening complications lived on average **8 km** from the nearest emergency obstetric care facility, vs. **5 km** for those without such outcomes (not statistically significant due to wide variability).
- Clusters of adverse outcomes observed in remote regions — particularly parts of **Micheweni** and southern **Mkoani**.
- Travel time can far exceed geographic distance due to road infrastructure — remote villages face delays in obstetric emergencies.

## Findings Part II: Neonatal Deaths

### Overall Neonatal Mortality and Timing

- 78 deaths among 4,395 live births — **NMR 17.7 per 1,000 live births (1.77%)**.
- Most deaths occurred on day 0 or within the first week, suggesting birth asphyxia, extreme prematurity, or infections as major contributors.

### Neonatal Mortality by Maternal Factors

**Maternal Age**

| Age Group | Neonatal Deaths | Survived | Approx. Rate |
|---|---|---|---|
| Under 20 | 4 | 282 | 1.4% |
| 20–25 | 17 | 1,136 | ~1.5% |
| 26–30 | 21 | 1,211 | ~1.7% |
| 31–35 | 17 | 868 | ~1.9% |
| Over 35 | 19 | 820 | 2.3% |
| **Total** | **78** | **4,317** | |

Slight increase with maternal age; median ages of mothers of deceased vs. surviving neonates were similar — age alone is not a strong discriminator.

**Maternal Education**

| Education Level | Neonatal Deaths | Survived |
|---|---|---|
| Primary | 33 | 2,015 |
| Secondary | 42 | 2,228 |
| Advanced Level | 3 | 49 |
| Higher Education | 0 | 25 |
| **Total** | **78** | **4,317** |

Primary vs. secondary NMR close (1.6% vs. 1.8%). Advanced group small (5.8% loss); higher education group had zero neonatal deaths — suggestive but not conclusive.

### Neonatal Mortality by Newborn Factors

**Gestational Age**
- Preterm birth: the single most important predictor — nearly half of all neonatal deaths were preterm babies.
- Babies born preterm had an estimated NMR of ~6–8%, several times greater than term/post-term (<1%).
- Deaths heavily skewed toward extremely preterm (<32 weeks).

**Birth Weight**
- Mean birth weight: ~2.8 kg (deceased) vs. ~3.3 kg (survivors) — statistically significant.
- Low birth weight (<2.5 kg) overrepresented among deaths; virtually all babies over 3.5 kg survived.
- Some near-normal-weight deaths suggest intrapartum complications or congenital issues.

**Mode of Delivery**
- Vast majority vaginal; C-section numbers too low for definitive comparison.
- NMR among C-sections not significantly different; mode of delivery did not emerge as an independent risk factor once underlying conditions were accounted for.

### Geospatial Patterns in Neonatal Mortality

- Deaths not uniformly distributed; areas with higher stillbirth rates also showed higher neonatal death rates.
- Geographic disparities in neonatal survival less pronounced than for stillbirths (families seek care for sick newborns even from remote areas).
- Micheweni district had slightly higher NMR (~2.3%) vs. Chake Chake (~1.5%).

## Recommendations

1. **Strengthen Antenatal Care for High-Risk Pregnancies** — enhance screening/management of hypertensive disorders; regular BP monitoring, urinalysis, prompt referral — especially for older and obese mothers.
2. **Improve Nutrition and Weight Management** — community nutrition programs for women of reproductive age; healthy prepregnancy BMI and adequate pregnancy weight gain.
3. **Emergency Obstetric and Newborn Care Access** — expand/upgrade facilities in remote districts; strategically located maternity waiting homes and basic emergency obstetric care centers.
4. **Transport and Referral Systems** — reliable ambulance services and communication networks for rapid transfer of mothers with complications and newborns needing specialized care.
5. **Neonatal Care Interventions** — strengthen NICU capabilities (resuscitation, incubators/warming devices, CPAP); train workers in essential newborn care and kangaroo mother care.
6. **Community Health Education** — promote early antenatal booking, facility deliveries, prompt postnatal check-ups; engage community health volunteers for postpartum follow-up.
7. **Geospatial Planning** — target high-mortality districts/villages with mobile clinics or outreach; ensure basic maternal and newborn care within a reasonable distance (e.g., 5 km).

## Conclusions

Maternal mortality was notably low in the dataset, reflecting improvements in obstetric care, but maternal morbidity (hypertension, hemorrhage, prolonged labor) remains a concern and contributes directly to stillbirths — at **24 per 1,000 births**, still unacceptably high. The neonatal mortality rate of **17.7 per 1,000 live births** means nearly two in every 100 babies born alive do not survive their first month; many of these deaths are preventable and associated with prematurity and low birth weight.

Socio-demographic patterns suggest maternal age and education have some influence, but **clinical and access factors are more critical**. Older mothers and those with high-risk conditions (often linked with obesity) had poorer outcomes; geospatial analysis revealed that distance and location subtly affect mortality, highlighting health system inequities within the island.

Pemba's maternal and newborn health profile reflects both progress and challenge. Continued efforts to strengthen healthcare infrastructure, ensure equitable access to quality care, and focus on high-risk cases are essential to move closer to the ultimate goals: **zero preventable maternal deaths, zero stillbirths, and every newborn having a healthy start to life.**

