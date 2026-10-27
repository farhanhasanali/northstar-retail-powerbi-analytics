# NorthStar Retail | Sales, Profitability & Data Quality Analysis

## Project Overview

This Power BI portfolio project analyzes a fictional retail sales dataset to evaluate profitability, identify data-quality issues, and explore the potential financial impact of problematic transactions.

The project includes two interactive dashboards designed for management reporting and detailed data-quality investigation.

## Business Objectives

- Analyze retail sales profitability.
- Identify duplicate transactions, missing information, invalid dates, and invalid discounts.
- Measure the percentage of source records affected by data-quality issues.
- Evaluate hypothetical profit adjustment scenarios.
- Develop interactive dashboards to support business decision-making.

## Tools and Technologies

- **Power BI Desktop** — Dashboard development and visualization
- **Power Query** — Data transformation and preparation
- **DAX** — Business calculations and dynamic measures
- **Data Modeling** — Supporting relationships and filter-aware analysis
- **Data Validation** — Reconciliation and quality checks

## Dashboard 1: Management Dashboard

The Management Dashboard provides an executive-level overview of business performance and data quality.

**Key metrics:**

| Metric | Result |
|---|---:|
| Total Source Rows | 25 |
| Data Quality Findings | 4 |
| Affected Source Rows | 5 |
| Affected Row Rate | 20% |
| Preliminary Total Profit | $211.40 |
| Profit Excluding Invalid Discounts | $226.40 |
| Filter-Aware Profit Scenario | $301.40 |
| Combined Profit Adjustment Scenario | $316.40 |

Financial adjustment scenarios are hypothetical and require source-data and Finance verification. They do not represent approved financial results.

## Dashboard 2: Data Quality Analysis

The Data Quality Analysis dashboard allows users to investigate specific data-quality issues using interactive filters, a bar chart, a transaction-level issue table, and dynamic KPI Cards.

### Identified Data Quality Issues

| Order ID | Issue Type | Affected Source Rows |
|---|---|---:|
| 1013 | Duplicate OrderID | 2 |
| 1021 | Missing Region | 1 |
| 1022 | Invalid OrderDate | 1 |
| 1024 | Invalid Discount > 100% | 1 |

**Total:** Four findings affecting five source rows.

## DAX Example: Affected Row Rate

```dax
Affected Row Rate =
DIVIDE(
    [Affected Rows],
    CALCULATE(
        COUNTROWS(Profitability_Analysis),
        REMOVEFILTERS(DQ_Summary)
    ),
    0
)
```

This measure calculates the percentage of affected rows against the full source dataset while allowing the numerator to respond to the selected data-quality issue.

For example, selecting Duplicate OrderID displays 2 affected rows out of 25, or 8%.

## Key Findings

1. Four distinct data-quality issues were identified.
2. Five of 25 source rows were affected, representing 20% of the dataset.
3. Duplicate OrderID affects two source rows.
4. Invalid discount values can distort preliminary profitability calculations.
5. Financial adjustments should be validated before being used for business reporting.

## Skills Demonstrated

- Data cleaning and transformation with Power Query
- DAX measures and filter context
- Interactive report development
- Data-quality analysis and reconciliation
- Financial scenario analysis
- Business-focused KPI design
- Communicating analytical findings to management

## Project Limitations

This project uses fictional retail data for educational and portfolio purposes. Financial scenarios are illustrative, not approved accounting corrections. Identified source-data issues require investigation before any production changes.

## Conclusion

The NorthStar Retail project demonstrates how Power BI can combine profitability analysis with data-quality monitoring to help business stakeholders understand performance, investigate unreliable records, and make more informed decisions.

A key lesson from this project is that reliable business intelligence requires both effective visualization and careful validation of the underlying data.
