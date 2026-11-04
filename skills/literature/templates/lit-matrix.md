# Literature matrix

## How to use this file

One row per paper, six content columns plus a marker. Copy this file to `lit-matrix.csv` in your project folder and delete the example row. Fill it as you read, not afterwards: a matrix written from memory at the end of the week is a fiction with authors attached.

## The seven columns

| Column | What goes in it | What does not |
|---|---|---|
| `id` | A DOI, or venue + year + volume(issue) + pages, or a working-paper number | "the Card paper", a bare title, a URL you will lose |
| `citation` | Author, year, short title, as it will appear in your reference list | A full formatted reference you have not checked |
| `question` | The paper's question in one sentence | The paper's title |
| `design` | The actual design and estimator: two-way fixed effects DiD, bunching, IV with a named instrument, RDD with a named running variable | "empirical", "quantitative", "panel data" |
| `finding` | Direction or magnitude, with the outcome it applies to: +3.2% on employment, negative and insignificant | "significant", "positive effect" |
| `source` | Journal name or working-paper series | "the internet" |
| `closest` | `yes` on exactly one row, empty elsewhere | `yes` on three rows |

## A worked row

```text
id       : 示例刊甲 2019, 5(2), 11-40
citation : Example A (2019), Short title of the example paper
question : Does a city-level wage floor reduce teenage employment?
design   : Two-way fixed effects DiD, 2004 reform, county-year panel
finding  : Teen employment falls 3.2%; effect concentrated in small firms
source   : 示例刊甲
closest  : 
```

## What to do with each row

1. Pasted only from an abstract, or from a citation you saw inside another paper, mark `[verify]` in `finding` and do not cite it until you have opened it.
2. If two rows compete for `closest`, the gap sentence is not sharp yet; rewrite the gap until one row wins.
3. Keep rejected rows in a second file, not in this one. A matrix that carries everything shows nothing.

## What this file is not

It is not a summary of what you read: it is the evidence table behind one gap sentence. It is not a substitute for the paper itself, and it is not reviewed by `check_matrix.py` for truth — the checker reads format only.
