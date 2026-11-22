# NurseSleep AI

**Reproducible analysis of sleep, shift-work patterns, and cognitive-performance indicators, with an exploratory nursing subgroup analysis.**

NurseSleep AI is a data-science project focused on data validation, exploratory analysis, occupational comparisons, shift-work patterns, baseline predictive modelling, and model evaluation.

> **Data limitation:** Findings are exploratory and describe patterns in the data used for this project. They should not be interpreted as evidence about real nurses, patients, or clinical outcomes.

## Research Questions

1. How do sleep duration, sleep quality, and stress vary across occupational groups?
2. What patterns are visible in records labelled `Nurse`?
3. How do shift-work and non-shift-work records compare on selected sleep and performance variables?
4. How well can baseline models predict the `felt_rested` label?
5. How well can a baseline model estimate `cognitive_performance_score`?

These questions are exploratory. Group differences are descriptive and do not establish causation.

## Project Workflow

| Notebook | Purpose |
|---|---|
| `01_data_audit_and_eda.ipynb` | Data audit and exploratory analysis |
| `02-group shift and analysis` | Group and shift-work analysis |
| `3-baseline models` | Baseline model development and evaluation |

## Repository Structure

```text
nursesleep-ai/
├── 01_data_audit_and_eda.ipynb
├── 02-group shift and analysis
├── 3-baseline models
├── LICENSE
├── .gitignore
├── README.md
└── results/
    ├── figures/
    │   └── felt_rested_metrics_bar.png
    ├── metrics/
    │   └── felt_rested_random_forest (1).csv
    └── tables/
        └── model_performance_summary (1).csv
```

## Model Results

### Random Forest Classifier

**Prediction target:** `felt_rested`

| Evaluation Metric | Score |
|---|---:|
| Accuracy | 0.73885 |
| Precision | 0.735263 |
| Recall | 0.73885 |
| F1 Score | 0.735472 |

### Performance Visualization

![Random Forest Performance](results/figures/felt_rested_metrics_bar.png)

### Results Files

- [Model evaluation metrics](results/metrics/)
- [Performance summary table](results/tables/)
- [Performance figure](results/figures/)

## Methods

- Data validation and quality checks.
- Exploratory data analysis and descriptive summaries.
- Occupational and shift-work comparisons.
- Random Forest classification for `felt_rested`.
- Evaluation using accuracy, precision, recall, and F1 score.

Further validation is required before interpreting model performance or applying findings beyond this dataset.

## Reproducibility

The analysis notebooks are provided in this repository. Raw dataset files are not included. An authorised input file is required to reproduce the analysis.

## Responsible Use

This project is intended for educational and exploratory data-science purposes. It is not a clinical decision-support system, diagnostic tool, fitness-for-duty assessment, or employment-screening tool.

Results should not be used to make medical or employment decisions.

## Licence

See the `LICENSE` file for licensing information.

---

**NurseSleep AI — Data Analysis and Machine Learning Project**
