# Persistent Requirements -- Shopify SupplyMaster Workspace

> **For AI Assistant:** This file contains standing instructions that apply to every session in this workspace. Read this file at the start of any session involving this project.

---

## Requirement 1 -- Observation Logging

### Purpose
Mark is actively exploring the SupplyMaster app and recording real-time observations for future use in an **employee Standard Operating Procedure (SOP)** for The Golf Shop at Torrey Pines / shoptorreypines.com. All observations are indexed and stored in the Observations Log (see below).

### Trigger Convention
When Mark submits a message beginning with **OBS:**, treat it as an observation to be logged.

**Format examples:**
- OBS: the browse catalog view shows all supplier styles including ones without pre-decorated SKUs
- OBS [filters]: equal to any filter accepts comma-separated style numbers
- OBS [question]: not sure if the safety stock buffer applies before or after the sync writes inventory

The category tag in brackets is optional -- infer the category if not provided.

### AI Response Protocol on OBS: Messages
When an OBS: message is received:
1. **Acknowledge** the observation briefly
2. **Pull relevant context** from the SupplyMaster documentation files in this workspace and from the Project Overview (SupplyMaster Docs/Project-Overview-SupplyMaster-CutterBuck.md) -- surface anything that helps interpret or contextualize the observation
3. **Append a new indexed entry** to Observations/SupplyMaster-Observations-Log.md using the standard entry format below
4. **Report back**: the observation index number (e.g., OBS-003), the category filed under, and any relevant context worth highlighting

### Standard Entry Format

Each entry appended to the log must follow this exact structure:

```
### OBS-[NNN] -- [Short Title]
- **Date:** YYYY-MM-DD
- **Category:** [see categories below]
- **Type:** [Observation | Question | Decision]
- **Details:** Full text of the observation as submitted.
- **Context:** Relevant notes pulled from SupplyMaster documentation or project context.
```

Replace `[NNN]` with the next sequential 3-digit number (e.g., 001, 002, 003...).

### CRITICAL -- How to Write to the Observations Log

> **The `write_to_file` and `replace_in_file` tools crash in this workspace** with a "Failed to open diff editor" error. This is a known VS Code issue related to the Dropbox sync path.
>
> **Always append new entries to the log using `execute_command` with PowerShell `Add-Content`**, like this:
>
> ```powershell
> Add-Content -Path "c:\Users\Mark\Dropbox\TP Tech Projects\Shopify\Shopify SupplyMaster\Observations\SupplyMaster-Observations-Log.md" -Value "`n### OBS-001 -- Example`n- **Date:** 2026-06-17`n..." -Encoding UTF8
> ```
>
> Use a PowerShell here-string (`@' ... '@`) for multi-line entries to avoid escaping issues.

### Observation Categories
Infer the best-fit category from the observation content:

| Category | Covers |
|----------|--------|
| Catalog | Browse Catalog interface, product discovery, SKU identification |
| Filters | Filter panel, Equal To Any, variant filters, Filter History |
| Field Mapping | Match Fields, Liquid modifiers, pricing formulas, field assignments |
| Order Sync | PromoStandards PO flow, Manual/Automatic mode, tracking writeback |
| Inventory | Inventory mapping, warehouse locations, safety stock buffer |
| Sync | Auto Sync schedule, Update Settings, Sync History, errors |
| AI+ | AI+ Enrichment, copy quality, categories, tags |
| UI/UX | App navigation, interface behavior, workflow friction |
| Pricing | Margin formulas, Compare At Price, MSRP behavior |
| General | Anything that does not fit a specific category |

### Observation Types (Auto-Inferred)
Since observations are freeform, I will infer and label the type in the log:
- **Observation** -- a factual finding from the app
- **Question** -- an open item or uncertainty
- **Decision** -- a confirmed choice or confirmed behavior

---

## Log File Location

Observations/SupplyMaster-Observations-Log.md

---

## Project Context Summary

- **Store:** shoptorreypines.com -- The Golf Shop at Torrey Pines, La Jolla, CA
- **Integration:** SupplyMaster x Cutter & Buck (pre-decorated hero styles, standing program)
- **Status at requirement creation:** Pre-installation (SupplyMaster not yet installed)
- **Plan:** Basic (/mo) -- estimated 720-1,440 variants for curated hero set
- **Fulfillment model:** Model A -- C&B holds dedicated Torrey Pines pre-decorated SKUs; PromoStandards PO auto-submitted at time of sale; blind drop-ship to buyer
- **Master project doc:** SupplyMaster Docs/Project-Overview-SupplyMaster-CutterBuck.md
- **All SupplyMaster reference docs:** SupplyMaster Docs/ folder
