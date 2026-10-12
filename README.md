# CMS Nursing-Home Fire-Safety Citations Analysis

This repository contains a CRISP-DM style analysis of CMS nursing-home fire-safety citations and a companion blog page that summarizes the key findings from `data_science3.ipynb`.

## Motivation

Fire-safety failures in nursing homes can directly threaten residents who may have limited mobility and need assisted evacuation. That makes proactive detection of severe citation patterns especially important: waiting until only the worst events occur is too late for prevention. This project was chosen to explore whether historical citation data can highlight where enforcement pressure is highest, which deficiency types recur most often, and how a basic model can help prioritize follow-up when severe outcomes are rare but high impact.

## Blog Structure Requirements Covered (`index.html`)

- The page keeps the concise title: **Inside Nursing Home Fire Safety — Finding Patterns in Citations**.
- A large **hero thumbnail image** appears immediately after the `<h1>` title, with visible attribution directly below it.
- Each of the three numbered questions has explicit blocks labeled:
  - **Hypothesis**
  - **Answer**
  - **Visual evidence** (HTML-native table + CSS bar chart, with optional PNG support figure)
  - **Conclusion**

## Questions, Hypotheses, and Evidence Summary

1. **Which states see the highest volumes of fire-safety citations?**  
   - **Hypothesis:** Larger-state systems should contribute the most citations.  
   - **Evidence:** Notebook-backed state section includes a table and bar chart showing **California (>23,600)** and **Ohio (>16,300)** at the top, with **TX/NY/PA** in the upper tier.  
   - **Conclusion:** Hypothesis supported.

2. **What are the most common deficiency categories?**  
   - **Hypothesis:** Smoke-related violations are the most common deficiency type.  
   - **Evidence:** HTML-native table/bar chart plus notebook figure show **Smoke Deficiencies (>78,000; ~39%)** as dominant, with gas/vacuum/electrical and related systems behind it.  
   - **Conclusion:** Hypothesis supported.

3. **Can high-severity citations be predicted from early features?**  
   - **Hypothesis:** A model can provide useful high-severity risk screening, but class imbalance limits certainty.  
   - **Evidence:** Severity-distribution table/bar chart (99.8951% low-to-moderate vs 0.1049% high severity), model metrics (**97.8595% accuracy**, **45% high-severity recall**), and scenario probabilities (**84.78% low-to-moderate**, **15.22% high severity**).  
   - **Conclusion:** Partially supported; useful for triage, not causality claims.

## Libraries Used

The notebook uses:

- `pandas`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `numpy`

Optional install command:

```bash
pip install pandas matplotlib seaborn scikit-learn numpy
```

## Running the Analysis

1. Open and run `data_science3.ipynb` from top to bottom.
2. Ensure internet access is available so the CMS CSV URL can be loaded.
3. Open `index.html` to view the blog summary page.

## Repository File Guide

- `index.html` — Blog-style post with the three questions, answers, notebook-backed visuals, and links to sources.
- `styles.css` — Responsive/accessibility-focused styling for the hero thumbnail, question cards, HTML-native data tables, and CSS bar charts.
- `data_science3.ipynb` — Full analysis notebook (data understanding, EDA, feature engineering, modeling, and scenario inference).
- `README.md` — Project documentation and reproducibility notes.
- `assets/state-citations-top15.png` — Optional supporting state citation-volume chart from notebook output.
- `assets/deficiency-categories-top10.png` — Optional supporting deficiency-category chart from notebook output.
- `assets/severity-distribution.png` — Optional supporting scope-severity chart from notebook output.

## Image/Chart Assets and Attribution

- **CMS dataset**: Nursing Home Fire Safety Citations CSV  
  https://data.cms.gov/provider-data/sites/default/files/resources/98aa3596a9af76e285beb7aa7c7244d9_1790792146/NH_FireSafetyCitations_Sep2026_2.csv
- **Hero thumbnail attribution**: Pixabay, “Fire alarm smoke detector”  
  https://pixabay.com/photos/fire-alarm-smoke-detector-502893/  
  License: Pixabay Content License
- **Notebook PNG chart assets**:
  - `assets/state-citations-top15.png`
  - `assets/deficiency-categories-top10.png`
  - `assets/severity-distribution.png`
  - Source: exported from notebook visualizations in `data_science3.ipynb`

## Data Source and Acknowledgements

This analysis is for educational exploration and does **not** replace official regulatory review, inspection, or legal compliance assessment.

## Model Caveats

- The target class (high severity) is strongly imbalanced (~0.1% positive cases).
- In this setting, a high overall accuracy can still hide missed severe cases.
- Recall/sensitivity for the minority class should be monitored alongside precision and confusion-matrix behavior before operational use.

## Quick Links

- Notebook: `data_science3.ipynb`
- CMS data source: link above