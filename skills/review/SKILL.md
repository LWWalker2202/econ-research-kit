---
name: review
description: Take a decision letter and two referee reports apart — classify every comment as must-do, arguable, or decline, convert the accepted ones into owned tasks, write a point-by-point response letter, and decline a request without conceding the design. Use when a revise-and-resubmit arrives, when coauthors disagree about what to change, or when a referee asks for an analysis the data cannot deliver. Triggers: 审稿意见、回复审稿人、返修、rebuttal、不改、point-by-point response, referee report, revise and resubmit, response letter.
---

# Referee reports and responses

## When to use this

- Two referee reports arrived and the decision letter says revise and resubmit.
- You have to separate comments that must be done from comments worth arguing and comments to decline.
- A referee asks for an analysis the design cannot deliver and the editor wants the reason in writing.
- The comments need to become a task list that coauthors can own and close.
- You are replying to a second round and the first round's refusals have to stay consistent.

## Inputs

| What you need | Where it comes from | If it is missing |
|---|---|---|
| Referee reports, verbatim | the decision letter | ask the handling editor for the full text before starting |
| The submitted version with page and line numbers | the submission file | recompile the submitted version; pointers resolve against it, not against the latest draft |
| A task board the coauthors actually use | the shared project board | create the tasks before drafting, so the letter cannot promise work nobody owns |
| Estimates and appendix for the requested robustness | `output/estimates/` and `output/tables/` | run the specification before writing the reply, not after |
| Journal policy on revisions and appeals | the journal's author guidelines | ask the editor; do not assume the revision window |

## Procedure

1. Transcribe every comment into `review/comments.csv` with columns for comment ID, referee, verbatim text, requested action, class, effort, owner, and task ID. Done when the row count equals the number of comment paragraphs across both reports.
2. Classify each row as must-do, arguable, or decline. Must-do covers factual errors, missing definitions, unreported standard errors, and an absent robustness check. Arguable covers specification choices, framing, and additional literature. Decline covers a request that contradicts the identification strategy, needs data that cannot be obtained, or asks for a different paper. Done when every row carries a class and a one-sentence reason.
3. Convert the must-do and arguable rows into board tasks with an acceptance condition and a write scope. Done when every must-do row carries a task ID and an owner.
4. For each decline, design the substitute: a footnote, an appendix table, or one sentence that addresses the concern at the level the data allow. Done when the substitute is a named deliverable rather than a promise to consider it.
5. Write the cover note, one page: what changed, what did not change, and the single reason behind each refusal. Done when the note names every refusal before the referees reach the detail.
6. Write the per-referee sections: comment verbatim in italics, response, then the change with section, page, and line. Done when every comment ID appears exactly once and no response claims a change the revised file does not contain.
7. Recompile and resolve every pointer against the revised PDF. Done when a checked pass finds no pointer to a page that lacks the claimed change.
8. Record each refusal and its reason in `review/decisions.md`, for the editor and for the next round on this paper or the next paper with the same design.

Saying no without compromising, the reusable shape: accept the concern, state the design or data constraint in one sentence with no apology and no adjectives, then point at the substitute. "We agree that X would sharpen the mechanism evidence. Our data contain no measure of Y, so Z cannot be estimated on this sample. We now report W in Appendix Table A5, which addresses the same concern at the level the data allow." The sentence never tells the referee they are wrong; it states what the data can and cannot identify.

## Outputs (artifacts)

| File | Contents | Consumer |
|---|---|---|
| `review/comments.csv` | one row per comment with class, effort, owner, and task ID | coauthors |
| `review/response_letter.md` | cover note plus per-referee point-by-point response | editor and referees |
| `review/decisions.md` | every refusal with its reason and its substitute | editor, next revision round |
| `review/revision_log.md` | change-by-change record with section, page, and line | corresponding author |
| `manuscript/manuscript_v2.tex` | revised manuscript with tracked changes marked | submission system |

## Acceptance

- [ ] `review/comments.csv` holds one row per comment paragraph and its row count matches a manual count of both reports.
- [ ] Every row carries a class of must-do, arguable, or decline, plus a one-sentence reason.
- [ ] Every must-do row has an owner and a task ID on the shared board.
- [ ] Every decline row names a concrete substitute deliverable.
- [ ] Every comment ID appears exactly once in `review/response_letter.md`.
- [ ] Every cited change resolves to a real page and line in the revised PDF.
- [ ] The cover note names every refusal within its first page.

## Common failure modes

| Pattern | Symptom | Correction |
|---|---|---|
| Answering the comment's headline and not its request | the referee repeats the same point in round two | restate the request in your own words in the requested-action column |
| Promising an analysis that nobody owns | the revision returns with the promise missing | task ID and owner before the letter is drafted |
| Refusing with no substitute | the referee reads the reply as evasion | every decline carries a footnote, an appendix table, or a sentence |
| Citing stale page numbers | the editor cannot locate the change | resolve pointers after the final compile, against the revised PDF |
| Arguing about tone rather than substance | the substantive point is lost in the exchange | state the constraint, then the substitute; no adjectives about the referee |

## Interfaces with other skills

- Upstream: `writing` supplies the submitted manuscript and the statements; `tables-figures` supplies the exhibit IDs the response letter cites.
- Downstream: `report` rebuilds the exhibits after the revision; `estimation` reruns the specifications the revision requires.

## Where to look up domain details

- Energy and environment: `domains/energy-env/pitfalls.md` lists the questions referees ask in this field, with a response direction for each.
- Labor: `domains/labor/pitfalls.md` for the identification objections that recur in labor reports.
- Behavioral: `domains/behavioral/pitfalls.md` for balance check, manipulation check, and statistical power questions that recur in experimental reports.
