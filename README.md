# marketplace-seller

A Claude skill for selling secondhand goods on Facebook Marketplace: price research, listing copy, photo direction, buyer negotiation, scam screening, and inventory tracking.

Claude never touches Facebook. It produces paste-ready artifacts you post yourself — no automation, so no account risk and nothing to break when Facebook changes its interface.

## What it does

| Stage | You get |
|-------|---------|
| Get it live | Comps-backed ask price and floor, a category-specific photo shot list, condition graded from your actual photos, and paste-ready listing copy |
| Close the buyer | Reply drafts, negotiation scripts held to your floor, scam screening, and handoff logistics |
| Lifecycle | An inventory board, a staleness sweep, markdown schedules, and relist copy |

## Install

**Claude Code**

```
/plugin marketplace add /path/to/marketplace-seller
/plugin install marketplace-seller
```

Adds the `marketplace-seller` skill plus `/sell-new`, `/sell-reply`, `/sell-board`, and `/sell-refresh`.

**Claude app (desktop, web, mobile)**

Zip the `skills/marketplace-seller/` folder and upload it under Settings → Capabilities → Skills. The skill works unchanged; the slash commands are Claude Code only, so start with plain language instead — "help me sell this iPad".

## Where your data lives

With a working directory, one folder per item:

```
inventory/
  INDEX.md              generated board
  nike-airmax-90-42/
    item.md             status, cost, ask, floor, dates
    listing.md          paste-ready copy
    photos/
```

Without one — the claude.ai app with no filesystem connection — the same records live in a single `inventory.md` you keep as Project knowledge and re-attach when it changes.

## Markets

The skill core is country-neutral. Market specifics — currency, payment rails, couriers, meetup norms, local scam patterns, and comp sources — live in `market/`. `ph.md` (Philippines) ships active. Add a sibling file to support another country.

## Layout

```
.claude-plugin/     plugin + marketplace manifests
commands/           /sell-* entry points (Claude Code only)
skills/marketplace-seller/
  SKILL.md          master router
  helpers/          pricing · photos · listing · policy
                    buyer-chat · safety · inventory
  market/ph.md
  templates/
research/           sourced findings behind the helper content
```
