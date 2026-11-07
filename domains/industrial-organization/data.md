# Industrial organization and regulation: data

## Data sources

The Chinese data environment for industrial organization is an assembly of partial universes, and almost every design choice follows from which universe is used. The 中国工业企业数据库 (Chinese Industrial Enterprises Database, CIED) is the workhorse firm-level source: annual records for manufacturing firms above a size threshold, with sales, employment, capital, intermediate inputs, ownership, and a four-digit industry code. It is not a census of firms and never was. The threshold was raised at the start of the 2010s, which changed the composition of the sample at that year (to confirm against the official codebook), and firms that fall below the threshold after having been in the database look like exits unless the analyst reconstructs the panel carefully.

The 中国海关数据库 (China Customs Trade Database) supplies firm-level and transaction-level trade records: product code, destination or origin, quantity, value, unit price, trade regime, and a firm identifier. Its value for industrial organization is the unit price, which is the closest observable to a transaction price for traded goods, and the ability to separate processing trade from ordinary trade, because the two operate on different pricing logics. Its weakness is the firm identifier, which is not the same identifier as in the CIED and which changes when a firm's registration status changes.

Business registration records from the market regulation system cover the population of registered firms rather than the population above a threshold: registration date, registered capital, address, industry, ownership type, business scope, and the date of deregistration or revocation. This is the only source in which entry and exit can be measured without size truncation, but registration is a legal status rather than an operating status, and the gap between the two is large for shell firms.

Ownership data come from the state asset supervision system and from listed-firm databases. Listed firms are larger and more profitable than the industrial survey average, so they are the right sample for questions about accounting markups and the wrong sample for questions about market structure. Price data come from statistical yearbooks, price monitoring by price authorities, and commercial scanner data where available; the last is the only source with actual retail prices at product level, and it is proprietary and geographically partial. Zone lists and merger case announcements are administrative documents that can be turned into dated treatment variables but require hand coding.

## Variables and definitions

| Variable (English original) | Definition | Source |
|---|---|---|
| firm id | Unique firm identifier within a source, not comparable across sources | CIED, customs, registry |
| industry code | Four-digit industry classification, revised across years; must be recoded to one vintage | CIED, registry |
| sales revenue | Total sales of the firm in the reference year, in nominal yuan | CIED |
| value added | Output minus intermediate inputs; the definition is not consistent across years | CIED |
| employment | Number of employees at year end | CIED |
| capital stock | Original value or net value of fixed assets; the two are not interchangeable | CIED |
| intermediate inputs | Materials, fuel, and purchased services used in production | CIED |
| exports value | Free-on-board value of exported goods in US dollars | Customs |
| unit price | Export or import value divided by quantity, in US dollars per unit | Customs |
| trade regime | Processing trade or ordinary trade, a firm-product-year attribute | Customs |
| registered capital | Subscribed capital at registration, in yuan | Registry |
| registration and exit dates | Date of establishment and date of deregistration or revocation | Registry |
| ownership type | Registered ownership category, or ultimate controller for listed firms | Registry, listed-firm data |

## Coverage

| Data | Years | Level | Sample size magnitude |
|---|---|---|---|
| 中国工业企业数据库 (CIED) | Late 1990s to the early 2010s (to confirm against the official codebook) | Firm | About hundreds of thousands of firms per year (to confirm against the official codebook) |
| 中国海关数据库 (customs) | Early 2000s onwards (to confirm against the official codebook) | Transaction, aggregable to firm-product | About millions of records per year (to confirm against the official codebook) |
| Business registration | 2000s onwards, with electronic coverage improving over time (to confirm against the official codebook) | Firm | About tens of millions of firms (to confirm against the official codebook) |
| Listed-firm financials | 1990s onwards | Firm | About thousands of firms (to confirm against the official codebook) |
| Price monitoring and yearbooks | Varies by series (to confirm against the official codebook) | Product or city | About hundreds of price series (to confirm against the official codebook) |
| Zone lists and merger cases | 1984 onwards for zones, 2008 onwards for cases (to confirm against the official codebook) | Zone, case | About thousands of zones and cases (to confirm against the official codebook) |

## Known issues

- The CIED sample threshold changed during the sample period, so a year-on-year change in the number of firms is a change in coverage as well as a change in the firm population. Report the number of firms per year and the threshold rule before any trend claim.
- Disappearance from the CIED is not exit. A firm can fall below the threshold, fail to report, or change its legal form. Distinguish these using registry deregistration records, and report the share of disappearances that are genuine exits.
- Value added, capital, and intermediate inputs are reported in current prices. Deflating them with the same index assumes the same price change for outputs and inputs, which biases markup estimates; use output and input deflators separately and report both.
- Industry codes are revised, and the revision date does not coincide with any policy date. Recode to a single vintage, and check that the recoding does not move firms across industries in the years when a policy binds.
- The customs firm identifier covers trading firms, including pure trading intermediaries that own no production capacity. Merging customs to the CIED without separating intermediaries mixes producers and traders in the same markup calculation.
- Registry data record legal existence. A registered firm may never operate, and a deregistered firm may have stopped operating years earlier. Entry and exit measured from registry dates are upper bounds on economic entry and exit.
- Listed-firm data are selected on size and on the ability to raise equity. Accounting markups computed there are not comparable to production-function markups computed on the CIED.
- Merger case lists contain notified cases only, and the published fields change with the enforcing agency. Coding enforcement intensity across the 2018 reorganization requires documenting the change in case definitions rather than assuming continuity.
