# Crēdo Legal — Meta Ads · Competitive v1 · Upload

One Facebook + Instagram campaign for the **whole US** (5 Oct 2026). It holds the Competitive v1 ads (built from a
Freedom Debt Relief teardown) and, consolidated into it, every ad of the earlier main Meta build (Debt Defense v4,
`handoff/meta/`), which is no longer a separate campaign. Build it in Ads Manager or via MCP. **Launch PAUSED.**
Competitive v1 ads in the feed: https://2-human.github.io/credo-public-meta-ads-preview/handoff/meta-competitive-v1/?review=1 (section "Ads · Facebook feed preview").

## Structure

One campaign → **20 ad sets** → **87 ads**. Each ad set holds one concept; its ads carry the same copy with
different creative versions, so each ad set is a clean creative test.

**Competitive v1** (6 ad sets, 24 ads; versions `v3` = Designer set 1 · `light` = Set 1 in the light style · `v4` = Designer
set 2 · `video` = lip-synced spokesperson video):

| Ad set | Concept | Ads (creative version) | Landing page | Meta number on the page |
|---|---|---|---|---|
| `AS_A1_prove-it` | Validation | `v3` · `light` · `v4` · `video` | `/debt-harassment-stop-calls` | (612) 256-8820 |
| `AS_A2_is-it-yours` | Validation | `v3` · `light` · `v4` · `video` | `/debt-harassment-stop-calls` | (612) 256-8820 |
| `AS_A3_three-things` | Rights education | `v3` · `light` · `v4` · `video` | `/debt-harassment-stop-calls` | (612) 256-8820 |
| `AS_A4_before-after` | Validation | `v3` · `light` · `v4` · `video` | `/credit-card-debt-negotiation` | (407) 624-3722 |
| `AS_A5_medical` | Medical | `v3` · `light` · `v4` · `video` | `/medical-debt-bills-errors` | (801) 386-9050 |
| `AS_A6_in-writing` | Brand | `v3` · `light` · `v4` · `video` | `/debt-harassment-stop-calls` | (612) 256-8820 |

**From Debt Defense v4** (14 ad sets, 63 ads; versions `illustration` · `photo` · `stilllife` · `video` · `bold`):

