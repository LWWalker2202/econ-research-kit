# Cleaning decision table

Every row of this table is one action that changes the data. Fill it in, show it to the person who owns the research question, and only then run the cleaning code. A cleaning log written afterwards tells you what happened; this table is what turns that into a decision someone approved.

## How to use this file

- Copy this file into the project and rename it to `cleaning-decisions.md`.
- One row per action, in the order the script will run them. Do not fold two actions into one row; splitting them is what makes a change traceable later.
- `Rows in` and `Rows out` come from a dry run, which touches no data:
  `python skills/data-prep/templates/clean_panel.py --decisions`
- `Default` is what the script does if nobody objects. `Your call` is the only column the researcher writes.
- An action that is not in the table does not happen. If the code does something the table does not list, the code is wrong.

## The six actions

| # | Action | Rows in | Rows out | Touched | Default | Your call |
|---|---|---|---|---|---|---|
| 1 | Drop exact duplicate rows | | | rows | drop the later copy | |
| 2 | Drop rows missing a key field | | | rows | drop, log the rate first | |
| 3 | Report panel gaps, fill nothing | | | cells | report only | |
| 4 | Winsorize ratios at 1 and 99 percent | | | values | clip, keep the row | |
| 5 | Harmonise the unit in code | | | rows | add a new column, keep the old | |
| 6 | Flag the definition drift | | | rows | add a vintage column | |

## What to do with each row

- **Accept**: write `ok` in `Your call`. The script's default stands, and the log will record the count.
- **Change**: write the rule you want instead, in one sentence with a number in it. "Winsorize at 5 percent" is a rule; "be careful with outliers" is not.
- **Defer**: write `open:` and the reason. An open row must be closed before the estimation stage, otherwise the sample is whatever the default produced.
- **Never** delete a row to make the table look clean. A row you removed from the table is a change nobody will find again.

## Worked example

Run the dry run once and copy the counts across: the synthetic panel is seeded, so the counts are exact and a rerun reproduces them. Then change one row on purpose, for example winsorize at 5 percent instead of 1 percent, and check that the count in `Touched` moves. If nothing moves, the row was decoration rather than a decision.

## What this file is not

- It is not the cleaning log. The log is written by the script after the run; this file is signed off before it.
- It is not a substitute for reading the codebook. The drift row in particular comes from the codebook, not from the data.
- It is not a place to hide a judgement. Every row has a number in it, and a number can be checked.
