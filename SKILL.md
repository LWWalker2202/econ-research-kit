---
name: econ-research-kit
description: 经济学实证研究的动作库——把一次研究拆成八道可执行工序（可行性、识别、数据、估计、表图、报告、写作、审稿），每道工序都有输入、步骤、产出文件与验收标准。Use for any empirical economics research task: feasibility checks, identification design, data cleaning, regression tables, publication-quality figures, reproducible reports, paper writing, and referee responses. Triggers: 怎么做实证、识别策略、数据清洗、回归表、三线表、复现、写论文、回复审稿、研究流程、econ research workflow、empirical pipeline、applied micro.
---

# econ-research-kit

Economics research as a set of executable steps. Not a prompt collection — a workflow library where every skill declares its inputs, its artifacts, and its acceptance criteria.

## What this is, and what it is not

**This is** a set of eight skills, each covering one stage of an empirical project. Each skill tells you when to enter it, what it needs, what to do, what files it must produce, and how to check the result.

**This is not** a prompt dump. A prompt produces text. A skill produces files that another person can re-run. If a stage ends with "the assistant wrote a nice paragraph", the stage was not completed.

**Also not**: a substitute for your judgement about identification. The skills here force you to state your assumptions and their threats. They cannot tell you whether the assumptions hold.

**Companion book**: `book/` holds *Prompt Engineering for Economists* by LW Walker, with dear friends and lovely family, 208 pages and sixty templates. The book says why each stage is shaped this way; this repository says what to do in it. `book/README.md` maps chapters onto stages.

## The eight stages

| # | Stage | Skill | The question it answers |
|---|---|---|---|
| 0 | Feasibility gate | `skills/feasibility/` | Can this be done at all with the data and variation available? |
| 1 | Problem and literature | `skills/literature/` | Is the gap real, and is it worth a paper? |
| 2 | Identification design | `skills/identification/` | What variation identifies the effect, and what would break it? |
| 3 | Data | `skills/data-prep/` | Are the variables defined the way I think they are? |
| 4 | Estimation | `skills/estimation/` | Is the specification defensible, and what does each robustness check protect against? |
| 5 | Tables and figures | `skills/tables-figures/` | Do the outputs meet journal format? |
| 6 | Report | `skills/report/` | Can someone else reproduce this from my files? |
| 7 | Writing and submission | `skills/writing/` | Does the prose carry the identification story? |
| — | Referee response | `skills/review/` | How do I answer without conceding what I should not? |

**Stage 0 is a gate, not a step.** If it fails, stop. Do not clean data for a project whose identification cannot work.

## Routing: what the user says, which skill to enter

Before reading the table below, run `python scripts/preflight.py "<the user's words>"`. It tells you which of the four slots are missing. Then run `python scripts/spec.py "<the user's words>"`: it prints a task-spec draft — the four slots, the stage it reads, an editable prompt, and the three things to confirm — and **that draft is what you show the user before doing any work**. At any point, `python scripts/dashboard.py` prints one page: which stage the project stands in, the question the next stage will ask, how many checks pass, and how far the cleaning has moved the sample. `python scripts/coverage.py` then scores the project itself: twelve named checks (spec written, contract on disk, ledger present, every promised artefact there, table labels, panel freshness), so a gap shows up as `4/14` instead of a feeling. `python scripts/crosscheck.py` recomputes the gold coefficients with a second implementation (7/7 within 1e-6), so a number that drifts is caught by a machine rather than by an eye; `python scripts/to_fill.py` triages every placeholder into `.econ-kit/to-fill.csv` by who must fill it; `python scripts/estimator_choice.py --data panel` names the estimator whose assumptions fit the design. The DSH bundle also watches `.econ-kit/gate.json` and rewrites the panel by itself every ten seconds, so nobody has to remember the dashboard command.

**Open the gate before writing anything**: `python scripts/gate.py status`. No state yet means `gate.py start "<the question>"`. `gate.py pass` refuses until `.econ-kit/spec.md` exists, and that file is written by `scripts/spec.py` — the spec plus prompt draft you show the user first. `gate.py start` also drops `AGENTS.md` and `.econ-kit/PROTOCOL.md` into the project so any later agent sees the contract. Edit it together, then start.

