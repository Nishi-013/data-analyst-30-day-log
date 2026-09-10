# Day 2 — Reading a dataset: rows, columns, dimensions & measures

Dataset: [day2-sample-orders.csv](day2-sample-orders.csv) — 28 orders, 9 columns, 7/2/2026–7/28/2026.

## Column inventory

| Column | Type |
|---|---|
| OrderID | ID |
| OrderDate | Dimension |
| Region | Dimension |
| Category | Dimension |
| Product | Dimension |
| CustomerName | Dimension |
| Units | Measure |
| UnitPrice | Attribute (numeric, but not additive — it describes the Product, doesn't sum meaningfully across rows) |
| Revenue | Measure |

**Key lesson:** not every numeric column is a measure. `SUM(UnitPrice)` across different products is meaningless; `SUM(Units)` and `SUM(Revenue)` are real, addable business numbers. This distinction resurfaces on Day 24 (Power BI star schema) — UnitPrice belongs inside a Product dimension table as an attribute, not in the fact table as a measure.

## Dataset shape

- **Rows:** 28 orders (`=COUNTA(A2:A29)`)
- **Regions (4):** West, East, Central, South (`=UNIQUE(C2:C29)`)
- **Categories (3):** Furniture, Office Supplies, Technology (`=UNIQUE(D2:D29)`)
- **Date range:** 7/2/2026 – 7/28/2026 (`=MIN()` / `=MAX()` on OrderDate)

*Bonus: found and used `UNIQUE()`, `MIN()`, `MAX()` on my own — ahead of where the roadmap introduces them.*
