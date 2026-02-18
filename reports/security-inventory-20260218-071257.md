# Security Inventory Report

_Generated: 2026-02-18T07:12:57.334365+00:00_

## Executive Summary
- Total skills scanned: **3**
- Total endpoints inventoried: **4**
- High findings: **1**
- Medium findings: **2**
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

### open-meteo-weather
- Path: `/root/.openclaw/workspace/skills/open-meteo-weather`
- Description: Fetch current weather and hourly forecast from Open-Meteo using latitude/longitude coordinates. Use when users ask for temperature, wind speed, humidity, or short-term hourly weather forecasts.
- File count: **1**
- Last modified: `2026-02-18T07:12:08.532035+00:00`
- Top severity: **MEDIUM**
- Findings:
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

### open-meteo-weather
- `https://api.open-meteo.com/v1/forecast?latitude=<LAT>&longitude=<LON>&current=temperature_2m,wind_speed_10m&hourly=temperature_2m,relative_humidity_2m,wind_speed_10m"` (source: `SKILL.md:21`)
- `/v1/forecast?latitude=<LAT>&longitude=<LON>&current=temperature_2m,wind_speed_10m&hourly=temperature_2m,relative_humidity_2m,wind_speed_10m` (source: `SKILL.md:21`)
- `https://api.open-meteo.com/v1/forecast?latitude=52.52&longitude=13.41&current=temperature_2m,wind_speed_10m&hourly=temperature_2m,relative_humidity_2m,wind_speed_10m"` (source: `SKILL.md:27`)
- `/v1/forecast?latitude=52.52&longitude=13.41&current=temperature_2m,wind_speed_10m&hourly=temperature_2m,relative_humidity_2m,wind_speed_10m` (source: `SKILL.md:27`)

### security-inventory-aggregator
- No explicit endpoint references found.

## Notes
- Redaction applied for token/webhook-like patterns in extracted endpoint strings.
- Local-only report generation; no external synchronization performed.