# NurseSleep AI

**Reproducible analysis of sleep, shift-work patterns, and cognitive-performance indicators, with an exploratory nursing subgroup analysis.**

NurseSleep AI is a focused data-science project built around the Sleep Health & Daily Performance Dataset. It provides a reproducible workflow for data validation, exploratory analysis, occupational comparisons, baseline predictive modelling, and model interpretation.

> **Data limitation:** The source dataset is described as synthetic. Results therefore describe patterns in this dataset only; they are not evidence about real nurses, patients, or clinical outcomes.

## Research questions

1. How do sleep duration, sleep quality, and stress vary across the occupations represented in the dataset?
2. What patterns are visible in records labelled `Nurse`?
3. How do shift-work and non-shift-work records compare on selected sleep and performance variables?
4. How well can baseline models predict the dataset's `felt_rested` label?
5. How well can a baseline model estimate `cognitive_performance_score`?

These are exploratory questions. Group differences are descriptive and do not establish causation.

## Dataset

- **Name:** Sleep Health & Daily Performance Dataset
- **Source:** [CSV source](https://raw.githubusercontent.com/mohan13krishna/Sleep-Health-Daily-Performance-Dataset/main/sleep_health_dataset.csv)
- **Credit:** Mohan Krishna Thalla
- **Use:** Downloaded at runtime by the notebook or helper script; the dataset is not bundled in this repository.

The source has been described as synthetic. Verify the dataset's current licence and attribution terms at its original source before reuse or redistribution. Do not infer that the dataset is a real-world nursing cohort.

## Quick start

Python 3.10+ is recommended.

```bash
git clone https://github.com/CareerCore/nursesleep-ai.git
cd nursesleep-ai

python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

pip install -r requirements.txt
pip install -e .
python -m nursesleep_ai.download_data
```

Run notebooks from the repository root:

```bash
jupyter lab
```

Open the notebooks in numerical order.

## Workflow

| Notebook | Purpose |
|---|---|
| `01_data_audit_and_eda.ipynb` | Load, validate, summarise, and visualise the dataset |
| `02_nursing_and_shift_work.ipynb` | Explore occupation, nursing-labelled records, and shift work |
| `03_baseline_models.ipynb` | Train and evaluate baseline classification and regression models |

## Repository layout

```text
nursesleep-ai/
├── README.md
├── LICENSE
├── .gitignore
├── requirements.txt
├── pyproject.toml
├── data/
│   └── README.md
├── docs/
│   ├── methodology.md
│   └── limitations.md
├── notebooks/
│   ├── 01_data_audit_and_eda.ipynb
│   ├── 02_nursing_and_shift_work.ipynb
│   └── 03_baseline_models.ipynb
├── src/
│   └── nursesleep_ai/
│       ├── __init__.py
│       ├── config.py
│       ├── download_data.py
│       ├── data.py
│       ├── analysis.py
│       └── modeling.py
└── results/
    ├── figures/
    ├── tables/
    └── metrics/
```

## Methods

- Data validation: dimensions, data types, missingness, duplicate rows, and category counts.
- Exploratory analysis: distributions, descriptive summaries, and group comparisons.
- Classification: a scikit-learn preprocessing pipeline and Random Forest baseline for `felt_rested`.
- Regression: a preprocessing pipeline and Random Forest baseline for `cognitive_performance_score`.
- Evaluation: held-out test metrics; no performance values are claimed in advance.

The modelling code excludes identifiers and all designated outcome columns from predictors by default. Review the feature set and the meaning/timing of each variable before interpreting a model. If records are repeated for the same individual, use a person-level grouped split rather than a random row split.

## Reproducibility

- Fixed random seeds are used for baseline splits and models.
- Data is downloaded from the source URL at runtime.
- Generated tables, figures, and metrics are saved under `results/`.
- No result is hard-coded. Run the notebooks to generate project outputs.

## Responsible use

This repository is an educational and exploratory data-science project. It is **not** a clinical decision-support system, diagnostic tool, fitness-for-duty assessment, or employment-screening tool. Synthetic data cannot establish clinical validity or representativeness. Any future real-world research would require appropriate data governance, ethics review, privacy protection, and independent validation.

## Licence and attribution

The original code in this repository is released under the MIT License. This does not change the licence or terms governing the external dataset. See `data/README.md` and the dataset source for dataset-specific terms.

Dataset credit: **Mohan Krishna Thalla, Sleep Health & Daily Performance Dataset**.

## Project status

**Status: Initial reproducible workflow.** Results should be added only after running the notebooks and checking the outputs.

