# Prompt for Claude: build the Crēdo Legal Meta campaign from this hand-off

How to use it: unzip `credo-meta-handoff-full.zip`, open a new Claude session (Claude Code, or Claude with file access
and, if you have one, a Meta Ads connection) **in the `credo-meta-handoff/` folder**, and paste everything below the line.
Before you paste it, choose what to build in the section "What to build": every folder is ticked; untick (`[ ]`) the
ones you do not want, or replace the list with a sentence such as "only the A1 to A6 ad sets".

---

You are setting up a Facebook + Instagram ad campaign for **Crēdo Legal** (a consumer debt-defense law firm) in Meta Ads
Manager, from the hand-off package in this folder. The goal is the campaign built exactly as specified, with the ad
sets I choose below, and **left PAUSED**. Nothing may spend money. I (the operator) switch ads on later, after the firm's attorney approves them.

## The package

- `README.md`: the upload guide. Read it first and in full.
- `campaign-manifest.json`: the source of truth. 1 campaign, 20 ad sets, 87 ads, with every ad's copy, links and
  creative per placement. If the README and the manifest ever disagree, follow the manifest and tell me.
- `copy/ads.csv`: the same ads, one row per ad (useful when building by hand).
- `asset-manifest.csv`: every creative file with its ratio, placement and status. Use only rows with status `upload`.
- `creatives/<ad set>/`: the 215 creative files. The file name is the last part of each creative URL in the manifest.

## What to build

Build **only the ticked folders** below. Each folder in `creatives/` is one ad set (`AS_<folder>` in the manifest) with
all its ads. If I wrote a sentence instead of ticks, follow the sentence. If anything about the choice is unclear,
ask before you start. Everything else in this prompt applies to the chosen ad sets only.

Competitive v1:
- [x] `A1_prove-it`: Validation · 4 ads · /debt-harassment-stop-calls
- [x] `A2_is-it-yours`: Validation · 4 ads · /debt-harassment-stop-calls
- [x] `A3_three-things`: Rights education · 4 ads · /debt-harassment-stop-calls
- [x] `A4_before-after`: Validation · 4 ads · /credit-card-debt-negotiation
- [x] `A5_medical`: Medical · 4 ads · /medical-debt-bills-errors
- [x] `A6_in-writing`: Brand · 4 ads · /debt-harassment-stop-calls

From Debt Defense v4:
- [x] `DD_CC_Lawsuit`: Credit Card · Sued over a card · 4 ads · /credit-card-debt-lawsuit-respond
- [x] `DD_CC_Harassment`: Credit Card · Collector harassment · 5 ads · /credit-card-debt-stop-calls
- [x] `DD_CC_Negotiation`: Credit Card · Negotiate the balance · 5 ads · /credit-card-debt-negotiation
- [x] `DD_Collection_Lawsuit`: Lawsuit · Collection lawsuit · 4 ads · /debt-lawsuit-respond-on-time
- [x] `DD_Creditor_Suing`: Lawsuit · Creditor suing you · 4 ads · /debt-lawsuit-attorney
- [x] `DD_Served_Papers`: Lawsuit · Just got served · 4 ads · /debt-lawsuit-summons-respond
- [x] `DD_Creditor_Harassment`: Harassment · Creditor harassment · 5 ads · /debt-harassment-stop-calls
- [x] `DD_FDCPA_Harassment`: Harassment · FDCPA violations · 4 ads · /debt-harassment-fdcpa-attorney
- [x] `DD_Multiple_Collectors`: Harassment · Multiple collectors · 4 ads · /multiple-collectors-one-attorney
- [x] `DD_Medical_Harassment`: Medical Debt · Medical collector calls · 5 ads · /medical-debt-bills-errors
- [x] `DD_Medical_Lawsuit`: Medical Debt · Medical debt lawsuit · 4 ads · /medical-debt-lawsuit-respond
- [x] `DD_Medical_Rights`: Medical Debt · Do you owe it? · 5 ads · /medical-debt-credit-report-removal
- [x] `DD_Pre_Judgment_Garn`: Garnishment · Prevent garnishment · 5 ads · /wage-garnishment-prevention
- [x] `DD_Post_Judgment_Garn`: Garnishment · Active garnishment · 5 ads · /wage-garnishment-exemptions

## Rules you must never break

1. **Everything stays PAUSED**: the campaign, every ad set and every ad. Never set anything to active, never
   launch, never raise a budget. Ads Manager needs "Publish" to save new items; publishing is allowed only after you
   have checked that the campaign, every ad set and every ad in it is set to Paused. If a step would start delivery,
   stop and ask me.
2. **Copy is legally reviewed text. Paste it exactly.** Use `primary_text`, `headline` and `description` character for
   character. Never shorten, reword, translate or "improve" them, and never move or cut the disclaimer at the end of
   each primary text. If Meta rejects or flags a text, stop and report it to me; do not rewrite it.
