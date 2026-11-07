# International Trade and Spatial Economics: Data

## Data sources

**中国海关数据库 (China Customs Trade Database).** Transaction-level records of imports and exports by firm, product, trade mode, and partner country, with quantity and US dollar value. This is the workhorse microdata for trade exposure: it identifies the firm, the HS code, the trade mode (加工贸易 versus 一般贸易), the customs district (关区), and the destination or origin. The extracts used in most papers cover 2000 to 2016 (to confirm against the official codebook); later years are less complete, so the window of any firm-level trade design should be stated explicitly. Firm identifiers are the customs registration code, which is not the code used in the industrial enterprise database.

**中国工业企业数据库 (Chinese Industrial Enterprises Database, CIED).** Annual firm-level data for above-scale manufacturing firms, described in the data dictionary entry on the industrial firms database. Here it is used to attach firm characteristics to customs transactions and to map firms to two-digit industries, so that product-level shocks can be aggregated to the firm or region. Matching customs records to CIED records relies on name, address, telephone, and postal code, and a material share of records remains unmatched.

**City and county statistics.** 中国城市统计年鉴 (China City Statistical Yearbook) and 中国县域统计年鉴 (China County Statistical Yearbook) report GDP, employment by sector, industrial output, foreign direct investment, and population at the prefecture and county level, usually with both 全市 and 市辖区 definitions. They are the standard source for local outcomes and for the pre-period industry structure that weights exposure measures.

**Nighttime lights.** Grid-level radiance from DMSP-OLS and from NPP-VIIRS, used as a proxy for local activity where statistical data are missing or unreliable. The two sensors overlap only briefly and have different saturation and calibration properties.

**Bilateral trade at the product level.** CEPII-BACI and UN Comtrade give HS6-level bilateral flows by year, used to build world demand shocks, import penetration from third countries, and partner-level exposure. Mirror statistics disagree systematically, because importers and exporters report different values and because goods pass through entrepots.

**Tariff schedules and trade policy instruments.** The annual Customs Import and Export Tariff of the People's Republic of China gives the statutory most-favoured-nation rate by HS line; TRAINS and the WTO tariff database reproduce the series for cross-checking; the processing-trade catalogues define which products cannot be processed duty-free.

**Transport networks and timetables.** Railway timetables give city-pair travel times and direct services; railway and highway statistical bulletins give opening dates and mileage; port statistics give throughput. Timetable snapshots matter because the schedule is revised periodically, so a travel time from a single year is a point estimate of a changing object.

**Administrative divisions.** 民政部行政区划代码 (administrative division codes) and the annual boundary-change announcements record when a county became a district, when a county-level city was upgraded, and when a code was reassigned. Any city panel spanning these announcements needs the code history, not only the current code.

## Variables and definitions

| Variable | Field or construction | What to check |
|---|---|---|
| Firm identifier | 企业代码 (customs registration code) | Stability across years; how the firm is matched to the industrial firms database |
| Firm location | 行政区划代码 of the registration place | Whether the code is the prefecture, the county, or the urban district |
| Product | HS code at the recorded digit level | Whether the HS revision is the same in both years compared |
| Trade mode | 贸易方式 (ordinary trade, processing with imported materials, processing with supplied materials) | Whether processing trade is included in the exposure measure |
| Value and quantity | US dollar value, quantity, unit of quantity | Unit changes across records; value is not net of re-exports |
| Destination or origin | Partner country code | Whether entrepot trade through Hong Kong is attributed to the final destination |
| Tariff | Statutory most-favoured-nation rate on the HS line, weighted by pre-period trade | Whether the weight is pre-period or contemporaneous trade |
| Regional industry share | Employment or output share by two-digit industry from the industrial firms database | Consistency of the industry classification across revisions |
| Travel time | Network travel time between city pairs from timetables | Station to station or door to door; which timetable vintage |
| Light | Calibrated radiance at the grid cell | Whether the series is harmonized across the two sensors |
| Market access | Income-weighted sum of inverse travel cost | Whether destination income is lagged to before the shock |

## Coverage

| Data | Years | Level | Size order |
|---|---|---|---|
| China Customs Trade Database | 2000 to 2016 (to confirm against the official codebook) | Firm-product-partner country | About one hundred thousand to one million firms per year (to confirm against the official codebook) |
| Chinese Industrial Enterprises Database | 1998 to 2013, with gaps | Firm | About one hundred thousand firms per year (to confirm against the official codebook) |
| City statistical yearbooks | Annual from the 1990s | Prefecture-level city | Several hundred cities |
| County statistical yearbooks | Annual | County and district | About two thousand county-level units (to confirm against the official codebook) |
| DMSP-OLS night lights | 1992 to 2013 | Grid cell | Global coverage |
| NPP-VIIRS night lights | 2012 onward | Grid cell | Global coverage |
| CEPII-BACI and UN Comtrade | 1995 onward (to confirm against the official codebook) | Exporter-importer-HS6 | All reporting countries |
| Rail timetables and network data | 2008 onward (to confirm against the official codebook) | City pair | Several thousand station pairs (to confirm against the official codebook) |
| Administrative division codes | Annual | Province, city, county | All units above township level |

## Known issues

1. Customs firm codes are not permanent: a firm that re-registers or changes its trade arrangement can appear under a new code, so an unbalanced firm panel loses and gains firms for administrative rather than economic reasons (to confirm against the official codebook).
2. HS classifications were revised repeatedly, and a product-level panel breaks at each revision unless a concordance is applied; the correspondence is many-to-many in some cells, so the mapped measure carries errors that should be reported.
3. Processing imports are exempt from duty, so a tariff measure built on all customs imports understates the exposure of processing firms and overstates the average response to a tariff cut.
4. Customs values are gross border values, not value added; re-exports through Hong Kong and other entrepots are attributed to the entrepot in some series and to the final destination in others, which changes bilateral totals.
5. The industrial firms database has gaps and definitional breaks in key financial items across years, so firm-level matching on financial variables should be restricted to comparable years.
6. City statistics report 全市 and 市辖区 for the same city; a series built without choosing one mixes two populations, and the two diverge most for cities that absorbed counties, where a merger-induced jump in population and output can be mistaken for a policy effect (to confirm against the official codebook).
7. Nighttime light saturates in urban cores and blooms across boundaries, and the sensor changes between the DMSP and VIIRS eras, so a level series is not comparable before and after the change without cross-calibration.
8. Timetable-based travel time moves when the railway is rescheduled (调图), so a travel-time shock includes schedule changes unrelated to infrastructure investment.
