# econ-research-kit

A **stage-by-stage toolkit for empirical work in economics**: from "is this question even answerable", through "run the regression", "produce a publication table", "write the report", to "answer the referee", in eight stages. Every stage ships either a template you can actually run (and compare against a golden output) or a checker that reads what you produced and tells you line by line what is missing.

**Version 0.3.20** ｜ This is the English master repository; the Chinese mirror is [`econ-research-kit-zh`](https://github.com/LWWalker2202/econ-research-kit-zh), and CI compares the structure of the two on every push.

> First time here? Jump straight to "Step one". You do not need to understand why the repository is shaped this way before you use it.

## What this is, in one sentence

You have a research question but you are not sure what the first step is, or the second. This repository splits the work into eight stages and states, for each stage: **what you must have in hand before you start, two questions to ask yourself, which file you must hand over when you finish, and what makes that file acceptable**.

It will not write the paper for you and it will not tell you whether your identification strategy holds up. It does one thing only: **it forces you to put the things you should have thought about into files, and then checks whether you actually did.**

## When you will need it

Any one of these situations is enough:

1. You have been handed a topic and do not know where to start, and you do not want to open with "write me the code" the moment you open a chatbot.
2. You ran the regression and produced a table, but you do not know whether that table can go into a paper.
3. A referee asks about parallel trends or about why you clustered at that level, and you do not know how to answer.
4. You want AI help, but you re-explain the project every single time, and the output looks plausible while being unusable.
5. You are supervising an undergraduate or a first-year student and need something they can follow without you sitting next to them.

## Step one: install nothing, read three things first

About three minutes, no commands.

| Read | File | What you will know afterwards |
|---|---|---|
| One, the overall shape | this file | eight stages, twelve fields, how to install |
| Two, what is special about your field | the five files in `domains/labor/` or `domains/energy-env/` | where your project most often goes wrong |
| Three, how one stage actually runs | `skills/feasibility/SKILL.md` | the four questions to ask before you start |

Only come back and install something if you still want to.

## Step two: pick one of three ways to install it

Ask yourself one question: **which AI tool do you use?**

| Your tool | How to install | Where you then use it |
|---|---|---|
| An AI coding tool (Codex desktop, Claude Code, DeepSeek Harness) | copy this whole repository into that tool's skills directory (table below) | in the chat, say "help me check whether this question is answerable"; it reads the skill by itself |
| A web chatbot only (ChatGPT, Claude, Kimi, Doubao) | do not install anything. open the stage you need under `skills/`, copy the prompt body in full, paste it into the chat | paste and go |
| No AI at all | do not install anything. read it as documentation | follow it while you work |

Skills directories (pick one; replace `<you>` with your Windows user name):

| Tool | Where to put it |
|---|---|
| Codex desktop | `C:\Users\<you>\.codex\skills\econ-research-kit\` |
| Claude Code | `C:\Users\<you>\.claude\skills\econ-research-kit\` |
| DeepSeek Harness | `C:\Users\<you>\.agents\skills\econ-research-kit\` |

After copying, that directory must contain `SKILL.md` immediately. Do not leave one extra folder of the same name on top of it; that is the most common mistake.

## Step three: confirm that it is really loaded

Open a **new** chat (the skills list is read when a chat starts), then ask:

> What does the feasibility stage decide?

If the answer mentions the four slots, the data coverage matrix, stop criteria, and a go / reduce-scope / stop verdict, the skill is loaded.

If it instead gives you a generic paragraph about "considering feasibility", the skill was not read. Say:

> Did you load the econ-research-kit skill? Read its SKILL.md first, then answer.

## Step four: run it once and look at three outputs

This step produces real files. You need Python 3.11 or newer (type `python --version` in PowerShell; if you see a version number, you have it) and one install command.

Install two libraries first:

```
pip install pandas pyfixest
```

Now open PowerShell, go to the root of this repository (the level where you can see the `skills` and `domains` folders), and paste these three commands **one at a time**:

```
python skills\estimation\templates\estimate_main.py --lang en
python skills\tables-figures\templates\panel_ols.py --lang en
python skills\report\templates\build_report.py --results output\estimation-results.json --tables output\table1.tex --out output\report.md --lang en
```

Each command prints a line starting with `wrote`. When all three have run, an `output` folder appears with four files:

| File | What it is |
|---|---|
| `estimation-results.md` | a description of three regression specifications: coefficients, standard errors, clustering level |
| `estimation-results.json` | the same results in machine-readable form, used by the next step |
| `table1.tex` | a booktabs regression table you can drop into a paper |
| `report.md` | a reproducible report: one-line conclusion, main results, robustness, how to reproduce |

**Important**: those three commands run on synthetic data made by the scripts themselves. The point is to show you the shape of the workflow; **none of the numbers may be cited**. Your own data belongs in your own project folder, never in this repository.

If you also want to confirm the repository has not been damaged, run the two self-checks:

```
python scripts\lint_content.py .
python scripts\check_parity.py
```

The first prints `OK` plus how many markdown files are clean. The second prints `OK — parity holds. 246 files, 131 markdown files compared.` If both are OK, the repository is intact.

## What each folder is for

One line each. Do not memorise them; look them up when you need them.

| Folder | What it is for |
|---|---|
| `skills/` | **how to do it.** one folder per stage, each with `SKILL.md` (the procedure), `templates/` (runnable scripts), `expected/` (the golden output) |
| `domains/` | **what is special about this field.** twelve directions, five files each: institutional background, how the treatment variable is built, what the data look like, what referees ask, how the eight stages run in this field |
| `data-dict/` | **what the variable is actually called.** one entry each for CFPS, CHARLS, the Chinese industrial firms database and pollution monitoring, plus a pointer to an external catalogue of data sources |
| `index/` | a forty-nine-row list of actions: what you want to do now, and which stage it belongs to. readable by people and by models |
| `scripts/` | four self-check and lookup scripts (content lint, cross-repository parity, action table rendering, data source lookup) |
| `teaching/` | how to use the kit at undergraduate, master and doctoral level |
| `book/` | reading notes for the companion booklet (first edition archive) |
| `glossary.yaml` | the term table: what it is called in Chinese, in English, and which rendering is mandatory |

## One page that says where you are

```
python scripts/dashboard.py
python scripts/dashboard.py --html dashboard.html
```

The first prints four things: which stage the project stands in, the question the next stage will ask, how many checks each checker passes, and how many rows the cleaning moved. The second writes the same page as one self-contained HTML file (inline CSS and inline SVG, no network, no scripts) that you can send to a coauthor or drop into a slide.

It reads three things that already exist: `state/progress.json`, `.econ-kit/gate.json` in your research project, and whatever the runnable scripts wrote to `output/`. Nothing is typed twice.

## The eight stages: wherever you are stuck, go there

| Stage | Name | What is in your head when you are stuck | The file you hand over |
|---|---|---|---|
| 0 | feasibility | "Can this even be done? Is my data enough?" | `feasibility-memo.md` |
| 1 | question and literature | "How does this relate to the literature? What is my contribution?" | literature matrix and question statement |
| 2 | identification | "How would someone argue my result is fake?" | `identification-memo.md` |
| 3 | data | "Did this variable change definition between years?" | `cleaning-log.md` |
| 4 | estimation | "How do baseline, robustness and event study line up?" | `estimation-results.json` |
| 5 | tables and figures | "Can this table be submitted as it stands?" | `table1.tex` and figures |
| 6 | report | "How do I turn these results into prose?" | `report.md` |
| 7 | writing | "How do I write the abstract and the contribution sentence?" | the manuscript |
| 8 | referee response | "How do I answer this comment without bluffing?" | the response letter |

Note that stage 0 is a **gate, not a step**: if it returns "do not do this" or "do this with a reduced scope", the remaining seven stages stop. People ask whether they can skip it. Skip it and the remaining seven stages will multiply the mistake by seven.

## The stages hand work to each other

`workflows/main.yaml` writes the eight stages as a contract. Every stage declares what must already be on
disk before it starts (`requires`) and what it must leave behind (`produces`).

- `python scripts/workflow_check.py` fails if a stage requires a file that no earlier stage produces.
- `python scripts/gate.py status` shows where you are, and refuses to move on until the stage's artifacts
  exist and you have given it one answer of your own words.
- `python scripts/spec.py "<your sentence>"` prints the task spec and an editable prompt, which is what the
  kit shows you before it does anything.

## The twelve fields: which cell does your question fall into

| Directory | Field | Directory | Field |
|---|---|---|---|
| `energy-env` | energy and environment | `labor` | labour |
| `education` | education | `health` | health |
| `behavioral` | behavioural and experimental | `development` | development and field experiments |
| `public` | public policy evaluation | `industrial-organization` | industrial organization and regulation |
| `trade-spatial` | trade and spatial economics | `macro-finance` | macroeconomics and finance |
| `economic-history` | economic history and sources | `theory` | theory and mechanism design |

A question spanning two fields is normal (an environmental inspection affecting firm investment is both energy-environment and industrial organization). Read both; do not agonise over which cell it belongs to.

## Five things people get wrong about it

1. **It is not an automatic paper writer.** It produces no prose. It tells you which file to hand over and what makes that file acceptable.
2. **It does not judge whether your identification strategy holds.** It forces you to list the threats and write the test for each one; the judgement stays yours.
3. **The numbers in `expected/` cannot be cited.** They come from synthetic data and exist to pin down format and workflow, not to report a result.
4. **`[待填]` and `[待核实]` are not missing text.** There are about two hundred of them on purpose: data definitions and literature references must be verified by you. If a model fills them in, it is inventing.
5. **It is not a prompt collection.** The point of each stage is the sequence of files you hand over and the way you verify them; the prompt is only one part of it.

## If you do not want to install anything, reading alone works

That is a complete path, not a degraded one:

1. Read section four of this file to learn the eight stages.
2. Find the stage you are stuck at, open `skills/<that stage>/SKILL.md`, read three sections: when to enter, procedure, acceptance.
3. Work down the procedure, tick off the acceptance list after each step.
4. Any item you cannot tick: read the common failure modes in the same file.

No AI tool, no scripts, still complete.

## When something goes wrong, check these three first

| Symptom | Cause | Fix |
|---|---|---|
| the AI never mentions this kit | the skill is not loaded, or the folder is one level too deep | open a new chat; make sure `SKILL.md` sits directly inside the skill folder |
| a script says "No module named pandas" | the libraries are not installed | run `pip install pandas pyfixest` |
| the self-checks report a wall of errors that look unrelated | you ran them from the wrong directory | `cd` to the repository root (the level with `skills` and `domains`) and pass `.` as the argument |

Longer troubleshooting (encoding, GitHub connectivity, red CI) lives in `02_组合包与Codex包_安装说明_v1.md` under `交付/` in the working project; that document is about "I cannot get it installed".

## Who maintains it, and how to change it

- Author and copyright holder: **LW Walker, with dear friends and lovely family**.
- Relationship between the two repositories: the English one is the master, the Chinese one is a mirror. **The structures must stay identical**; `python scripts/check_parity.py` compares them on every push.
- Order of work: change the English repository, mirror the change into the Chinese one, run the self-checks, then commit. **These must be byte-identical in both repositories**: every script under `scripts/`, `glossary.yaml`, `index/actions.csv`. Changing only one side is caught by CI immediately.
- Where new material goes: new stages under `skills/`, new fields under `domains/`, new data under `data-dict/`, and each of them needs a matching row in `index/actions.csv`.

## Licence, citation, and the companion book

- Licence: MIT. Use it, change it, ship it inside your own project, keep the copyright notice.
- The third-party material under `skills/*/vendor/` is **not** MIT: each directory keeps its own licence, and its `LICENSES.md` records the upstream repository, the commit, the exact files and where the licence text sits.
- Citation: see `LICENSE` and the format given in `book/README.md`.
- Companion booklet: `book/` keeps the first-edition archive only; the current edition is not distributed with the repository. A much more detailed **user manual** (58,000 characters, eighteen chapters, written for people with no command-line experience) sits in the release assets.
