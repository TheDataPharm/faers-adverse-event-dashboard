# GLP-1 Safety Signal Dashboard 🏥
**Analyzing 200,000+ FDA Adverse Event Reports for GLP-1 Agonists**

### 📺 **[Watch the 90-Second Project Demo](https://www.loom.com/share/cd741ea34ee74b01a1d20676bc423d3d)**

> *Note: I investigated if the safety profile of Ozempic, Mounjaro, Wegovy.... changes when prescribed to a generally healthy population (Obesity) versus a diabetic one.*

---

## 📊 Project Overview
With the explosion of GLP-1 agonists like **Ozempic** and **Wegovy**, I built a data pipeline to analyze real-world safety signals from the FDA FAERS database.

**The Business Question:**
Do the high hospitalization rates reported in the media reflect the drug's intrinsic toxicity, or are they driven by the underlying health conditions of the patients taking them?

## 🔎 Key Findings

### 1. The "Safety Gap" (Severity Analysis)
* **Observation:** While the *types* of side effects (Nausea, Vomiting) are identical across both groups, the *severity* differs drastically.
* **Insight:** **Diabetes patients have a 2.3x higher rate of serious outcomes** (Hospitalization/Life-Threatening) compared to Obesity patients (42% vs 18%). This suggests that severe outcomes are driven by patient comorbidities (e.g., cardiovascular disease), not the drug molecule itself.

### 2. Statistical Validation (Reporting Odds Ratio)
* **Hypothesis:** Is the risk of Nausea statistically higher in one group?
* **Result:** Calculated a **Reporting Odds Ratio (ROR) of 0.92** (95% CI: 0.85 - 1.00).
* **Conclusion:** The ROR is close to 1.0, statistically confirming that the *intrinsic risk* of the drug is the same across groups. The disparity in hospitalization is therefore a function of patient health status.

---

## Technical Approach

### 1. Data Engineering (Python)
* **Ingestion:** Processed raw FDA ASCII files (200k+ rows) using Pandas.
* **Cleaning:** Implemented fuzzy matching logic to standardize 30+ variations of drug names (e.g., `Semaglutide Sodium`, `Ozempic (Compounded)`) into clean analytical cohorts.
* **Deduplication:** Applied "Golden Record" logic to remove duplicate reports from multiple sources.

### 2. Visualization (Power BI)
* **Interactive Dashboard:** Built slicers for demographics, outcomes, and report sources.
* **Cohort Analysis:** Created custom DAX measures to compare "Serious %" between Diabetes and Obesity indications.

### 3. Statistics (SciPy)
* **Signal Detection:** Utilized a 2x2 contingency table to calculate Reporting Odds Ratios (ROR) and Confidence Intervals to validate visual trends.

---

## ⚠️ Limitations
* **Webber Effect:** The spike in reports in 2023-2024 is likely correlated with increased media attention (reporting bias).
* **No Denominator:** As FAERS is a spontaneous reporting system, we cannot calculate true incidence rates, only reporting odds.
* **Duplicate Bias:** While deduplication logic was applied, some anonymous duplicate reports may remain.

---
