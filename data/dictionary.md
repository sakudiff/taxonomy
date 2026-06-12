# Data Dictionary

## Source
**Philippine Statistics Authority (PSA) — 2021 Census of Establishments**

The data was retrieved from the PSA's annual census of business enterprises operating in the Philippines. It provides a cross-sectional snapshot of the formal economy at the establishment level.

## Files

### `main data set.xlsx`

| Sheet | Description | Rows |
|-------|-------------|------|
| Table 1 | Establishments and Employment by Region (2021 vs 2018) | 24 regions |
| Table 2 | Establishments and Employment by Industry Section × Region (2021) | 27 sections |
| Table 3 | Establishments and Employment by 3-Digit PSIC Industry Group (2021) | 238 industries |
| Table 4 | Establishments by MSME Category and Region (2021) | 142 provinces/regions |
| Table 5 | Establishments by MSME Category and 3-Digit PSIC Industry Group (2021) | 239 industries |
| Table 6 | Newly Listed Establishments by Region and Province (2021) | 144 entries |
| Table 7 | Newly Listed Establishments by MSME and Region (2021) | 28 regions |
| Table 8 | Permanently Closed and Temporarily Stopped Establishments by Region and Province (2021) | 143 entries |
| Table 9 | Closed Establishments by MSME and Industry Section (2021) | 29 entries |

## Key Variables

| Variable | Description | Source Table |
|----------|-------------|-------------|
| `PSIC Code` | 3-digit Philippine Standard Industrial Classification code | Table 3, Table 5 |
| `Industry Group` | Name of the 3-digit PSIC industry | Table 3, Table 5 |
| `Total Establishments` | Count of establishments in operation (2021) | Table 3 |
| `Total Employment` | Sum of all employees across establishments (2021) | Table 3 |
| `Micro` | Establishments with 1–9 employees | Table 5 |
| `Small` | Establishments with 10–99 employees | Table 5 |
| `Medium` | Establishments with 100–199 employees | Table 5 |
| `Large` | Establishments with 200+ employees | Table 5 |
| `Region` | Administrative region of the Philippines | Table 1, Table 2, Table 4 |
| `Province` | Province-level geographic identifier | Table 6, Table 8 |
| `Closures` | Establishments with permanently closed status (2021) | Table 8, Table 9 |
| `Year Closed` | Year of permanent closure | Table 8 |
| `Newly Listed` | Establishments newly registered (2021) | Table 6, Table 7 |

## Engineered Variables (from `main.ipynb`)

| Variable | Description | Formula |
|----------|-------------|---------|
| `avg_firm_size` | Average employees per establishment | Total Employment ÷ Total Establishments |
| `sme_density` | Share of firms in SME range (10–199 employees) | (Small + Medium) ÷ Total Establishments |
| `large_firm_density` | Share of firms with 200+ employees | Large ÷ Total Establishments |
| `micro_density` | Share of firms with 1–9 employees | Micro ÷ Total Establishments |
| `entropy` | Shannon Entropy of firm-size distribution | -Σ(pᵢ × log₂(pᵢ)) across size bins |
| `cluster_label` | K-Means assigned archetype (0–3) | From `main.ipynb` |
| `closure_rate` | Industry closure rate | Closures ÷ Total Establishments |

## License
The PSA data is publicly available from the Philippine Statistics Authority. Users should cite the PSA as the original data source when publishing findings derived from this dataset.
