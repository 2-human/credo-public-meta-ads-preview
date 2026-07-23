# Crēdo Legal — Meta Ads · Upload

Facebook + Instagram debt-defense campaign. Build in Ads Manager or via MCP. **Launch PAUSED.**
See the top-level `../README.md` for shared compliance and call-tracking numbers.

## Files

```
meta/
├── campaign-manifest.json   ← source of truth: campaign → 5 ad sets → 14 ads → copy + creative paths
├── copy/
│   ├── headlines.csv        ← 6 campaign-wide headline options (default = index 0)
│   ├── messages.csv         ← 70 messages (14 ads × 5), disclaimers already baked in
│   └── ads.csv              ← per-ad final URL, UTM URL, topic, description
├── asset-manifest.csv       ← every creative file → ad / direction / ratio
└── creatives/<Ad>/          ← 12 images (3 directions × 4 ratios) + 1 video (9:16) per ad
```

`campaign-manifest.json` drives a scripted upload; the CSVs are the same data for humans.

## Structure

One campaign → **5 ad sets** (by debt/service type) → **14 ads** (one per topic).

| Ad set (`AS_*_NW`) | Ads |
|---|---|
| Credit Card | CC_Lawsuit, CC_Harassment, CC_Negotiation |
| Lawsuit | Collection_Lawsuit, Creditor_Suing, Served_Papers |
| Harassment | Creditor_Harassment, FDCPA_Harassment, Multiple_Collectors |
| Medical Debt | Medical_Harassment, Medical_Lawsuit, **Medical_Rights** *(repointed — see below)* |
| Garnishment | Pre_Judgment_Garn, Post_Judgment_Garn |

Each ad ships with **6 headline options** (shared), **5 message options** (Default / Fight /
Reassurance / Affordability / Fresh Start), **3 image directions** (Illustration / Photo / Still
life) × **4 ratios** (1:1, 4:5, 9:16, 1.91:1), and **1 video** (9:16). CTA = **Book Now**;
destination = the ad's landing page.

## Required campaign settings

- **Special Ad Category = CREDIT** (US). Restricts targeting — see top-level README.
- **Objective:** Leads (`OUTCOME_LEADS`); conversion is the LP qualifier form (wire pixel/dataset +
  a Lead event). Confirm with the operator if Meta Lead Forms are preferred instead.
- **Geo:** US, **exclude NY**; **exclude TX & FL** at launch (filing/disclosure gated).
- **Status: PAUSED.**

Placeholders the operator must supply (also in the manifest under `placeholders_operator_must_fill`):
ad account ID, Facebook Page ID, Instagram account (optional), pixel/dataset ID, budget per ad set,
schedule.

## Copy

- **Headlines (6, shared):** in `copy/headlines.csv`; default = "Get a Free Review of Your Case".
- **Messages (5 per ad):** in `copy/messages.csv` and the manifest. Each already ends with *"Prior
  outcomes don't guarantee similar results."* + the universal footer. Meta primary text can't be
  styled, so both appear as plain final lines. State-specific disclosures are **not** included — add
  per the compliance matrix before those states run.

## Medical_Rights — repointed

Medical_Rights now runs the **debt-validation** angle ("a collector says you owe it — can they prove
it?") to match its repurposed LP (`/medical-debt-credit-report-removal`, now a validation page).
Crēdo does **not** do credit-report corrections, so the old angle was retired. **This copy is newly
written and needs legal sign-off** like the rest.

## Landing pages

Each ad points to the production slug on `start.credolegal.com` whose angle matches its message; the
`final_url_utm` adds `utm_source=meta…utm_content=<ad>` (UTM campaign kept as `credo_meta_v3` for
analytics continuity with the live v4 campaign). `landing_page_redesign_preview` in the manifest
links the redesigned version on the `2-human.github.io` mirror.

## Recommended staged test plan

Full library = 6 headlines × 5 messages × (3 directions × 4 ratios + video) per ad — too many to
launch at once.
1. **Creative:** per ad, one message + default headline, 4 sibling ads differing only by direction
   (Illustration / Photo / Still life / Video). Upload 1:1 + 4:5 as primaries; let Meta serve
   9:16 / 1.91:1 per placement.
2. **Message:** on the winning creative, test the 5 message variants.
3. **Headline:** on the winner, rotate the 6 headlines.

Keep ads within their ad set. Avoid Dynamic Creative if you want clean per-variant attribution.

## Asset naming

`creatives/<Ad>/<Ad>_<direction>_<ratio>.<ext>` — directions `illustration` / `photo` / `stilllife`
/ `video`; ratios `1x1` / `4x5` / `9x16` / `1.91x1`. Most images are PNG; some 4:5 masters are JPEG
(extension preserved in the filename and the manifest).

## Note

The **Bold** creative set + animated **reels** are **not** in this package — they're pending legal
sign-off. This is the standard launch set.
