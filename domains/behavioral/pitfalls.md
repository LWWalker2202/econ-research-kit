# Behavioral and Experimental Economics: Pitfalls

## What referees ask

1. "What is the minimum detectable effect for your sample size, and how did you choose that sample size?"
2. "Your participants are undergraduates from one university. What makes the result informative about anyone else?"
3. "Could participants have guessed the hypothesis? What evidence do you have against experimenter demand effects?"
4. "The manipulation check failed for part of the sample. Does the treatment work at all, or only for the participants who understood it?"
5. "The pre-registration lists a different primary outcome from the one in the paper. What happened?"
6. "You report three significant results out of twelve outcomes. How do you account for multiple comparisons?"
7. "The stakes are small. Would behaviour change if participants were paid more?"
8. "Participants in your public goods game interacted repeatedly. How do you rule out spillovers across groups or sessions?"
9. "Did attrition or missing data differ across treatment arms?"
10. "The effect is statistically significant, but is it economically meaningful?"

## How to respond

1. Report the minimum detectable effect computed from the design and the planned sample, not after the fact from the realized sample. If the design is underpowered for the effect size the literature suggests, say so, and present the estimate as descriptive rather than as a test. Do not claim a null result means no effect.
2. Be precise about what the sample identifies. A student sample is fine for testing a mechanism that is not supposed to depend on age or education; it is not fine for estimating population prevalence. Report the sample composition, replicate the key result on a broader online panel, and state which claim each sample supports.
3. Treat demand effects as a measurement problem with a design solution. Use a between-subject design in which the hypothesis is not visible, avoid leading instructions, add a suspicion probe and report its distribution, and compare the treatment effect across participants who report different suspicion levels. The strongest version includes a condition in which the treatment is delivered but the outcome cannot be inferred from the instructions.
4. Report the intention-to-treat estimate on the full sample as the headline, then show the estimate for participants who passed the check as a secondary result. If the effect exists only among those who passed, the interpretation is that the manipulation works conditional on comprehension, and the paper should say so rather than dropping the rest.
5. Disclose the deviation at the top of the results section, give the date of the change and whether it was made before or after seeing the data, and report both the pre-registered and the reported specification. A deviation that is declared and justified is survivable; a deviation that is discovered by the referee is not.
6. Report all outcomes that were measured, group them into families specified in the pre-analysis plan, and apply a correction within each family (Bonferroni, Holm, or a false discovery rate procedure). Report the uncorrected and corrected p-values and state which results survive. An index built from the family is usually more credible than the best single outcome.
7. Vary the stakes within the design rather than defending the stakes after the fact. If only the show-up fee was paid, the interpretation of the choice as a preference is weaker. If there was a performance-based payment, report its distribution and its relation to the decisions.
8. Make the group the unit of observation, or model the correlation explicitly. Sessions are usually the right cluster, and with few sessions the same inference problem as few treated provinces applies: report wild cluster bootstrap or randomization inference over sessions.
9. Report attrition by arm as a balance table and estimate the effect of attrition on the outcome using pre-treatment covariates. If attrition differs, present bounds or a Lee-style correction rather than assuming it is random.
10. Compare the effect to a policy-relevant benchmark: what would the effect imply for take-up, for revenue, or for welfare, computed from the estimated magnitude. A coefficient with no benchmark invites exactly this question.

## Where it goes wrong

| Problem | What you see in the output | Fix |
|---|---|---|
| Power calculated for a larger effect than the design can detect | The estimate is large and insignificant, and the confidence interval includes both zero and the hypothesised effect | Pre-specify the minimum detectable effect from the design, and report the confidence interval as the result |
| Manipulation check placed before the outcome | The treated-control gap in the outcome is larger than in the pilot, and the gap in the check is unusually large | Move the check after the outcome and re-run the pilot |
| Outcome index built after seeing the data | The index loads on the outcomes that came out significant | Fix the index and its weights in the pre-registration, or report the full family |
| Attention checks applied asymmetrically across arms | Passing rates differ by arm, and the analysed sample is no longer randomized | Pre-specify the rule, apply it identically, and report intention-to-treat alongside |
| Reporting a within-subject comparison as if it were between-subject | Standard errors are too small and the effect is overstated | Cluster at the participant level, or report the between-subject replication |