| Ad set | Concept | Ads (creative version) | Landing page | Meta number on the page |
|---|---|---|---|---|
| `AS_DD_CC_Lawsuit` | Credit Card · Sued over a card (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` | `/credit-card-debt-lawsuit-respond` | (407) 624-3722 |
| `AS_DD_CC_Harassment` | Credit Card · Collector harassment (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` · `bold` | `/credit-card-debt-stop-calls` | (407) 624-3722 |
| `AS_DD_CC_Negotiation` | Credit Card · Negotiate the balance (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` · `bold` | `/credit-card-debt-negotiation` | (407) 624-3722 |
| `AS_DD_Collection_Lawsuit` | Lawsuit · Collection lawsuit (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` | `/debt-lawsuit-respond-on-time` | (718) 521-4060 |
| `AS_DD_Creditor_Suing` | Lawsuit · Creditor suing you (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` | `/debt-lawsuit-attorney` | (718) 521-4060 |
| `AS_DD_Served_Papers` | Lawsuit · Just got served (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` | `/debt-lawsuit-summons-respond` | (718) 521-4060 |
| `AS_DD_Creditor_Harassment` | Harassment · Creditor harassment (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` · `bold` | `/debt-harassment-stop-calls` | (612) 256-8820 |
| `AS_DD_FDCPA_Harassment` | Harassment · FDCPA violations (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` | `/debt-harassment-fdcpa-attorney` | (612) 256-8820 |
| `AS_DD_Multiple_Collectors` | Harassment · Multiple collectors (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` | `/multiple-collectors-one-attorney` | (612) 256-8820 |
| `AS_DD_Medical_Harassment` | Medical Debt · Medical collector calls (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` · `bold` | `/medical-debt-bills-errors` | (801) 386-9050 |
| `AS_DD_Medical_Lawsuit` | Medical Debt · Medical debt lawsuit (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` | `/medical-debt-lawsuit-respond` | (801) 386-9050 |
| `AS_DD_Medical_Rights` | Medical Debt · Do you owe it? (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` · `bold` | `/medical-debt-credit-report-removal` | (801) 386-9050 |
| `AS_DD_Pre_Judgment_Garn` | Garnishment · Prevent garnishment (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` · `bold` | `/wage-garnishment-prevention` | (720) 414-5055 |
| `AS_DD_Post_Judgment_Garn` | Garnishment · Active garnishment (from Debt Defense v4) | `illustration` · `photo` · `stilllife` · `video` · `bold` | `/wage-garnishment-exemptions` | (720) 414-5055 |

Bold creatives held back (not in the upload): CC_Lawsuit (Bold "fist"): baked line "You have 20 to 28 days to answer." is not true in every state; Collection_Lawsuit (Bold "fist"): baked line "You have 20 to 28 days to answer." is not true in every state; Creditor_Suing (Bold "fist"): baked line "You have 20 to 28 days to answer." is not true in every state; Served_Papers (Bold "fist"): baked line "You have 20 to 28 days to answer." is not true in every state; FDCPA_Harassment (Bold "pointing"): baked line "up to $1,000 per violation" overstates the FDCPA (the cap is per lawsuit); render glitch "FREE.E."; Multiple_Collectors (Bold "pointing"): baked line "up to $1,000 per violation" overstates the FDCPA (the cap is per lawsuit); render glitch "FREE.E."; Medical_Lawsuit (Bold "fist"): baked line "You have 20 to 28 days to answer." is not true in every state.

## Required campaign settings

- Objective **Leads** (`OUTCOME_LEADS`), website conversion; wire the pixel/dataset and the Lead event.
- Special Ad Category **CREDIT** (US). This limits targeting: no age, gender or ZIP targeting; location radius at least 15 miles.
- Location **United States**. Exclude **New Jersey** and the 7 jurisdictions Credo does not serve: **District of Columbia,
  Delaware, Idaho, North Carolina, Oklahoma, West Virginia, Wyoming**.
- Call to action **Book Now** on every ad.
- **Status PAUSED** until QA and attorney sign-off.
- Fill the operator placeholders in `campaign-manifest.json`: ad account, Facebook Page, Instagram account, pixel/dataset, daily budget per ad set, start date.

## Copy — `copy/ads.csv`

One row per ad: primary text, headline, description, CTA, website URL, **URL parameters**, and the creative
link for each placement. Paste the primary text exactly as written. It ends with the nationwide disclaimer, the same in every
state: the New York line (`Attorney Advertising. Credo Legal Services, P.C., 1 Liberty Street, Suite 4010, New York, NY 10006.
(212) 461-4026.`), where services are offered, the choice-of-lawyer line, "Image is a dramatization." where the creative shows a
person or a staged scene, and "Prior results do not guarantee a similar outcome." Do not shorten it or move it to a comment.

The Debt Defense v4 copy is its Default message (the Bold message with the Bold creative). Two claims that are not true
nationwide were corrected: "up to $1,000 per violation" → "up to $1,000 in statutory damages", and "20 to 28 days to reply"
→ "only a few weeks to reply".

Put the website URL in **Website URL** and the `url_parameters` value in **Tracking → URL parameters**. Every ad uses
`utm_campaign=credo_meta_competitive_v1`; `utm_content` names the ad and its creative version, so reports show which creative won.

## Creatives — `asset-manifest.csv`

Every file is listed with its ad, ratio, placement and a direct download link.

| Ratio | Competitive v1 | Debt Defense v4 |
|---|---|---|
| **4:5** | Feeds | Feeds |
| **1:1** | Right column, Search, Marketplace | Right column, Search, Marketplace |
| **9:16** | **Stories/Reels** | **Stories/Reels** (safe-zone baked); videos are 9:16 only, for every placement |
| 16:9 / 1.91:1 | not used | not used |

**Competitive v1 9:16 (operator decision, 5 Oct 2026):** published for Stories/Reels. In 16 of its 18 static 9:16 banners,
and in the videos' burned-in strip, the baked disclaimer sits in the bottom 20% of the frame, where Stories and Reels may
cover it with the CTA button and caption. The full nationwide disclaimer is in the primary text of every ad.

## Before launch (checklist)

1. Responsible attorney pre-approves all 87 ads (NY Rule 7.1(k)); keep a copy of each ad (New York: at least one
   year for online ads; other states can require longer, so the attorney sets the retention period).
2. Confirm the entity name "Credo Legal Services, P.C." (the BBB profile says P.A.).
3. Open each landing page from its ad preview with its URL parameters and check the phone number shown
   is the Meta number in the tables above.
4. Check a test lead arrives with the UTM values filled in.
5. Leave everything PAUSED; switch on one ad set at a time.

## Test plan

Inside each ad set the ads differ only in creative, so compare them there first. Keep the ads in their ad sets and avoid
Dynamic Creative, so each result maps to one creative version. With 20 ad sets, start with a few and add more as
budget allows rather than switching all on at once.

## Download

**Full package (one zip, about 290 MB):** https://github.com/2-human/credo-public-meta-ads-preview/releases/download/meta-handoff/credo-meta-handoff-full.zip
It holds this guide, the manifest, `copy/ads.csv`, `asset-manifest.csv` and all 215 creatives to upload, in
`creatives/<ad set>/`.

`credo-meta-handoff.zip` next to this guide has the same files without the creatives (for a scripted upload, which
reads the creative URLs from the manifest).

## Files

- `campaign-manifest.json` — campaign → ad sets → ads, with copy, links and creative URLs (for MCP/scripted upload)
- `copy/ads.csv` — the same, one row per ad (for building by hand)
- `asset-manifest.csv` — every creative file with placement, status and download link
