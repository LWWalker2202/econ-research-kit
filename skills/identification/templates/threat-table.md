# Threat table

Every row of this table is one way your design could be wrong. You fill one row per threat, name the test that would catch it, and write what result would sink the design. A memo that says "there may be endogeneity" has not thought about it; this table is what thinking about it looks like.

## How to use this file

Copy it to your project as `threat-table.md`. Fill the first four columns before you run anything. Add a row the moment a referee, a classmate or your own reading suggests a new threat. Leave the fifth column empty until you know the answer, and write `open` in it when you do not.

The file is meant to sit next to `identification-memo.md`. The memo is the argument; this table is the checklist behind the argument.

## The five columns

| Column | What goes in it |
| --- | --- |
| Threat | One sentence naming the alternative explanation, not the word for a category. Write “better-performing firms were inspected first”, not “selection”. |
| Mechanism | How the threat would produce the pattern you find. Name the variable that moves and the direction it moves the coefficient. |
| Test you can run | One test that exists in your data, with the sample and the variable it uses. If you cannot name the sample, you do not have a test. |
| What result would sink it | The pattern that would tell you the threat is binding. Write the sign and the order of magnitude, not “a large effect”. |
| Verdict | `cleared`, `weakened`, `binding` or `open`. Fill it only after the test has run. |

## Worked example

| Threat | Mechanism | Test you can run | What result would sink it | Verdict |
| --- | --- | --- | --- | --- |
| Larger firms were inspected first | Inspection targets high-emission firms, and larger firms also invest more, so the post-2016 rise in investment could be size, not regulation | Re-estimate on the 2015 size quartile, and on a sample trimmed to firms within 20 per cent of the median | The coefficient keeps its sign and stays within one standard error of the baseline across all four quartiles | cleared |
| Localities anticipated the inspection | Provinces cut production before the inspection team arrived, so the effect is anticipation rather than enforcement | Event-study coefficients for the two years before the first inspection batch | A pre-trend coefficient above 0.02 in absolute value | weakened |
| Pollution monitors were relocated | Unfavourable monitors were moved after the campaign, so measured pollution falls without real abatement | Count monitors by county-year from the monitoring station list | The number of monitors per county falls in treated counties in 2017 | binding |

## What to do with each row

- `cleared`: one line in the robustness section, with the number.
- `weakened`: say what it does to the magnitude, and whether the conclusion survives.
- `binding`: either change the design, or state the claim the design can still support. Do not keep the original claim and add a footnote.
- `open`: this is the first thing you do next, before writing anything else.

## What this file is not

It is not a substitute for `identification-memo.md`, and it is not a place to list threats you have no intention of testing. A table with eight `open` rows is an honest table; a table with eight `cleared` rows and no numbers behind them is a decoration.
