# grc-workbench inputs

**Doc ID:** IE-REP-005 | **Title:** Annex A multi-framework control library | **Version:** 1.0 | **Issued:** 2026-10-28 | **Owner:** Hakim Bilal | **Status:** Draft | **Next Review:** 2027-10-28

Reference data for **grc-workbench Stage 3** (the Statement of Applicability). 

## What it holds

`IE-REP-005 annex-a-control-library.csv`: one row for each of the 93 ISO/IEC 27001:2022 Annex A controls.

| Column | Meaning |
| --- | --- |
| `control_id` | Annex A number, for example A.8.22 |
| `theme` | Organisational (37), People (8), Physical (14), Technological (34) |
| `short_name` | Our own short label. The ISO wording is ISO's copyright and is not reproduced |
| `uae_ia_family` | UAE IA Regulation control family (M1 to M6, T1 to T9) |
| `iec62443_ref` | IEC 62443 part (for example 2-4) or 3-3 system requirement (for example SR 5.1). Blank means no meaningful match |
| `ot_crosswalk_rows` | Rows in the iec62443-building-ot-crosswalk repo that cite this control |

## Why it exists

So one SoA answers three frameworks. When a client marks A.8.22 as implemented, the workbench can show progress against UAE IA family T4 and IEC 62443 SR 5.1 at the same time. That is the "second framework" point turned into a feature.

## Limits

- UAE IA and IEC 62443 mappings are the author's judgement at family and SR level. Check before client use.
- SR numbers were checked on 2026-10-28 against two secondary sources (Open Security Architecture and TeepTrak), not the paywalled standard. One conflict: TeepTrak titles SR 4.3 "cryptographic key management", while this file uses it for use of cryptography. Either way it maps to A.8.24. Confirm against the standard before client use [likely].

## Change log

| Version | Date | Summary |
| --- | --- | --- |
| 1.0 | 2026-10-28 | First issue. 93 controls tagged to UAE IA families and IEC 62443; back-links to OT-01 to OT-31 checked by script. |
