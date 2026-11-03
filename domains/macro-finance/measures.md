# Macroeconomics and Finance: Constructing the Treatment Variable

## Constructing the treatment variable

In this field the treatment is rarely an individual assignment. It is a policy stance, a policy announcement, a regulatory break, or a macro shock, and the unit of analysis is usually a region, a bank, a firm or a bond. That changes what "constructing the treatment" means: the task is to date the shock, measure its surprise or its exposure, and argue that the variation is not simply the business cycle. Three families of constructs cover most published work: high-frequency surprises around announcement windows, narrative or episode coding from policy documents, and differential exposure designs in which an aggregate policy is interacted with a pre-determined measure of who is exposed.

The high-frequency surprise is the most defensible construct when a genuine announcement exists, and the least defensible when it is imported from a market that does not price the policy. The measure is the change in a policy-sensitive rate, yield or exchange rate inside a window narrow enough that other news is unlikely to dominate, with the window documented in the appendix. The narrative approach instead reads policy documents and contemporaneous commentary to date and characterize the stance: the test is whether the coder could have made the same call before the outcome was observed, and whether two independent codings agree on the dates. Exposure designs start from an aggregate event and exploit heterogeneity: the share of local debt intermediated by financing vehicles, bank dependence of a firm, foreign-currency liabilities, land-revenue dependence of a city. Their credibility rests entirely on the exposure being measured before the shock and being plausibly unrelated to its timing.

A fourth construct, the structural break dummy, is common for regulatory reforms: the 2018 asset management rules, the 2019 loan prime rate reform, the 2015 debt swap. It is easy to construct and hard to defend, because the break is dated by the reform while the anticipation and the transition are not.

| Construct | Data source | Implied assumption | When to use |
|---|---|---|---|
| High-frequency surprise in an announcement window | Intraday or daily money-market rates, bond yields, exchange rate; announcement calendar from the central bank | The market prices the surprise inside the window and orthogonal news is small or controlled | The policy has a dateable announcement and the instrument is traded |
| Narrative or episode coding | Monetary policy reports, regulatory documents, contemporaneous press, central bank speeches | The coder recovers the intended stance without using the outcome; coding is transparent and replicable | The stance is communicated in documents and the timing is documented |
| Differential exposure to an aggregate shock | Pre-period shares: financing-vehicle debt, bank credit dependence, FX liabilities, land revenue | Exposure is pre-determined and affects the outcome only through the shock | A national policy exists but implementation or incidence differs across units |
| Reform dummy with pre and post periods | Reform date from the official publication | No other contemporaneous change differentially affects treated units | The reform is sharp and there is a credible pre-period with placebo outcomes |

## Identification assumptions by definition

**High-frequency surprise.** The window must be narrow enough that the surprise dominates, and the mapping from the rate change to the policy surprise must be argued rather than assumed. If the announcement date is also a data release date, the window contains two signals, and the paper needs either a decomposition or a robustness window.

**Narrative coding.** Two assumptions carry the design: that the coder did not see the outcome, and that the policy stance is identifiable from the documents. Both are checkable — report the coding protocol, keep the coding before the outcome sample is assembled, and have a second coder cover a subsample.

**Differential exposure.** The exposure measure must be fixed before the shock, must not be a function of the outcome trend, and must satisfy a relevance condition: units more exposed should show a larger first-stage movement in the intermediate variable the policy acts on. Weak relevance turns the design into a difference in differences with no treatment intensity.

**Reform dummy.** Parallel pre-trends are necessary but not sufficient; the reform must be the only differentially relevant change on that date, and placebo outcomes unrelated to the reform should be flat.

## Common construction errors

| Error | Consequence | Correct approach |
|---|---|---|
| Dating the shock by the outcome, for example by locating the peak of credit growth | The shock is mechanically correlated with the dependent variable and leads are contaminated | Fix the date from an official announcement or publication and put the full date list in an appendix |
| Treating benchmark rate changes as exogenous to the outlook | Estimates absorb the central bank's reaction to the economy and the sign can flip | Isolate the surprise component, or use episodes in which the stance was communicated in advance |
| Measuring exposure after the shock, for example classifying hidden debt from a later regulatory list | Exposure is endogenous to the outcome and to expectations about recognition | Measure exposure in a base year before the shock and report its stability across adjacent years |
| Splicing instruments across regimes, for example one market rate before 2015 and another after | A regime break is estimated as a policy effect | Split the sample, report both series, or use an instrument available throughout with a documented splice |
| Aggregating firm data to the province without weights, or the reverse | Aggregation bias and standard errors computed at the wrong level | Run the design at the level where the policy acts, show weighted and unweighted results, and cluster at the policy level |
