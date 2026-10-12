# CMS Nursing-Home Fire-Safety Citations Analysis

This repository contains a CRISP-DM-style analysis of CMS nursing-home fire-safety citations and a simple blog page that presents the findings with visible local visuals.

## Motivation

Fire-safety failures in nursing homes can threaten residents who may have limited mobility or need assisted evacuation. This project examines where citations are concentrated, which deficiency categories recur most often, and whether a model can help prioritize follow-up for rare high-severity cases.

## Blog requirements covered

`index.html` contains a title, a local thumbnail immediately after the title, and three numbered questions. Each question includes four visible sections: **Hypothesis**, **Answer**, **Visual evidence**, and **Conclusion**. The visual evidence uses committed SVG charts plus accessible HTML tables, so the visuals render without external image dependencies.

## Questions, hypotheses, and results

1. **Which states see the highest volumes of fire-safety citations?**
   - **Hypothesis:** Larger nursing-home systems will produce the highest citation volumes.
   - **Evidence:** The local Q1 chart and table show California above 23,600 citations and Ohio above 16,300; Texas, New York, and Pennsylvania appear in the notebook's top-15 group.
   - **Conclusion:** Supported by the notebook ranking.

2. **What are the most common safety issues?**
   - **Hypothesis:** Smoke-related deficiencies are the dominant issue.
   - **Evidence:** The local Q2 chart and table show Smoke Deficiencies above 78,000 citations, approximately 39% of the 200,188 records, ahead of other categories.
   - **Conclusion:** Supported.

3. **Can high-severity citations be predicted?**
   - **Hypothesis:** A model can support screening, but class imbalance limits certainty.
   - **Evidence:** The local Q3 chart and table show 99.8951% low-to-moderate versus 0.1049% high severity, 97.8595% accuracy, 45% high-severity recall, and a scenario probability of 84.78% low-to-moderate versus 15.22% high severity.
   - **Conclusion:** Partially supported for triage; not evidence of causality.

## Libraries and installation

The notebook uses `pandas`, `numpy`, `matplotlib`, `seaborn`, and `scikit-learn`.

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## Running the project

1. Open `data_science3.ipynb` and run it from top to bottom. Internet access is needed for the CMS CSV URL.
2. Open `index.html` directly or deploy the repository with GitHub Pages.

## Repository files

- `index.html` — Blog post with the title image, three questions, hypotheses, answers, local visuals, tables, and conclusions.
- `styles.css` — Responsive styling for the blog, local charts, bars, tables, captions, and mobile layout.
- `data_science3.ipynb` — CRISP-DM analysis notebook, EDA, feature engineering, model, and scenario output.
- `assets/fire-safety-thumbnail.svg` — Original local project thumbnail illustration; no external hotlink required.
- `assets/q1-state-visual.svg` — Local state citation-volume visual.
- `assets/q2-category-visual.svg` — Local deficiency-category visual.
- `assets/q3-model-visual.svg` — Local severity/model visual.
- `assets/state-citations-top15.png`, `assets/deficiency-categories-top10.png`, `assets/severity-distribution.png` — Optional notebook-exported backup charts.
- `README.md` — Project documentation.

## Data source and acknowledgements

- CMS Nursing Home Fire Safety Citations dataset: https://data.cms.gov/provider-data/sites/default/files/resources/98aa3596a9af76e285beb7aa7c7244d9_1790792146/NH_FireSafetyCitations_Sep2026_2.csv
- The local thumbnail and SVG visuals are original project assets created for this repository. The analysis uses CMS data and standard open-source Python libraries.

This project is educational and does not replace official regulatory inspection, legal compliance review, or professional fire-safety advice.

## Model caveats

The high-severity class is extremely rare, so accuracy alone can be misleading. Recall/sensitivity, precision, confusion-matrix behavior, and validation on new data should be reviewed before any operational use.
