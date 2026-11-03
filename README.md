# econ-research-kit

A workbench for empirical economics: **eight stages, twelve fields**, and for every stage either a runnable template with a golden output to diff against, or a checker that reads what you produced.

**Version 0.3.1** · Mirror of the Chinese edition: [`econ-research-kit-zh`](https://github.com/LWWalker2202/econ-research-kit-zh) (parity checked in CI)

## Why this exists

Three things go wrong when you ask a language model to help with research, and none of them is "the model is not smart enough".

1. **You explain the project from scratch every time.** The setup lives in a chat window that scrolls away, so the hundredth conversation is as uninformed as the first.
2. **The code looks right and you cannot tell whether it is.** A defensible-looking table is not a table. Nothing in a chat checks whether the clustering matches the treatment assignment.
3. **Everyone in the group does it differently.** Handing a project over means handing over a conversation, and the student who inherits it cannot see what was tried and rejected.

This kit takes the opposite bet: **write the procedure down once, as files, so that the model reads the same procedure you do.** A file can be checked, versioned, argued with and replaced. A conversation cannot.

## What is in the box

| Layer | What it holds | The question it answers |
|---|---|---|
| `skills/` | eight stage procedures | How is this step actually done? |
| `domains/` | twelve field packs, five files each | What is special about my field here? |
| `data-dict/` | Chinese micro data sources | What is this variable called? |
| `index/actions.csv` | forty-nine actions, bilingual columns | What am I trying to do right now? |
| `scripts/` | four checks | Is the repository still consistent? |
| `book/` | the companion handbook | Why is it built this way? |

One sentence: `skills/` tells you **how**, `domains/` tells you **what is special here**, `data-dict/` tells you **what the variable is called**.

## Five minutes

Nothing to install. Python 3.11 or newer, standard library only.

```bash
# 1. is the content clean?
python scripts/lint_content.py .

# 2. do the two editions still match?
python scripts/check_parity.py

# 3. produce a table and diff it against the golden output
cd skills/tables-figures
python templates/panel_ols.py --lang en
diff output/table1.tex expected/table1.tex
```

If the third command prints nothing, you have just reproduced a publication-grade three-line table from a fixed seed. That is the whole idea: the interesting part is not that the table appeared, it is that you can tell whether it is right.

## The eight stages

| # | Stage | Skill | The question it answers |
|---|---|---|---|
| 0 | Feasibility gate | `skills/feasibility/` | Can this be done at all with the data and variation available? |
| 1 | Problem and literature | `skills/feasibility/` (part two) | Is the gap real, and is it worth a paper? |
| 2 | Identification design | `skills/identification/` | What variation identifies the effect, and what would break it? |
| 3 | Data | `skills/data-prep/` | Are the variables defined the way I think they are? |
| 4 | Estimation | `skills/estimation/` | Is the specification defensible, and what does each robustness check protect against? |
| 5 | Tables and figures | `skills/tables-figures/` | Do the outputs meet journal format? |
| 6 | Report | `skills/report/` | Can someone else reproduce this from my files? |
| 7 | Writing and submission | `skills/writing/` | Does the prose carry the identification story? |
| - | Referee response | `skills/review/` | How do I answer without conceding what I should not? |

**Stage 0 is a gate, not a step.** If it fails, stop. Do not clean data for a project whose identification cannot work; that is how a year disappears.

## Twelve domains

| Directory | Field |
|---|---|
| `domains/energy-env/` | Energy and environmental economics |
| `domains/labor/` | Labour economics |
| `domains/education/` | Economics of education |
| `domains/health/` | Health economics |
| `domains/behavioral/` | Behavioural and experimental economics |
| `domains/development/` | Development and field experiments |
| `domains/public/` | Public economics and policy evaluation |
| `domains/industrial-organization/` | Industrial organisation and regulation |
| `domains/trade-spatial/` | Trade and spatial economics |
| `domains/macro-finance/` | Macroeconomics and finance |
| `domains/economic-history/` | Economic history and textual sources |
| `domains/theory/` | Theoretical modelling and mechanism design |

Each pack has five files: `institutional.md` (background, timeline, paragraphs you can paste), `measures.md` (how the treatment variable is built, and what each definition assumes), `data.md` (sources, variable names, coverage, known problems), `pitfalls.md` (what referees ask and how to answer), and `route.md` (which of the eight stages to look at, and what to confirm there).

**Fields are a filter, not a funnel.** A paper on environmental regulation and firm investment touches energy, public economics and industrial organisation at once. Read the packs you need; do not pick one and stay in it.

## Which stages can actually run

Three stages produce artefacts; five read what you produced. No stage is a memo asking you to be careful.

| Stage | What ships | How to check it |
|---|---|---|
| Feasibility | `check_memo.py`, a filled memo, six machine checks | `python skills/feasibility/templates/check_memo.py skills/feasibility/expected/feasibility-memo.md` |
| Identification | `check_design.py`, a filled memo, six machine checks | `python skills/identification/templates/check_design.py skills/identification/expected/identification-memo.md` |
| Data | `clean_panel.py` and a Stata twin, cleaning log as golden output | run the script twice, the hash must not move |
| Estimation | `estimate_main.py` and a Stata twin, a five-step specification chain | `python skills/estimation/templates/estimate_main.py --lang en` |
| Tables | `latex_table.py`, `panel_ols.py`, `table1.tex` as golden output | diff against `expected/table1.tex` |
| Report | `build_report.py`, turns artefacts into a report | numbers come only from the input files, never invented |
| Writing | `check_abstract.py`, seven machine checks | `python skills/writing/templates/check_abstract.py skills/writing/expected/abstract.md` |
| Review | `check_response.py`, five machine checks | `python skills/review/templates/check_response.py skills/review/expected/response-letter.md` |

Two habits sit behind all of it: **deterministic fixtures** (fixed seeds, so a hash that moves means you changed something) and **a golden output for every generator** (so a library upgrade that silently changes formatting is visible the next time you run it).

## The companion book

`book/` holds *Prompt Engineering for Economists* by LW Walker, with friends and family: 208 pages, sixty templates, written for undergraduate, master's and PhD readers at once. The book explains why the procedure looks like this; this repository is the version you run. `book/README.md` says which file to read and which chapter pairs with which stage.

Its one-line thesis is also this repository's: **a prompt that cannot be checked is a wish, not a specification.** If you only read one chapter, read the third one, the eight elements of an economics problem description, and then open `skills/identification/SKILL.md` to see the same idea as a file.

## Design principles

1. **Stage 0 is a gate, not a step.** A project that fails feasibility does not deserve clean data.
2. **Artefacts over prose.** Every stage must leave a file. If a session produced only a nice answer, it produced nothing.
3. **Scripts over results.** A number without a script is a rumour. Always generate the script, not just the output.
4. **Domain knowledge and procedure live apart.** `skills/` says how to do it; `domains/` says what is special here. Mixing them makes both stale.
5. **An acceptance item you cannot answer yes or no is a broken item.** Rewrite it; do not soften it.
6. **Anything that can be machine-checked is not left to memory.** Machines do not get tired at eleven at night.

## Common misreadings

- **It is not a prompt collection.** Sixty templates live in the book. These are eight procedures with inputs, steps, artefacts and acceptance lists.
- **It does not run your research.** It stops you from spending three months on something that could not have worked, and it makes what you did defensible afterwards.
- **Twelve domains are not twelve skills.** A domain answers "what is special in my field"; a skill answers "how is this step done". They are orthogonal on purpose.
- **Golden outputs are not data.** Every fixture is synthetic. Never cite a number from a directory called `expected`.
- **The Chinese mirror is not a translation.** The differences that matter are submission conventions: abstract length, JEL codes versus a Chinese classification number, table notes, online appendices. That is why `writing` and `tables-figures` differ between editions while everything else matches.

## Install

Four ways, pick one.

```bash
# Codex
git clone https://github.com/LWWalker2202/econ-research-kit.git ~/.codex/skills/econ-research-kit

# Claude Code
git clone https://github.com/LWWalker2202/econ-research-kit.git ~/.claude/skills/econ-research-kit

# DSH: the shared directory is read by DSH and others; the second is DSH only
git clone https://github.com/LWWalker2202/econ-research-kit.git ~/.agents/skills/econ-research-kit
git clone https://github.com/LWWalker2202/econ-research-kit.git ~/.dsh/skills/econ-research-kit
```

On Windows the same paths are `%USERPROFILE%\.codex\skills\`, `%USERPROFILE%\.agents\skills\` and so on. The fourth way needs no agent at all: read `SKILL.md`, follow the routing table, open the file it names. The repository is designed to be useful as a document.

## Check that it loaded

Ask the agent three things. If the first answer is vague, the skill was not picked up.

1. "What does the feasibility stage decide, and what happens if it fails?"
2. "Which file do I read before I construct an environmental regulation treatment variable?"
3. "What are the six checks in the identification checker?"

## Extending this

- **Add a field.** Copy any `domains/<field>/` directory, keep the five file names, write `route.md` last. Then run both checks.
- **Add a stage.** Create `skills/<name>/SKILL.md` with the eight fixed sections, and add the actions to `index/actions.csv`. The CSV has bilingual columns on purpose: one file serves both editions and stays byte-identical.
- **Vendor an upstream.** Copy it byte for byte into `skills/<name>/vendor/<upstream>/`, keep its licence and notice files beside it, record the commit and the copied date in `LICENSES.md`, and never edit inside `vendor/`. If a repository has no licence, do not vendor it at all.
- **After any edit**, run `lint_content.py`, then `check_parity.py`, then push the English repository first and the mirror second. The parity check is what keeps two editions from drifting into two projects.

## Status and licence

Version 0.3.1. Eight stages, twelve field packs, four data dictionaries, three teaching tracks, twelve vendored upstream components, two sets of conventions measured from actual journal issues, and a runnable artefact or a checker for every stage.

The kit is MIT licensed: Copyright (c) 2026 LW Walker, with dear friends and lovely family. Vendored material keeps its own licence; the licence, notice and commit for each upstream are recorded in the `LICENSES.md` next to it. The companion book is a working handbook distributed for reference and teaching, and it carries the same credit.
