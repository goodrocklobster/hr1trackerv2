# Sources and methodology

## Sources

- Enrollment: Connecticut Department of Social Services, [People Served by Town and Type of Assistance by Month](https://data.ct.gov/Health-and-Human-Services/DSS-People-Served-by-Town-and-Type-of-Assistance-T/g7bd-zbqw/about_data).
- Machine-readable records: https://data.ct.gov/resource/g7bd-zbqw.json
- Source metadata: https://data.ct.gov/api/views/g7bd-zbqw.json
- Map: [Connecticut town boundaries](https://services1.arcgis.com/FCaUeJ5SOVtImake/ArcGIS/rest/services/CTTowns/FeatureServer/0), simplified for display.
- Policy dates: [Connecticut DSS work rules toolkit](https://portal.ct.gov/dss/all-programs/dss-benefits-and-hr1/hr1-for-members/hr1-work-rule-changes).

Saved snapshot: September 28, 2026 (Eastern time). Records cover January 2025–August 2026 in the dashboard. Source `rowsUpdatedAt`: September 11, 2026, 20:05:27 UTC. The date shown is the source update date, not the site deployment date.

## Geography and program definitions

Totals sum all 169 municipalities. Unknown and Out of State records are excluded.

SNAP: TP09 and TBA.

Medicaid selected categories: D01, D03, D04, D10, D11, D25, F06C, F06P, F99, G06-I, G99, H01, L01, L99, M01, M04, M06, M07, M08, M09, M10, M11, N01, P99, S01, S02, S03, S04, S05, S95, S99, T01, W01, X01, X02, X03, X04, X07, X10, X25.

These are categories described as HUSKY A, C, D or Limited Benefit, excluding explicitly state-funded and refugee medical categories. CHIP / HUSKY B, emergency medical, Medicare Savings Programs and other state medical categories are excluded. Category descriptions are also retained in `data.js`.

## Measures

- Net loss = July 2025 count − selected-month count.
- Percent loss = net loss / July 2025 count × 100.
- Monthly loss = previous-month count − selected-month count.

Negative losses are gains; the headline cards switch to gain labels. Percentages are unavailable when the published baseline is zero. The chart includes months before July 2025 for context. The July comparison overlaps enactment on July 4 and is not a fully pre-law baseline.

## Interpretation

These are sums of published assistance-category counts, not unduplicated program enrollment totals. A person may appear in more than one assistance category. Do not sum SNAP and Medicaid to estimate distinct people. Net changes do not measure gross exits or the cumulative number of people removed.

DSS publishes counts below five as zero. Zeros may therefore represent suppression, not absence of recipients. Levels are understated, differences carry suppression uncertainty, and small-town percentages require care. Source revisions can also alter comparisons; DSS generally refreshes the latest three months.

The dataset contains no reason for termination. Changes cannot be attributed entirely to H.R.1 using this dataset alone. Eligibility, applications, renewals, migration and administrative processes also affect enrollment. Medicaid work requirements begin in January 2027, after this snapshot. The working-draft branding implies no endorsement by DSS or another organization.

## Snapshot checks

All 169 municipalities have records for both program groups for every included month. Duplicate town/month/TOA records were checked during preparation.

Published category sums for July 2025 → August 2026:

| Program group | July 2025 | August 2026 | Net decline |
| --- | ---: | ---: | ---: |
| SNAP | 359,399 | 297,142 | 62,257 |
| Medicaid selected categories | 887,048 | 863,639 | 23,409 |

These checks apply only to this saved snapshot and these exact category definitions.

The chart marks OBBBA enactment on July 4, 2025 at the July monthly position, with a burgundy point and lightly shaded subsequent period. It is a policy-event annotation, not a daily enrollment observation or causal estimate.


## District allocation

State House (151), State Senate (36), and congressional (5) estimates use the supplied Town × District 2020 Census population weights: sldl26, sldu26, and cd120. These represent 2026 state legislative districts and the 120th Congress, applied consistently to all months; they do not identify officeholders or the district boundaries in force in each historical month.

For each town, divide each supplied afact by the sum of its afacts, correcting rounding discrepancies of at most 0.0001. District monthly count = sum of town monthly count × normalized share. Net loss = allocated July 2025 count minus allocated selected-month count. Percent loss = net loss / allocated July count × 100. Monthly change uses the same allocation for both months. Do not average town percentages. Calculations retain fractional counts until display rounding; rounded district values may not sum exactly. Gains remain negative net losses.

These are population-based estimates, not observed district caseloads. They assume recipients are distributed within a town like the total 2020 population, with constant shares over time. Suppression and assistance-category duplication in the underlying data still apply. No claim of causal attribution to OBBBA is established.

Every file includes two additional records with MCDName 0914046520 and 0917014160, population 726 each. These do not match the 169 DSS municipality names and are excluded, not added as additional towns. All 169 named towns are covered. See allocation-audit.json for excluded records and normalization details.

Boundaries: US Census TIGERweb Legislative MapServer layers 2 (House), 1 (Senate), 0 (Congress), retrieved October 6, 2026, filtered to Connecticut STATE=09. Geometry is simplified at 0.00015 degrees for display. Non-district ZZZ/ZZ water areas are excluded. https://tigerweb.geo.census.gov/arcgis/rest/services/TIGERweb/Legislative/MapServer

In district mode, the map shows only the selected district geography, shaded by district estimates. Municipality boundaries and town shading appear only in municipality mode. Hover/selection in district mode reports district estimates. Census geography downloads do not change the DSS last-updated date.
