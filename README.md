# Case 09 — Threat Intelligence Dashboard

**MSc IT Part 1 | Threat Intelligence Dashboard Mini Project**

## Project Overview
This project investigates removable-media activity in a simulated research laboratory using Microsoft Power BI.

## Investigation Objectives
- Identify suspicious USB activity across hosts.
- Link USB mount, file-read, write and unmount events.
- Assess data sensitivity and approximate write volume.
- Verify device approval scope and threat-feed context.
- Evaluate possible copying, onward disclosure and user intent.
- Identify evidence gaps and recommend next actions.

## Dashboard Pages
1. **Triage:** Event overview, affected hosts, action distribution, timeline and event details.
2. **Investigation:** USB write events, host activity, allowlist scope and threat-feed context.
3. **Intelligence Assessment:** Key findings, evidence chain, potential impact, candidate MITRE ATT&CK mapping, false-positive considerations and recommended actions.

## Key Finding
The supplied records show a 2,600,000,000-byte write involving USB-9921 on host H06 after access to the restricted research file `materials_trial_raw.csv`. The reviewed allowlist entry A09-05 approves USB-1002 on H05 for inventory export only; it does not establish approval for USB-9921 on H06.

The evidence supports suspected unauthorized copying that requires further investigation. Onward disclosure and user intent remain unconfirmed.

## Main Evidence Chain

| Event ID | Time (UTC) | Host / Device | Activity |
|---|---|---|---|
| C09-E138 | 17:00, 19 Sep 2026 | H06 / USB-9921 | USB mounted |
| C09-E140 | 17:03, 19 Sep 2026 | H06 | Restricted file read |
| C09-E142 | 17:08, 19 Sep 2026 | H06 / USB-9921 | 2,600,000,000-byte write |
| C09-E145 | 17:11, 19 Sep 2026 | H06 / USB-9921 | USB unmounted |

## Repository Files
All project files are currently in the repository root.

- `Case09_Dashboard.pbix` — Editable Power BI report.
- `Case09_Dashboard.pdf` — Dashboard PDF export.
- `Case09_Analysis.docx` — Analyst Note.
- `Case09_DATA MODEL & TRANSFORMATION NOTE.docx` — Data Model & Transformation Note.
- `Case_09_Dataset.xlsx` — Source dataset.
- `README.md` — Project overview and evidence summary.

## Tools Used
- Microsoft Power BI
- Power Query
- Microsoft Excel

## Limitations and Next Actions
The available records do not prove onward disclosure, malicious intent or actor attribution. The expired feed indicator is not treated as current corroboration. Further investigation should preserve host and USB evidence, verify file hashes and copy records, and review user approvals, DLP alerts and network logs.

The most important missing evidence is a forensic image or reliable USB file manifest linked to the host's file-copy records.

## Disclaimer
This is an academic investigation based on simulated case data. Conclusions are limited to the available records, and suspected copying does not establish confirmed external disclosure.
