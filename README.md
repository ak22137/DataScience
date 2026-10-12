# CMS Nursing-Home Fire-Safety Citations Analysis

This repository contains a CRISP-DM style analysis of CMS nursing-home fire-safety citations and a companion blog page that summarizes the key findings from `data_science3.ipynb`.

## Motivation

Fire-safety failures in nursing homes can directly threaten residents who may have limited mobility and need assisted evacuation. That makes proactive detection of severe citation patterns especially important: waiting until only the worst events occur is too late for prevention. This project was chosen to explore whether historical citation data can highlight where enforcement pressure is highest, which deficiency types recur most often, and how a basic model can help prioritize follow-up when severe outcomes are rare but high impact.

## Questions of Interest and Notebook-Supported Results

1. **Which states see the highest volumes of fire-safety citations?**  
   Notebook state-volume charts show the highest counts in states including **California** and **Ohio**.

2. **What are the most common deficiency categories?**  
   The deficiency-category chart shows **Smoke Deficiencies** as the leading category, followed by categories such as gas/vacuum/electrical and related systems.

3. **Can high-severity citations be predicted from early features?**  
   The Random Forest pipeline reports **97.86% accuracy** and **45% recall** for the high-severity class, while the class itself is rare (~0.1%), so accuracy alone is insufficient.  
   For the notebook scenario (`CA`, `Smoke Deficiencies`, `Inspection Cycle=2`, `ResolutionDays=20`), the model outputs **84.78% low-to-moderate** vs **15.22% high-severity** probability.

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
- `styles.css` — Responsive/accessibility-focused styling for the blog layout, image thumbnail, figures, tables, and callouts.
- `data_science3.ipynb` — Full analysis notebook (data understanding, EDA, feature engineering, modeling, and scenario inference).
- `README.md` — Project documentation and reproducibility notes.
- `assets/state-citations-top15.png` — State citation-volume chart extracted from notebook output.
- `assets/deficiency-categories-top10.png` — Deficiency category chart extracted from notebook output.
- `assets/severity-distribution.png` — Severity distribution chart extracted from notebook output.

## Data Source and Acknowledgements

- **CMS dataset**: Nursing Home Fire Safety Citations CSV  
  https://data.cms.gov/provider-data/sites/default/files/resources/98aa3596a9af76e285beb7aa7c7244d9_1790792146/NH_FireSafetyCitations_Sep2026_2.csv
- **Hero image attribution**: Pixabay, “Fire alarm smoke detector”  
  https://pixabay.com/photos/fire-alarm-smoke-detector-502893/  
  License: Pixabay Content License

This analysis is for educational exploration and does **not** replace official regulatory review, inspection, or legal compliance assessment.

## Model Caveats

- The target class (high severity) is strongly imbalanced (~0.1% positive cases).
- In this setting, a high overall accuracy can still hide missed severe cases.
- Recall/sensitivity for the minority class should be monitored alongside precision and confusion-matrix behavior before operational use.

## Quick Links

- Notebook: `data_science3.ipynb`
- CMS data source: link above