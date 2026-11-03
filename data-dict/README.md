# Data dictionaries

## What this directory is

One file per data source, recording the things that are not in the official codebook and that a new user always gets wrong: the exact variable names, the definitions that changed across waves, the merge keys, the coverage holes.

This directory is not a complete list of datasets an economist might use. It cannot be, and it should not try to be. It is a cache of hard-won knowledge: every file here exists because someone already lost a week to that source.

So the directory is open-ended by design: there is no "supported sources" list to fall off. What is fixed is the procedure below, and it is exhaustive — every source, including one that does not exist yet, falls into class A, B, or C. A source you have never seen is not an exception to the rules; it is exactly what the rules are for.

## The four sections every entry has

1. `## Basic information` — full name in Chinese and English, abbreviation, maintaining institution, first year, update frequency, unit of observation.
2. `## Variables` — variable name, label, definition, typical values. Only the ones an empirical paper actually uses.
3. `## Known issues` — coverage gaps, definition changes across waves, known measurement problems, what referees ask.
4. `## Access` — the institution to apply to, the application route, typical lead time. Not a URL: URLs rot, institution names do not.

Five rules for an entry: no URLs, no software version numbers, no invented sample sizes, mark every unverified variable name `[to fill]`, and keep it to the variables you have actually used.

## Class A: Chinese micro data, worth adding an entry

Examples: CFPS, CHARLS, CHFS, CGSS, CHNS, CLDS, the Chinese Industrial Enterprises Database, China Customs, CSMAR, Wind.

These belong here because their variable names are not guessable, their definitions drift between waves, and referees ask about them. A well-written entry for one of these saves every future user of that source the same week.

When you add one, add it back to this directory. That is the whole point of the cache.

## Class B: international public databases, do not add an entry

Examples: World Bank, FRED, IPUMS, Penn World Table, OECD, Eurostat, national statistical offices.

These ship their own authoritative, machine-readable documentation. A second-hand summary in this directory would be worse than the original and would rot silently.

What is worth recording is not the variable list but the traps: which price base, which PPP vintage, whether coverage changed in a given year, and how comparability was enforced across countries. Those notes go in the project's own `data-dictionary.csv`, next to the analysis, not here.

## Class C: data you built yourself, the dictionary is your design

Examples: a laboratory experiment, a survey you fielded, scraped text, hand-coded policy documents, interview transcripts.

There is no external codebook for these, because the data did not exist until you made it. The dictionary is therefore part of the design, not a lookup: the instrument, the randomization script, the scraping specification, the codebook you wrote for coders.

Record it in the project's `data-dictionary.csv`, and keep it consistent with the pre-registration and the ethics approval. If the definition changed after the pre-registration, that change is a finding about the study, not a housekeeping detail.

## How to add an entry

1. Search this directory first. If a file already covers the source, extend it; do not create a second one.
2. Classify the source as A, B, or C using the sections above.
3. For class A: copy the four section headings, fill what you know, and mark the rest `[to fill]`.
4. For classes B and C: write the notes into the project's `data-dictionary.csv` and do not add a file here.
5. Run `python scripts/lint_content.py .` before committing.

## Naming and scope

Lowercase with hyphens, one file per source rather than per wave: `cfps.md`, `industrial-firms.md`, `pollution-monitoring.md`.

A source deserves an entry when at least one of these holds: its variable names cannot be guessed, a definition changed across waves, the merge key needs a crosswalk, or referees commonly ask about it. If none of those hold, the official documentation is enough and this directory should stay out of the way.