Each stage lists the **floor**, not the ceiling: do more when the task needs it and record it with `gate.py pass --extra "..."`; skipping extras is not a gap, and doing them is never wasted (`C7`). Every "first move" in the table happens only after the four slots are filled; while a slot is open, the only move is to ask about it.

| The user says something like | Enter | First move |
|---|---|---|
| "我想研究 X，这东西能做吗？" / "有没有数据？" / "this is probably infeasible" | `skills/feasibility/` | Enumerate the data and the variation before writing any code |
| "这个题目有没有人做过？" / "novelty" / "文献缺口" | `skills/literature/` | Write the search plan first, then build the matrix |
| "我用 DID / IV / RDD / 事件研究" / "识别策略" / "how do I identify this" | `skills/identification/` | Write the threat list before the regression |
| "数据洗一下" / "变量怎么构造" / "merge 不上" / "口径" | `skills/data-prep/` | Check variable definitions across years first |
| "跑个回归" / "加固定效应" / "稳健性" / "robustness" | `skills/estimation/` | Justify the clustering level and the FE set |
| "做个表" / "三线表" / "画事件研究图" / "regression table" | `skills/tables-figures/` | Decide Stata or Python, then match the journal format |
| "整理成报告" / "复现" / "replication package" | `skills/report/` | Make the report a script output, never a hand-edited file |
| "写摘要" / "写引言" / "投稿" / "abstract" | `skills/writing/` | Draft the identification paragraph before the introduction |
| "审稿意见怎么回" / "referee report" / "rebuttal" | `skills/review/` | Classify each comment as must-do / arguable / rejectable |

If two skills could both apply, **go upstream**. A table problem is usually a specification problem; a specification problem is usually an identification problem.

## Before anything else: recall, then ask

Every session starts with files, not with memory:

```
python scripts/recall.py
```

It prints where the project stands, what the last step produced, and what is still open.
A session that skips it will re-ask questions the repository already answers, or rebuild
something that already exists. Run it first, then `scripts/preflight.py`, then answer.

## Five hard rules

**1. Ask before you answer: do not proceed until the four slots are filled.**
On any research request, the first action is `python scripts/preflight.py "<the user's words in their own language>"`. It splits the question into four slots — unit of analysis, treatment variable, outcome, comparison — and tells you which ones are missing.
- Missing slots: write **at most three questions**, ask them all at once, then stop and wait for the answer.
- A slot you filled by inference must be marked "assuming X", and the user must confirm it.
- Only when all four slots are filled — by the user, or by an assumption the user confirmed — may you enter step 2 of any skill.
**This is the only rule in the kit that requires stopping to wait for a human.** Work produced past this gate is a guess wearing a document's clothes.

**2. Read `glossary.yaml` before writing any method term.**
It has three levels: `locked` (use verbatim), `pending` (use the first candidate and parenthesise the alternative), `fallback` (keep the Chinese proper noun, give the English expansion once). Violating a `locked` translation is a defect, not a style choice.

**3. Domain specifics live in `domains/`, not in the skills.**
Skills describe how to work. They do not describe what 中央环保督察 is, how CFPS defines education, or what referees ask about pollution exposure. Every skill's last section says which domain file to open. Open it.

**4. Every stage must leave a file, and every file must pass its acceptance list.**
`## Acceptance` is a checklist, not a suggestion. An item you cannot answer yes/no to is a badly written item — rewrite it.

**5. Say where you are before you do anything else.**
Every reply that enters a stage opens with three lines: which stage (number and name), what this step alone does (one sentence, never "analyse the data"), and which file it will produce plus whether the user must confirm before you continue. A reply without that header is a black box, and the user pays for it.

Every stage also ends by asking one question and waiting. See the table below.

## Eight confirmation points

The gate at stage 0 is not the only one. Each stage closes with one question and stops. This is not politeness: a decision the user never saw is a decision the user cannot correct.

