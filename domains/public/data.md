# Public economics: data sources

Public finance work in China is constrained less by the number of datasets than by the fact that the fiscal data a researcher needs are scattered across budget documents, statistical yearbooks, and administrative files that were not built for research. The practical rule is to build the fiscal variable from the most disaggregated public document available, then validate it against a second source at a higher level of aggregation. This file lists the datasets used most often, the variables with their original names, the coverage each source offers, and the problems that recur across studies.

## Data sources

**China Finance Yearbook.** Annual provincial and national fiscal aggregates: revenue by tax, expenditure by function, and transfers received. It is the workhorse source for provincial panels and the natural cross-check for county data.

**County and prefecture fiscal statistics.** The China County Statistical Yearbook and the prefecture-level fiscal tables in the China City Statistical Yearbook provide expenditure and revenue by locality. These are the main source for county-level panels, and their main weakness is that different volumes report slightly different categories.

**National Tax Survey.** Firm-level tax and financial records collected by the tax administration. Access is restricted, and the sample is not a random draw of firms; it is nevertheless the standard source for firm tax burden measured from tax returns rather than from financial statements.

**China Migrants Dynamic Survey (CMDS).** Repeated cross-sections of migrant workers with income, employment, and social insurance participation. It is the main survey source for questions about how local fiscal and social policy reaches migrants.

**Provincial and municipal budget disclosure.** Final accounts and budget reports published by finance departments. Coverage and format differ across localities, which is itself a source of variation for transparency studies.

**Debt and audit documents.** Audit reports and debt-resolution documents published at the provincial level. These are the only public source for off-budget obligations, and they are reported at irregular intervals.

**Minimum living guarantee statistics.** Ministry of Civil Affairs annual statistics on recipients and expenditure, plus provincial implementation documents that determine local standards.

## Variables and definitions

| Variable (original name) | Chinese name | Definition | Typical values |
|---|---|---|---|
| general transfer | 一般性转移支付 | Formula-allocated transfers from higher-level government | Yuan per capita, positive |
| earmarked transfer | 专项转移支付 | Transfers tied to a named program or matching requirement | Yuan per capita, positive |
| local fiscal revenue | 地方财政收入 | Revenue retained by the local government | Yuan per capita |
| local fiscal expenditure | 地方财政支出 | Budgetary expenditure by the local government | Yuan per capita, real |
| tax sharing ratio | 税收分成比例 | Share of a tax retained locally | [0, 1] |
| VAT revenue | 增值税收入 | Value-added tax collected and shared | Yuan, positive |
| minimum living guarantee standard | 低保标准 | Monthly or annual benefit level set locally | Yuan per month |
| social insurance contribution rate | 社保缴费率 | Employer and employee contribution as share of wage | Percentage |
| local government debt balance | 地方政府债务余额 | Outstanding interest-bearing local debt | Yuan; on- and off-budget differ |
| budget transparency index | 财政透明度指数 | Score from disclosure of budget documents | Index, higher is more transparent [verify] |

## Coverage

| Data | Years | Level | Sample size order |
|---|---|---|---|
| China Finance Yearbook | Annual volumes, year range varies by table | Province and nation | All provinces |
| China County Statistical Yearbook | Annual volumes, county fiscal tables | County | Several thousand counties |
| China City Statistical Yearbook | Annual volumes | Prefecture | Several hundred prefectures |
| National Tax Survey | Restricted access, periodic | Firm | [待填] |
| China Migrants Dynamic Survey | Repeated waves | Individual | About the hundred-thousand level per wave [verify] |
| Budget disclosure documents | Fiscal year documents | Province and municipality | All provinces, coverage uneven |
| Minimum living guarantee statistics | Annual | Province and county | All provinces |

## Known issues

1. Fiscal categories are revised repeatedly, so a series built from yearbooks has breaks that are not documented in the yearbook itself; the year of a category change must be checked against the underlying reports.
2. Budget versus final account figures differ, sometimes by a lot, because mid-year adjustments are common. A paper must say which one it uses and why.
3. Transfer data are often reported as a total, with the general and earmarked split available only in some years.
4. County fiscal data are sometimes imputed or back-filled by the yearbook compiler, which matters for panels that treat the county as the unit.
5. Off-budget debt is not observed in any routine statistical source; audit documents give snapshots, not a panel.
6. Survey weights and coverage in the migrant survey do not match the local population register; comparisons across waves require attention to the sampling frame [verify].
7. Local budget documents are published in formats that change, so a transparency index built by scraping is sensitive to the scraper, not only to the government [verify].
8. Firm tax records and financial statements measure tax burden differently, and studies that mix the two sources can produce an apparent change that is measurement, not behavior.
