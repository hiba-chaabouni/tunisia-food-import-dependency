# Tunisia Food Import Dependency

Analysis of Tunisia's imports of strategic food and health products from 2015 to 2024: which countries supply them, how concentrated that supply is, and how the prices Tunisia paid compare with world benchmark prices.

## Products covered

| HS code | Product | Category | World Bank benchmark |
| --- | --- | --- | --- |
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

## Data

```
raw/
  UNComtrade_Tunisia_Imports_5products_2015-2024.csv   Tunisia-reported annual imports by partner (UN Comtrade)
  UNComtrade_Tunisia_Imports_8products_2015-2024.csv   Tunisia-reported annual imports by partner (UN Comtrade)
  NOT_IN_MODEL_SupplierReported_2024-2025_*.csv        Partner-reported exports to Tunisia, kept out of the model
  CMO-Historical-Data-Monthly.xlsx                     World Bank Commodity Price Data (Pink Sheet), monthly
prepared/
  Dim_Product.csv                                      Product dimension (HS code, category, benchmark)
  Dim_Country.csv                                      Partner dimension (ISO, region, EU, AfCFTA, Black Sea, supplier group)
  AnswerKey_WorldPrice_long.csv                        World Bank monthly prices in long format (USD per tonne)
```

Supplier groups used: EU, Black Sea, Americas, Africa & Middle East, Other, Unspecified.

## Sources

- UN Comtrade Database, United Nations Statistics Division: https://comtradeplus.un.org/
- World Bank Commodity Price Data (The Pink Sheet): https://www.worldbank.org/en/research/commodity-markets

## Author

Hiba Chaabouni, Business Analytics (major) and IT (minor), Tunis Business School
Ghada Ben Amira, Business Analytics (major) and IT (minor), Tunis Business School