3. **Turn off every Advantage+ creative enhancement** (text improvements, text variations, image or video touch-ups,
   music, overlays, generated backgrounds and the like) and do not use Dynamic Creative. They change approved ads.
4. **Special Ad Category: Credit**, country United States. Do not add age, gender, ZIP code or interest targeting,
   and do not switch on Advantage+ audience or audience expansion.
5. **Location:** United States, excluding New Jersey, District of Columbia, Delaware, Idaho, North Carolina, Oklahoma, West Virginia, Wyoming. Florida and Texas are included.
6. Use **only** the creatives the manifest assigns. Do not use 16:9 files or anything with another status. Do not create,
   crop or edit images or videos. If Meta will not accept a file in a placement, do not swap in another file: note it
   and tell me in the report.
7. **URL parameters exactly as given**: the `url_parameters` value goes in Tracking → URL parameters, unchanged.
8. **Never guess a missing value.** Ask me for: the ad account ID, Facebook Page, Instagram account (optional),
   pixel/dataset ID, daily budget per ad set and the start date. If I give no Instagram account, ask whether the ads
   may run on Instagram through the Facebook Page. Before creating anything, confirm with me that the ad account you
   are connected to is Crēdo Legal's (show me its name and ID), and look for a campaign, ad set or ad that already has
   one of the names below; if one exists, ask me before creating or changing anything.

## Steps

1. **Read and check.** Read `README.md` and `campaign-manifest.json`. The full package is 1 campaign, 20 ad
   sets, 87 ads, 87 rows in `copy/ads.csv` and 215 files in `creatives/`; if any of these differs, stop and
   tell me. Then list the ad sets I chose, with the number of ads in each and the total, and check that every file
   their `placement_creatives` name is in `creatives/<folder>/`. Wait for my OK on the list before building.
2. **Ask me for the missing values** (rule 8), and wait for my answers.
3. **Campaign:** name `Credo Legal — Competitive v1 (Meta)`, objective **Leads**, conversion location **Website**, Special Ad Category
   **Credit** (United States), auction buying, budget set **per ad set** (not at campaign level), status **PAUSED**.
4. **Ad sets (the ones I chose):** one per chosen `ad_sets[]` entry, named exactly as `name`. Each: the pixel/dataset with the
   **Lead** event, the location from rule 5, the start date and daily budget I give you, placements on Advantage+
   placements with a creative per placement (step 5), status **PAUSED**.
5. **Ads:** every `ads[]` entry of each chosen ad set, in that ad set, named exactly as `ad_name`. Each: my Facebook Page (and
   Instagram account), the format in `format` (single image or video), and for each placement the exact file that
   `placement_creatives` names (`feeds`, `stories_reels`, `right_column_search_marketplace`). As a rule that is
   **Feeds = 4:5**, **Stories and Reels = 9:16**, **right column, Search and Marketplace = 1:1**, but some ads use one file
   in several placements (the Debt Defense videos are 9:16 only), so always take the file from the manifest, not from
   the rule. Then `primary_text`, `headline`, `description`, call to action
   **Book Now**, `website_url` as the website URL and `url_parameters` under Tracking. Status **PAUSED**.
   The 9:16 files of the six `AS_A*` ad sets carry a small disclaimer near the bottom that Stories and Reels may cover.
   That is a known, accepted choice (the full disclaimer is in every primary text): upload them as they are.
6. **Verify.** Count the ad sets and ads in Ads Manager against the ones I chose. Confirm every item is PAUSED. For
   every ad, check the primary text ends with "Prior results do not guarantee a similar outcome." and the URL
   parameters are filled in. Open the preview of at least one ad per ad set in Feeds and in Stories, and check the
   right file shows in each.
7. **Report to me:** a table of the ad sets built, with their ID, number of ads, landing page and the Meta phone number
   the README lists for it (so I can check the pages); anything Meta rejected or flagged; anything you could not do or
   did differently; and questions. Do not switch anything on.

If Ads Manager looks different from these steps (Meta changes its screens), describe what you see and ask me rather
than guessing.

## For the operator (before switching anything on; not for Claude to do)

- The responsible attorney approves every ad built, and a copy of each ad is kept (New York: at least one year).
- Confirm the entity name "Credo Legal Services, P.C." (the BBB profile says P.A.).
- Florida and Texas are targeted. Lawyer ads there are subject to state bar filing rules (Florida reviews them before
  they run). Confirm with Crēdo's attorney that these are handled before those ad sets go live.
- Open each landing page from an ad preview and check the phone number matches the Meta number in `README.md`.
- Send one test lead and check the UTM values arrive with it.
- Switch on one ad set at a time.
