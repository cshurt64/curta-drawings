# Curta drawings viewer

A browser viewer for the complete Contina (Curta) engineering drawing set, 257 scanned sheets, for people building,
restoring or studying the Curta calculator. It needs no server and no installation.

**Open it:** <https://cshurt64.github.io/curta-drawings/>, or clone this repository and open `index.html`.

## What it does

- **Catalog** (`index.html`): every sheet, searchable by part number or name, with filters for section and revision status.
- **Drawing viewer** (`viewer.html`): the original scan, plus an **interactive bilingual guide** on most sheets. Numbered
  markers sit beside each German part number, note or dimension; hover or click one to read the English translation.
  Part numbers in the notes link to that part's own sheet.
- **3× values (opt-in)**: on a sheet that has them, a *Show 3× values* switch adds each dimension multiplied by 3 to the marker text, for
  people building the 3× replica. They are derived project values, not on the scan, and are off by default.
- **3× redraw (pilot: 10.010, 10.041 and 10.021 so far)**: a third view of the sheet, redrawn with every value at 3× and the factory value in brackets. It is
  labelled as a derived redraw, with the disclosure repeated inside the image; the original scan is authoritative.
- **Used in / Contains**: which assembly a part goes into (with quantities and the evidence for them) and what an
  assembly contains.
- **Dimensions**: for 88 parts, a full audit of the dimensions and tolerances on the current sheet, with an ISO 286
  recalculation of every hole/shaft fit (the `audits/` pages).
- **Where-used index** (`where-used.html`): every recorded parent/child relationship in one table.
- **Bill of materials** (`bom.html`): every part and assembly with its per-machine quantity, sortable and searchable, as a flat table or an expandable assembly tree. Each quantity is checked against the recorded parent/child links, and disagreements are marked. CSV download included.

## Things to know before relying on it

- **Dimensions are in microns** (`Abmasse in μ = 1/1000 mm`): `22,5 ±20` means 22.5 mm ±0.020 mm.
- **Use the highest revision.** The set interleaves superseded revisions of a part on consecutive pages; the catalog marks which is current.
- The translations, quantities and audits are one person's reading of the scans. They are labelled `Confirmed`,
  `Derived` or `Unverified`; treat `Unverified` as a question, not a fact. Where a quantity could not be settled
  from the sheets, the page says so rather than guessing.
- Sheets are cited by their page number in the scanned set.

## Layout

| Path | What it is |
|---|---|
| `index.html`, `viewer.html`, `where-used.html`, `bom.html` | The four pages |
| `pages/` | The 257 scans (grayscale WebP) |
| `sources/` | The images the interactive guides are drawn on |
| `audits/` | The per-part dimensional audits, rendered to HTML |

The files here are generated from a private working repository; please don't edit them by hand. Corrections and
questions are welcome as GitHub issues on this repository.

## Licence

- **The original drawings** are the work of Contina AG and are in the public domain.
- **Everything added here** (the translations, the bilingual guides, the where-used data, the dimension audits and
  the viewer code) is © Chris Hurt and licensed under
  [Creative Commons Attribution 4.0 International](LICENSE) (CC BY 4.0). You may share and adapt it, including
  commercially, provided you credit "Chris Hurt, curta-drawings" and link to this repository.
