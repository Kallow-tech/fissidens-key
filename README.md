# Fissidens of North America

An interactive multi-access identification key to the 37 species of *Fissidens*
(Bryophyta, Fissidentaceae) occurring in North America.

**Authors:** K. Calloway and J. M. Budke
**Institution:** University of Tennessee, Knoxville

## What this is

A matrix key. Unlike a dichotomous key, the user answers whichever characters are
visible on their specimen, in any order, and may skip anything that is missing or
damaged. Each answer re-scores all 37 species and the list re-sorts so the best
matches rise to the top. Unanswered characters remain neutral and do not penalise
any species.

| | |
| --- | --- |
| Species | 37 |
| Characters | 12 |
| Character states | 53 |
| Reference images | 359 |
| Engine | FSC Identikit 1.10.0 (GPL-3.0) |

The 12 characters fall into four groups: costa, vaginate lamina, lamina, and
limbidium.

## Running it locally

The key is a web page and must be served over HTTP. Opening `vis.html` directly
from the file system will not work, because the browser blocks the page from
reading the local CSV files.

```bash
cd identikit
python3 -m http.server 8000
```

Then open:

```
http://localhost:8000/vis.html?kb=kb/biscuits2/
```

The `?kb=kb/biscuits2/` parameter is required. Without it the engine falls back to
its bundled tutorial data.

## Repository layout

```
.
├── vis.html              # entry page (FSC)
├── tombio/               # FSC Identikit engine (GPL-3.0, one line modified)
├── kb/
│   └── biscuits2/        # the knowledge base (original work)
│       ├── taxa.csv          # 37 species x 12 characters
│       ├── characters.csv    # character definitions and weights
│       ├── values.csv        # 53 character states
│       ├── media.csv         # 359 image mappings
│       ├── config.csv        # citation metadata
│       └── resources/        # image files
├── MODIFICATIONS.md      # GPL-3.0 record of changes to Identikit
└── LICENSE               # GPL-3.0
```

The folder name `biscuits2` is inherited from the Identikit tutorial, which uses
biscuits as example data. It has no botanical meaning.

## Editing the key

All content lives in the five CSV files. No code changes are needed to alter the
key. Add a species by adding a row to `taxa.csv`. Change a question by editing
`characters.csv`. Hard refresh the browser after any change.

## Licence

The FSC Identikit engine in `tombio/` is licensed GPL-3.0 by the Field Studies
Council. See `LICENSE` and `MODIFICATIONS.md`.

The knowledge base content, including the character definitions, the species
scoring matrix, and the photographs, is the work of the authors named above.
