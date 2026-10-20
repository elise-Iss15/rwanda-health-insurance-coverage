# Data availability and access

This project uses microdata that cannot be redistributed, so the raw data is not in this repository or in the shared Drive folder.

## 1. Dataset

| Item | Detail |
|---|---|
| Name | Integrated Household Living Conditions Survey (EICV7), 2023-2024, Cross-Sectional Sample |
| Producer | National Institute of Statistics of Rwanda (NISR), National Data Archive |
| Catalog page | https://microdata.statistics.gov.rw/index.php/catalog/119 |
| Download page | https://microdata.statistics.gov.rw/index.php/catalog/119/get_microdata |
| Citation | https://statistics.gov.rw/data-sources/surveys/EICV/integrated-household-living-conditions-survey-7-eicv-7 |

## 2. Why the raw data is not included

NISR's terms say data from the National Data Archive may not be redistributed or sold to other people, institutions, or organizations without the Archive's written agreement. To follow that, I share code, trained models, and aggregated results only. I do not include any row-level data, or any cleaned or feature-engineered copy of it.

## 3. How to obtain the data

1. Go to the catalog page above and click Register or Login.
2. Open the Get Microdata page.
3. Fill in the short project description, read and accept the terms, and submit.
4. Download two files:
   - the person-level file, which has the section 3 health variables
   - the poverty file, which has household consumption quintile and poverty category
5. Put both files in a folder named `data/` next to the notebook. It is listed in `.gitignore`, so it must never be committed.

## 4. Check you have the right files

The counts below come from the NISR catalog. The notebook prints the same numbers so you can compare.

| Check | Expected |
|---|---|
| Person file rows | 62,110 |
| Poverty file households | 15,054 |
| `s3q3` (insurance type): valid / missing | 53,149 / 8,961 |
| `s3q4` (reported illness in last 4 weeks): yes | 16,801 |
| `s3q5a` (reason for not consulting): valid answers | 4,826 |

If your counts differ, you may have a different EICV7 sample (for example the VUP sample) or a different version.

## 5. Reproducing the results

1. Install dependencies: `pip install -r requirements.txt`
2. Set `PERSON_PATH` and `POVERTY_PATH` in the first cells of the notebook.
3. Run the notebook top to bottom. The setup cell sets `SEED = 42`.
4. Train/test splits are grouped by household (`hhid`), so no household appears in both sets.

## 6. What the Drive folder contains

Included:
- Saved best traditional ML model: [file name]
- Saved best deep learning model: [file name]
- Notebook and README files
- Aggregated outputs only (metric tables, plots)

Not included:
- The raw dataset, or any row-level or derived row-level copy of it

## 7. Terms followed

- Data used for statistical and scientific research only
- Results reported in aggregate, with no attempt to identify respondents
- Person and poverty files from the same survey merged by household ID only, to add household welfare indicators
- NISR cited as the data source
- A copy of the final report will be sent to the National Data Archive


