# Geniuslink performance baseline — 2026-11-18

Source: read-only Geniuslink production MCP connector. Data fetched 2026-11-18. Do not treat clicks as purchases or commissions.

## Account click trend

Requested period: 2026-10-19 through 2026-11-17 (daily). API returned 28 dated records, so totals below cover **returned records**, not necessarily every calendar day in the requested window.

- Raw clicks: **169**
- Clicks excluding bots (Geniuslink `ClicksMinusBot`): **111**
- Spider traffic reported: **57**
- These fields are separate counters and may not sum exactly because other traffic classifications exist.

Recent non-bot daily clicks:

| Date | Non-bot clicks |
|---|---:|
| 2026-11-11 | 3 |
| 2026-11-12 | 3 |
| 2026-11-13 | 2 |
| 2026-11-14 | 21 |
| 2026-11-15 | 22 |
| 2026-11-16 | 8 |
| 2026-11-17 | 13 |

## Link inventory

- 67 links returned in the inventory
- 24 links had nonzero lifetime click totals
- These totals are lifetime per-link values, not the account period totals above.

| Product | Shortlink | Lifetime clicks |
|---|---|---:|
| Renewed HP ProDesk Mini PC | https://geni.us/QmhH7 | 42 |
| Home Assistant Green | https://geni.us/igyZr | 25 |
| LD2410C sensor | https://geni.us/TfpZvN | 8 |
| ESP32-C3 SuperMini | https://geni.us/mZse | 8 |
| Raspberry Pi 5 | https://geni.us/Lf4SuLL | 5 |

## Changes made after baseline

- PIP Builds MultiSensor project page: add visible parts links and nearby affiliate disclosure.
- PIP Builds Home Assistant hardware guide: add prominent links to three hardware choices and nearby disclosure.
- Prices remain unpublished.

## Measurement plan

Compare **non-bot clicks** over the next 7 and 30 days. Review the five links above and the complete account click trend. Since the same links appear across GitHub, YouTube, and PIP Builds, link totals alone **cannot attribute clicks to the updated website pages**. To measure page-specific uplift, use dedicated tracked links or supported campaign parameters for each placement. Do not claim conversion rates without affiliate purchase/commission data.
