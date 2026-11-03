# Macroeconomics and Finance: Pitfalls

## What referees ask

1. "What makes this policy change exogenous to the state of the economy? The central bank responds to growth, and so does your dependent variable."
2. "If the stimulus was announced because credit was collapsing, how do you separate the policy from the cycle it was responding to?"
3. "Your treatment is a province-level exposure measure and your outcome is province-level credit growth. Where is the variation coming from, and why is the same shock not in both?"
4. "The sample spans a change in the policy instrument. Is the estimated effect a policy effect or a change in measurement?"
5. "Announcement days are also data release days in this window. What is left of the surprise once the release is netted out?"
6. "You interact an aggregate shock with an exposure share. What guarantees the exposure was not chosen in anticipation of the shock?"
7. "The effect is large relative to the size of the shock. Can you state the magnitude in terms of the size of the surprise?"
8. "Adding GDP growth to the specification absorbs the estimate. Does the result survive that control, and if not, what does the shock still mean?"
9. "The reform dummy is dated to a policy release. Were expectations not already priced before the announcement, and are there no other reforms of the same period affecting treated units?"
10. "What is the information channel here? If the announcement partly signals the policy rule, the coefficient mixes the stance effect with the signal effect."

## How to respond

1. Separate the two claims: the paper needs a response function story for the timing, and a surprise or exposure story for the variation. Provide a reaction-function table showing what predicts the policy action, and date the shock from the announcement rather than the outcome.

2. Use a narrow window around the announced date, and report the pre-announcement trend. If credit was already collapsing, say so and show that the estimate is not driven by the pre-trend; a placebo date in the pre-period is the direct answer.

3. State the level at which the policy acts and run the design there. If the exposure is a pre-period share, show its stability across adjacent base years and report the first-stage movement in the intermediate variable the policy targets.

4. Split the sample at the instrument change, report both estimates, and show that the sign and the ordering of magnitudes are stable. A specification that pools the regimes must include the regime-specific mapping.

5. Decompose the window: use intraday data if the announcement time is known, or subtract the release-implied surprise using a separate market reaction to the release. Report the window length used and a robustness window.

6. Address anticipation directly: show that the exposure measure is uncorrelated with pre-shock changes in the outcome, and use an earlier base year if the preferred one is contestable. Report results with the exposure measured two and three years before the shock.

7. Report the first-stage magnitude in the paper's units: a one-standard-deviation surprise in the policy rate, and the implied elasticity with respect to that surprise. Then the size of the effect can be judged against the size of the treatment.

8. Report both specifications, and interpret the one that survives: if growth absorbs the estimate, the correct statement is that the effect operates through the cyclical channel, not that the design failed. Do not delete the control to protect the estimate.

9. Test for anticipatory pricing with pre-announcement windows, and list the contemporaneous reforms. If another reform hits the same units in the same period, show that it does not explain the pre-trend, or narrow the window until it is clean.

10. Separate the stance from the signal where possible: use components of the announcement that are not informational, or split announcements into rule-based and deliberative ones, and report whether the effect concentrates in either.

## Where it goes wrong

| Problem | What you see in the output | Fix |
|---|---|---|
| Shock dated by the outcome | Sharp lead effects in the pre-period, or the estimate is sensitive to moving the date by one quarter | Fix the date from the official announcement and place a placebo date in the pre-period |
| Aggregate shock with no exposure logic | City or firm effects are mechanically equal to the aggregate shock and the standard errors are too small | Add a pre-determined exposure measure and cluster at the level of the policy |
| Policy proxy that changes identity | A break in the estimated coefficient at the reform date, or a large change in the first stage | Split the sample, report both proxies, or use a series available throughout |
| Exposure measured after the shock | The measure is correlated with post-shock regulatory classification and with the outcome | Measure exposure in a base year before the shock and report its stability |
| Control set that absorbs the treatment | Coefficient collapses to zero once a cycle proxy is added | Report both and reinterpret the channel rather than dropping the control |
