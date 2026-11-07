# Pollution monitoring data in China (national control stations and key-discharger online monitoring)

> Where this sits: stage 3 (data). A dictionary entry is usable only when five fields are filled: unit of observation, coverage (years and regions), the key variables with their exact definitions, the access route, and the known defects. Anything still marked ` (to confirm against the official codebook)` / ` (to confirm against the official codebook)` is a question for the person who owns the data, not a fact you may quote.

## Basic information

| Item | Detail |
|---|---|
| Full name (Chinese) | 中国污染监测数据（国控站点与重点排污单位在线监测） |
| Full name (English) | Pollution monitoring data in China: national control air-quality stations and online monitoring of key pollutant discharging units |
| Abbreviation | No single abbreviation is in general use (to confirm against the official codebook) |
| Maintainer | Ministry of Ecology and Environment (MEE); national air-quality network operated by the China National Environmental Monitoring Centre (CNEMC) |
| Start year | Real-time publication of new-standard air quality began in 2013 for the first batch of cities; the network reached all prefecture-level and above cities in 2015 |
| Frequency | Hourly and daily for air quality; daily or monthly for online emissions monitoring |
| Unit of observation | Station-hour, station-day, city-day, and enterprise discharge outlet-day |

## Variables

| Variable name | Chinese name | Meaning and definition | Typical values |
|---|---|---|---|
| `station_id` | 站点编码 | Identifier of the national control monitoring station | Unique code; check whether it is stable when stations are relocated |
| `city_code` | 城市代码 | Administrative code of the city the station belongs to | GB/T 2260 numeric code |
| `date` | 日期 | Calendar date of the observation | YYYY-MM-DD |
| `hour` | 小时 | Hour of the observation in local time | 0 to 23 |
| `pm25` | PM2.5 浓度 | Fine particulate matter concentration | Micrograms per cubic metre |
| `pm10` | PM10 浓度 | Inhalable particulate matter concentration | Micrograms per cubic metre |
| `so2` | 二氧化硫浓度 | Sulphur dioxide concentration | Micrograms per cubic metre |
| `no2` | 二氧化氮浓度 | Nitrogen dioxide concentration | Micrograms per cubic metre |
| `o3` | 臭氧浓度 | Ozone concentration | Micrograms per cubic metre |
| `aqi` | 空气质量指数 | Air quality index computed from the individual pollutant indices | Integer, with a defined breakpoint table |
| `primary_pollutant` | 首要污染物 | Pollutant with the highest individual index on that day | Pollutant name or code |
| `enterprise_name` | 企业名称 | Name of the key pollutant discharging unit in the online monitoring data | Text, matched to the annual list of key units |
| `pollutant` | 污染物 | Pollutant measured at the discharge outlet | Coded pollutant name |
| `concentration` | 排放浓度 | Measured concentration at the outlet | Milligrams per cubic metre or per litre, depending on the pollutant |
| `flow` | 流量 | Exhaust or wastewater flow at the outlet | Volume per unit time |

Station-level air quality files and enterprise-level online monitoring files are separate products maintained by different parts of the same system. Do not treat them as one dataset.

## Known issues

- The station panel is not continuous. Stations are added, relocated and retired, and a station identifier that appears in all years may have changed its physical location or its measurement method. Build the panel on a fixed station list and report how many stations leave.
- PM2.5 is unavailable before the new-standard rollout. Only the first batch of cities had it from 2013, and the network reached all prefecture-level and above cities in 2015, so using 2013 as a nationwide pre-period for PM2.5 is wrong.
- Missing hours are sometimes coded as zero. Daily means require a minimum number of valid hours; treating non-reporting hours as zero biases city means downward, which can be mistaken for a policy effect.
- Real-time published values differ from the audited values used in official annual reports. Identify which version a series comes from before mixing sources; the revision is not documented per value.
- Station siting is not random. National control stations sit mostly in urban built-up areas, so the data do not represent county-level or rural exposure; county-level designs need a different source or an explicit exposure model.
- Online emissions data are self-reported. Enterprises report through the platform, and the coverage follows the annual list of key pollutant discharging units, which changes every year, so the monitored set is an endogenous selection.
- Outlet versus firm. Emissions are reported at discharge-outlet level and a firm may have several outlets; aggregating to the firm requires matching outlet records to the enterprise and the match rate should be reported.
- Only permitted pollutants are monitored. Fugitive emissions and pollutants outside the permit or the monitoring requirement are absent, so a null result on a monitored pollutant does not rule out substitution towards an unmonitored one.

## Access

| Item | Detail |
|---|---|
| Entry type | Public download for station-level air quality; request or purchase for long historical and enterprise-level series |
| Channel | CNEMC and provincial or municipal environmental monitoring centres for air quality; MEE and provincial ecology and environment departments for online monitoring |
| Institutional account | Not required for the public real-time pages; required for bulk or historical downloads (to confirm against the official codebook) |
| Cost | Free for non-commercial use; some historical and enterprise-level products are paid |
| Ethics review | No human-subjects review is involved, but enterprise identifiers and permit records may be confidential |
| Usage agreement | No redistribution, attribute the monitoring authority, and obtain permission before commercial use; the terms of the platform that supplied the data take precedence |
