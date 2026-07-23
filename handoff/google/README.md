# Crēdo Legal — Google Ads · Upload

Search + Performance Max structure for account **`9399506772`**. Build via **Google Ads Editor**
(fastest) or MCP. **Launch PAUSED.** See the top-level `../README.md` for shared compliance.

> **Exclude `consumerlegalgroup.com`** — that's the legacy CLG entity, not Crēdo's execution target.

## Files

```
google/
├── campaign-manifest.json   ← full structure: 7 search campaigns, 19 ad groups (live RSA copy),
│                              extensions, PMax — for scripted / MCP upload
├── rsa-import.csv           ← Google Ads Editor bulk-import: one Responsive Search Ad per ad group
├── extensions.csv           ← callouts / structured snippets / call, per campaign
├── pmax-asset-groups.json   ← 2 PMax asset groups (headlines, descriptions, image lists, YT videos)
├── asset-manifest.csv       ← every Google image → campaign / asset-group / role
└── creatives/               ← 41 Google image files (search + PMax)
```

## Structure

**7 Search campaigns · 19 ad groups** (RSAs use the **live** copy set):

| Campaign | Ad groups |
|---|---|
| S_All-States | Credit Card, Debt Collector, FDCPA, Garnishment, Lien, Medical |
| S_CreditCard_NW | CC_Branded, CC_Lawsuit, CC_Negotiation |
| S_Lawsuit_NW | Collection_Lawsuit, Creditor_Suing, Served_Papers |
| S_Harassment_NW | Creditor_Harassment, FDCPA_Harassment |
| S_MedicalDebt_NW | Medical_Lawsuit, Medical_Rights |
| S_Garnishment_NW | Garnishment |
| S_PaydayLoan_NW | Payday_Brand_Harassment, S_PaydayLoan_General |

**PMax:** `PMax_Core_HighLTV` with **2 asset groups** (Harassment, Collection_Lawsuit).

## Upload

**Editor (manual):**
1. Import `rsa-import.csv` — creates one RSA per ad group with headlines (up to 15), descriptions
   (up to 4), paths, final URL, and the `Final URL suffix` (`utm_source=google&utm_medium=cpc&utm_campaign=credo_search`).
   Headlines/descriptions are imported **unpinned** — pin in Editor if desired.
2. Add extensions from `extensions.csv` — callouts and a structured-snippet set per campaign, plus a
   call extension where present. Decide account- vs campaign-level as you prefer.
3. Build PMax asset groups from `pmax-asset-groups.json` + `creatives/`. **YouTube videos are
   referenced by ID, not bundled** — they're hosted on the client's channel; link them in the asset
   group (or let PMax auto-generate if omitted).

**MCP:** drive from `campaign-manifest.json` (structure + copy) and `pmax-asset-groups.json`; upload
images from `creatives/`.

## Notes

- **Keywords** are not in this package — they live in the account already and in
  `../../google-ads/keywords-*.md`. This handoff is ads + extensions + PMax assets.
- RSA copy here is the **live** set (not the pending-legal "bold"/debt-validation variants shown in
  the review hub). Google's `Medical_Rights` ad group points to `/medical-debt-fdcpa-rights` (a
  rights LP), so it does **not** share the Meta credit-report repoint.
- Everything imports **PAUSED**; QA in the account before enabling.
