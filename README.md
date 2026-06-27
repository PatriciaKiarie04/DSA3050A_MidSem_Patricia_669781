# DSA3050A_MidSem_Patricia_669781
# DSA3050A Mid-Semester Practical Exam — Business Intelligence & Visualization

**Student Name:** Patricia Kiarie
**Student ID:** 669781
**Course:** DSA3050A — Business Intelligence & Visualization

---

## Dataset Source

**Dataset:** World Bank World Development Indicators
**Source URL:** https://www.kaggle.com/datasets/nicolasgonzalezmunoz/world-bank-world-development-indicators
**Original Provider:** The World Bank (compiled and published on Kaggle)

This dataset compiles macro-economic, social, political, and environmental indicators for 268 countries and regions, covering the years 1960–2023.

## Dataset Size

- **Rows:** ~16,000+ (268 countries/regions × ~63 years)
- **Columns:** 48 indicator columns (after Power Query cleaning, several low-coverage columns were removed — see Transformations below)

## Business Problem

Acting as a Business Intelligence Analyst for an international frontier-markets investment fund, this project analyzes macroeconomic, social, and environmental indicators across countries to support investment-risk assessment. The dashboard helps identify infrastructure gaps, environmental/ESG exposure, and development trends relevant to long-term investment decisions in emerging and developing economies.

---

## Power Query Transformations Performed

### Basic Data Cleaning
- Replaced literal "null" text strings with proper blank/null values across all columns
- Renamed unclear/typo'd columns (e.g. `CO2_emisions` → `CO2_Emisions_kt`, `renewvable_energy_consumption%` → `Renewable_energy_consumption_pct`, `goverment_effectiveness_estimate` → `Goverment_Effectiveness_Estimate`, `central_goverment_debt%` → `Central_Goverment_Debt_pct`)
- Corrected data types (Decimal Number for indicators, Whole Number for population/area fields, Date for the date column)
- Removed duplicate records
- Removed fully blank rows (e.g. incomplete 2023 entries)
- Trimmed and cleaned text in the `country` column
- Replaced inconsistent country/region naming values
- Removed indicator columns with very low data coverage (identified via Column Profiling)

### Intermediate Transformations
- Extracted Year from the `date` column for time-based analysis
- Created a custom column calculating CO2 emissions per capita
- Created a conditional column ("Development_Category": Developed / Developing / Emerging) based on access-to-electricity and economic indicator thresholds
- Filtered rows using multiple conditions (e.g. Year ≥ 2000 and non-null CO2 emissions)
- Sorted data by Country then Year
- Added an Index column

### Advanced Power Query Tasks (5+ completed)
- Merged queries using Country as a common key
- Built a Date table for time-based analysis
- Used Group By with multiple aggregations (average CO2 and indicators by Development Category)
- Applied nested conditional logic to build the multi-tier Development_Category classification
- Used Column Profiling to identify and act on data-quality/missing-value issues
- Replaced/handled errors in calculated columns

---

## Power BI Dashboard — Visuals Created

1. **KPI Cards (3):** Average Access to Electricity, Average CO2 Emissions, Average Inflation
2. **Bar Chart:** Top 10 CO2 Emitting Countries
3. **Column Chart:** Electricity Access by Development Category
4. **Line Chart:** CO2 Emissions Trend over time (global)
5. **Donut Chart:** Countries by Development Category
6. **Table:** Country Statistics (Country, Year, Inflation, and other indicators)
7. **Matrix:** Average CO2 Emissions by Country × Development Category
8. **Map:** Global CO2 Emissions Map (by country)
9. **Additional Visual 1 — Treemap:** Renewable Energy Consumption by Country
10. **Additional Visual 2 — Scatter Chart:** Electricity Access vs. CO2 Emissions

### Interactivity
- **Slicers (3):** Year, Country, Development_Category
- **Drill-down:** enabled on the country/category hierarchy visual
- **Cross-filtering:** demonstrated across donut, table, bar, and scatter visuals

---

## Business Insights

 `Insights.pdf` for the full write-up. Summary:

1. **Infrastructure gap in developing economies** - Developing nations make up the largest share of tracked countries (25.37%) but show markedly lower electricity access than Developed nations, pointing to both risk and infrastructure-investment opportunity.
2. **Rising global emissions increase long-term ESG exposure** — Global CO2 emissions trend upward consistently from 2000–2020, signaling rising future compliance/regulation costs relevant to long-horizon investment theses.
3. **Electricity access and emissions move together in early industrialization** — A positive relationship between electricity access and CO2 emissions suggests that closing the infrastructure gap in emerging markets will likely worsen emissions profiles before they stabilize, reinforcing the case for pairing infrastructure investment with renewable energy strategy.

---

## Repository Structure

```
DSA3050A_MidSem_Patricia_669781/
│
├── Dataset/
│   └── world_bank_development_indicators.csv
│
├── PBIX/
│   └── MidSemExam.pbix
│
├── Screenshots/
│   ├── (raw dataset, Power Query editor, applied steps, column profiling,
│   │    final cleaned dataset, advanced task evidence, dashboard, interactivity)
│
├── README.md
│
└── Insights.pdf
```
