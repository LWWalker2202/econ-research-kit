# econ-research-kit

An executable workflow library for empirical economics. Eight stages, each with inputs, artifacts, and acceptance checks.

**Version 0.2.0** · Mirror of the Chinese edition: [`econ-research-kit-zh`](https://github.com/LWWalker2202/econ-research-kit-zh) (parity checked in CI)

---

## Why this exists

Most "AI for research" advice stops at prompts. A prompt produces a paragraph. A paper needs a pipeline: a feasibility judgement, an identification design, a clean dataset, a defensible specification, journal-formatted outputs, and a replication package.

This kit turns that pipeline into eight skills. Each skill answers four questions:

1. **When** do I enter this stage? (concrete triggers, not "when you need analysis")
2. **What do I need** to get in? (inputs, and what to do when they are missing)
3. **What do I do**? (steps with checkable completion conditions)
4. **What must come out**? (named files, plus an acceptance checklist)

A stage is finished when the files exist and every acceptance item can be answered yes.

## What's inside

```
econ-research-kit/
├── SKILL.md                 router — which skill for which request
├── skills/                  eight stages
│   ├── feasibility/         stage 0 — can this be done at all?
│   ├── identification/      stage 2 — what variation identifies the effect?
│   ├── data-prep/           stage 3 — are the variables what I think they are?
│   ├── estimation/          stage 4 — is the specification defensible?
│   ├── tables-figures/      stage 5 — do outputs meet journal format?
│   ├── report/              stage 6 — can someone else reproduce this?
│   ├── writing/             stage 7 — does the prose carry the design?
│   └── review/              referee responses
├── domains/                 domain knowledge, no procedure
│   ├── energy-env/         institutional · measures · data · pitfalls
│   ├── labor/
│   ├── behavioral/
│   ├── development/
│   ├── public/
│   ├── industrial-organization/
│   ├── trade-spatial/
│   ├── macro-finance/
│   ├── economic-history/
│   └── theory/
├── data-dict/               CFPS · CHARLS · industrial firms · pollution monitoring
│   └── _catalog.md          pointer to an external directory of 1000+ sources
├── teaching/                undergraduate · master · PhD
├── index/actions.csv        the action checklist (bilingual columns, one source)
├── scripts/                 structure checks, source lookup
├── glossary.yaml            locked terminology
├── VERSION
└── LICENSE
```

**Division of labour**: `skills/` says how to work; `domains/` says what is special about this field; `data-dict/` says what the data looks like. Skills never contain domain facts, and domains never contain procedures.

## Install

Clone into your agent's skills directory.

**Codex**

```bash
git clone https://github.com/LWWalker2202/econ-research-kit.git \
  ~/.codex/skills/econ-research-kit
```

**Claude Code**

```bash
git clone https://github.com/LWWalker2202/econ-research-kit.git \
  ~/.claude/skills/econ-research-kit
```

**DSH (DeepSeek Harness)**

DSH reads two skill directories, a shared one and its own:

```bash
# shared across agents, recommended
git clone https://github.com/LWWalker2202/econ-research-kit.git \
  ~/.agents/skills/econ-research-kit

# or DSH-only
git clone https://github.com/LWWalker2202/econ-research-kit.git \
  ~/.dsh/skills/econ-research-kit
```

On Windows these are `%USERPROFILE%\.agents\skills\` and `%USERPROFILE%\.dsh\skills\`; one skill is one directory that contains `SKILL.md`, so no extra registration step is needed. If DSH is already running, start a new session so the skill list is rebuilt.

Restart the agent. To verify it loaded, ask: *"In econ-research-kit, what does the feasibility skill decide?"* If the agent cannot answer, the skill is not on its path.

No build step, no dependencies beyond Python 3.9+ for the scripts in `scripts/`.

## Quick start

**Check whether a project is worth starting**

> My data is a firm-level panel from 2010 to 2019. I want to know whether the central environmental inspection reduced firm emissions. Is this feasible?

The agent should enter `skills/feasibility/`, enumerate the data and the variation, and produce `feasibility.md` with an explicit stop/go verdict — before writing any code.

**Clean a panel and document the definitions**

> Merge the firm panel with the pollution monitoring data and construct the emission variable.

The agent should enter `skills/data-prep/`, check variable definitions across years first, and produce a cleaning script plus a variable-definition table. It should not hand-edit the data.

**Produce a journal-formatted regression table**

> Turn these three specifications into a table for submission.

The agent should enter `skills/tables-figures/`, ask Stata or Python, and match the target journal's format — booktabs rules, coefficients with standard errors beneath, note placement.

## Design principles

1. **Stage 0 is a gate, not a step.** If feasibility fails, stop. Never clean data for a project whose identification cannot work.
2. **Artifacts over prose.** Every stage leaves a named file. A paragraph is not an artifact.
3. **Scripts over results.** A number that cannot be regenerated by running a script does not exist.
4. **Domain knowledge is separate from procedure.** It is the only part that cannot be outsourced to a generic toolkit, so it gets its own directory.
5. **Acceptance items must be answerable yes/no.** "The table looks good" is not an acceptance item. "Column widths do not overflow the text block" is.

## Vendoring third-party toolkits

The heavy lifting for tables, figures, and data cleaning is already solved by open-source projects. Do not rewrite it, and do not edit it in place.

`skills/tables-figures/` and `skills/data-prep/` each contain two layers:

| Layer | Rule |
|---|---|
| `vendor/` | Copied verbatim, never modified. Each directory carries a `LICENSES.md` recording upstream repository, commit hash, licence, and "unmodified". |
| `overrides/` | Our own layer. Journal-specific formatting, Chinese-journal conventions, fixes for data quirks. This is the only place we edit. |

Vendored content is code and LaTeX templates — language-neutral — so it is **byte-identical in both language mirrors**. Only `overrides/` is translated.

Vendored so far:

| Directory | Upstream | Commit | Licence |
|---|---|---|---|
| `skills/tables-figures/vendor/stata-schemepack/` | asjadnaqvi/Stata-schemes (package `schemepack`) | `580187ca3cd1101a17da6518a258b8ac533f7c5e` | MIT |
| `skills/tables-figures/vendor/awesome-econ-ai-stuff/` | meleantonio/awesome-econ-ai-stuff | `dd890d51c789fb8f8e316a2d7e4ed5d4bd793c50` | CC0 1.0 Universal |
| `skills/tables-figures/vendor/mgmt-paper-skills/` | HaonanAlex/mgmt-paper-skills | `971d2f510dc849b3fbf55836f78f6f2847203a1f` | Apache-2.0; `LICENSE` and `NOTICE` travel with it |
| `skills/tables-figures/vendor/tex4econ-tab/` | FanWangEcon/Tex4Econ | `8f7a254656b98ce5c152ea3b5ed1f2833cca496e` | MIT |
| `skills/data-prep/vendor/awesome-econ-ai-stuff/` | meleantonio/awesome-econ-ai-stuff | `dd890d51c789fb8f8e316a2d7e4ed5d4bd793c50` | CC0 1.0 Universal |

Five vendor directories, 103 files, about 350 KB. What they carry:

- Ten Stata graph schemes: the complete white-background family plus one colour-blind-safe scheme.
- Three prompt specifications with worked skeletons: `booktabs` regression tables, `ggplot2` figures, a Stata cleaning do-file.
- `mgmt-paper-skills/` contributes three whole subdirectories, copied unmodified: `mgmt-paper-tables/` with journal table rules for 《经济研究》, 《管理世界》, Journal of Finance and Management Science, significance and standard-error conventions, and Stata, R and Python templates with tests; `mgmt-paper-publication-figures/` with Chinese-journal figure and table conventions and seven matplotlib templates; `mgmt-paper-journal-figures/` with figure profiles across the UTD 24 business journals.
- Five LaTeX table fragments from `Tex4Econ`'s `_tab/`: estimation, multi-panel and text tables, `.tex` sources only.

Licence check outcome:

- `codex-stata-for-economists` looks useful, but the repository has no `LICENSE`, `LICENCE` or `COPYING` file and no licence statement in any of its markdown. No licence means no permission, so it is not vendored.
- `EthanDeng/Chinese-ERJ` at `8cd9523ae8f34c3d272e5369a66a341317bc6c96` is LPPL 1.3c. Verbatim redistribution is permitted, so copying unchanged would not conflict with it, but the material is one journal's document class (`chinese-erj.cls` for 《经济研究》) that depends on the external `biblatex-gb7714-2015` package: too narrow to carry, so not vendored.
- `esttab`, `coefplot`, `modelsummary` and `fixest` remain the right answer for tables and coefficient plots, but they are installed by the user's own Stata or R, so their code is not copied here.
- A candidate without a plain-text MIT, BSD-2, BSD-3, Apache-2.0, CC-BY or CC0 grant is rejected. Being public on GitHub is not a licence.

Three rules hold for every vendored directory: copy verbatim and never edit; carry a `LICENSES.md` recording repository URL, commit hash, the exact files copied, the licence, where the licence file sits, and the copy date; no git submodules, so a plain clone is complete. Each `vendor/` directory also carries an index `LICENSES.md` listing its upstreams and the candidates rejected. Journal conventions belong in `overrides/`. Do not paste code in without recording its commit.

## Parity with the Chinese mirror

`econ-research-kit-zh` is the same tree in Chinese. Rules:

- File paths and filenames are identical and never translated.
- `scripts/` and `glossary.yaml` are **byte-identical**.
- Every other file has the same heading structure, the same acceptance-item count, and the same placeholder set — only the language differs.
- `writing` and `tables-figures` are the deliberate exception: the English edition documents English-journal conventions, the Chinese edition documents Chinese-journal conventions. Same sections, different content.

`scripts/check_parity.py` enforces all of this. CI runs it on every push.

## Contributing

1. Read `_glossary` rules first: method terms must use `locked` translations.
2. New skills need all eight sections. `scripts/lint_content.py` will tell you what is missing.
3. Do not add a ninth skill without removing one. Eight stages is the design, not a starting point.
4. Numbers, page references, and policy document numbers are never invented. Write `[to fill]` instead.
5. Looking for a source? `scripts/lookup_source.py CFPS` searches an external directory of over a thousand sources. A hit is a lead; write a numbered entry in `data-dict/` once you actually use it.

## Status

Version 0.2.0. Eight skills, ten domains, four data dictionaries, three teaching tracks. Three stages ship with a runnable template and a golden output to diff against: `data-prep`, `estimation`, and `tables-figures`. Vendoring done in two passes: graph schemes, prompt specifications, three management-journal table and figure skill directories, and LaTeX table fragments; licences recorded under `skills/*/vendor/`. Reporting conventions measured from 28 Chinese-journal articles sit under `skills/*/overrides/`. Chinese mirror at parity.

## Licence

MIT for our content. Vendored material keeps its own licence, recorded in each `vendor/LICENSES.md`.
