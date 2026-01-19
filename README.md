# faers-adverse-event-dashboard
Post-market pharmacovigilance dashboard analyzing FDA FAERS adverse event reports for GLP-1 agonists.


# FDA Adverse Event Signal Detection Dashboard 🏥

## Executive Summary
This project analyzes **Post-Market Drug Safety surveillance data** from the FDA Adverse Event Reporting System (FAERS). By visualizing adverse drug reactions (ADRs) for [Insert Drug Class, e.g., GLP-1 Agonists], this dashboard aids pharmacovigilance teams in identifying safety signals, demographic trends, and outcome severity distribution.

## Business Value
* **Regulatory Compliance:** Accelerates signal detection for safety updates.
* **Risk Management:** Identifies high-risk patient demographics (e.g., elderly vs. pediatric).
* **Commercial Intelligence:** Tracks adverse event reporting volume against market competitors.

## Technical Approach
1.  **Data Ingestion:** Processed raw ASCII/XML files from FDA FAERS using **Python (Pandas)**.
2.  **Data Cleaning:** Mapped MedDRA terms and standardized drug names using fuzzy matching.
3.  **Visualization:** Built an interactive dashboard in **PowerBI** to filter by:
    * Serious vs. Non-Serious Outcomes
    * Age & Sex Distribution
    * Top 10 Reported PTs (Preferred Terms)

## Tech Stack
* **Language:** Python 3.9
* **Libraries:** Pandas, NumPy
* **Visualization:** Tableau Public / Power BI
* **Domain:** Pharmacovigilance, MedDRA Coding

## Key Insights
* *Example:* "Gastrointestinal disorders accounted for 60% of reports for Drug X, with a spike in hospitalization rates among patients >65 years."
* *Example:* "Signal detected for [Side Effect] which is currently not listed in the black box warning."

## How to Run
1.  Clone the repo.
2.  Run `data_cleaning.py` to process the raw FDA files.
3.  Open `Dashboard.twbx` to view the visualizations.
