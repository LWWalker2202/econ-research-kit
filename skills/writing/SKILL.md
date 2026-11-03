---
name: writing
description: Write and submit an economics manuscript to an English-language journal — 100 to 150 word abstract, JEL codes, five-paragraph introduction, identification strategy paragraph, mechanism and limitations paragraphs, submission statements, and a point-by-point response. Use when results are final and the draft still reads like a lab notebook, or when the submission package must be assembled. Triggers: 写摘要、引言、投稿、识别策略段落、数据可得性、point-by-point、manuscript writing, abstract, JEL codes, submission statement, response letter.
---

# Writing and submission

## When to use this

- The estimates are final and the manuscript still reads like a lab notebook with references attached.
- You are cutting the abstract down to a journal's word limit and cannot afford to lose the main estimate.
- The submission portal asks for JEL codes, a data availability statement, a conflict of interest statement, or an Online Appendix.
- The introduction has to deliver the contribution in the third sentence rather than on the third page.
- You are drafting a point-by-point response and it has to stay consistent with the revised text.

## Inputs

| What you need | Where it comes from | If it is missing |
|---|---|---|
| Final estimates with magnitudes and units | `estimation` output and the built tables | write the abstract only after the headline number is fixed |
| Exhibit map | `output/tables/table_index.csv` | build it first; every claim in the abstract must point to an exhibit |
| Journal style sheet | the target journal's author guidelines | use the defaults below and list each deviation in `[to fill]` |
| Prior literature and the gap | your reading notes | name the two or three papers this one speaks to; do not write a survey inside the introduction |
| JEL classification | the published JEL list | look up each code's official description; never copy codes from a neighbouring paper |

## Procedure

House conventions in this skill: refer to the paper as "this paper" and reserve "we" for author choices; spell out every abbreviation at first use, including inside the abstract; capitalise "Online Appendix" and "Table"; italicise Latin phrases; number sections in Arabic numerals; put table notes below the table, where they define the estimator, the sample, and the star thresholds; send every robustness result the main text only summarises to the Online Appendix.

1. Draft the abstract last, at 100 to 150 words, in five moves: question, design, data, the main estimate with its magnitude and unit, contribution. Done when the abstract has no citation, no undefined abbreviation, and states both a number and the unit it is measured in.
2. Fix the JEL codes: two or three codes, each with its official description copied into `paper/jel_codes.md` together with the reason it applies. Done when every code printed on the title page appears in that file with its description.
3. Write the introduction in five labelled paragraphs: stylised fact, question, what this paper does, what it finds with the magnitude, what it adds relative to the named papers. Done when each paragraph's first sentence states that paragraph's function.
4. Write the identification strategy paragraph: name the assumption in one sentence, state where the variation comes from, list the tests that support the assumption, and name the threat that would break it. Done when a referee could quote the assumption sentence and then test it.
5. Write the mechanism analysis paragraph as mechanism analysis, not as a mediation effect claim: state which intermediate outcome should move, in which direction, and report it in its own table. Done when the paragraph names the intermediate variable and the sign of its expected movement.
6. Write the limitations paragraph with three limitations, each paired with the result that would overturn the paper. Done when no limitation appears without its falsifier.
7. Write the submission statements, one sentence each: data availability, pre-registration where the design needs it, conflict of interest, funding, and ethics approval. Done when all five exist and the data availability wording reproduces the journal's required phrase.
8. Write the point-by-point response: a one-page cover note first, then per referee the comment verbatim in italics, the response, and the location of the change in section, page, and line. Done when every comment ID appears exactly once and every location resolves in the compiled PDF.

## Outputs (artifacts)

| File | Contents | Consumer |
|---|---|---|
| `paper/abstract.md` | abstract at the journal's word limit plus five keywords | submission system |
| `paper/jel_codes.md` | two or three JEL codes with official descriptions and the reason each applies | manuscript front matter |
| `paper/manuscript.tex` | full manuscript with numbered sections and table references | journal submission |
| `paper/statements.md` | data availability, pre-registration, conflict of interest, funding, ethics | submission portal |
| `paper/cover_letter.md` | one page naming the contribution and the journal fit | handling editor |
| `review/response_letter.md` | point-by-point response with quoted comments and change locations | editor and referees |
| `submission/checklist.md` | every required portal item with its status | corresponding author |

- `skills/writing/templates/check_abstract.py` — run it on the drafted abstract before the portal; the expected report is `skills/writing/expected/check-report.txt`.

## Acceptance

- [ ] The abstract falls within the journal limit, 100 to 150 words by default, and contains no citation.
- [ ] Two or three JEL codes appear, each with its official description recorded in `paper/jel_codes.md`.
- [ ] Each of the five introduction paragraphs opens with a sentence stating that paragraph's function.
- [ ] The identification strategy paragraph names the assumption, the source of variation, the supporting tests, and the main threat.
- [ ] The limitations paragraph pairs every limitation with the result that would overturn the paper.
- [ ] All five statements appear in `paper/statements.md`, with the data availability wording taken from the journal's required phrase.
- [ ] Every referee comment in the response letter is quoted verbatim and carries a section, page, and line location that resolves in the compiled PDF.

## Common failure modes

| Pattern | Symptom | Correction |
|---|---|---|
| Abstract written first and never revised | it describes a specification the results section no longer reports | write it last, from the final table |
| Contribution asserted without a named comparison | a referee asks what is new relative to the obvious prior paper | name the two or three papers and state the difference in one sentence |
| Mechanism paragraph dressed up as a mediation effect | the design cannot separate the channel from a proxy | report the intermediate outcome as mechanism analysis, not as a mediation effect |
| Statement section assembled from another submission | the data availability sentence promises data you may not share | write it from the actual sharing agreement |
| Response letter changes the number but not the text | the reply cites a revision the manuscript does not contain | update the text and the location pointer in the same pass |

## Interfaces with other skills

- Upstream: `estimation` supplies the magnitudes; `tables-figures` supplies the exhibit map and the table notes; `report` supplies `values.json`.
- Downstream: `review` turns the submitted manuscript into a revision workflow; the `report` provenance block answers reproducibility questions raised at submission.

## Where to look up domain details

- Energy and environment: `domains/energy-env/institutional.md` for the ready-to-cite institutional paragraph, and `domains/energy-env/pitfalls.md` for the objections the introduction should pre-empt.
- Labor: `domains/labor/pitfalls.md` for the referee questions the introduction should answer in advance.
- Behavioral: `domains/behavioral/measures.md` for the treatment definitions an experiment needs and the identifying assumptions behind each one.
