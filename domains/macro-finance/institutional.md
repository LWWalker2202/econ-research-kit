# Macroeconomics and Finance: Institutional Background

## Institutional background

Most credible variation in macro-finance research comes from policy, and policy is chosen in response to the economy it is meant to affect. This file orients the reader to the Chinese institutional setting in which that feedback loop is unusually direct: a central bank that still operates multiple short and medium-term lending facilities alongside a benchmark rate system, local governments whose spending is financed through off-balance-sheet vehicles, and a banking system whose credit intermediation has repeatedly migrated outside the loan book. The purpose is not to settle what counts as exogenous, but to give enough institutional detail that a reader can see which variation a paper is actually using.

Monetary policy implementation changed twice in a way that matters for identification. Before the mid-2010s the main operating targets were the administered benchmark deposit and lending rates, adjusted in discrete steps; quantity targets such as credit quotas and reserve requirements did the heavy lifting, and interbank rates were a by-product rather than an instrument. From 2013 onward the central bank added standing lending facilities, the medium-term lending facility (MLF) and a standing set of open-market operations, so that liquidity and the cost of bank funding began to be managed at the margin. In 2019 the loan prime rate (LPR) was reformed: it was redefined as a quote-based rate anchored on MLF, adding a second and more discretionary pricing layer. For research purposes the consequence is that a "policy rate" series assembled across the two regimes is a construct, and the choice of proxy determines the sample break. Papers that treat any single market rate as the policy stance must say which instrument they take it to represent.

Fiscal policy is where local government behaviour enters the identification problem. After the 2008 stimulus the financing of local infrastructure shifted to local government financing vehicles (LGFVs), which borrowed on behalf of governments and appeared in credit data but not in the formal budget. The 2014 budget law revision and the subsequent debt swap moved part of this stock into officially recognized local government debt, and the regulatory cycle after 2017 tightened the treatment of hidden debt. A fiscal shock identified through infrastructure investment is therefore jointly a credit-supply shock and a shock to expectations about debt recognition. The land-revenue channel runs the other way: property sales fund local budgets, so housing policy is also a fiscal instrument.

Shadow banking and asset management complete the picture. Credit intermediated through wealth management products, trust loans and entrusted loans expanded when loan quotas or regulatory capital bound, and contracted when they did not. The 2018 asset management rules (资管新规) imposed a common set of constraints across products and triggered a visible contraction in off-balance-sheet credit. Social financing is the usual empirical object here, but its composition shifts across the period, so level and composition series support different stories.

Exchange rate and capital account policy form the last block. The mid-2000s reform moved the renminbi to a managed float, the 2015 change to the central parity mechanism was followed by a period of capital flow management, and the currency basket reference introduced afterwards made the daily fix a partly discretionary object. Announcement-based identification in this setting must therefore contend with instruments used jointly and with offshore-onshore price divergence.

Why this matters for identification: the treatment in this literature is typically a policy event or a policy stance, not an individual assignment. That makes the reaction function the first-order threat. Before choosing a design, a paper should be able to state what the policy would have done absent the shock, which instrument carries the shock, and which sector or region is differentially exposed. The designs that survive review tend to use a narrow event window on announcement dates, an institutional break with a clear pre-period, or cross-sectional exposure that is measured before the shock rather than after; the ones that fail use the aggregate outcome to date the shock.

## Timeline

| Year | Event | What makes it useful for identification |
|---|---|---|
| 2008 | Large stimulus package announced | Fiscal shock with a dated announcement and heterogeneous regional exposure |
| 2013 | Standing lending facility and liquidity operations become regular | Beginning of the shift from administered benchmark rates to facility-based liquidity management |
| 2014 | Medium-term lending facility introduced | A second policy price, useful for separating funding-cost shocks from quantity shocks |
| 2015 | Budget law revision and local debt swap | Institutional change in which local debt is recognized, allowing pre/post designs |
| 2015 | Central parity mechanism changed | Dated exchange-rate regime change with a visible offshore-onshore spread reaction |
| 2017 | Regulatory tightening on hidden local debt | Repeated, staggered enforcement across provinces; useful for exposure designs |
| 2018 | Asset management rules issued | Common constraint applied to a dateable set of products; compression of off-balance-sheet credit |
| 2019 | Loan prime rate reformed | Pricing reform that changed the mapping from policy rate to lending rate |
| 2020 | Pandemic-era easing and fiscal expansion | Simultaneous shocks to demand, supply and policy, so it is rarely a clean natural experiment |

## Ready-to-cite paragraphs

Use these where a paper needs one paragraph of institutional context before the identification section; adapt the wording, keep the citations.

Chinese monetary policy over this period combined a gradually liberalized price instrument with a still-active quantity instrument. Benchmark deposit and lending rates were administered and adjusted in discrete steps until the 2019 loan prime rate reform, while liquidity and bank funding costs were managed through standing facilities and open-market operations from the mid-2010s onward. As a result, any series used to proxy the policy stance encodes a choice about which instrument the author believes was operative, and papers should state that choice rather than leave it implicit in a variable name.

Local government borrowing in China moved through three partially overlapping regimes: borrowing through financing vehicles after the 2008 stimulus, recognition and swap of part of that stock into formal local government debt following the budget law revision, and a tightening of the treatment of hidden debt from 2017 onward. Because these regimes overlap in time, an indicator that flags "local government debt" can change meaning within a single sample, and a level series that spans the regimes mixes measurement changes with economic ones.

## Sources

- People's Bank of China, *Monetary Policy Report* (中国人民银行货币政策执行报告), quarterly.
- People's Bank of China, *Statistics* on monetary aggregates and social financing.
- Ministry of Finance, *Public Finance Statistics* and annual budget reports.
- National Bureau of Statistics, annual and monthly macro series.
- Wind Financial Terminal and CSMAR, for market rates, bond yields, credit spreads and local government financing data.
- BIS and IMF country reports, for cross-checking the regulatory and external-sector chronology.
- Bond prospectuses, issue documents and rating reports, for firm-level debt and spread construction.

Do not cite page numbers or document numbers; cite institution, title and year, and mark specific clauses ` (to confirm against the official codebook)` until checked.
