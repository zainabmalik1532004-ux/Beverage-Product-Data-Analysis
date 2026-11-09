# Beverage-Product-Data-Analysis
Python analysis of nutritional properties of beverages sold in Germany, using open data from Open Food Facts. Includes automated data quality checks and a structured test report.

## Objective

- Compare sugar, energy, fat and salt content across beverage types (sodas, juices, energy drinks, waters, teas)
- Compare regular vs. "zero/light" products
- Check data quality before analysis (missing, impossible and duplicate values)

## Data Source

- **Open Food Facts** – open food product database: https://world.openfoodfacts.org
- Filter: category `beverages`, country `Germany`
- Fields: product name, brand, category, sugars_100g, energy-kcal_100g, fat_100g, salt_100g, nutriscore_grade
- Licence: Open Database License (ODbL)

## Data Quality Checks

| Check | Rule | Action |
|---|---|---|
| Missing values | Sugar or energy is empty | Excluded |
| Impossible values | Sugar > 100 g per 100 g | Excluded |
| Duplicates | Same product code twice | Excluded |

Every rule is covered by automated tests (`pytest`).

## Results

| Beverage type | Products | Avg. sugar (g/100 ml) | Avg. energy (kcal/100 ml) |
|---|---|---|---|
| Sodas | – | – | – |
| Juices | – | – | – |
| Energy drinks | – | – | – |
| Waters | – | – | – |
| Teas | – | – | – |

**Key findings:**
- *(add 3 short findings after running the analysis)*

Full details: [`report/test_report.pdf`](report/test_report.pdf)

## Repository Structure

beverage-data-analysis/
├── data/
│ └── beverages_clean.csv # cleaned dataset
├── src/
│ ├── fetch_data.py # downloads data from Open Food Facts
│ ├── validation.py # data quality rules
│ └── analysis.py # statistics and charts
├── tests/
│ └── test_validation.py # pytest tests for quality rules
├── charts/ # generated charts (PNG)
├── report/
│ └── test_report.pdf # structured test report
├── requirements.txt
└── README.md


## How to Run

```bash
git clone https://github.com/zainabmalik1532004-ux/beverage-data-analysis.git
cd beverage-data-analysis
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt

python src/fetch_data.py        # 1. download data
python src/analysis.py          # 2. validate, analyse, create charts
pytest -v                       # 3. run quality tests
```

## Tech Stack

Python 3.11 · pandas · matplotlib · requests · pytest

## Note

Educational portfolio project. Nutritional values come from a crowd-sourced database and may contain errors; the data quality checks reduce but do not fully remove them.

## Author

Zainab Malik – Health Informatics, Deggendorf Institute of Technology – November 2026

requirements.txt:

pandas
matplotlib
requests
pytest