| Stage | The question to stop and ask | Continue without an answer |
|---|---|---|
| 0 Feasibility | The four slots are filled; can you settle the two I inferred? | No |
| 1 Problem and literature | Which of these three candidate questions? Is the gap this one? | No |
| 2 Identification design | Treatment group, comparison group, timing set this way: do you accept it? | No |
| 3 Data | Variable definitions and sample boundaries drawn this way: do you accept it? | No |
| 4 Estimation | Main specification and this robustness list: add or drop anything? | No |
| 5 Tables and figures | This table layout and note style: is this what you want? | No |
| 6 Report | One-page conclusion written this way: any change to how the numbers read? | No |
| 7 Writing | Which part of this draft goes back? | No |
| 8 Referee response | Do we revise this comment or push back, and is this the reason? | No |

`python scripts/stage.py 3` prints the header and the question for any stage, so the wording does not drift between sessions. `workflows/main.yaml` is the same mainline written as a machine-readable handoff contract: each stage declares `requires` (what must already be on disk) and `produces` (what it must leave behind), and `python scripts/workflow_check.py` fails if a stage requires something no earlier stage produces. `python scripts/gate.py status` makes the gate mechanical rather than a convention: it keeps a per-project state file (`.econ-kit/gate.json`), refuses to advance until the stage's artifacts exist and a human answer of at least eight characters is recorded, and logs the answer with a timestamp. `gate.py pass "<the answer>"` is the only way forward; `--force` exists but writes the gap on the record. To see what the checks of any stage actually look for, run `python scripts/explain.py 6` (`--list` shows all nine stages; for stages 3 and 4, which already have runnable scripts, it points at those scripts and at the skill's acceptance list instead).

## When a term is uncertain

Never silently pick a translation. If the term is in `pending`, use the first candidate and append the alternative in parentheses. Mark at most three such places in one output; beyond that, use the first candidate silently and add one summary line at the end.

If the term is not in the glossary at all, keep the Chinese original and give an English expansion in parentheses. Then add it to `pending` in `glossary.yaml` so the next person does not have to decide again.

## Domain lookup

| Direction | Directory |
|---|---|
| Energy and environmental economics | `domains/energy-env/` |
| Labour economics | `domains/labor/` |
| Economics of education | `domains/education/` |
| Health economics | `domains/health/` |
| Behavioural and experimental economics | `domains/behavioral/` |
| Development and field experiments | `domains/development/` |
| Public economics and policy evaluation | `domains/public/` |
| Industrial organization and regulation | `domains/industrial-organization/` |
| Trade and spatial economics | `domains/trade-spatial/` |
| Macroeconomics and finance | `domains/macro-finance/` |
| Economic history and textual sources | `domains/economic-history/` |
| Theoretical modelling and mechanism design | `domains/theory/` |

Twelve directions are covered. The first three are the ones this kit was built around; labour, education and health are the three fields the book treats together under applied micro; the rest were added so that a reader outside applied micro still finds a shelf to stand on.

Each direction has five files: `institutional.md` (background and ready-to-cite paragraphs), `measures.md` (how the treatment variable is built), `data.md` (sources and variable names), `pitfalls.md` (what referees ask and how to answer), and `route.md` (how this direction walks the eight stages).

## Data

`data-dict/` holds Chinese micro-data sources: CFPS, CHARLS, the Chinese Industrial Enterprises Database, and pollution monitoring data. Check it before inventing a variable name — the dataset probably already has one. If your source is not there, read `data-dict/README.md` first: some sources get an entry and some deliberately do not, and a guessed variable name is worse than a marked one.

When the question is not "what is this variable called" but "does a source even exist for this", `data-dict/_catalog.md` and `scripts/lookup_source.py` search an external directory of over a thousand sources with access links and application papers. Those hits are leads, not entries: the numbered files here stay the only place where variable-level detail is written down.

## What this kit will not do

- It will not decide whether your identification is credible. It will make you write down the threats.
- It will not replace reading the paper you are citing. Hallucinated references are the most common failure of AI-assisted writing; `skills/writing/` includes a verification step.
- It will not run on its own. The scripts in `scripts/` check structure; the analysis is yours.
