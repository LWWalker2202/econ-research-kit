# Energy and Environmental Economics: Data

## Data sources

Air pollution outcomes come from the national air quality monitoring network. Hourly concentrations are published by the China National Environmental Monitoring Centre for a first set of cities from 2013 and for all prefecture-level cities in the following years, and are usually aggregated to the city-day or city-month level. Stations are geocoded, which allows a monitor-level or ring-based design around a plant rather than a city average.

Firm emissions come from three distinct sources that are often confused. Continuous emission monitoring (CEMS) records outlet-level concentrations and flow for key pollutant discharging units. The annual environmental statistics system and the pollutant discharge declaration collect firm-reported annual discharge totals. Permit records contain the permitted limit rather than the realized emission. Only CEMS is high-frequency; only the permit record is a legal limit; only the annual report covers non-key firms.

Carbon data come from the pilot exchanges and, from 2021, the national market. Transaction records give price, volume, and contract type by day and by product. Allowance allocation plans give each covered firm its free allocation, and verified emission reports give the compliance position. The pilot schemes differ in whether the price is administratively bounded, so a price series from two pilots is not the same object.

Energy data come from the China Energy Statistical Yearbook (中国能源统计年鉴), which reports provincial energy balances and sectoral consumption, and from city government work reports, which state the energy intensity targets. Firm-level energy use is available in the Chinese Industrial Enterprises Database (中国工业企业数据库, CIED) for the years it covers, and in the pollution declaration for the years after it.

## Variables and definitions

| Variable (English original) | Definition | Source |
|---|---|---|
| PM2.5 concentration | Annual or monthly mean of hourly mass concentration, micrograms per cubic metre | National air quality monitoring network |
| AOD | Aerosol optical depth from satellite retrievals, used where ground monitors are sparse | Satellite aerosol products |
| SO2 emission | Firm annual sulphur dioxide discharge in tonnes | Environmental statistics, CEMS |
| COD discharge | Chemical oxygen demand in wastewater, tonnes per year | Environmental statistics, pollutant discharge declaration |
| energy consumption | Total energy use converted to standard coal equivalent, 10 000 tonnes of standard coal | China Energy Statistical Yearbook |
| energy intensity | Energy consumption per unit of GDP, tonnes of standard coal per 10 000 yuan | Yearbook and statistical bulletins |
| carbon price | Settlement price in yuan per tonne of CO2 equivalent | Pilot exchanges, national market |
| allowance | Free allocation in tonnes of CO2 equivalent | Allocation plans |
| permit limit | Permitted discharge concentration and annual volume | Pollutant discharge permit records |
| inspection batch | The batch in which a province entered CEPI, plus the stationing dates | Ministry of Ecology and Environment announcements |

## Coverage

| Data | Years | Level | Sample size magnitude |
|---|---|---|---|
| National air quality monitoring | 2013 onwards | Station-hour, city-day | About one thousand stations [verify] |
| CEMS | 2013 onwards for key units | Firm-outlet-hour | Tens of thousands of outlets [verify] |
| Environmental statistics and pollutant discharge declaration | Annual | Firm | About one hundred thousand firms [verify] |
| Pollutant discharge permit records | 2017 onwards | Firm-outlet | About one hundred thousand firms [verify] |
| Pilot ETS transactions | 2013 onwards | Firm-day | About one thousand covered firms per pilot [verify] |
| National ETS transactions | 2021 onwards | Firm-day | About two thousand covered firms at launch [verify] |
| China Energy Statistical Yearbook | Annual, long series | Province and sector | 31 provincial units |
| Chinese Industrial Enterprises Database (CIED) | 1998 to 2013, with gaps | Firm | About one hundred thousand firms per year [verify] |
| China Customs Trade Database (中国海关数据库) | 2000 onwards | Firm-product-destination | About one hundred thousand firms [verify] |

## Known issues

- Monitoring stations move. A station that is relocated or reclassified changes the local mean for reasons unrelated to emissions, and the move is not always documented in the published data. Fix the station set to those present in all sample years, or use monitor fixed effects and report the number of dropped stations.
- CEMS series contain long runs of zeros and repeated values, which usually indicate a sensor outage or a reporting default rather than clean production. Treat zero and missing as distinct values and check how the share of zeros varies around the policy date.
- Firm-reported annual discharge is rounded and is subject to local reporting incentives that move with the enforcement cycle. The direction of the reporting bias is not known in advance, so an effect on reported emissions is not the same as an effect on emissions.
- Carbon markets are thin. In the pilots, a large share of volume is traded in a few days around compliance deadlines, so a monthly average price is a weak summary of the marginal abatement cost. Report trading volume next to any price series.
- Energy statistics were revised substantially in the early 2010s, and provincial totals do not always sum to the national total. Use one vintage of the yearbook across the panel and state which one.
- CIED changes its variable definitions and its sample frame over time, and firm identifiers are not stable across the 2007 economic census. Match on name, address, and industry code, and report the match rate.
- Firm names in permit, tax, and customs records do not match by construction. Any merge across these sources needs a documented name-normalization step and a reported match rate.
- Treatment status changes more than once for many firms, because inspection rounds, permit issuance, and tax rate changes overlap. Count the firms with more than one transition and report the number, otherwise the post indicator silently averages over several distinct regimes.
- The treatment date in a paper is often the date of the first news report rather than the date in the official announcement. Check the source date for every unit and report how many differ by more than a month.
