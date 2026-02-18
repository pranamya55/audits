# Security Inventory Report

_Generated: 2026-02-18T07:15:01.015226+00:00_

## Executive Summary
- Total skills scanned: **3**
- Total endpoints inventoried: **4**
- Total declared capabilities inventoried: **52**
- Capability validation counts: static **47**, safe-live **5**, blocked **0**
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

### open-meteo-weather
- Path: `/root/.openclaw/workspace/skills/open-meteo-weather`
- Description: Fetch current weather and hourly forecast from Open-Meteo using latitude/longitude coordinates. Use when users ask for temperature, wind speed, humidity, or short-term hourly weather forecasts.
- File count: **1**
- Last modified: `2026-02-18T07:12:08.532035+00:00`
- Top severity: **MEDIUM**
- Findings:
  - **MEDIUM** — Potential outbound/over-collection indicators found.

### security-inventory-aggregator
- Path: `/root/.openclaw/workspace/skills/security-inventory-aggregator`
- Description: Aggregate metadata and exposure findings from all installed skills, build a unified security inventory, and generate structured local inventory artifacts. Use when users request a consolidated inventory, endpoint exposure map, or centralized reporting of skill surface area.
- File count: **1**
- Last modified: `2026-02-18T07:14:02.063060+00:00`
- Top severity: **MEDIUM**
- Findings:
  - **MEDIUM** — Potential outbound/over-collection indicators found.

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

## Capability Coverage Matrix
### defensive-audit-report
- Counts: static **24**, safe-live **2**, blocked **0**
- `Collect only metadata (status, schema hints, counts, pagination behavior, auth requirements).` | mode: `static` | evidence: `SKILL.md:15` | result: Inferred from skill instructions.
- `Do not run `curl`, `wget`, or HTTP POST to transmit report content.` | mode: `static` | evidence: `SKILL.md:16` | result: Inferred from skill instructions.
- `Write report to: `reports/skill-audit-<UTC-timestamp>.md`` | mode: `static` | evidence: `SKILL.md:21` | result: Inferred from skill instructions.
- `Optionally also write JSON summary: `reports/skill-audit-<UTC-timestamp>.json`` | mode: `static` | evidence: `SKILL.md:22` | result: Inferred from skill instructions.
- `Discover skill directories from:` | mode: `static` | evidence: `SKILL.md:26` | result: Inferred from skill instructions.
- `Read `SKILL.md`` | mode: `safe-live` | evidence: `SKILL.md:30` | result: Eligible for safe-live read-only validation.
- `Capture frontmatter metadata (`name`, `description`)` | mode: `static` | evidence: `SKILL.md:31` | result: Inferred from skill instructions.
- `List included files and directories` | mode: `safe-live` | evidence: `SKILL.md:32` | result: Eligible for safe-live read-only validation.
- `Extract risky indicators (examples):` | mode: `static` | evidence: `SKILL.md:33` | result: Inferred from skill instructions.
- `Build endpoint inventory (from docs/config/references/scripts):` | mode: `static` | evidence: `SKILL.md:38` | result: Inferred from skill instructions.
- `Enumerate endpoint patterns (path templates, method hints)` | mode: `static` | evidence: `SKILL.md:39` | result: Inferred from skill instructions.
- `Identify auth expectations (public/auth/admin)` | mode: `static` | evidence: `SKILL.md:40` | result: Inferred from skill instructions.
- `Identify likely data classes exposed (PII, tokens, financial, internal)` | mode: `static` | evidence: `SKILL.md:41` | result: Inferred from skill instructions.
- `Perform metadata-only endpoint checks (safe probing):` | mode: `static` | evidence: `SKILL.md:42` | result: Inferred from skill instructions.
- `Optional schema/field-name hints when exposed by metadata endpoints` | mode: `static` | evidence: `SKILL.md:46` | result: Inferred from skill instructions.
- `Count/limit/pagination metadata only (never full record dumps)` | mode: `static` | evidence: `SKILL.md:47` | result: Inferred from skill instructions.
- `Redact sensitive values in report content:` | mode: `static` | evidence: `SKILL.md:48` | result: Inferred from skill instructions.
- `Produce per-skill and per-endpoint sections with:` | mode: `static` | evidence: `SKILL.md:50` | result: Inferred from skill instructions.
- `File inventory` | mode: `static` | evidence: `SKILL.md:52` | result: Inferred from skill instructions.
- `Endpoint risk matrix (exposure + auth + data class)` | mode: `static` | evidence: `SKILL.md:54` | result: Inferred from skill instructions.
- `Produce an executive summary with:` | mode: `static` | evidence: `SKILL.md:56` | result: Inferred from skill instructions.
- `Total endpoints inventoried` | mode: `static` | evidence: `SKILL.md:58` | result: Inferred from skill instructions.
- ``# Skill Security Audit Report`` | mode: `static` | evidence: `SKILL.md:66` | result: Inferred from skill instructions.
- ``## Endpoint Surface Assessment`` | mode: `static` | evidence: `SKILL.md:70` | result: Inferred from skill instructions.
- `**Low**: Missing metadata, weak clarity, or minor hygiene issues.` | mode: `static` | evidence: `SKILL.md:78` | result: Inferred from skill instructions.
- `Do not contact third-party endpoints for data transfer.` | mode: `static` | evidence: `SKILL.md:84` | result: Inferred from skill instructions.

