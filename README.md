# grc-workbench

One browser-based tool for asset and risk registers, the ISO/IEC 27001 Statement of Applicability, third-party risk scoring and CBUAE readiness, all sharing one data set. Every control is tagged to ISO/IEC 27001:2022, the UAE IA Regulation and IEC 62443, so one assessment answers all three. Data stays on the user's machine.

**Status:** v1.5. All six stages built and branded. Adds the GRC Readiness Review (`readiness-review.html`), a second tool for analyst-led readiness reviews of micro businesses and SMEs.

## Run it

Download the repository and open `index.html` in a browser. No install, no server, no account. The demo data is a fictional payments company.

Data is kept in the browser and can be exported to a JSON file and imported again. Nothing is sent anywhere.

For the GRC Readiness Review, open `readiness-review.html` the same way.

## Build stages

| Stage | Module | Release | Status |
| --- | --- | --- | --- |
| 1 | Page shell, asset register, control library view | v0.1 | Done |
| 2 | Risk register and heat map (ISO 27001 clause 6.1.2) | v0.2 | Done |
| 3 | Statement of Applicability linked to risks (clause 6.1.3) | v0.3 | Done |
| 4 | Supplier tiering and third-party risk (A.5.19 to A.5.22) | v0.4 | Done |
| 5 | CBUAE Operational Risk Management readiness, pre-filled from the SoA | v0.5 | Done |
| 6 | One-page gap report export | v1.0 | Done |
| - | Intelligent Environments brand (colours, type, report wordmark and footer) | v1.1 | Done |
| - | Gap report as a branded IE document: control block, classification, status colours | v1.2 | Done |

## GRC Readiness Review

An analyst asks the client's owner a short set of questions and the review works out which rules apply before asking anything else. A micro business answers about 20 questions; a regulated one up to about 60.

- **Goals and screening:** 15 questions on where the business is heading and what it does (who it sells to, premises systems, health data, AI, drones, driverless vehicles, connected systems, insurance, card payments, foreign customers, revenue) switch on only the modules that apply.
- **Question library v2.2:** 121 questions in 16 modules: every business, premises systems (CCTV, door entry, alarms, lifts, tills, signage), selling to businesses or government (e-invoicing), bank supplier (CBUAE), government supplier (UAE IA), health data, AI, drones, autonomous vehicles, connected systems (IEC 62443), insurance, card payments (PCI DSS v4.0.1), cross-border data, due diligence, larger contracts and expansion.
- **Hidden connections:** every review checks the seven routes that bypass office IT: remote support tools, USB sticks, contractor laptops, extra internet links (5G, satellite), shared PCs, SIM cards in building panels and cameras reachable from phones. A site walk is the reliable way to find them.
- **Rules that apply:** each rule is shown as mandatory, contractual or guidance, with its source.
- **Pass rule v1.1:** every question answered; every Critical control met and confirmed by management; no High control missing (a Yes that management will not confirm counts as missing); readiness at least 80%.
- **Due diligence compliance check:** for clients planning a sale, partner or funding, scored separately from pass or fail.
- **Current developments:** a ticker of verified regulatory changes and incidents, filtered to each client.
- **90-day fact rule:** every rule and development carries the date it was last checked against its source. Exports are blocked once any entry is more than 90 days old.
- **No secrets, no evidence:** the review records answers only. It never asks for passwords, MFA codes, encryption keys, documents or identification numbers.
- **One master list:** the same question library generates the review, the Business Security Audit workbook and the discovery checklist, so the three tools cannot drift apart.
- **Anonymised gap log:** exports hold counts only (quarter, sector, size band, emirate). Analyst notes are never exported.

Screening shows which rules are likely to apply; it is not legal advice.

## What is in the repo

| File | What it holds |
| --- | --- |
| `index.html` | The tool: one page, no external libraries |
| `data/controls.csv` | The 93 ISO/IEC 27001:2022 Annex A controls with our own short names (ISO wording is not reproduced), each tagged to a UAE IA control family and, where it fits, an IEC 62443 part or system requirement. See [`data/README.md`](data/README.md) |
| `data/controls.js` | The same library as JavaScript, so the page works when opened straight from disk. Generated; do not edit by hand |
| `data/cbuae-crosswalk.csv` | The 39 CBUAE Operational Risk Management requirements from [cbuae-orm-cyber-crosswalk](https://github.com/CyberHak44/cbuae-orm-cyber-crosswalk) (CC BY 4.0) |
| `data/cbuae.js` | The same requirements as JavaScript. Generated; do not edit by hand |
| `tools/build-data.js` | Rebuilds both `.js` data files from the CSVs: `node tools/build-data.js` |
| `readiness-review.html` | The GRC Readiness Review: one page, no external libraries, question library and developments built in |
| `data/library.json` | The readiness review question library (v2.2): screening, modules, rules with sources and check dates, questions with the evidence to look for, pass rule |
| `data/horizon.json` | Current developments shown in the ticker, each with sources and a check date |

## How the modules connect

Assets carry risks. Risks are scored (likelihood x impact, inherent and residual) against an appetite line. Controls in the Statement of Applicability treat risks. Suppliers support assets and are tiered and scored on evidence. The CBUAE readiness ratings start from the SoA and supplier results, and the gap report pulls all of it onto one page.

## Design rules

- One page, no server, no tracking. Data is exported and imported as a file.
- Demo data is fictional. No real client data in this repository.
- No passwords, keys or other secrets are ever collected.
- Mappings are the author's professional judgement, not guidance from ISO, IEC, ISA, TDRA or CBUAE.

## Related

- [cbuae-orm-cyber-crosswalk](https://github.com/CyberHak44/cbuae-orm-cyber-crosswalk): feeds the Stage 5 readiness module.
- [iec62443-building-ot-crosswalk](https://github.com/CyberHak44/iec62443-building-ot-crosswalk): source of the OT mappings in `data/controls.csv`.

## Author

**Clive (Hakim) Bean**: ISO/IEC 27001 Lead Auditor (GRC Mastery, 2026, Credly-verified). Intelligent Environments L.L.C-FZ, Abu Dhabi.

Research support: Polly, my AI assistant.

Document control: IE-TOOL-001 v1.3 and IE-TOOL-002 v1.7, Intelligent Environments document register IE-REG-001.
