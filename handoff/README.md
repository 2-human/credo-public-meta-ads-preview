# Crēdo Legal — Ads Upload Handoff (Meta + Google)

Everything the client needs to build the Crēdo Legal debt-defense campaigns on **Meta Ads** and
**Google Ads** — by hand in Ads Manager / Ads Editor, or via MCP automation. Prepared 2026-07-23.

> **Launch everything PAUSED and QA before any spend.** These are consumer-debt / legal ads: the
> compliance rules below are not optional.

## Package layout

```
credo-ads-handoff-2026-07/
├── README.md            ← you are here (shared context + compliance)
├── meta/                ← Meta (Facebook + Instagram) — see meta/README.md
│   ├── campaign-manifest.json   source of truth for a scripted upload
│   ├── copy/{headlines,messages,ads}.csv
│   ├── asset-manifest.csv
│   └── creatives/<Ad>/…         12 images + 1 video per ad (182 files)
└── google/              ← Google Ads (Search + PMax) — see google/README.md
    ├── campaign-manifest.json   full structure (7 search campaigns, 19 ad groups, PMax)
    ├── rsa-import.csv           Google Ads Editor bulk-import (all 19 RSAs)
    ├── extensions.csv           callouts / structured snippets / call
    ├── pmax-asset-groups.json   2 PMax asset groups
    ├── asset-manifest.csv
    └── creatives/…              41 Google images
```

Each platform folder is self-contained with its own README, machine-readable manifest (for MCP /
scripted upload), human-readable CSVs, and the actual creative files.

## Two ways to upload

**A. Manual**
- *Meta* → Ads Manager. Create the campaign with the settings below, build 5 ad sets, upload the
  creatives from `meta/creatives/`, paste copy from `meta/copy/`.
- *Google* → **Google Ads Editor** → import `google/rsa-import.csv` (RSAs for all 19 ad groups),
  then add extensions from `extensions.csv` and build the PMax asset groups from
  `pmax-asset-groups.json` + `google/creatives/`.

**B. Via MCP**
- The `campaign-manifest.json` in each folder is structured for a scripted build. Point your Meta /
  Google Ads MCP at it. Upload creatives from the `creatives/` folders, wire the placeholders
  (account IDs, pixel/dataset, budget, schedule), and **leave status PAUSED**.

## Shared compliance (read before uploading either platform)

- **Special Ad Category = CREDIT** (Meta) / consumer-finance policy (Google). Restricts targeting:
  no gender/ZIP targeting, limited detailed targeting, geo radius minimums. Build accordingly.
- **Geo: United States, exclude New York.**
- **Texas & Florida** require attorney-ad **filing** + local-counsel disclosure — **FL is
  pre-approval before launch** (~15-day review), **TX** is post-filing within 10 days. **Exclude TX
  and FL at launch**; add them once cleared with the state-specific disclosures.
- **State-specific attorney disclosures** (KS / OH / SD / NJ / KY name+address, jurisdiction notice)
  are **not** baked into the copy — add per the compliance matrix before those states run.
- Every Meta message already carries two disclaimer lines: *"Prior outcomes don't guarantee similar
  results."* and the universal footer *"Crēdo Legal. The choice of a lawyer is an important decision
  and should not be based solely upon advertisements."*
- **Launch status: PAUSED**, both platforms.

## Prerequisites

- **Meta:** requires a Facebook Page, Instagram Business account, Meta Pixel/dataset, and Ad
  Account. Supply the IDs listed under `placeholders_operator_must_fill` in `meta/campaign-manifest.json`.
- **Google:** account `9399506772` already exists (structure here mirrors it). **Exclude
  `consumerlegalgroup.com`** — that is the legacy CLG entity, not Crēdo's execution target.

## Call-tracking numbers (dynamic-number insertion)

The landing pages already carry the tracking numbers; these are for reference. **Meta** traffic uses
one number per cluster (set on the LP): Credit Card **(407) 624-3722** · Lawsuit **(718) 521-4060** ·
Harassment / All-States **(612) 256-8820** · Garnishment **(720) 414-5055** · Medical **(801) 386-9050**.
**Google** uses per-ad-group call extensions (in `google/extensions.csv`) and its own per-ad-group
DNI numbers — do not cross the two platforms' numbers.

## What's new in this refresh (vs the 2026-06 Meta-only handoff)

- **Google added** — full 7-campaign / 19-ad-group Search structure + extensions + 2 PMax asset groups.
- **Medical_Rights (Meta) repointed** from the retired credit-report-removal angle to the
  **debt-validation** angle ("make them prove you owe it"), matching its repurposed landing page.
  *This ad copy is newly repointed and needs the same legal sign-off as the rest.*
- **"Prior outcomes don't guarantee similar results."** added to every Meta message.
- **Landing-page redesign previews** moved to the `2-human.github.io` mirror.
- Regenerated **CC_Negotiation still-life** (US-dollar notes) is included automatically.
- The **Bold** creative set and animated **reels** are **excluded** (pending legal sign-off); the
  standard Illustration / Photo / Still-life / Video set is the launch set.
