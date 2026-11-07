# Feasibility memo: environmental inspection and manufacturing investment

Worked example for `skills/feasibility/`. The province, the campaign, and every dataset below stand for a real project; no figure in this memo is a finding, and the years, lead times and cost figures below are the ones a real project would confirm against its own documents before circulating the verdict.

## Question (four slots)

| Slot | Content |
|---|---|
| unit | manufacturing firm-year in one province, years 2015 to 2019 |
| treatment variable | inspection intensity in the firm's prefecture in the campaign year, built from the published inspection waves and the count of public case notices naming manufacturing firms |
| outcome | firm investment, measured as the change in fixed assets net of depreciation, scaled by the pre-period capital stock |
| comparison | firms in prefectures where the same wave ran but no case notice was issued, plus pre-campaign years in the treated prefectures |

The claim, if the design holds: within one province, firms in prefectures named in the inspection case notices cut investment relative to firms in prefectures inspected but not named, in the year of the campaign.

## Source of variation

The province schedules the inspection waves, and the case notices follow a published checklist rather than the investment behaviour of the firms inspected. Variation therefore comes from the timing and size of the wave that reaches a prefecture. The identifying assumption is that the wave is unrelated to pre-existing investment trends within the province.

## Data access

| Dataset | Access route | Lead time (weeks) | Responsible |
|---|---|---|---|
| Firm survey above the size threshold | university library subscription, then a written application to the survey office | 10 | project PI |
| Business registration records | provincial market regulation bureau, written request under the open-data rules | 4 | research assistant |
| Inspection waves and case notices | provincial environment department, published archive | 2 | research assistant |
| Prefecture statistical yearbook | library holdings for the province | 1 | project PI |

Lead times are planning assumptions taken from earlier requests; confirm each one with the office named in the row before the review date.

## Data coverage

| Dataset | Unit | Treatment variable | Outcome | Comparison |
|---|---|---|---|---|
| Firm survey above the size threshold | present | missing | present | present |
| Business registration records | present | missing | proxy | present |
| Inspection waves and case notices | proxy | present | missing | present |
| Prefecture statistical yearbook | missing | proxy | proxy | present |

`present` means the field is measured directly in the dataset, `proxy` means it is measured by a variable of the same sign but a different magnitude, and `missing` means the dataset cannot carry the field at all. The outcome is a proxy in the registration records, because gross capital formation there mixes investment with entry.

## Cost

| Stage | Person-weeks | Compute hours |
|---|---|---|
| Cleaning and matching | 6 | 0 |
| Estimation | 3 | 40 |
| Writing | 4 | 0 |

## Stop criteria

- If the firm survey cannot be obtained within 10 weeks of the review date, stop: the outcome is measured directly only in that source.
- If fewer than 3 case notices name manufacturing firms in the province during the campaign year, stop: there is no treated group to compare with.
- If the minimum detectable effect is above 0.05 of the pre-period investment mean, go with reduced scope: report the direction of the effect and drop the heterogeneity analysis.
- If the size threshold of the firm survey changes inside the estimation window, stop: the outcome comparison then picks up a coverage change rather than an investment response.

## Verdict

Verdict: go with reduced scope

Binding constraint: the size threshold of the firm survey may change inside the estimation window. If that change is confirmed for 2019, the outcome and the treatment variable can no longer be measured on the same frame, and the project stops. Until the threshold history is checked, the scope is firms above the threshold in pre-campaign years only, with the inspection wave serving as the treatment and the prefecture as the comparison level.

## Review date

2019-03-15, before any cleaning code is written; the memo is re-read at the review date, and a triggered stop criterion is acted on the same day.
