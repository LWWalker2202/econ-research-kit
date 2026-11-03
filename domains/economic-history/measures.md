# Economic history: constructing the treatment variable

In this field the treatment is usually built twice: first as a coding decision about what a historical record means, and then as a variable. The literature has converged on four workable definitions, and the choice among them is a choice about what the historical institution actually varied. Text-derived variables (event indicators, sentiment, classification of gazetteer entries) follow the same logic and need the same documentation.

## Constructing the treatment variable

| Definition | Data source | Implied assumption | When to use |
|---|---|---|---|
| Port opening indicator: one from the year a port enters the treaty-port regime onward | Treaty texts, lists of ports opened to foreign trade, customs establishment dates | Opening dates were set by diplomacy and are unrelated to each port's pre-opening trade trend | Port-level panels with several pre-opening years and staggered openings |
| County fiscal quota: land-tax or labour-service quota per registered household, or the quota divided by cultivated area | Fuyi quanshu, provincial and county gazetteers, imperial statutes | Quotas were fixed at an early administrative settlement and were not revised in response to the outcome | Long-run county comparisons where the quota predates the outcome by a century or more |
| Rationing intensity: share of grain or cloth obtained through official channels, or the coupon entitlement per capita | Plan-era statistical yearbooks, unit archives, coupon regulations | Central allocation followed a national balance plan, not local demand shocks | Plan-era region or household panels where entitlement changes at a dated administrative moment |
| Market-over-plan price ratio: market price of a good divided by its state list price, or the plan share of output | Price yearbooks, price gazetteers, county price records, enterprise histories | The plan share was set administratively and did not respond to the enterprise's own productivity | Firm or region designs that use liberalization as a dose |

Three notes on reading the table. First, the port opening indicator is absorbing and its timing is dated by treaty, so it can carry a modern difference-in-differences design only if the panel starts well before the first opening in the sample. Second, the county fiscal quota is a stock measure of an administrative decision that was revised in some periods and not in others, so the date of the last revision has to be established before the quota is treated as fixed. Third, text-derived variables such as an event indicator coded from a newspaper or a gazetteer entry need a coding manual that states the inclusion rule, the unit of coding, and the adjudication rule for disagreements; without it, the treatment is a researcher's interpretation rather than a documented source.

## Identification assumptions by definition

**Port opening indicator.** The assumption is that, conditional on port and year fixed effects, the diplomatic order in which ports were opened is unrelated to their trade trends. It fails if the ports opened early were the ones already growing fastest, which is a real risk because treaty negotiations followed existing trade. The diagnostic is an event-study plot with pre-opening coefficients for each port group, and a check of whether the opening date correlates with pre-opening trade levels or with distance to the coast and to the treaty powers' shipping routes.

**County fiscal quota.** The assumption is that the quota was fixed before the outcome and was not revised in response to it. It fails when a county's quota was adjusted after a famine, a rebellion, or a tax arrears campaign, which happened repeatedly in the nineteenth century. The diagnostic is a comparison of quota editions across the gazetteer's publication dates, and a restriction to counties whose quota was unchanged over a stated interval.

**Rationing intensity.** The assumption is that entitlement responded to the national grain balance rather than to the local outcome. It fails in years when a province's own procurement target drove both the ration and the labour allocation being studied. The diagnostic is a check of whether the entitlement change coincides with local harvest or procurement shocks, and whether individuals with the same entitlement in different provinces have similar outcomes.

**Market-over-plan price ratio.** The assumption is that the enterprise's plan share was assigned by the plan rather than chosen in anticipation of the reform. It fails when well-connected enterprises obtained a larger above-plan share precisely because they expected to profit from it. The diagnostic is a placebo on pre-reform profitability, and a check of whether the above-plan share changes before the reform date.

## Common construction errors

| Error | Consequence | Correct approach |
|---|---|---|
| Matching historical counties to modern counties by name only | Boundary changes and county mergers put the wrong territory in the panel, so the quota or trade series is attached to the wrong place | Match through historical administrative geography (CHGIS) and record the correspondence explicitly |
| Deflating cross-era prices with one modern price index | The index does not exist before the base period, so the comparison embeds a modern consumption basket | Use a silver or grain-based numeraire for the pre-modern period, and state the conversion explicitly |
| Treating a customs return as a value at constant prices | Customs values are current prices in the currency of the treaty period, and the currency changed several times | Convert through the documented exchange and price series, and show the result at more than one conversion |
| Coding an event indicator from a newspaper without a coding manual | Different coders produce different coverage, and the coefficient reflects the coder rather than the event | Write the inclusion rule and the unit of coding, code a sample twice, and report agreement and the adjudication rule |
| Using plan-era quantities as if they measured consumption | Plan allocation recorded supply, while actual consumption in part ran through informal exchange | State which side of the transaction the source measures, and triangulate with a second source where possible |
