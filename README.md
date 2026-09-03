Fissidens of North America

An interactive multi-access identification key to the 37 species of Fissidens (Bryophyta, Fissidentaceae) occurring in North America.

Authors: K. Calloway, A. Mazzatta and J. M. Budke Institution: University of Tennessee, Knoxville Version: 0.1 (2025)

Use the key

https://kallow-tech.github.io/fissidens-key/

Works in any browser, on any device, with nothing to install.

What this is

A matrix key. Unlike a dichotomous key, the user answers whichever characters are visible on their specimen, in any order, and may skip anything that is missing or damaged. Each answer re-scores all 37 species and the list re-sorts so the best matches rise to the top. Unanswered characters remain neutral and do not penalise any species.

	
Species	37
Characters	12
Character states	52
Matrix cells	444
Reference photographs	359
Engine	FSC Identikit 1.10.0

The 12 characters fall into four groups: costa, vaginate lamina, lamina, and limbidium.

Species concepts and character states follow Flora of North America Volume 27.

Licence

This project combines three things under three different terms.

The software

The FSC Identikit engine in tombio/ is © Field Studies Council and licensed under the GNU General Public License v3.0. See LICENSE. One line has been modified; see MODIFICATIONS.md.

The photographs

Photographs © 2025 K. Calloway, A. Mazzatta and J. M. Budke.

Licensed under a Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0).

https://creativecommons.org/licenses/by-nc/4.0/

You are free to share and adapt these images for non-commercial purposes, including teaching and research, provided you give appropriate credit. Commercial use requires permission from the authors.

The knowledge base

Licensing of the character definitions, the species scoring matrix, and the associated data is still being decided. Please contact the authors before reusing these files.

How to cite

Calloway, K. Mazzatta, A. & Budke, J.M. (2025) Fissidens of North America (Version 0.1) [Knowledge-base] (for FSC Identikit). University of Tennessee. Knoxville, Tennessee.

Running it locally

Only needed for development. Everyone else should use the link above.

The key must be served over HTTP. Opening vis.html directly from the file system will not work, because the browser blocks the page from reading the local CSV files.

bash
git clone https://github.com/Kallow-tech/fissidens-key.git
cd fissidens-key
python3 -m http.server 8000

Then open:

http://localhost:8000/vis.html?kb=kb/biscuits2/

The ?kb=kb/biscuits2/ parameter is required. Without it the engine falls back to its bundled tutorial data.

Repository layout
.
├── index.html            # redirects to the key
├── vis.html              # entry page (FSC)
├── tombio/               # FSC Identikit engine (GPL-3.0, one line modified)
├── kb/
│   └── biscuits2/        # the knowledge base
│       ├── taxa.csv          # 37 species x 12 characters
│       ├── characters.csv    # character definitions and weights
│       ├── values.csv        # 52 character states
│       ├── media.csv         # 359 image mappings
│       ├── config.csv        # citation metadata
│       └── resources/        # image files
├── MODIFICATIONS.md      # GPL-3.0 record of changes to Identikit
└── LICENSE               # GPL-3.0 (engine only)

The folder name biscuits2 is inherited from the Identikit tutorial, which uses biscuits as example data. It has no botanical meaning.

Editing the key

All content lives in the five CSV files. No code changes are needed to alter the key. Add a species by adding a row to taxa.csv. Change a question by editing characters.csv. Hard refresh the browser after any change.

Reference

Flora of North America Editorial Committee. (Ed.). (2007). Flora of North America north of Mexico: Vol. 27. Bryophytes: Mosses, part 1. Oxford University Press.
