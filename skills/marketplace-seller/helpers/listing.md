# Listing

Turns a graded item and a price into paste-ready copy. Runs after `photos.md` has graded condition and `pricing.md` has set the ask — writing copy before either produces claims the photos don't support.

Fill `templates/listing.md`. Everything above the rule is for pasting; everything below is the human's own reference.

## Voice

Plain, factual, flaw-forward. Short lines. No hype words, no urgency, no emoji-led headings.

This is a conversion choice, not a modesty one. Marketplace buyers are screening for scams, and Meta's own safety guidance teaches them to distrust prices far under market and sellers who rush them or stay vague about an item's history. Sales language mimics exactly that. Disclosed flaws do the opposite: they raise trust, pre-empt haggling over things the buyer would have found anyway, and prevent the meetup collapsing over a surprise.

**The binding rule: never write a claim the photos do not support.** Every stated fact traces to something visible, or to something the human confirmed. Where they claim something you cannot see — "battery is fine", "barely used" — either get a photo or attribute it as their statement.

## New, used, or refurbished

The copy changes shape with what is being sold.

**Used** — the flaw list is the trust-builder. Lead with condition and be specific.

**New or sealed** — there are no flaws to disclose, so trust has to come from elsewhere: state that it is sealed and unopened, show the proof from `photos.md`, and say where it came from if that helps. Grading an item `New` commits you to unused and unopened — an opened-but-unused item is `Used (like new)`, and calling it New is the kind of mismatch that ends at the meetup.

**Refurbished** — say who refurbished it and what was replaced or repaired. Meta's definition covers inspection, replacing parts that don't work, cleaning, and repackaging; cleaning alone is not refurbishment.

**Multiple units** — say how many are available and that more are on hand. Keep one record per listing; `inventory.md` tracks the count.

**Vehicles are only partly covered.** Facebook requires year, make, model, mileage, and transmission, and grades vehicles on a condition scale separate from the five values in `photos.md`. That scale's exact values could not be confirmed against Meta's own page, so **do not grade a vehicle's condition** — have the human pick from the values the listing form actually offers. Facebook also supplies its own Kelley Blue Book price range for vehicles, which is better evidence than the comps in `pricing.md`; use it as the anchor. Everything else here still applies: flaw-forward copy, photographing every flaw, and disclosing accident and service history.

## Title

Meta does not document how title text is weighted against description text in search, and publishes no keyword guidance for peer-to-peer listings. So write for a human scanning a grid of results, not for an algorithm nobody has described.

Front-load identity: **brand, model, then the one attribute that disambiguates it** — capacity, size, year, or colour.

```
iPhone 12 128GB Blue
Nike Air Max 90 US 9 / EU 42
Uratex Foam Mattress Double 54x75
```

Keep the distinguishing words within roughly the first 65 characters. That is Meta's own recommendation for catalog titles, to avoid truncation where display space is limited, and Marketplace grids truncate the same way. The widely-quoted 100-character cap on native listings is unverified — treat 65 as the target, not a limit to fill.

Leave out condition words, prices, and pleading. `SALE`, `RUSH`, `LEGIT`, and `!!!` all cost you the trust the rest of the listing is building.

## Structured fields

Fill every field the form offers rather than describing its value in prose. Structured attributes power the filters buyers narrow by — an item that omits size or brand disappears from a filtered search regardless of how well the description reads.

Set them from the graded facts: **condition** to the exact value `photos.md` returned, then **brand**, **size**, **colour**, and **material** as the category exposes them. Vehicles additionally require year, make, model, mileage, and transmission, and grade on their own condition system.

## Description

Structure, in order:

1. **What it is** — one line, full identification
2. **Condition** — the grade in plain words, and what that means for this item
3. **Flaws** — every one, each pointing at its photo number
4. **What's included** — and, where it matters, what isn't
5. **Why you're selling** — one line; it answers a question every PH buyer asks anyway
6. **How to collect** — meetup areas and payment, from `market/ph.md`

```
iPhone 12 128GB, Blue. Unlocked.

Used (good). Battery health 87%. Screen is clean,
no cracks or dead pixels.

Flaws: small dent on the bottom-left corner (photo 5),
light scuffing on the frame (photo 6).

Includes the phone and a charging cable. No box.
Factory reset, iCloud removed.

Selling because I upgraded.

Meetup at SM North or Trinoma. GCash or cash.
```

Sentence case throughout — no ALL CAPS. **Keep contact details, external links, and shipping-company information out of the description**; Meta's catalog rules prohibit them, and on Marketplace the conversation belongs in Messenger where you keep a record of it.

No published data links description length to sell-through on any platform, so write what a buyer needs to decide and stop. Answering their questions in advance is the goal, not filling space.

## Before it goes live

Check the item against the traps in `policy.md` — supplements, medical devices, anything digital or service-shaped, animals, vapes, opened cosmetics, and recalled goods are the ones that catch honest sellers. When it is near a line, read `policy.md` properly before advising.

Then confirm three things:

- Every claim in the copy is visible in a photo or attributed to the human
- Condition matches the grade exactly, in both the structured field and the prose
- No overlay text, watermark, or price is baked into any image

Write the copy to the item's `listing.md`, then set `status: listed` and `listed_on` once the human confirms it is actually posted — not before. A record marked live while the listing sits unposted corrupts every day-count and staleness decision downstream.

**In the Philippines, posting is capped at 10 listings per week.** Where the human has more items ready than slots remaining, say so and let them choose the order — `market/ph.md` covers how to spend the slots.
