---
name: literature
description: 文献工序——把「这个缺口是不是真的」写成可核验的文献矩阵与可复现的检索方案。Triggers: 文献综述、找文献、有没有人做过、缺口在哪、literature matrix、literature review、search plan、gap analysis.
---

# Literature

## When to use this

You have a research question in one sentence and you need to answer two things before designing anything: **has someone already done this**, and **what exactly is still missing**. This skill is also what you enter when a referee says "the contribution is not clear" — that sentence almost always means the matrix behind the introduction was never built.

If the question itself is still vague (no unit, no treatment, no outcome, no comparison group), do not start here. Run `python scripts/preflight.py "<your question>"` first; the head of the pipeline is the feasibility gate.

## Inputs

- One sentence of the research question, in the form "X affects Y for U, compared with C".
- A first guess at the two keywords that define the topic (you do not have to be right; the search plan is supposed to be revised).
- If you already have papers: at least three PDFs or citations you have actually opened. Name them.
- The target outlet, if known: the same gap is written differently for a field journal and for a general-interest journal.

## Procedure

1. **Write the search plan before searching.** Run `python skills/literature/templates/search-plan.py "<your question>" --lang en` (add `--out` to choose the path). It writes `search-plan.md` with a three-layer keyword matrix (concept / measure / outcome, each with synonyms), candidate JEL codes, four Boolean strings, and inclusion-exclusion criteria. Fill in the gaps it leaves as `[to fill]`; do not accept the first draft as final.
2. **Search in at least three places.** EconLit or Web of Science for peer-reviewed work, NBER / CEPR / IZA for working papers, and Google Scholar or OpenAlex for forward citations of your two closest papers. Record every string you ran and how many hits it returned in the search log at the end of `search-plan.md`.
3. **Fill the matrix, one row per paper.** Start from `python skills/literature/templates/lit-matrix.md` and keep the six columns. A row is not allowed to be written from the abstract alone: open the paper, and for the design column copy the actual estimator or design from the identification section.
3b. **Or let the kit do the first pass.** `python skills/literature/templates/litsearch.py "minimum wage youth employment" --top 20 --year-from 2000 --lang en` queries Crossref, then enriches every DOI through OpenAlex (abstract, citation count, open-access links) and writes `lit-hits.md`, `lit-hits.csv` and `lit-search.json`. Add `--min-tier A` to keep only the A-tier outlets listed in `skills/literature/journals.json`, or `--sort citations` to surface seminal work. `--from-file lit-search.json` replays the same table byte for byte, and `--verify lit-hits.csv` re-resolves every DOI and fails if any title does not match. This step needs a network connection and anonymised access is rate-limited (a 429 reply means wait, not broken); the plan in step 1 works offline and is still the thing you put in the appendix.
4. **Mark the closest paper.** Exactly one row gets `closest = yes`. If you cannot pick one, the gap is not yet sharp enough to write about — go back to step 1.
5. **Write the gap in one sentence that names the rows.** The shape is "rows 3, 7 and 11 all estimate X on Y but none of them can separate M, because ...", not "few studies have examined ...". A gap sentence with no row numbers is a wish.
6. **Run the mechanical check, then read the matrix again.** `python skills/literature/templates/check_matrix.py lit-matrix.csv --lang en` verifies format and completeness. It does **not** verify that a paper exists or that you read it — that is your job, and step 7 of the acceptance list.

## Outputs (artifacts)

- `search-plan.md` — keyword matrix, JEL candidates, four Boolean strings, inclusion criteria, search log.
- `lit-matrix.csv` — the six-column matrix, one row per paper, with exactly one `closest` row.
- `expected/check-report.txt` style report from the checker, kept next to the matrix as `lit-matrix-check.txt`.
- One gap sentence, written into `identification-memo.md` later as the "why this is new" line.
- If you ran the online search: `lit-hits.md`, `lit-hits.csv`, `lit-search.json` and the appended `search-log.csv`, kept next to the matrix as the record of what the machine found and what you kept.

## Acceptance

- [ ] `search-plan.md` records at least three databases and at least one string per database, with dates.
- [ ] Every row of `lit-matrix.csv` has an identifier you could resolve today (DOI, or venue + year + volume + pages, or a working-paper number).
- [ ] For every row, the design column names the actual design, not "empirical" or "quantitative".
- [ ] Every row's finding states a direction or a magnitude; "significant" alone fails.
- [ ] Exactly one row is marked `closest = yes`, and you can say in one sentence why it is the closest.
- [ ] The gap sentence names at least two row numbers.
- [ ] If `litsearch.py` was used, every row you kept has been opened at least to the abstract, and the hits you dropped are still visible in `lit-hits.md` (dropping a paper without a reason on record is how a convenient gap gets invented).
- [ ] You have personally opened every paper in the matrix. No row may come from a citation you only saw quoted somewhere else; if it did, mark it `[to verify]` and do not cite it in the paper.

- `python scripts/litsearch.py --verify <doi>` re-checks a recorded hit against Crossref; `--from-file` replays a search exactly.
- `python scripts/journal_pack.py --journal <name>` states the outlet's table conventions for the papers you cite.

## Common failure modes

| Failure | What it looks like | Fix |
|---|---|---|
| Fabricated citations | A plausible title, plausible authors, a DOI that resolves to something else | Resolve every identifier in a browser before it enters the matrix |
| Abstract-only rows | The design column says "uses panel data" because that is all the abstract said | Open the identification section; if you cannot, drop the row |
| Gap without rows | "Few studies examine the effect of X on Y in China" | Attach row numbers; if none fit, the gap is bigger than you think |
| Everything is closest | Three rows all marked `closest = yes` | The matrix is not doing its job; pick one and explain the choice |
| Search plan never revised | First draft of keywords, one database, no dates | Re-run step 1 after the first 10 papers; keywords move |

## Interfaces with other skills

- Upstream: `feasibility` — the four slots and the stop criteria come from there; this skill takes the question as given.
- Downstream: `identification` — the gap sentence and the closest paper's design become the "why this is new" and the threat list.
- Parallel: `data-prep` when a paper's data source is a candidate for you; `writing` for how the gap is phrased in the introduction.

## Where to look up domain details

A field's canonical papers, the measurement conventions, and the referee questions are in `domains/<field>/institutional.md`, `measures.md` and `pitfalls.md`. The outlet tiers used by `--min-tier` live in `skills/literature/journals.json`: twelve fields, A and B tiers plus working-paper DOI prefixes. Editing that file is a code-free way to make the search prefer the journals your field actually respects.

For a source outside `data-dict/`, read `data-dict/README.md` first: it tells you whether the source needs an entry at all.
