# Case 09 — Threat Intelligence Dashboard

## Project Overview
This project investigates removable-media activity in a simulated research-lab environment using Microsoft Power BI.

## Investigation Objectives
- Identify suspicious USB activity across hosts.
- Correlate device mount, file-read, write, and unmount events.
- Review allowlist scope and threat-feed context.
- Assess potential impact and identify evidence gaps.
- Map observed behavior to a candidate MITRE ATT&CK technique.

## Dashboard Pages
1. **Triage:** Event overview, host activity, timeline, and event details.
2. **Investigation:** USB write events, allowlist scope, and threat-feed context.
3. **Intelligence Assessment:** Key findings, evidence chain, impact, and recommended actions.

## Key Finding
The supplied records show a 2,600,000,000-byte write involving USB-9921 on host H06 after access to a restricted research file. The reviewed allowlist entry does not authorize this device on H06. Suspected unauthorized copying requires further investigation; onward disclosure and user intent remain unconfirmed.

## Project Files
- `Dashboard/` — Editable Power BI report and PDF export.
- `Documentation/` — Analyst Note and Data Model & Transformation Note.
- `Dataset/` — Source dataset, only if redistribution is permitted.

## Tools Used
- Microsoft Power BI
- Power Query
- Excel

## Disclaimer
This project uses simulated case data for academic investigation and educational purposes. Findings are limited to the supplied records.
