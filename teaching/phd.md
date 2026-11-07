# Teaching: PhD level

## How to use this at this level

Treat the gate as the audit trail a referee will ask for. `gate.py status` at the start of every session; `gate.py pass` only with artifacts on disk and a real answer recorded in the ledger; `--extra` for the work you did beyond the floor of that stage (the floor is a minimum, not a ceiling). Before submission, three machine checks should be green: `coverage.py` (fifteen project-level items), `verify_chain.py --project .` (cleaning rows to regression sample to reported decimals), and `crosscheck.py` (a second implementation re-estimating the baseline). The panel is the same information in the interface; the ledger is the durable record. If the two ever disagree, the ledger is right.
At the PhD level the object of work is not the template but the procedure. The question is not "how do I use this workflow well" but "is this the right sequence for this question, and what should be deleted, reordered, or added". The templates encode a default choice at every step; your job is to know why each default exists, when the field's best practice has moved past it, and what your design assumes that the default does not.

Three things separate this level from the master's level. First, domain knowledge: you are expected to know the institution well enough to spot a variable that measures the wrong thing, and to know which reforms are plausibly exogenous rather than merely convenient. Second, the referee's eye: you read your own draft the way the most hostile competent referee will, and you answer the strongest objection before it is raised. Third, reproducibility and submission as a craft: a package another person can run, a paper that states its own limits, a cover letter that does not oversell.

The workflow is then a set of defaults to be redesigned rather than followed. If the question needs a pre-registration, add it. If the feasibility step should be a two-week pilot rather than a desk check, change it. If the estimation step should include a specification curve rather than a table of five columns, rebuild it. The skills directory is a starting point for that redesign, not a ceiling.

## Which skills to use

| Skill | When to use | What to watch at this level |
| feasibility | To decide go or no-go, and to set the kill criteria that will govern the project | Write the pilot results down; a feasibility judgment you cannot point to is a wish |
| identification | To design against the strongest alternative explanation, not the most convenient one | State the assumption in the form a referee can falsify, and name the test that would falsify it |
| data-prep | To establish provenance, versioning, and the exact sample restriction | Every restriction is a choice that a referee will ask about; test it at the boundary |
| estimation | To run the specification the design implies, plus the sensitivity analysis that maps out the result's fragility | The fragility report matters more than the preferred coefficient |
| tables-figures | To set defaults that make the paper auditable rather than merely attractive | A figure that cannot be regenerated from the package is decoration |
| report | To produce a package that a stranger rebuilds and a verifier can audit | Include the provenance of each input and the version of each processing step |
| writing | To place the contribution and to write the limitations the paper can defend | The limitations section is a claim about what you know, not a disclaimer |
| review | To simulate the referee report before submission, and to answer one afterwards | Read as three referees: one on identification, one on measurement, one on external validity |

## What not to do

1. Do not follow the workflow as a checklist. The steps exist to be reordered and, where the question demands it, replaced; running them in default order because they are in default order is the failure this level is supposed to correct.
2. Do not delegate identification to the template. The template encodes somebody else's assumption about which comparison is credible; if you cannot state that assumption yourself, the design is not yours.
3. Do not let the data substitute for the institution. A variable that is measured cleanly but means the wrong thing produces a precise answer to the wrong question, and no amount of robustness checks fixes it.
4. Do not submit without a referee simulation. The report you write for yourself should be harsher than the one you will receive; the objections you leave unaddressed become the revision.
5. Do not publish a package you have not rebuilt on a clean machine. The first run on a fresh environment is the only test that counts, and it should happen before submission, not during revision.
6. Do not write the limitations section as a ritual. If you cannot say what the estimate would look like under the alternative assumption, you have not finished the design.
