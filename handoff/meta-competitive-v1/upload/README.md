# Crēdo Legal — Meta Ads · Competitive v1 · Upload

Facebook + Instagram campaign built from a Freedom Debt Relief teardown. Build it in Ads Manager or via
MCP. **Launch PAUSED.** Browse every ad as it will look in the feed on the review page:
https://2-human.github.io/credo-public-meta-ads-preview/handoff/meta-competitive-v1/?review=1 (section "Ads · Facebook feed preview").

## Structure

One campaign → **6 ad sets** → **24 ads**. Each ad set holds one concept; its four ads are the same copy
with four creative versions, so the ad set is a clean creative test.

| Ad set | Concept | Ads (creative version) | Landing page | Meta number on the page |
|---|---|---|---|---|
| `AS_A1_prove-it` | Validation | `v3` · `light` · `v4` · `video` | `/debt-harassment-stop-calls` | (612) 256-8820 |
| `AS_A2_is-it-yours` | Validation | `v3` · `light` · `v4` · `video` | `/debt-harassment-stop-calls` | (612) 256-8820 |
| `AS_A3_three-things` | Rights education | `v3` · `light` · `v4` · `video` | `/debt-harassment-stop-calls` | (612) 256-8820 |
| `AS_A4_before-after` | Validation | `v3` · `light` · `v4` · `video` | `/credit-card-debt-negotiation` | (407) 624-3722 |
| `AS_A5_medical` | Medical | `v3` · `light` · `v4` · `video` | `/medical-debt-bills-errors` | (801) 386-9050 |
| `AS_A6_in-writing` | Brand | `v3` · `light` · `v4` · `video` | `/debt-harassment-stop-calls` | (612) 256-8820 |

Versions: `v3` = Designer set 1 · `light` = Set 1 in the light style · `v4` = Designer set 2 · `video` =
lip-synced spokesperson video.

## Required campaign settings

- Objective **Leads** (`OUTCOME_LEADS`), website conversion; wire the pixel/dataset and the Lead event.
- Special Ad Category **CREDIT** (US). This limits targeting: no age, gender or ZIP targeting; location radius at least 15 miles.
- Location **United States**. Exclude the 7 jurisdictions Credo does not serve: **District of Columbia, Delaware, Idaho, North Carolina,
  Oklahoma, West Virginia, Wyoming**. Also exclude **Florida and Texas** until the ads are filed with those state bars
  (Florida at least 20 days before they run), then remove those two exclusions.
- Call to action **Book Now** on every ad.
- **Status PAUSED** until QA and attorney sign-off.
- Fill the operator placeholders in `campaign-manifest.json`: ad account, Facebook Page, Instagram account, pixel/dataset, daily budget per ad set, start date.

## Copy — `copy/ads.csv`

One row per ad: primary text, headline, description, CTA, website URL, **URL parameters**, and the creative
link for each placement. Paste the primary text exactly as written — it ends with the nationwide disclaimer: the New York
line (`Attorney Advertising. Credo Legal Services, P.C., 1 Liberty Street, Suite 4010, New York, NY 10006. (212) 461-4026.`),
the responsible attorney, where services are offered, the choice-of-lawyer line, "Image is a dramatization." where the creative
shows a person, and "Prior results do not guarantee a similar outcome." It covers the stricter states' rules, so it is the same
in every state. Do not shorten it or move it to a comment. **Replace `[RESPONSIBLE ATTORNEY NAME]` with the attorney's full name
in every ad before launch.**

Put the website URL in **Website URL** and the `url_parameters` value in **Tracking → URL parameters**.
`utm_content` names the ad and its creative version, so reports show which creative won.

## Creatives — `asset-manifest.csv`

Every file is listed with its ad, ratio, placement and a direct download link.

| Ratio | Use for | Status |
|---|---|---|
| **4:5** | Feeds **and** Stories/Reels (placement asset customisation) | upload |
| **1:1** | Right column, Search, Marketplace | upload |
| 9:16 | Stories/Reels | **hold** |
| 16:9 | — | not used |

**Why 9:16 is on hold:** in 16 of the 18 static 9:16 banners, and in the videos' burned-in strip, the
disclaimer sits in the bottom 20% of the frame, where Stories and Reels place the CTA button and caption.
A covered disclaimer is a compliance problem, so use 4:5 in Stories/Reels (Meta fits it inside the frame)
until the 9:16 files are fixed. The two that are clear today are Set 2 "Before you pay, get proof" (A4 v4) and
Set 2 medical (A5 v4); using 4:5 everywhere keeps the set consistent.

Videos: upload the **4:5** video for Feeds and for Stories/Reels. Sound on; captions are burned in.

## Before launch (checklist)

1. Fill in the responsible attorney's full name in all 24 primary texts (`[RESPONSIBLE ATTORNEY NAME]`).
2. Responsible attorney pre-approves all 24 ads (NY Rule 7.1(k)); keep a copy of each ad (New York: at least one
   year for online ads; other states can require longer, so the attorney sets the retention period).
3. Confirm the entity name "Credo Legal Services, P.C." (the BBB profile says P.A.).
4. Florida and Texas stay excluded until the ads are filed with the Florida Bar and the Texas Advertising Review Committee.
5. Open each landing page from its ad preview with its URL parameters and check the phone number shown
   is the Meta number in the table above.
6. Check a test lead arrives with the UTM values filled in.
7. Leave everything PAUSED; switch on one ad set at a time.

## Test plan

Inside each ad set the four ads differ only in creative, so compare them there first. Keep the ads in
their ad sets and avoid Dynamic Creative, so each result maps to one creative version.

## Files

- `campaign-manifest.json` — campaign → ad sets → ads, with copy, links and creative URLs (for MCP/scripted upload)
- `copy/ads.csv` — the same, one row per ad (for building by hand)
- `asset-manifest.csv` — every creative file with placement, status and download link
