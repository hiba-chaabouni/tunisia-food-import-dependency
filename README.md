<div align="center">
# 🇹🇳 Tunisia Food Import Dependency
 
**Which countries supply Tunisia's strategic imports, how concentrated is that supply, and are the prices fair?**
 
![Period](https://img.shields.io/badge/Period-2015--2024-blue?style=flat-square)
![Products](https://img.shields.io/badge/Products-13-green?style=flat-square)
![Source](https://img.shields.io/badge/Source-UN_Comtrade-1f6feb?style=flat-square)
![Benchmark](https://img.shields.io/badge/Benchmark-World_Bank_Pink_Sheet-orange?style=flat-square)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)
 
[About](#about) · [Findings](#key-findings) · [Products](#products-covered) · [Data](#data) · [Pipeline](#pipeline) · [Limitations](#limitations) · [Authors](#authors)
 
</div>
---
 
## About
 
Analysis of Tunisia's imports of strategic food and health products from **2015 to 2024**: which countries supply them, how concentrated that supply is, and how the prices Tunisia paid compare with world benchmark prices.
 
---
 
## Key Findings
 
| Theme | Finding |
|---|---|
| **Black Sea dependence** | Share rose from **33% (2015)** to **65% (2024)** |
| **2022 crisis** | Import spending went from about **$1.6B (2019)** to **$2.7B (2023)** |
| **Substitution** | **Bulgaria** became top soft-wheat supplier in 2022-23 |
| **Single supplier** | **Soybean meal** came almost entirely from **Argentina** |
| **Price check** | Most products cost **1.0-1.2x** the world price. In 2024: **rice 2.1x**, **sugar 2.0x**, **palm oil 1.45x** |
 
Price ratio = (import value ÷ import weight) ÷ world benchmark price. Import values include freight and insurance, so a ratio slightly above 1.0 is normal.
 
---
 
## Products Covered
 
| HS code | Product | Category | World Bank benchmark |
|---|---|---|---|
| 100119 | Durum wheat | Cereals | Wheat, US HRW (proxy) |
| 100199 | Soft wheat | Cereals | Wheat, US SRW |
| 1003 | Barley | Cereals | Barley (series ends Sep 2020) |
| 1005 | Maize | Cereals | Maize |
| 1006 | Rice | Cereals | Rice, Thai 5% |
| 1201 | Soybeans | Oilseeds & feed | Soybeans |
| 2304 | Soybean meal | Oilseeds & feed | Soybean meal |
| 1507 | Soybean oil | Vegetable oils | Soybean oil |
| 1511 | Palm oil | Vegetable oils | Palm oil |
| 1512 | Sunflower oil | Vegetable oils | Sunflower oil |
| 1701 | Sugar | Sugar | Sugar, world (raw) |
| 0402 | Milk powder | Dairy | none |
| 3004 | Medicines | Health | none |
 
---
 
## Data
 
### raw/ (original downloads)
 
| File | Description |
|---|---|
| `UNComtrade_Tunisia_Imports_5products_2015-2024.csv` | Tunisia-reported annual imports by partner (UN Comtrade) |
| `UNComtrade_Tunisia_Imports_8products_2015-2024.csv` | Tunisia-reported annual imports by partner (UN Comtrade) |
| `NOT_IN_MODEL_SupplierReported_2024-2025_*.csv` | Partner-reported exports to Tunisia, kept out of the model |
| `CMO-Historical-Data-Monthly.xlsx` | World Bank Commodity Price Data (Pink Sheet), monthly |
 
### prepared/ (model-ready tables)
 
| File | Description |
|---|---|
| `Dim_Product.csv` | Product dimension (HS code, category, benchmark) |
| `Dim_Country.csv` | Partner dimension (ISO, region, EU, AfCFTA, Black Sea, supplier group) |
| `AnswerKey_WorldPrice_long.csv` | World Bank monthly prices in long format (USD per tonne) |
 
**Supplier groups:** EU, Black Sea, Americas, Africa & Middle East, Other, Unspecified.
 
**Sources:** [UN Comtrade Database](https://comtradeplus.un.org/) · [World Bank Pink Sheet](https://www.worldbank.org/en/research/commodity-markets)
 
---
 
## Pipeline
 
```mermaid
flowchart LR
    A[UN Comtrade CSVs] --> C{Clean and standardise}
    B[World Bank Pink Sheet] --> C
    C --> D[Dim_Product, Dim_Country, World prices]
    D --> E[(Power BI model)]
    E --> F[Dashboard]
```
 
---
 
## Limitations
 
- Tunisia's data ends in **2024**; supplier-reported 2025 data is incomplete and kept out of the model
- Import data is **yearly**, not monthly
- **2024 weights** are missing for maize and medicines
- **Barley** has no world price after Sep 2020
- **Durum wheat** uses a proxy price
- **Milk powder and medicines** have no benchmark
---
 
## Authors
 
| Name | Programme |
|---|---|
| **Hiba Chaabouni** | Business Analytics (major) and IT (minor), Tunis Business School |
| **Ghada Ben Amira** | Business Analytics (major) and IT (minor), Tunis Business School |
 
