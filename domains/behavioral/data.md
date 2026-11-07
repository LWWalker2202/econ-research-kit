# Behavioral and Experimental Economics: Data

## Data sources

Experimental data is collected rather than obtained, so the data sources are the recruitment channel, the software that ran the session, and the payment record. The recruitment channel determines the sample and has to be described in enough detail that another team could repeat it: the subject pool, the recruitment message, the screening criteria, and the platform version in the sense of the platform's stated features, not a version number.

Laboratory data comes from university subject pools. Participants are recruited by announcement, by a standing registry, or in class, and sessions are run in a computer laboratory with a fixed number of seats. The software writes an assignment file, a decision file, and a payment file, and the three must be linked by participant identifier before any analysis.

Online data comes from domestic research panels (Credamo 见数 and comparable platforms) and from international platforms (Prolific, MTurk). These provide the participant identifiers, the screening answers, the timing of each page, and sometimes a quality flag. The platform's own data quality flags are not a substitute for attention checks designed into the study.

Reusable materials come from three places. The Open Science Framework hosts pre-registrations, instructions, stimulus materials, and analysis code. The AEA RCT Registry hosts pre-analysis plans for field experiments. Journal replication packages host the data and code of published experiments, and are the fastest way to see how a paradigm was implemented in practice. Chinese experimental data is mostly self-collected, so the share of it that can be reused by others is small; deposit your own materials even when the data cannot be shared.

## Variables and definitions

| Variable (English original) | Definition | Source |
|---|---|---|
| treatment | The randomized condition assigned to the participant | Assignment file |
| contribution | Tokens or yuan contributed to the public account in a public goods game | Decision file |
| bid | Bid submitted in an auction or a BDM procedure | Decision file |
| WTP | Willingness to pay for a good, in yuan, elicited by an incentive-compatible mechanism | Decision file |
| discount rate | Implied annual discount rate from a multiple price list or a convex time budget | Decision file |
| risk aversion | Curvature parameter from a Holt-Laubach or Binswanger task | Decision file |
| loss aversion | Ratio of the loss coefficient to the gain coefficient from a mixed gamble task | Decision file |
| effort | Output on a real-effort task, for example the number of correctly solved sliders | Decision file |
| CRT score | Number of correct answers on the cognitive reflection test | Post-session questionnaire |
| attention check | Indicator for passing the pre-registered attention items | Questionnaire and page timing |
| manipulation check | Participant's report of the intended treatment dimension | Post-outcome questionnaire |
| participant id | Unique identifier linking assignment, decisions, payment, and questionnaire | Recruitment file |

## Coverage

| Data | Years | Level | Sample size magnitude |
|---|---|---|---|
| University laboratory sessions | Continuous | Participant-session | About one hundred participants per study (to confirm against the official codebook) |
| Domestic online panel | Continuous | Participant | About one thousand participants per study (to confirm against the official codebook) |
| International online platform | Continuous | Participant | About one thousand participants per study (to confirm against the official codebook) |
| Field experiment with administrative records | Varies by project | Individual or firm | About one thousand to ten thousand units (to confirm against the official codebook) |
| Open Science Framework deposits | Continuous | Study | Varies; materials only in many cases (to confirm against the official codebook) |
| Journal replication packages | Continuous | Study | Varies by outlet policy (to confirm against the official codebook) |

## Known issues

- Student samples are young, educated, and concentrated in a few universities. Report the age, gender, and major distribution, and do not describe the sample as representative of the Chinese population.
- Online panel composition changes over time, and the same platform can deliver different samples in different years. Record the recruitment date window and the screening filters, and compare the sample to the platform's stated panel profile.
- Attrition differs by treatment arm when the treatment is delivered across multiple waves. Report the attrition rate by arm and test whether it predicts the outcome.
- Translation is part of the treatment. If instructions were translated from English, report the translation procedure and check comprehension with a pilot, because a poorly translated frame changes behaviour.
- Stakes are small relative to income. Report the payment distribution and, where the design allows, vary the stake to show that behaviour is not driven by the show-up fee alone.
- Multiple outcomes are common and are rarely pre-specified in full. Deposit the full instrument and the analysis script so that the reader can see which outcomes were measured and which were reported.
- Participant data are personal data under the Personal Information Protection Law (个人信息保护法). Store identifiers separately from decisions, and state the retention period and who can access the files.
- The session log records what the software displayed, not what the participant understood. Keep the raw page timings and the open-ended responses, because they are the evidence for comprehension and for demand effects.
