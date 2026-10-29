# grc-workbench

One browser-based tool for asset and risk registers, the ISO/IEC 27001 Statement of Applicability, third-party risk scoring and CBUAE readiness, all sharing one data set. Every control is tagged to ISO/IEC 27001:2022, the UAE IA Regulation and IEC 62443, so one assessment answers all three. Data stays on the user's machine.

**Status:** v0.1 (Stage 1 of 6).

## Run it

Download the repository and open `index.html` in a browser. No install, no server, no account. The demo data is a fictional payments company.

Data is kept in the browser and can be exported to a JSON file and imported again. Nothing is sent anywhere.

## Build stages

| Stage | Module | Release | Status |
| --- | --- | --- | --- |
| 1 | Page shell, asset register, control library view | v0.1 | Done |
| 2 | Risk register and heat map (ISO 27001 clause 6.1.2) | v0.2 | Planned |
| 3 | Statement of Applicability linked to risks (clause 6.1.3) | v0.3 | Planned |
| 4 | Supplier tiering and third-party risk (A.5.19 to A.5.22) | v0.4 | Planned |
| 5 | CBUAE Operational Risk Management readiness, pre-filled from the SoA | v0.5 | Planned |
| 6 | One-page gap report export | v1.0 | Planned |

## What is in the repo

| File | What it holds |
| --- | --- |
| `index.html` | The tool: one page, no external libraries |
| `data/controls.csv` | The 93 ISO/IEC 27001:2022 Annex A controls with our own short names (ISO wording is not reproduced), each tagged to a UAE IA control family and, where it fits, an IEC 62443 part or system requirement. See [`data/README.md`](data/README.md) |
| `data/controls.js` | The same library as JavaScript, so the page works when opened straight from disk. Generated; do not edit by hand |
| `tools/build-controls.js` | Rebuilds `data/controls.js` from the CSV: `node tools/build-controls.js` |

## Design rules

- One page, no server, no tracking. Data is exported and imported as a file.
- Demo data is fictional. No real client data in this repository.
- Mappings are the author's professional judgement, not guidance from ISO, IEC, ISA, TDRA or CBUAE.

## Related

- [cbuae-orm-cyber-crosswalk](https://github.com/CyberHak44/cbuae-orm-cyber-crosswalk): feeds the Stage 5 readiness module.
- [iec62443-building-ot-crosswalk](https://github.com/CyberHak44/iec62443-building-ot-crosswalk): source of the OT mappings in `data/controls.csv`.

## Author

**Clive (Hakim) Bean**: ISO/IEC 27001 Lead Auditor (GRC Mastery, 2026, Credly-verified). Abu Dhabi.
