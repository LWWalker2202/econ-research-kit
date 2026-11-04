# The companion book

One PDF sits in this directory: the archived first edition. The current edition is not distributed through this repository. The book is still the reason the rest of the repository is shaped the way it is, so the archive is worth five minutes even if you never read it cover to cover.

## What the book is

*Prompt Engineering for Economists* is a handbook written for readers at three levels at once: undergraduate, master's, and PhD. It is written in Chinese, because the institutional detail it deals with is Chinese, and it is 208 pages long in the current edition. Its central claim is one sentence: **a prompt that cannot be checked is a wish, not a specification.** Everything else in the book is an unpacking of that sentence for economics.

It contains sixty templates. Twelve are general-purpose (decomposing a hard question, stress-testing an idea, reading a paper's structure, self-auditing a prompt). Thirty are field templates, grouped by branch: applied micro, development and field experiments, industrial organisation, trade and spatial, macro and finance, public economics, behavioural and experimental, economic history and textual sources, theoretical modelling, writing and submission. The remaining eighteen go deeper into three directions: behavioural and experimental, labour, and energy and environment. Each template follows the same eight-part shape: when to use it, input and output, a variable table, the prompt itself, a worked fragment, common anti-patterns, an acceptance checklist, and sources.

## Which file to read

- `prompt-engineering-for-economists-v1.pdf` is the first edition (170 pages, 42 templates). It is kept for the archive: if a reader cites a page number that no longer matches, this is why.

## Author and acknowledgement

Written by **LW Walker, with dear friends and lovely family**. This little book is a flower nourished by countless ordinary days: everyone who helped me, everyone who walked beside me, is a co-author of it.

## How the book and this kit differ

They answer different questions, and neither replaces the other.

- The book answers **why** and **how to write it**: why seven slots are enough to specify a task, why an acceptance item that cannot be answered yes or no is a broken item, how to turn a vague request into a specification.
- The kit answers **what to run**: eight stage directories, twelve field packs, and for every stage either a runnable template with a golden output or a checker that reads what you produced.

The book's sixty templates are task templates. The kit re-cut them along a different axis: the book asks "what kind of task is this", the kit asks "which stage of the research pipeline are you in". Twelve general templates became the procedure files under `skills/`; the field templates became the field packs under `domains/`; the eighteen deep templates are the reason three fields got their own packs first.

## Where to read what

| If you want to | Read in the book | Then use |
|---|---|---|
| Specify a task without forgetting something | Chapter 2, the seven slots | `skills/*/SKILL.md`, the Inputs section |
| Describe an economics question properly | Chapter 3, the eight elements | `skills/feasibility/`, `skills/identification/` |
| Get a field template for your own area | Chapter 5, by branch | `domains/<your field>/` |
| Go deeper in behavioural, labour, or energy | Chapter 6 | `domains/behavioral/`, `domains/labor/`, `domains/energy-env/` |
| Judge whether an output is any good | Chapter 8, the six-dimension rubric | the `## Acceptance` list in each skill |
| Avoid fabricated references | Chapter 9 | `domains/*/pitfalls.md` |

## Licence and citation

The book is a working handbook, not a formally published title, and it is distributed here for reference and teaching. Cite it as:

> LW Walker, with friends and family. *Prompt Engineering for Economists*, first edition, 2026.

If you reuse a template in teaching material, keep the eight-part shape and the acceptance checklist; that shape is the part that took the longest to get right.
