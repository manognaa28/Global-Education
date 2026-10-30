# Global Education Dashboard

An interactive Power BI dashboard that analyses female secondary education
completion across countries, and how it relates to birth rate and
unemployment.

<img width="1327" height="721" alt="Dasboard 1" src="https://github.com/user-attachments/assets/7cf4a56f-869c-474d-bba4-162401cc7e0e" />


## Project overview
Girls' access to secondary education varies widely between countries. This
dashboard helps answer where completion is lowest, where girls drop out
between lower and upper secondary school, and whether completion is linked
to demographic and economic factors such as birth rate and unemployment.

## Key questions
- Which countries have the lowest female lower secondary completion?
- How large is the drop-off from lower to upper secondary completion?
- Is a higher birth rate associated with lower upper secondary completion?
- How do out-of-school rates compare between females and males?

## Dashboard features
- **4 KPI cards:** average lower secondary completion (female), average upper
  secondary completion (female), average birth rate and average unemployment
  rate.
- **Bar chart:** the 10 countries with the lowest female lower secondary
  completion (Bottom N filter, sorted ascending).
- **Scatter plot:** birth rate vs. upper secondary completion for every
  country, with a trend line to show the relationship.
- **Clustered bar chart:** lower vs. upper secondary completion side by side,
  showing where girls drop out.
- **Treemap:** countries compared by size on an enrollment measure.
- **Slicers:** a country dropdown and a birth rate range slider that filter
  the whole page.

## Design choices
- Custom colour theme (navy, teal and orange) applied through the report
  theme so every visual stays consistent.
- A header band, cards with rounded corners, and a grid layout with equal
  spacing.
- Sum aggregations were replaced with **Average**, because summing
  percentages and rates gives misleading numbers.
- Clear, plain-English chart titles instead of default field names.

## Data
Source: Global Education Statistics (World Bank / UNESCO), file included.

Note: some countries show 0 for completion and OOSR fields. These are
treated as missing values rather than real zeros, so they are excluded
from the analysis using a "greater than 0" filter.

**Main fields used**

| Field | Meaning |
|---|---|
| Countries and areas | Country name |
| Latitude / Longitude | Country coordinates |
| Completion_Rate_Lower_Secondary_Female | Share of girls completing lower secondary |
| Completion_Rate_Upper_Secondary_Female | Share of girls completing upper secondary |
| Birth_Rate | Birth rate for the country |
| Unemployment_Rate | Unemployment rate for the country |
| OOSR_* | Out-of-school rates by education level, split by gender |
| Gross_Tertiary_Education_Enrollment | Tertiary enrollment ratio |

## Data cleaning and limitations
- Zeros in completion and out-of-school fields were treated as missing data
  and filtered out, so averages are not pulled down by absent records.
- Without the filter, the average completion rates are much lower
  (around 33% and 23%), because many countries have no recorded value.
- The data is a single snapshot per country with no year column, so the
  dashboard shows differences between countries, not trends over time.
- The scatter plot shows association, not causation.

## How to open the dashboard
1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free,
   Windows only).
2. Download `GlobalEducation.pbit` from this repository.
3. Open it in Power BI Desktop. The data is embedded, so no setup is needed.

For a `.pbi` template , Power BI asks for the data source.
Point it to `global_education_data.csv`.

## Repository contents
| File | Description |
|---|---|
| `GlobalEducation.pbix` | The Power BI report with embedded data |
| `global_education_data.csv` | Exported dataset |
| `dashboard-preview.png` | Screenshot of the dashboard |
| `README.md` | Project documentation |

## Tools
Power BI Desktop, Power Query, data modelling, data visualization, Excel

## Author
Manogna Addanki