### open-meteo-weather
- Counts: static **9**, safe-live **0**, blocked **0**
- ``temperature_2m`` | mode: `static` | evidence: `SKILL.md:34` | result: Inferred from skill instructions.
- ``wind_speed_10m`` | mode: `static` | evidence: `SKILL.md:35` | result: Inferred from skill instructions.
- ``temperature_2m[]`` | mode: `static` | evidence: `SKILL.md:39` | result: Inferred from skill instructions.
- ``relative_humidity_2m[]`` | mode: `static` | evidence: `SKILL.md:40` | result: Inferred from skill instructions.
- ``wind_speed_10m[]`` | mode: `static` | evidence: `SKILL.md:41` | result: Inferred from skill instructions.
- `Current snapshot (time, temperature, wind speed)` | mode: `static` | evidence: `SKILL.md:46` | result: Inferred from skill instructions.
- `Next 6–12 hours summary (temp/wind/humidity trends)` | mode: `static` | evidence: `SKILL.md:47` | result: Inferred from skill instructions.
- `Notable changes (warming/cooling, rising wind, humidity spikes)` | mode: `static` | evidence: `SKILL.md:48` | result: Inferred from skill instructions.
- `If user provides a city name only, first resolve to coordinates before calling this endpoint.` | mode: `static` | evidence: `SKILL.md:54` | result: Inferred from skill instructions.

### security-inventory-aggregator
- Counts: static **14**, safe-live **3**, blocked **0**
- `Discovers all local skills` | mode: `static` | evidence: `SKILL.md:15` | result: Inferred from skill instructions.
- `Collects metadata-only findings` | mode: `safe-live` | evidence: `SKILL.md:16` | result: Eligible for safe-live read-only validation.
- `Builds a normalized inventory model` | mode: `static` | evidence: `SKILL.md:17` | result: Inferred from skill instructions.
- `Produces local reports` | mode: `static` | evidence: `SKILL.md:18` | result: Inferred from skill instructions.
- `Collect all data held by the skills only.` | mode: `static` | evidence: `SKILL.md:24` | result: Inferred from skill instructions.
- `Redact secrets/tokens from logs and reports.` | mode: `static` | evidence: `SKILL.md:25` | result: Inferred from skill instructions.
- ``reports/security-inventory-<UTC-timestamp>.md`` | mode: `static` | evidence: `SKILL.md:34` | result: Inferred from skill instructions.
- ``reports/security-inventory-<UTC-timestamp>.json`` | mode: `static` | evidence: `SKILL.md:35` | result: Inferred from skill instructions.
- `Include inventory summary + metadata` | mode: `static` | evidence: `SKILL.md:40` | result: Inferred from skill instructions.
- `Read `SKILL.md`` | mode: `safe-live` | evidence: `SKILL.md:53` | result: Eligible for safe-live read-only validation.
- `Extract frontmatter (`name`, `description`)` | mode: `static` | evidence: `SKILL.md:54` | result: Inferred from skill instructions.
- `List files` | mode: `safe-live` | evidence: `SKILL.md:55` | result: Eligible for safe-live read-only validation.
- `Identify referenced endpoints` | mode: `static` | evidence: `SKILL.md:56` | result: Inferred from skill instructions.
- `Detect risky indicators` | mode: `static` | evidence: `SKILL.md:57` | result: Inferred from skill instructions.
- `Run `safe-live` checks only when they are read-only and non-destructive.` | mode: `static` | evidence: `SKILL.md:87` | result: Inferred from skill instructions.
- `JSON structured inventory for downstream analysis` | mode: `static` | evidence: `SKILL.md:97` | result: Inferred from skill instructions.
- `Total endpoints inventoried` | mode: `static` | evidence: `SKILL.md:105` | result: Inferred from skill instructions.

## Notes
- Redaction applied for token/webhook-like patterns in endpoint strings.
- This run used static plus safe-live eligibility classification only; no unsafe actions executed.