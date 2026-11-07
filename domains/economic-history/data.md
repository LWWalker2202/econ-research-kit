# Economic history: data sources

Most of the data in this field is a transcription of a document into a table, and the quality of the table is bounded by the quality of the document and of the transcription. The sources below are the ones a paper is most likely to use, what each contains, and where the transcription usually goes wrong.

## Data sources

**Customs returns (haiguan ce).** The foreign-administered customs service published annual trade returns for each port, plus decennial reports that describe the port's hinterland, shipping, and prices. The annual returns give imports and exports by commodity and by country for each port, in the currency of the customs regime; the decennial reports give the qualitative context a referee will ask about. The series are the most complete quantitative record of China's foreign trade before the 1949 break.

**Local gazetteers (difangzhi).** County and provincial gazetteers record population, cultivated land, tax quotas, grain prices, market towns, and local events such as floods, famines, and banditry. The quota sections are the standard source for imperial fiscal variables; the price sections are uneven but are often the only local price record. Gazetteers were compiled at irregular intervals, and a new edition sometimes copies the previous edition without revision, so a date in a gazetteer is the date of the record and not always the date of the fact.

**Modern newspapers and periodicals.** The Shenbao and comparable papers carry commodity prices, shipping notices, company announcements, and local market reports, and they are the main source for event coding and for short-run price series in the late nineteenth and early twentieth centuries. They are indexed unevenly, and OCR quality varies by scan, so the same page can be transcribed differently by two readers.

**Enterprise and industry archives.** Factory histories, industry association records, and enterprise archives document output, employment, and prices for specific firms and sectors, especially in the Republican and plan periods. Coverage is concentrated on large or well-documented enterprises, which is the central source of selection in firm-level work.

**Historical administrative geography.** The CHGIS project reconstructs historical administrative units and their boundary changes, and it is the standard tool for matching historical counties to modern counties. Using it is not optional when a panel spans boundary changes: matching by name alone silently merges different territories.

**Republican statistical yearbooks.** Statistical yearbooks and ministry reports from the Republican period give provincial and national series for population, agriculture, industry, and finance. Definitions change between editions and between compiling agencies, and the same series can appear in two yearbooks with different values.

## Variables and definitions

| Variable | Source | Original unit or coding | Harmonization note |
|---|---|---|---|
| Customs trade value | Annual customs returns | Customs taels, then dollars after the currency reform (to confirm against the official codebook) | Convert through the documented exchange series and state the conversion in a table note |
| Tariff revenue | Customs returns; treaty tariff schedules | Customs taels per year | Separate regime change at the late 1920s tariff recovery |
| Grain price | Gazetteers, price gazetteers, newspapers | Local currency per dou or per shi, weights differing by region | Convert to a common grain unit and a common currency before comparison |
| Land-tax quota | Fuyi quanshu, gazetteers | Silver taels per county | Check whether the quota is per household, per cultivated mu, or a county total |
| Registered population | Gazetteers, household registers | Persons or households, by registration category | Distinguish registered population from estimated actual population |
| Ration entitlement | Coupon regulations, unit archives | Physical quantity per person per month | Identify whether the unit of the record is entitlement or issuance |
| Market price under the dual track | Price yearbooks, county price records | Yuan per unit at the market price | Match to the state list price of the same good and the same period |

## Coverage

| Data | Years | Unit | Rough size |
|---|---|---|---|
| Customs annual trade returns | Mid nineteenth century to 1949 | Port by year | Hundreds of ports (to confirm against the official codebook) |
| Gazetteer quotas and prices | Ming to the twentieth century | County by edition | Thousands of counties (to confirm against the official codebook) |
| Newspapers | Late nineteenth and early twentieth century | Page by date | Hundreds of thousands of pages, unevenly indexed (to confirm against the official codebook) |
| Enterprise archives | Mainly twentieth century | Firm by year | Hundreds of firms (to confirm against the official codebook) |
| Historical administrative geography | Ming to the present | County and prefecture | Thousands of units across dynasties (to confirm against the official codebook) |
| Republican yearbooks | 1910s to 1940s | Province by year | Tens of provinces and several agencies (to confirm against the official codebook) |

## Known issues

- Survival is not random. A port with a continuous customs series, a county with a complete gazetteer, or a firm with an archive is systematically larger, more commercial, or better connected than the units that left no record, so any panel built from surviving documents inherits that selection.
- Definitions drift across eras. The same word in a gazetteer can mean a different fiscal category in the Ming, the Qing, and the Republic, and the customs regime changed currency and recording conventions more than once.
- Units drift as well. Silver weights, grain measures, and currencies change between periods and between regions, and a comparison across them needs a documented conversion rather than a single index.
- Administrative boundaries change. Counties are split, merged, and renamed, and a panel matched by name silently assigns the wrong territory; historical geography has to be used to build the correspondence.
- Customs returns follow a trade year that does not coincide exactly with the calendar year, so annual alignment with other series needs an explicit rule.
- OCR and transcription errors concentrate in numbers and in proper names, and the same document can be transcribed differently by two readers; digitized collections also differ in which volumes were scanned, which compounds the selection problem.
- Text-derived variables need a coding manual, a second coder on a subsample, and a stated adjudication rule for disagreements; agreement statistics should be reported rather than asserted.
- Archives are administrative records. They record what the administration needed to know, so quantities are present where the state collected and absent where it did not, and informal market activity is systematically under-recorded.
