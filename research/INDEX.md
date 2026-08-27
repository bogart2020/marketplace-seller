# Research

Findings behind the `marketplace-seller` helpers. Six parallel agents, primary sources preferred, every claim tagged and every gap stated. Raw findings in `raw/`.

| File | Covers | Feeds |
|---|---|---|
| `raw/01-ranking-visibility.md` | Search ranking, recency, renewal, limits, Insights | `inventory.md`, `market/ph.md` |
| `raw/02-copy-and-photos.md` | Photo specs, titles, descriptions, condition taxonomy | `photos.md`, `listing.md` |
| `raw/03-pricing-negotiation.md` | Comps sources, depreciation, negotiation evidence | `pricing.md` |
| `raw/04-scams-and-policy.md` | Seller scams, Commerce Policy, appeals | `safety.md`, `policy.md` |
| `raw/05-philippines.md` | Payments, couriers, meetups, tax, glossary | `market/ph.md` |
| `raw/06-lifecycle-and-chat.md` | Listing lifecycle, buyer chat, badges, ratings | `buyer-chat.md`, `inventory.md` |

## Findings that shaped the design

**PH posting cap — 10 listings per week.** Meta-official, country-specific. Listing slots are the scarcest resource, which makes renewing preferable to delete-and-relist and turns the sweep into a slot-allocation decision.

**No platform protection for a local meetup.** Meta's Purchase/Seller Protection is onsite-checkout, shipped, US-only, capped at $500. Facebook Marketplace has no escrow, and the nearest PH equivalent requires selling on Carousell. Payment verification therefore has no recourse layer beneath it.

**Countering is worth real money.** Across 26.4M eBay Best Offer negotiations, sellers who countered conceded 63% of the gap instead of 86%. Later counters did better *and* failed less. Below ~20% of asking, deals essentially never close.

**Facebook picks the cover photo** — "based on quality and accuracy" — so the first-upload-is-the-thumbnail rule is wrong, and every photo must be cover-worthy.

**BEA depreciation rates** are the only primary quantitative source found for value retention by category. No line exists for phones or laptops; the AV proxy understates them.

**Marketplace listings *are* web-searchable.** Direct testing contradicted the common claim. Meanwhile eBay sold/completed comps went behind a login in July 2026, removing the one real transaction-price source. Carousell PH is the strongest remaining PH comps source, asking-prices only.

## Documented gaps — do not fill these with invented numbers

Meta publishes nothing on:

- **The renew mechanic** — no eligibility window, no cap, no stated visibility effect. "Every 7 days, five times" is folklore.
- **Badge thresholds** — the Marketplace Very Responsive badge has no published formula. The 90%-in-15-minutes figure belongs to Facebook Pages, a different surface.
- **Ranking weights** — including whether title outweighs description. Shipping performance is the only distribution factor Meta states explicitly.
- **Native listing limits** — no confirmed photo cap, title length, or active-listing ceiling. The "10 photos / 100 characters" figures are unverified.
- **Markdown timing** — no platform publishes repricing data for secondhand goods. Every "drop 10% after two weeks" rule is extrapolated or invented.
- **Duplicate listings** — no codified rule found.

Two further gaps carry real-world consequences and are flagged in the helpers rather than resolved:

- **LBC publishes no COD remittance timeline**, and no courier documents what happens when a buyer refuses a COD parcel.
- **No bright line separates casual disposal from "engaged in business"** under DTI or BIR rules. This matters for buy-to-resell operations specifically, and needs a professional rather than a guess.

## Method notes

Several Meta help pages auto-localize and render client-side; some returned Filipino text or empty bodies even with an `en_US` parameter. Where a page's existence was confirmed but its body was unreadable, the agents recorded "existence-only" instead of treating it as documented absence. Exact clause wording should not be quoted as Meta's text.
