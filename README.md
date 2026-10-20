# Who is still uncovered by health insurance in Rwanda?

Comparing traditional machine learning and deep learning on the EICV7 2023-24 household survey.

## Links
- **Video presentation:** https://youtu.be/xy3TloS9p6U
- **Google Drive folder (saved models, notebook, documentation):** [add link]

## Overview

About 85% of people in Rwanda have health insurance, yet 14.4% of people in the analysis sample are uncovered. This project predicts who is uncovered from household survey variables, compares traditional models (logistic regression, random forest, gradient boosting) with two neural networks, and checks where the models fail. Models are selected by validation PR-AUC, and the decision threshold is set on validation to reach 90% sensitivity.

## Key results (test set)

| Model | Sensitivity | Precision | ROC-AUC | PR-AUC |
|---|---|---|---|---|
| Gradient boosting (E5b) | 0.853 | 0.201 | 0.751 | 0.353 |
| Neural network | [ ] | [ ] | [ ] |

## Repository contents

| File or folder | What it is |
|---|---|
| `rwanda_insurance_simplified.ipynb` | The full pipeline, run top to bottom with outputs |
| `README_DATA.md` | Data source, terms, and how to obtain the data |
| `requirements.txt` | Python dependencies |
| `outputs/` | Aggregated results and plots only (no survey rows) |
| `logs/` | TensorBoard logs behind the experiment table |

## How to reproduce

1. Obtain the two EICV7 files by following `README_DATA.md`. Do not commit them.
2. Put them in a `data/` folder, or edit `PERSON_PATH` and `POVERTY_PATH` in the notebook.
3. Install dependencies: `pip install -r requirements.txt`
4. Open the notebook and run all cells top to bottom. The random seed is 42.

## Data availability

The raw data comes from the National Institute of Statistics of Rwanda (NISR). NISR's terms forbid redistribution, so it is not included here. See `README_DATA.md`.

## Citation

NISR data citation:https://statistics.gov.rw/data-sources/surveys/EICV/integrated-household-living-conditions-survey-7-eicv-7.

## Author

Elyse Ishimwe, e.ishimwe3@alustudent.com
