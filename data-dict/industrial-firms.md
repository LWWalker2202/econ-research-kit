# Chinese Industrial Enterprises Database (CIED)

> Where this sits: stage 3 (data). A dictionary entry is usable only when five fields are filled: unit of observation, coverage (years and regions), the key variables with their exact definitions, the access route, and the known defects. Anything still marked `[待核实]` / `[verify]` is a question for the person who owns the data, not a fact you may quote.

## Basic information

| Item | Detail |
|---|---|
| Full name (Chinese) | 中国工业企业数据库 |
| Full name (English) | Chinese Industrial Enterprises Database |
| Abbreviation | CIED |
| Maintainer | Compiled from the annual above-scale industrial enterprise survey of the National Bureau of Statistics of China (NBS) |
| First year | 1998 |
| Frequency | Annual; micro data are widely circulated for 1998 to 2013 |
| Unit of observation | Enterprise (legal entity) |

## Variables

| Variable name | Chinese name | Meaning and definition | Typical values |
|---|---|---|---|
| `id` | 企业法人代码 | Enterprise legal-entity code; the identifier used to link an enterprise across years | Alphanumeric code, not stable across years |
| `year` | 年份 | Reference year of the record | 1998 to 2013 in the commonly used files |
| `province` | 省地县代码 | Province (and city, county) of the enterprise, stored as administrative codes in the raw files | GB/T 2260 numeric code; split into province, city and county components |
| `industry` | 行业代码 | Four-digit industry code of the main product | GB/T 4754 code; version differs before and after the break [verify] |
| `ownership` | 登记注册类型 | Registration type, used to separate state-owned, private, foreign and other firms | Categorical code |
| `employees` | 从业人员数 | Total number of employees at year end | Count, in persons |
| `total_assets` | 资产总计 | Total assets at year end | RMB, nominal |
| `fixed_assets` | 固定资产净值 | Net value of fixed assets | RMB, nominal |
| `output` | 工业总产值 | Gross value of industrial output | RMB, nominal |
| `revenue` | 主营业务收入 | Main business revenue, the variable that defines the above-scale threshold | RMB, nominal |
| `export` | 出口交货值 | Value of export deliveries | RMB, nominal; missing in some years |

Raw files carry Chinese column headers. The English names above are the conventional names used in cleaned versions, so match them against the data dictionary of the exact version you hold rather than assuming a one-to-one mapping.

## Known issues

- Coverage threshold changed in 2011. Above-scale meant main business revenue of at least RMB 5 million up to 2010 and at least RMB 20 million from 2011, so the sample is not a continuous panel and part of the observed entry and exit is a definitional artefact rather than firm dynamics.
- Industry classification changed. Enterprise industry codes follow the 2002 version of GB/T 4754 up to the break and the 2011 version afterwards [verify], so four-digit industries are not directly comparable across the two periods and must be mapped through a conversion table.
- The 2004 record is an economic-census year, and key items such as gross industrial output and value added are missing or measured differently [verify]. Do not use 2004 as a normal wave without checking each variable.
- Some financial items disappear in some years. Value added stops being reported in the later part of the period, and export delivery value is missing in several years [verify], so productivity and export measures cannot be computed for every year.
- Legal-entity codes are not stable across years. Linking firms over time usually requires matching on name, address and telephone number, and the match remains imperfect; report the match rate.
- Duplicate and erroneous records are common. The same enterprise can appear more than once in a year, some values are reported in thousand yuan instead of yuan, and extreme outliers exist. Trim by explicit rules and report them.
- The series ends in 2013. Comparable micro data after 2013 are not released, so the database cannot support designs that need a post-2013 outcome without a second source such as the annual industrial surveys from other providers.
- Enterprise status matters. The files include enterprises that are under construction, suspended or in bankruptcy, which should be filtered before computing any ratio; the filter rule should be reported.

## Access

| Item | Detail |
|---|---|
| Entry type | Not public; institutional access or purchase |
| Channel | The National Bureau of Statistics of China (NBS), university libraries, and research institutions that redistribute a cleaned version |
| Institutional account | Required; access is normally through an institutional licence or a data-sharing agreement |
| Cost | Paid or subscription-based for commercial vendors; some university licences cover academic use |
| Ethics review | Not required for firm-level administrative data, but firm identifiers are confidential and must be handled under the agreement |
| Usage agreement | No resale or redistribution, cite the source and the cleaning version used, and state the cleaning rules in the replication package |
