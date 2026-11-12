# Renewable Energy Zones Feasibility Tool

Public-data screening tool for comparing candidate wind and solar Renewable Energy Zones (REZs) in Ontario: land suitability, resource potential, representative grid connections, and infrastructure costs.

ENG 4000 Capstone, Group 17, Lassonde School of Engineering, York University. Faculty supervisor: Prof. Hany Farag.

> **Preliminary screening only.** Outputs are not connection approvals, confirmation of available grid capacity, land rights, environmental permits, or construction-ready designs. Public transmission maps do not confirm spare capacity at any station or line.

## Why

Ontario's 2026 Annual Planning Outlook projects demand rising to ~250 TWh by 2050. Midgard's review of IESO planning recommended evaluating REZs as part of least-regrets planning. The relevant public data (resource atlases, IESO guidance, Ontario geospatial layers) is spread across sources with different formats, periods and resolutions. This tool brings them into one traceable, explainable early-stage comparison.

## Architecture (planned)

Selected concept: **GIS screening plus selected connection and energy case studies** (Concept C). The fallback is screening only (Concept B).

```
Public sources + version register
  -> Spatial / land screening
  -> Wind and solar generation
  -> Connection alternatives
  -> Electrical checks
  -> Cost + scenario comparison
  -> Delivered energy, losses, curtailment
  -> REZ comparison + confidence / export

Cross-cutting: public-data gate | unit checks | saved inputs | test evidence
```

| Module | Input | Output |
|---|---|---|
| Data preparation | Public geospatial files and metadata | Checked layers and source register |
| Land screening | Land boundaries and chosen rules | Remaining land and flagged uncertainties |
| Wind and solar assessment | Resource inputs and example layouts | Representative generation estimates |
| Connection comparison | Generation output and public grid context | Documented alternative limits and losses |
| Cost and reporting | Included assets and model results | Comparable scenarios with assumptions |

The exact software packages and level of network detail are still under review.

## Requirements

| ID | Requirement |
|---|---|
| DATA-01 | Record each input's source, date, permitted use and processing history |
| GIS-01 | Calculate remaining land using documented exclusions; flag missing or uncertain constraints |
| GEN-01 | Compare wind and solar generation on a consistent, stated basis |
| CON-01 | Compare documented connection alternatives for selected cases |
| ELE-01 | Apply modelled network restrictions when estimating energy delivery |
| ENE-01 | Distinguish available generation, delivered energy, losses and curtailment |
| CST-01 | Transparent infrastructure-cost comparison without double-counting shared assets |
| UNC-01 | Flag missing data and show the effect of changing key assumptions |
| REP-01 | Retain sources, assumptions and software version to reproduce any assessment |
| SAFE-01 | Label outputs as preliminary; never claim approval or confirmed grid capacity |

## Data sources

- IESO 2026 Annual Planning Outlook and LT2 connection guidance
- AEMO 2026 Integrated System Plan and REZ appendix (method reference only)
- Global Wind Atlas, NRCan Canadian Wind Turbine Database
- Global Solar Atlas, NASA POWER hourly API
- Ontario Hydro Network (waterbodies), Ontario Utility Line dataset

Licences and permitted reuse are checked before any dataset is used. Raw datasets are not committed to this repository.

## Team

| Member | Area |
|---|---|
| Muhammed Abou-Hantash | Project coordination and report integration |
| Aaser Al-Hamoud | Validation, documentation and data governance |
| Hussein Amin | Wind resources and preliminary layouts |
| Julian John Kansiuse | Solar resources and preliminary layouts |
| Derek Morocho Bolanos | Transmission and infrastructure alternatives |
| Oscar Ye | GIS integration, software architecture and interface |

## Status

Problem definition and conceptual design are complete (Progress Report 1, Nov 2026). Software development runs Nov 2026 to Mar 2027, verification runs Feb 15 to Apr 9, 2027, and Capstone Day is Apr 23, 2027.
