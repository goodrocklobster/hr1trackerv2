# Data and methodology

## Sources

- Enrollment: [Connecticut DSS people served by town and type of assistance](https://data.ct.gov/Health-and-Human-Services/DSS-People-Served-by-Town-and-Type-of-Assistance-T/g7bd-zbqw/about_data).
- Machine-readable records: `https://data.ct.gov/resource/g7bd-zbqw.json` (paginate or set an adequate limit; the default response is not the full dataset).
- Metadata: `https://data.ct.gov/api/views/g7bd-zbqw.json`; `rowsUpdatedAt` supplies the displayed data-update date.
- Map: [Connecticut DOT towns](https://services1.arcgis.com/FCaUeJ5SOVtImake/ArcGIS/rest/services/CTTowns/FeatureServer/0), simplified to 0.001 degrees for display.
- Policy context: [DSS work rules toolkit](https://portal.ct.gov/dss/all-programs/dss-benefits-and-hr1/hr1-for-members/hr1-work-rule-changes).

Snapshot retrieved September 28, 2026, Eastern time. Source update: September 11, 2026. Latest reporting month: August 2026. Dashboard history starts January 2025. Comparisons start July 2025.

## Calculation rules

- Net loss = July 2025 count − selected-month count.
- Percent loss = net loss / July 2025 count × 100; unavailable if baseline is zero.
- Monthly loss = preceding-month count − selected-month count.
- Negative losses represent gains. Cards switch to “gain” labels.
- Combined counts sum only the 169 mapped municipalities; Unknown and Out of State are excluded.

SNAP includes TP09 and TBA. Medicaid includes D01, D03, D04, D10, D11, D25, F06C, F06P, F99, G06-I, G99, H01, L01, L99, M01, M04, M06, M07, M08, M09, M10, M11, N01, P99, S01, S02, S03, S04, S05, S95, S99, T01, W01, X01, X02, X03, X04, X07, X10 and X25. Category descriptions are available in the dashboard's expandable methods section and in `data.js`.

## Interpretation

These are sums of published assistance-category counts, not unduplicated counts of people. Recipients may occur in multiple categories. CHIP, emergency medical, Medicare Savings Programs, explicitly state-funded categories and refugee medical assistance are excluded from the selected Medicaid categories.

DSS reports counts below five as zero. Published zeros cannot be treated as verified absence of recipients. Aggregation and changes inherit suppression uncertainty, especially in small municipalities. DSS generally revises its latest three reporting months.

Net enrollment changes do not measure gross exits, cumulative people losing benefits, lost dollars, or causal effects of H.R.1. The July 2025 baseline overlaps enactment. The dashboard has no individual termination reasons or counterfactual comparison.

## Refresh validation

Before replacing `data.js`, check for duplicate town/month/TOA keys; confirm all 169 towns join to the map; distinguish absent records from published zeros; check all expected reporting months; verify the category list against current DSS definitions; and retain the source update timestamp. The object shape is `window.DATA`, containing `updated`, `months`, `towns`, `codes`, `data`, `geo`, and `categories`. Each program/town/month entry includes `n` (published sum), `s` (zero-valued cells), and `k` (included rows).
