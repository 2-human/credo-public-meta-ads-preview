# Crēdo Legal — Meta Competitive v1

A Meta campaign built by tearing down **Freedom Debt Relief**'s live Meta advertising and
rebuilding their highest-performing creative structures in Crēdo brand. **Launch PAUSED.**

Source: Meta Ad Library, page `69869352985`, **~96 active ads** (94 captured: 38 video / 56 static),
analysed **2026-09-08**.

## The core adaptation

FDR is a **debt-settlement company**; Crēdo is a **law firm**. Their best-performing copy
("become debt-free", "settle for less than you owe", "$438/mo avg program payment", "$22B resolved
for 1M members") is exactly what Crēdo cannot say. So this package mimics their **structure, hooks,
pacing and visual devices faithfully** and swaps the claim layer to Crēdo's validated-safe spine:
*make them prove it · debt buyers often can't prove they own it · you may owe far less than they
claim · free case review · flat monthly fee*.

## FDR device → Crēdo ad

| FDR creative | Device borrowed | Crēdo ad |
|---|---|---|
| "BECOME DEBT-FREE WITHOUT A LOAN" | Bold condensed type, keyword in a colour box, layered red sticker tags, baked CTA pill | **A1** `MAKE THEM PROVE IT.` |
| "Is debt your dirty little secret?" | iPhone **Notes** native-app card over a candid photo | **A2** "Is this debt even yours?" |
| "QUIZ TIME! Why choose FDR? A/B/C/D" | Quiz card, D highlighted | **A3** "What can you make a collector do?" |
| "$$$ Credit Card Bills" → "$438/mo Program Payment" | Red pain card → solution card colour-flip | **A4** Before / After |
| Synthetic-spokesperson UGC (32s) | Talking head at home, burned-in caption boxes, end card | **all six** videos |

## Excluded on instruction (no compelling review to show)

- **Trustpilot 4.5 / BBB A+ / ConsumerAffairs 4.5** badge row
- **Review-card screenshot** device ("Debt no more — Monica, 2 reviews")
- **NASCAR paid-influencer** partnership (no Crēdo analogue)
- **Real-client and creator testimonials** (NY bar testimonial rules)

## What's in the build

**6 ad groups — one static concept and one video concept each · 24 files.**

- **Statics** — 6 concepts × **1:1** (1200×1200) and **1.91:1** (1200×628). Built with a measured,
  auto-fitting block layout (landscape reflows to two columns) so text cannot overflow.
- **Video** — 6 lip-synced spokespeople × **9:16** (1080×1920) and **4:5** (1080×1350), **8s each**:
  6s performance + a 2s Crēdo end card, 30fps, H.264, **with audio** (AAC 48kHz stereo,
  normalised to −16 LUFS / −1.5 dBTP).
- Footage generated with **Higgsfield**; all type, caption boxes, sticker tags, CTA pills and end
  cards are **baked on** in the Crēdo system (Hanken Grotesk, `#c92028`, `#111418`) — the same way
  FDR builds theirs and the same way the Bold Meta set was made.

### Audio — all six are lip-synced

Every ad is a **lip-synced talking head** (`wan2_7`): the synthetic performer actually speaks the
scripted line, so there is no VO/lip mismatch anywhere. The earlier motion-poster and b-roll/voiceover
concepts were dropped in favour of a full spokesperson set.

### Cast

Ensemble cast for creative representation — **3 women, 3 men**:

| Ad | Performer | Spoken line |
|---|---|---|
| V1 | Woman (white), 30s, home kitchen | "Getting collection calls? Before you pay a cent, make them prove the debt is yours." |
| V3 | Woman (Black), 30s, home kitchen | "You can make them validate the debt. Many debt buyers can't prove they own it." |
| V5 | Woman (white), 50s, kitchen with paperwork | "A collector says you owe this bill. Can they prove the amount? Billing errors are common." |
| V2 | Man (white), 40s, living room | "A collection letter showed up. You can demand proof in writing. Many debt buyers can't produce it." |
| V4 | Man (white), 50s, home kitchen | "Make them prove it. A collector has to validate the debt in writing. Free case review." |
| V6 | Man (Black), 40s, living room | "The calls don't have to run your life. A free review shows where you stand." |

Note: Meta's CREDIT Special Ad Category restricts audience **targeting** by demographics; it places no
restriction on who appears in the creative.

Every spoken word is part of the copy Jack reviews — full scripts in `copy/vo-scripts.csv` and in the
manifest under each ad's `audio.spoken_script`. Each finished MP4 was **transcribed back and matched
against its script** to confirm nothing unscripted was said. Meta autoplays feed video muted, so all
six also read correctly with sound off via the burned-in captions.

## Compliance built into the creative

- **Synthetic-performer disclosure burned into V1, V2, V5** (the talking-head ads):
  *"Paid attorney advertising. Not a real client testimonial. Features a synthetic, AI-generated
  performer, not a real person. Prior outcomes don't guarantee similar results."*
  FDR runs the same disclosure on their AI spokesperson ads, and it satisfies NY's AI-generated-content
  rule at the same time.
- **General AI disclosure burned into V3, V4, V6.**
- Universal footer + "Prior outcomes don't guarantee similar results" on every primary text.
- Micro-disclaimer strip on every static.
- **`[CONFIRM]` before launch:** Jack's full name, firm mailing address / phone / email, exact NY
  AI-disclosure wording, and **Jack's pre-approval of every ad**.

## Required settings

Special Ad Category **CREDIT** (US) · Objective **Leads** · **Status PAUSED** · CTA **Book Now**.
UTM: `utm_source=meta&utm_medium=paid_social&utm_campaign=credo_meta_competitive_v1&utm_content={ad}`.

## Files

```
campaign-manifest.json   machine-readable: ads, copy, URLs, compliance, what each ad mimics
asset-manifest.csv       ad → creative file → kind → ratio
copy/ads.csv             headline · description · CTA · final_url · final_url_utm · mimics
copy/bodies.csv          primary text with the compliance footer baked in
creatives/static/        8 JPEGs (1:1 + 1.91:1)
creatives/video/         12 MP4s (9:16 + 4:5)
```

## Static variants 3 and 4 — agency designer sets (added 22 Sep 2026)

Two complete static sets from the designer, one concept per ad (C1–C6 ↔ A1–A6), each in **four
ratios — 1:1 (1440²), 4:5 (1440×1800), 9:16 (1080×1920), 16:9 (1920×1080)**:

- **Variant 3** = designer set 1 (16 Sep) → `creatives/static/v3/S{n}_{slug}_v3_{ratio}.jpg`
- **Variant 4** = designer set 2 (17 Sep) → `creatives/static/v4/S{n}_{slug}_v4_{ratio}.jpg`

They sit on the review page under each ad as "Designer sets · variants 3 and 4", every image
commentable, and in `campaign-manifest.json` as `review_variants` `S{n}_{slug}-v3` / `-v4`
(status: under review, not in the upload set). The supplied PNGs (31 MB + 68 MB) are stored here
as JPEG q92 (13 MB for all 48); the PNG originals stay with the designer's delivery.

## Review revisions — Sona, 22 Sep 2026

Applied in this package:

- **A1 headline** — "Make Them Prove You Owe It" → **"Make Collectors Prove Before You Pay"**.
  Sona: the old line doesn't signal consumer debt fast enough. Changed in `index.html`,
  `campaign-manifest.json` (`ads[0]`) and `copy/ads.csv`. **A6_in-writing still carries the old
  line** — it was not the ad she commented on.
  *Open consequence:* the S1 statics have `MAKE THEM PROVE IT.` baked into the artwork, so the
  art needs re-rendering to match the new headline field.
- **A1 static design** — option **C (light, no image)** chosen over B. Sona: "Lighter is better…
  the image looks very sad." The A1 strip and `ads[0].creatives` now point at
  `S1_prove-it-light-noimg_{1x1,1_91x1}.jpg`; the comparison block records the decision.

Videos re-generated 22 Sep (both now applied; previous cuts are in git history at 43bb515):

- **V2_is-it-yours** — re-shot at 8s instead of 6s so the performer holds a calm beat and a
  small nod after the line before the end card. Total 10.1s. Same script; transcribed back and
  matched word for word. New synthetic performer (a fresh generation cannot reproduce the earlier
  face).
- **V5_medical** — now speaks the primary text, not just the hook: *"A collector says you owe a
  medical bill. Can they prove it? Medical billing is full of coding errors and duplicate charges.
  They have to validate the amount if you ask. Our attorneys check it before you pay anything.
  Free case review."* Total 15.8s. A single 14s take garbled its last two sentences (wan2_7 drifts
  past ~10s of continuous speech), so the clean first 6.6s were kept and the rest generated as a
  second take started from that exact frame; the join is continuous and the whole thing
  transcribes back word for word.
- Bake pipeline (captions from Whisper word timings, compliance strip, end card, 4:5 cut,
  −16 LUFS) is now in the repo at `scripts/meta-ads/bake-talking-head.py`. Captions are set in
  Helvetica Neue Bold on this machine (Hanken Grotesk is not installed locally); the end cards are
  the original frames, unchanged.
