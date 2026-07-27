# Crēdo Legal — Ads Upload Handoff (Meta + Google)

Everything the client needs to build the Crēdo Legal debt-defense campaigns on **Meta Ads** and
**Google Ads** — by hand in Ads Manager / Ads Editor, or via MCP automation.

> **Launch everything PAUSED and QA before any spend.** These are consumer-debt / legal ads — the
> compliance rules below are not optional.

## Package layout

```
credo-ads-handoff-2026-07/
├── meta/    campaign-manifest.json · copy/*.csv · asset-manifest.csv · creatives/<Ad>/…
└── google/  campaign-manifest.json · rsa-import.csv · extensions.csv · pmax-asset-groups.json · creatives/…
```

Each platform folder is self-contained: machine-readable manifest (for MCP / scripted upload),
human CSVs, and the actual creative files. See `meta/README.md` and `google/README.md`.

## Two ways to upload

- **Manual** — Meta: Ads Manager (build campaign, upload `meta/creatives/`, paste `meta/copy/`).
  Google: **Google Ads Editor** → import `google/rsa-import.csv`, add `extensions.csv`, build PMax
  from `pmax-asset-groups.json` + `google/creatives/`.
- **MCP** — drive each `campaign-manifest.json`; upload creatives from the `creatives/` folders;
  leave everything PAUSED.

## Shared compliance (read first)

- **Special Ad Category = CREDIT** (Meta) / consumer-finance policy (Google): restricted targeting.
- **Geo: US, exclude New York.** **Exclude TX & FL at launch** (attorney-ad filing + local-counsel
  disclosure; FL pre-approval ~15-day review) — add once cleared.
- **State disclosures** (KS/OH/SD/NJ/KY name+address, jurisdiction notice) are **not** in the copy —
  add per the compliance matrix before those states run.
- Every Meta message carries two disclaimer lines ("Prior outcomes don't guarantee similar results."
  + the universal footer).
- **Launch status: PAUSED**, both platforms.

## Call-tracking numbers (on the landing pages)

Meta, per cluster: Credit Card (407) 624-3722 · Lawsuit (718) 521-4060 · Harassment/All-States
(612) 256-8820 · Garnishment (720) 414-5055 · Medical (801) 386-9050. Google uses per-ad-group call
extensions (`google/extensions.csv`).

## What's in this build

- **Meta** — 5 ad sets / 14 ads · 6 headlines · **6 message variants (incl. Bold)** · per ad: 3 image
  directions × 4 ratios + a 9:16 video + the **Bold** creative (gesture + 4 ratios + animated reel).
- **The Bold set is included and approved.** It carries hard-baked copy already positioned in the
  Meta safe zones; pair Bold creatives with the Bold message variant.
- **9:16 images are safe-zone-baked** — the standard 9:16s are re-exported with a subject-aware crop
  so the person/documents sit inside the safe zone (the 9:16 *videos* and Bold 9:16s are unchanged).
- **Google** — full 7-campaign / 19-ad-group Search structure + extensions + 2 PMax asset groups.
- **Medical_Rights (Meta) repointed** to the debt-validation angle to match its repurposed LP.
