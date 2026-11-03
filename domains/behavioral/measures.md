# Behavioral and Experimental Economics: Manipulation and Measurement

## Constructing the treatment variable

In this field the treatment is a manipulation, and it is defined by assignment rather than by exposure. The paper should state the construction, the exact wording of the stimulus materials, and the point in the session at which the manipulation was delivered. Four constructions cover most designs.

| Construction | What varies | Data source | Implied assumption | When to use |
|---|---|---|---|---|
| Binary between-subject assignment | treatment versus control condition | Assignment log written by the software | Randomization works and attrition is not differential | One dimension is manipulated and the contrast is the object of interest |
| Dose or intensity | A continuous level such as endowment, tax rate, or number of rounds | Assignment log with the level recorded | Response is monotonic in the dose and the delivered dose equals the designed dose | Estimating a marginal effect rather than a binary contrast |
| Framing or information | Labels, feedback, social comparison, or a belief update | Session script and stimulus materials | The treatment changes beliefs rather than payoffs | Testing a mechanism that is supposed to run through beliefs |
| Within-subject parameter variation | Price lists, budget sets, or piece rates presented in sequence | Decision records per participant | No order effects and no learning across rounds | Estimating preference parameters for risk, time, or labor supply |

The manipulation check is part of the design, not a robustness afterthought. Do four things. Pre-register the check, its wording, and the threshold that counts as a successful manipulation. Place the check after the outcome variables so that answering it cannot prime the outcome. Report the treated-control difference in the check with an effect size, not only a p-value. Report what happens to the main estimate when participants who fail the check are excluded, and keep the full-sample estimate as the headline.

Outcome variables need the same care, because the same construct can be measured in ways that carry different biases.

| Measure type | Example | Advantage | Direction of measurement error |
|---|---|---|---|
| Incentivized choice | BDM willingness to pay, real-effort output | Incentive compatible, observed rather than reported | Noise if stakes are small, but no systematic bias |
| Scale | Likert items on trust or satisfaction | Cheap and covers latent constructs | Acquiescence bias, ceiling effects, coarse resolution |
| Implicit measure | Response time, implicit association task | Less sensitive to experimenter demand | Noisy, low test-retest reliability |
| Behavioural trace | Take-up, clicks, session logs | Unobtrusive, no self-report | Confounded by task and interface design |
| Exit survey | Demographics, expectations, prior experience | Provides controls and balance checks | Self-report bias, differential item interpretation |

## Identification assumptions by definition

**Binary assignment.** Randomization gives identification within strata, so the assumptions are that the randomization was implemented as designed and that attrition is unrelated to the treatment. Report a balance table on pre-treatment covariates, the randomization method, and the attrition rate by arm. If randomization was stratified by session or by platform, include strata fixed effects.

**Dose or intensity.** Monotonicity is the substantive assumption: a higher dose should move the outcome in one direction, and saturation is a finding rather than a nuisance. The check is whether the delivered dose equals the designed dose, which requires recording what each participant actually saw and received, not only what the script intended.

**Framing or information.** The treatment is supposed to work through beliefs, so the paper has to measure the belief. If the frame also changes payoffs, it is not an information treatment and the label is wrong. The relevant falsification is whether a purely payoff-equivalent relabelling produces the same effect.

**Within-subject variation.** Order effects are the identification threat: a participant who sees the high price first may anchor. Randomize the order, test the order by treatment interaction, and report it. Learning across rounds is a separate problem and needs either a practice round excluded from the analysis or a between-subject design.

**Outcome measure validity.** Whatever the construction, identification also requires that the outcome measure measures the construct. Incentive compatibility matters when the paper claims willingness to pay; scale reliability matters when the paper builds an index; hypothetical bias matters when the choice is not paid. Report the elicitation mechanism, the payment rule, and the reliability of any scale.

## Common construction errors

| Error | Consequence | Correct approach |
|---|---|---|
| Using the manipulation check as the treatment variable | The coefficient reflects perception, which is endogenous to the participant, rather than the randomized condition | Use assignment as the treatment and the check as a diagnostic |
| Fielding the manipulation check before the outcome | Answering the check primes the construct and inflates the treatment effect | Put the check after the outcome or in a separate block |
| Interpreting a hypothetical choice as willingness to pay | Hypothetical bias overstates stated willingness to pay | Use an incentive-compatible mechanism or label the result as stated preference |
| Within-subject design without randomizing presentation order | Carryover and anchoring contaminate the comparison | Randomize order and report the order by treatment interaction |
| Dropping participants who fail the check | Selection on a post-treatment variable, and the estimate no longer has a design-based interpretation | Report intention-to-treat on all participants and present the check separately |
