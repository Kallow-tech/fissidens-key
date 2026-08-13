# Modifications to the FSC Identikit

This repository redistributes the FSC Identikit (version 1.10.0) by the Field
Studies Council, which is licensed under the **GNU General Public License v3.0**.
The original software is available at
https://github.com/FieldStudiesCouncil/tombiovis

GPL-3.0 requires that modified versions be marked as changed. The changes made
to the original Identikit code in this repository are listed below.

## Changed files

### `tombio/tombiovis.js`

**Line 326.** Changed `.text()` to `.html()` so that HTML markup in the
knowledge-base title renders instead of being escaped. This allows the genus
name in the key title to be shown in italics, following standard scientific
nomenclature convention.

Original:

```js
$("#tombiod3-header").text(tbv.d.kbmetadata.title);
```

Modified:

```js
$("#tombiod3-header").html(tbv.d.kbmetadata.title);
```

Note: the same call exists in `tombio/min/js/tombiovis.min.js`. If that file was
also patched, record it here.

## Not modified

No other files in the `tombio/` directory have been changed. All identification
content in `kb/biscuits2/` is original work by the authors of this knowledge base
and is not part of the Identikit software.

## If you upgrade Identikit

A new release of Identikit will overwrite `tombio/tombiovis.js` and the title
italics will silently stop working. Re-apply the change above after any upgrade.
