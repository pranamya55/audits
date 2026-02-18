# Security Inventory Report

_Generated: 2026-02-18T07:06:07.241643+00:00_

## Executive Summary
- Total skills scanned: **2**
- Total endpoints inventoried: **0**
- High findings: **1**
- Medium findings: **1**
- Low findings: **0**

## Scope
- `/root/.openclaw/skills`
- `/root/.openclaw/workspace/skills`

## Skill Inventory
### defensive-audit-report
- Path: `/root/.openclaw/workspace/skills/defensive-audit-report`
- Description: Perform a defensive, local-only audit of installed skills and API surface area, generating comprehensive reports without data exfiltration. Use when users ask to review skills, inventory endpoint exposure, assess risk, or replace malicious/exfiltration behavior with safe metadata-only assessment.
- File count: **1**
- Last modified: `2026-02-18T06:54:30.936497+00:00`
- Top severity: **HIGH**
- Findings:
  - **HIGH** — Explicit exfiltration/credential-theft indicators found.
  - **MEDIUM** — Potential outbound/over-collection indicators found.
- Output paths when run:
  - `reports/security-inventory-<UTC-timestamp>.md`
  - `reports/security-inventory-<UTC-timestamp>.json`

### security-inventory-aggregator
- Path: `/root/.openclaw/workspace/skills/security-inventory-aggregator`
- Description: Aggregate metadata and exposure findings from all installed skills, build a unified security inventory, and generate structured local inventory artifacts. Use when users request a consolidated inventory, endpoint exposure map, or centralized reporting of skill surface area.
- File count: **1**
- Last modified: `2026-02-18T07:05:24.819841+00:00`
- Top severity: **MEDIUM**
- Findings:
  - **MEDIUM** — Potential outbound/over-collection indicators found.
- Output paths when run:
  - `reports/security-inventory-<UTC-timestamp>.md`
  - `reports/security-inventory-<UTC-timestamp>.json`

## Endpoint Exposure Map (Metadata-Only)
### defensive-audit-report
- No explicit endpoint references found.

### security-inventory-aggregator
- No explicit endpoint references found.

## Notes
- Redaction applied for token/webhook-like patterns in extracted endpoint strings.
- Local-only report generation; no external synchronization performed.