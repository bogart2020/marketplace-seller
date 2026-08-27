# Inventory

State for every item: where it lives, what its status means, and how the board and the sweep are produced.

Pricing decisions live in `pricing.md` — this file moves items between states and never sets a number.

## Two storage modes

Establish the mode once per session, before the first write, and say which one is active.

**A writable directory is not enough — it has to persist.** Claude apps run skills in a sandbox that has a filesystem and discards it when the conversation ends. Writing an item record there looks like it worked and is gone by the next session. So decide by provenance, not by whether a write succeeds:

- A working directory the human named, or an `inventory/` that already holds records from an earlier session → **filesystem mode**.
- An `inventory.md` the human attached → **attached-file mode**.
- Neither, and you cannot tell → **ask which**, in one question, before writing anything. Never create `inventory/` in a sandbox and report it as saved.

**Say so when the location is volatile.** A path under `/tmp`, a scratch folder, or anything the human calls temporary is real storage that still gets cleared — by a reboot, or by the OS reaping untouched files. Write there if that is what they asked for, flag it once, and offer to move the records somewhere durable. They copy across unchanged.

**Filesystem mode** — a real working directory is available (Claude Code, or a Claude app with a filesystem connection). One folder per item:

```
inventory/
  INDEX.md
  nike-airmax-90-42/
    item.md
    listing.md
    photos/
```

**Attached-file mode** — no writable working directory (the claude.ai app without a filesystem connection). All state lives in one `inventory.md` the human keeps as Project knowledge: the same front-matter blocks concatenated under `## <slug>` headings, no photos folder. Read it at the start of a session and hand back the complete rewritten file whenever state changes, so the human replaces the attachment in one paste.

Both modes carry identical fields. An item written in one mode transfers to the other by copy-paste.

## Fields

`templates/item.md` is the authority on field names and order. Three fields carry rules worth stating:

- **`floor`** is yours. It never appears in `listing.md` above the rule, never in a reply draft, and never in anything the human is told to paste.
- **`cost`** is recorded even when the item was already the human's and cost nothing — write `0`. A missing cost makes margin uncomputable later; a zero is a fact.
- **`quantity`** is 1 for a one-off. For multi-unit stock, an item stays `listed` while units remain: on each sale add to `sold_qty` and decrement `quantity`, and only set `status: sold` when the last unit goes. Record `sold_price` as the unit price, and log a different unit price in `price_history` rather than overwriting it.

Dates are ISO `YYYY-MM-DD`. Take today's date from the environment rather than from memory — where a shell is available `date +%F` gives it; otherwise ask the human rather than guessing.

## Statuses

| Status | Means | Leaves to |
|--------|-------|-----------|
| `draft` | Being prepared. Not on Facebook. | `listed` |
| `listed` | Live and visible. | `pending`, `withdrawn`, `sold` |
| `pending` | A buyer has committed and a handoff is scheduled. | `sold`, `listed` |
| `sold` | Money received and item handed over. | — |
| `withdrawn` | Taken down unsold — kept, returned, or given away. | `listed` |

`pending` returns to `listed` when a buyer ghosts. That round-trip is the norm, not an error — record the no-show and its date under `## Notes` in the item, so the sweep can see a pattern of buyers committing at a given price and vanishing. Keep `price_history` for price changes only.

Reaching `sold` demands three writes together: `status`, `sold_price`, and `sold_on`. Margin analytics later depend on all three, and a `sold` item missing a price is unrecoverable once the human forgets the number.

## The board

`INDEX.md` is derived. Regenerate it from the `item.md` files rather than editing it, and regenerate on every status change.

**Days live** is today minus `listed_on`. **Next action** is whatever the sweep last sorted the item into, phrased as one action. No fixed repricing calendar exists — `pricing.md` sets prices from demand evidence, not from elapsed days — so never present a scheduled drop as due.

## The sweep

The sweep answers one question for every `listed` item: *is this still working?* Run it on `/sell-refresh`, and when the human asks what needs attention.

For each `listed` item, gather days live, current ask against floor, price changes so far, and buyer contact since listing.

**Ask for Insights numbers.** Facebook reports clicks, saves, and shares per listing under Marketplace → Selling → Seller Dashboard, filterable to the last 7, 14, or 30 days. Those three numbers separate two failures that look identical from the inbox — a listing nobody saw, and a listing everybody saw and rejected. Request them for any item stale enough to act on; diagnose from contact alone only when the human cannot get them.

Sort every item into exactly one of:

- **Working** — recent buyer contact, or listed too briefly to judge. Leave it.
- **Unseen** — few clicks. Buyers are not reaching the listing at all, so price is not the problem yet. The lead photo and title are what appear in search results: `photos.md` for the lead shot, `listing.md` for the title.
- **Seen and passed** — clicks but few saves and no messages. Buyers looked and declined, which points at price, condition disclosure, or a missing answer in the description. `pricing.md` sets the drop.
- **Wanted but unsold** — saves accumulating without messages. Buyers want it at *some* price and are waiting. This is the strongest markdown candidate on the board, because a price drop reaches people who already saved it.
- **Floor reached** — priced at floor with no takers. This is a decision the human makes, not the skill: hold, sell below floor, or withdraw. Present the numbers and ask.

Report the sweep as a single list ordered by days live, longest first. An item with nothing to do gets one line saying so — a silent item reads as an overlooked item.
