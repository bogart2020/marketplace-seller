# Pricing

Produces three numbers for an item: the **ask** (what goes on the listing), the **floor** (the walk-away, never shown to a buyer), and the **repricing trigger** (the evidence that justifies a drop). Also governs how to answer an offer.

## Which path

Condition decides how the price is derived. Establish it before anything else.

| What you're selling | How the price is built |
|---|---|
| **Used** — your own, or bought to flip | Retail anchor, depreciated, confirmed against secondhand comps. The path below. |
| **New / sealed stock** — bought to resell | Retail is a **competitor, not an anchor**. See below. |
| **Refurbished** | Between the two: comps against other refurbished units, and the refurbishment itself is the value story. |

**New stock inverts the logic.** For a used item, Shopee and Lazada sit *above* your price and justify it. For a sealed item they sit *beside* it — a buyer can order the same thing, from a rated seller, with returns and no meetup. That convenience gap is real and you are selling against it.

So price new stock from both ends:

- **Ceiling** — the landed price a buyer pays elsewhere today, minus something for the trust and convenience they give up buying from a stranger. Matching retail rarely works; beating it is the reason to buy from you.
- **Floor** — unit cost plus the margin that makes the work worth doing. Below that, don't list it.

When the ceiling sits under the floor, the item is not sellable at profit on Marketplace. Say so plainly instead of pricing it at a loss — that is a sourcing signal, and it is worth more to the human than a listing.

Depreciation curves do not apply to unused stock. Skip step 2 below.

For multiples, price the unit, and hold the floor across all of them — a discount given on the first unit sets the expectation for the rest.

## Build the ask

Work in this order and show the human each input, because a price they can't reconstruct is a price they won't hold under pressure.

**1. Retail anchor.** What the item costs new today, not what they paid. Shopee and Lazada are reliable for this in the Philippines — they carry retail pricing, which makes them a good anchor source and a poor comps source. If the model is discontinued, the last known retail price still anchors, with its age noted.

**2. Depreciate it.** Annual geometric depreciation rates from the US Bureau of Economic Analysis, derived from real used-asset resale studies — the strongest quantitative source found for this. Value retained:

| Category | Annual rate | 1 yr | 2 yr | 3 yr | 5 yr |
|---|---|---|---|---|---|
| Furniture, luggage | 11.79% | 88% | 78% | 69% | 53% |
| Household appliances | 15.00% | 85% | 72% | 61% | 44% |
| Video/audio electronics | 18.33% | 82% | 67% | 54% | 36% |
| Sports & photo gear | 16.50% | 84% | 70% | 58% | 41% |
| Jewelry & watches | 27.50% | 73% | 53% | 38% | 20% |

BEA publishes **no line for smartphones, laptops, or tablets**. Video/audio is the nearest proxy and it understates them — phone and laptop model cycles are faster than AV gear. Treat the proxy as a ceiling for those, and lean on comps instead.

These are US economy-wide accounting rates, not PH secondhand-market observations. They set the shape of the curve; comps set the level.

**3. Comps — asking prices, and know that's what they are.** Every source reachable now shows what sellers *want*, not what buyers *paid*. eBay's sold and completed listings, historically the one real transaction-price source, began requiring login in July 2026 and are no longer fetchable.

| Source | Use it for | Watch out |
|---|---|---|
| **Carousell PH** | Best PH secondhand comps — indexed, no login | Asking prices only; no sold filter |
| **Facebook Marketplace** | Direct competitors, same city | Item pages are reachable by web search, but coverage is patchy and unverified |
| Shopee / Lazada PH | Retail anchor | Retail/new pricing — not secondhand comps |
| PriceCharting | Games, consoles, cards | Real aggregated sold prices, but USD and US-market |
| eBay active listings | Global asking prices | Login-free, but wrong market for PH |

Search Marketplace and Carousell directly. Where results are thin or the human can see the local market better, ask them to search Marketplace in their own city and describe or screenshot what's live — their view is geo-personalised in a way a web fetch is not.

**4. Set ask and floor.** The ask sits at the top of the credible comp range when condition is genuinely above average, mid-range otherwise. The floor comes from the human, not from the skill — ask what number makes walking away easy. Record both; only the ask is ever spoken.

**Leave haggling room, and say that you are.** Where a discount is expected — as it is throughout the Philippines — the ask sits a modest step above the top credible comp so there is somewhere to move. State the buffer when you propose the price, so the human knows which part is market evidence and which part is negotiating room. Two limits: a buffer large enough to push the listing clear of the comp band stops it being clicked at all, and **the buffer never touches the floor.** The floor is anchored to comps and to cost, not to the ask.

**Use a precise number, not a round one.** Non-round prices anchor higher in negotiation experiments. ₱3,450 outperforms ₱3,500 as an anchor, and reads as considered rather than arbitrary.

## Answering an offer

The strongest evidence in this whole skill sits here: a study of **26.4 million eBay Best Offer negotiations**.

**Always counter. Never simply accept or refuse.** Across all completed negotiations, sellers conceded **86.4%** of the gap and buyers only **13.6%**. Where the seller made a counteroffer, the split moved to **63.3% / 36.7%**. Countering is the single highest-value habit available to a seller.

**Do not answer instantly with a concession.** Later counteroffers achieved better outcomes than early ones *and* lowered the chance of no deal. Acknowledge fast, concede slowly.

**The first number anchors nearly linearly** (R² = .997) — every point off the opening figure carries through proportionally to the final price. This cuts both ways: it is why the ask is set deliberately, and why a lowball should be countered rather than treated as the new baseline.

**Judge a lowball by how far below the ask it sits.** Deals fail rarely near 90% of asking, and failure risk climbs steeply as offers fall toward 20%; below roughly 20% of asking, almost nothing closes regardless of what either side does. An offer at a fifth of the ask is not a negotiation — answer once, politely, at or near the ask, and spend the attention elsewhere.

*(These figures come from eBay's structured Best Offer feature. The mechanisms — anchoring, asymmetric concession, non-linear impasse — should carry over to Messenger haggling; the exact percentages are eBay's, not Marketplace's, and shouldn't be quoted as Marketplace numbers.)*

`buyer-chat.md` turns these into actual replies.

## Repricing

**No platform publishes data on optimal markdown timing or size for secondhand goods.** Every "drop 10% after two weeks" rule in circulation is extrapolated from real-estate research or invented outright. Do not state one as fact.

Reprice on evidence instead of on a calendar. Mercari's published pricing system — the only documented automated approach — drops price against demand signals, listing age, and a seller floor, and can raise price when demand rises. The same inputs are available here from Insights via `inventory.md`:

- **Saves accumulating, no messages** — buyers want it and are waiting on price. The strongest markdown case, and the drop reaches people who already saved it.
- **Clicks without saves** — they looked and passed. Price is one candidate; condition disclosure and a missing answer in the description are the others. Check the listing before cutting.
- **Few clicks** — nobody is reaching it. A price cut is wasted here; `photos.md` and `listing.md` come first.
- **Demand rising** — hold. The floor is not a target.

Log every change in `price_history` with its date and the evidence behind it. Successive cuts in real-estate data correlate with *longer* total time to sell, so a drop needs a reason each time, and a pattern of repeated cuts is a signal to re-examine the listing rather than cut again.

Where the human wants a calendar anyway, say plainly that no measured rule exists, then agree an interval with them and hold to it — a stated assumption they chose beats a fabricated benchmark.
