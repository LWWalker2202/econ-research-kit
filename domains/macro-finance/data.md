# Macroeconomics and Finance: Data

## Data sources

The data landscape for Chinese macro-finance work is dominated by three kinds of source: commercial aggregators that resell official and market series, official statistical releases that define the concepts, and security-level records that allow spreads and leverage to be built at the firm or bond level. None of the three is complete, and the typical paper stitches them together, so the first practical task is to decide which source is authoritative for each concept and to keep the stitching visible in the replication package.

Commercial terminals are where most researchers start. Wind Financial Terminal carries money-market rates, government and policy-bank bond yields, credit bond yields, issue-level details and a large set of macro series; CSMAR covers listed firms, their financial statements, and substantial parts of the bond and loan data used in firm-level work. Commercial convenience has a cost: series are revised, coverage of the bond market changes as issuance rules change, and the identifier scheme is not stable across time, so the extract date and the vendor version of each series should be recorded.

Official statistics define the concepts the paper will be judged on. The People's Bank of China publishes monetary aggregates, social financing, and the policy documents that date the instruments; the Ministry of Finance publishes fiscal accounts and the local government debt stock; the National Bureau of Statistics publishes output, investment, prices and the housing indicators. Concept changes are the main hazard: the coverage of social financing, the treatment of local debt, and the definition of the housing price index have each been revised at least once in the period, and a level series that ignores a concept change will attribute the revision to economics.

Security-level data make spreads and leverage measurable. Bond issue documents, prospectuses and rating reports give coupon, maturity, guarantee, issuer industry and rating; matched Treasury or policy-bank yields give the risk-free benchmark for a spread. Rating actions and default or restructuring events need to be dated from announcements, not from the vendor's current status field, because the current field overwrites history. For city-level housing, the commercial city price indices differ in coverage and in how they treat new versus second-hand units; the official index is the narrower but better documented measure.

## Variables and definitions

| Variable (English original) | Definition | Source |
|---|---|---|
| Policy rate proxy | Short-term money-market or facility rate used to represent the stance, with the instrument stated | PBOC operations, Wind |
| Interbank repo rate | Seven-day pledged repo rate, used as a market-implied funding cost | Wind, CSMAR |
| Medium-term lending facility rate | Rate on the central bank's medium-term lending facility, used as a policy price | PBOC announcements, Wind |
| Loan prime rate | Quote-based lending rate, in force after the pricing reform | PBOC, Wind |
| Benchmark deposit rate | Administered one-year deposit rate, the pre-reform policy price | PBOC, Wind |
| Credit spread | Yield on a corporate or local government bond minus a matched-maturity government bond yield | Wind, bond issue records |
| Leverage ratio | Debt to assets or debt to output, with the numerator defined explicitly | CSMAR, PBOC flow of funds |
| Social financing aggregate | Total financing to the real economy, level and increments | PBOC statistics |
| Local government debt | Recognized local government debt, and separately financing-vehicle liabilities | Ministry of Finance, Wind, rating reports |
| Economic policy uncertainty index | Text-based index of policy uncertainty, with the underlying newspaper set recorded | Published index, reconstructed from sources |
| City house price | Commercial or official city-level price index, new or second-hand units stated | NBS, commercial vendors |

## Coverage

| Data | Years | Level | Sample size magnitude |
|---|---|---|---|
| Money-market and policy rates | From the mid-2000s, with the instrument changing across the period | Daily | Continuous series ` (to confirm against the official codebook)` |
| Government and credit bond yields | From the late 2000s, better covered after the market expanded | Daily, bond level | Tens of thousands of bond-months ` (to confirm against the official codebook)` |
| Listed-firm financials | From the late 1990s onward | Firm-year | Several thousand firms ` (to confirm against the official codebook)` |
| Local government debt and financing vehicles | From the late 2000s, recognition regime changes in the mid-2010s | Province or city-year | About a few hundred cities ` (to confirm against the official codebook)` |
| Fiscal accounts | From the 1990s, with definition changes | Province-year | About thirty provinces ` (to confirm against the official codebook)` |
| City house prices | From the 2000s, coverage expands over time | City-month | About one hundred cities in the official index ` (to confirm against the official codebook)` |

## Known issues

- Series revisions are not versioned by the vendors: an extract taken today will not reproduce a table built two years ago unless the extract date was recorded.
- The policy rate proxy changes identity across the sample; a single spliced series embeds a regime break.
- Bond coverage is truncated where issuance was thin, so cross-sectional samples before the market expanded are selected.
- Rating and default status fields are point-in-time current, not historical; events must be dated from announcements.
- Local government debt has at least two published definitions, recognized debt and platform liabilities, and they are not interchangeable.
- Social financing includes components whose coverage changed; using a level series across a revision attributes the revision to the policy.
- City-level housing indices differ in the treatment of new units, second-hand units and administrative boundaries.
- Fiscal and debt data are reported with lags and occasional restatements; the vintage used should be stated.
- Aggregated province data and firm-level data require an explicit weighting choice, and the choice changes the estimate.
