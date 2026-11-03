# Teaching: master's level

## How to use this at this level

A master's student should be able to change the template, not only fill it in. That means four concrete capabilities: adjusting the sample restriction and the variable definitions to fit the question while stating what the adjustment changes; deciding whether the identification strategy survives its own strongest objection; running the complete replication package; and reporting the result without overclaiming.

Changing the template means reading its assumptions, saying which one your question violates, and modifying the step that depends on it. It does not mean rewriting the workflow. The sequence of steps is the same at every level; what changes is how much of it you can defend on your own.

At this level the binding skill is identification judgment. You should be able to name the two or three threats that would kill the design, say which robustness check detects each one, and know in advance what result would make you abandon the project. A thesis that reports a coefficient and lists five robustness checks without saying which threat each one addresses is not yet doing identification; it is demonstrating that the software runs.

The second deliverable is the replication package. Raw data or access instructions, code that goes from raw data to the final tables in one command, a README a stranger can follow, and a table-to-code map. If the package does not run on another machine, the thesis is not finished.

## Which skills to use

| Skill | When to use | What to watch at this level |
| feasibility | Before committing to a thesis topic, to test whether the data and the comparison can carry the question | Set a kill criterion in advance: what result or data problem ends the project |
| identification | To choose the design and to stress-test it before estimation | Name the strongest alternative explanation and the check that distinguishes it from yours |
| data-prep | To build the analysis sample and reconcile every restriction | Every sample restriction is an assumption; write it down and test its sensitivity |
| estimation | To run the baseline, the heterogeneity analysis, and the checks the identification section promised | Report the full set of specifications, not the winning one |
| tables-figures | To produce the tables and figures the paper actually cites | Numbers in the text must trace to a table cell |
| report | To build the replication package a reader can rerun | One command, one README, a table-to-code map |
| writing | To frame the contribution and place the result against the literature | The contribution is the identification plus the data, not the coefficient |
| review | To read your own draft as a referee before submission | Simulate two referees: one attacks the design, one attacks the measurement |

## What not to do

1. Do not add control variables to fix endogeneity. Each added control changes the estimand, and post-treatment controls change it in a direction you cannot sign; if the design does not hold without the control, it does not hold with it either.
2. Do not treat robustness checks as a checklist. Each check exists to rule out a specific threat; a check that rules out nothing is a table that pads the appendix and invites the referee to ask what you were hiding.
3. Do not hand in a replication package that only runs on your machine. Absolute paths, manual edits, and a data file someone else cannot obtain are the three most common failures; fix them before the defence, not after.
4. Do not write the paper before the tables are frozen. Prose written around provisional numbers has to be rewritten anyway, and the rewriting is where numbers stop matching the output.
5. Do not treat a mechanism variable as a control. Hours, occupation, and firm size are outcomes of many of the treatments labor papers study; putting them on the right-hand side usually removes the effect you are trying to explain.
