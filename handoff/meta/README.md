# Crēdo Legal — Meta Ads · Upload

Facebook + Instagram debt-defense campaign. Build in Ads Manager or via MCP. **Launch PAUSED.**
See `../README.md` for shared compliance and call-tracking numbers.

## Structure

One campaign → **5 ad sets** → **14 ads**.

| Ad set (`AS_*_NW`) | Ads |
|---|---|
| Credit Card | CC_Lawsuit, CC_Harassment, CC_Negotiation |
| Lawsuit | Collection_Lawsuit, Creditor_Suing, Served_Papers |
| Harassment | Creditor_Harassment, FDCPA_Harassment, Multiple_Collectors |
| Medical Debt | Medical_Harassment, Medical_Lawsuit, Medical_Rights *(repointed → debt validation)* |
| Garnishment | Pre_Judgment_Garn, Post_Judgment_Garn |

Each ad ships with **6 headline options** (shared), **6 message options** (Default / Fight /
Reassurance / Affordability / Fresh Start / **Bold**), **3 image directions** (Illustration / Photo /
Still life) × **4 ratios** (1:1, 4:5, 9:16, 1.91:1), **1 video** (9:16), and the **Bold** creative
(the gesture mapped to that ad, in 4 ratios + an animated **reel**). CTA = Book Now.

## Required campaign settings

Special Ad Category = **CREDIT** (US) · Objective **Leads** (`OUTCOME_LEADS`; wire pixel + Lead
event) · Geo US, **exclude NY**, **exclude TX & FL** at launch · **Status PAUSED**. Operator
placeholders (ad account, Page, Instagram, pixel, budget, schedule) are in the manifest.

## Copy

- **Headlines (6, shared):** `copy/headlines.csv`; default = index 0.
- **Messages (6 per ad):** `copy/messages.csv`. Each ends with "Prior outcomes don't guarantee
  similar results." + the universal footer. State-specific disclosures not included.
- **Bold** pairs the Bold message variant with the Bold creative (which has its headline baked in).

## Creatives

- **Standard** — `creatives/<Ad>/<Ad>_<direction>_<ratio>.<ext>` (illustration/photo/stilllife;
  1x1/4x5/9x16/1.91x1) + `<Ad>_video_9x16.mp4`.
- **9:16 images are safe-zone-baked** (re-exported with a subject-aware crop so the subject sits in
  the Stories/Reels safe zone). 1:1 / 4:5 / 1.91:1 and the videos are the originals.
- **Bold** — `<Ad>_bold_<ratio>.jpeg` (4 ratios) + `<Ad>_bold_reel.mp4` (animated 9:16). The Bold
  set is **approved**; its copy is baked into the image and already inside the Meta safe zones.

Directions: `illustration` / `photo` / `stilllife` / `bold` / `video`. Most images PNG; 4:5 masters
and all Bold are JPEG (extension preserved in the manifest).

## Medical_Rights — repointed

Runs the **debt-validation** angle ("a collector says you owe it — can they prove it?") to match its
repurposed LP; the retired credit-report angle is gone (Crēdo does not do credit-report corrections).

## Staged test plan

Creative → message → headline, one variable at a time, ads kept within their ad set. Avoid Dynamic
Creative if you want clean per-variant attribution.
