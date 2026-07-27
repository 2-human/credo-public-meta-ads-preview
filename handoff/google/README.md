# Crēdo Legal — Google Ads · Upload

Search + Performance Max for account **9399506772**. Build via **Google Ads Editor** or MCP.
**Launch PAUSED.** See `../README.md` for shared compliance.

> **Exclude `consumerlegalgroup.com`** — legacy entity, not Crēdo's target.

## Structure — 7 Search campaigns · 19 ad groups (live RSA copy) + PMax (2 asset groups)

| Campaign | Ad groups |
|---|---|
| S_All-States | Credit Card, Debt Collector, FDCPA, Garnishment, Lien, Medical |
| S_CreditCard_NW | CC_Branded, CC_Lawsuit, CC_Negotiation |
| S_Lawsuit_NW | Collection_Lawsuit, Creditor_Suing, Served_Papers |
| S_Harassment_NW | Creditor_Harassment, FDCPA_Harassment |
| S_MedicalDebt_NW | Medical_Lawsuit, Medical_Rights |
| S_Garnishment_NW | Garnishment |
| S_PaydayLoan_NW | Payday_Brand_Harassment, S_PaydayLoan_General |

PMax `PMax_Core_HighLTV` → asset groups Harassment, Collection_Lawsuit.

## Upload

1. **Editor** → import `rsa-import.csv` (one RSA per ad group; headlines/descriptions unpinned;
   `Final URL suffix` adds Google UTMs).
2. Add extensions from `extensions.csv` (callouts / structured snippets / call, per campaign).
3. Build PMax asset groups from `pmax-asset-groups.json` + `creatives/`. **YouTube videos are
   referenced by ID, not bundled.**

Keywords are not in this package (already in the account). RSA copy is the **live** set; Google's
`Medical_Rights` points to `/medical-debt-fdcpa-rights` (rights LP) — no credit-report repoint there.
Everything imports **PAUSED**.
