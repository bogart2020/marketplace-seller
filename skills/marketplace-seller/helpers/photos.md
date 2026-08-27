# Photos

Two jobs, at opposite ends of the shoot: tell the human what to capture, then read what they captured and grade it.

## Every photo is a candidate cover

Facebook states it **may automatically select cover photos based on quality and accuracy**, and that it **may enhance listing photos and videos**. The widespread belief that your first upload becomes the thumbnail is therefore wrong — Meta picks.

The practical consequence: there is no single shot to perfect. Every photo needs to be clean enough to represent the listing in search results, because any of them might. Say this when a human asks which photo to put first.

## Shot list

Give the list before the shoot, adapted to the item. Meta publishes no guidance on angles, flaws, or lighting for organic listings, so this is craft convention, not platform rule — present it that way if asked.

**Every item:**
1. Whole item, straight on, filling the frame
2. Whole item, three-quarter angle
3. Back or reverse side
4. Brand mark and model number — legible
5. One close-up per flaw, close enough to judge severity
6. What is actually included, laid out together — cables, box, manuals, accessories

**Add by category:**
- **Electronics** — powered on and working, showing the home screen or output. Ports and charging area. Battery health screen for phones and laptops.
- **Shoes and clothing** — outsoles and heels, insoles, inner label with size and composition, any stretch, pilling, or staining
- **Furniture** — all four sides, joints and legs, underside, plus one shot in a room for scale
- **Appliances** — running, plus interior, seals, and filters
- **Bags and watches** — hardware, lining, stitching, serial or date code, clasp and strap wear

**Keep identifiers out of public photos.** A phone's IMEI, a laptop's serial, a bike frame number — photograph the model name, not the unique identifier. Published identifiers get cloned into fake listings and used to claim ownership. Offer the identifier privately in Messenger to a buyer who asks; someone checking it against a blocklist is a good sign, not a bad one.

**New and sealed items:** buyers screen hardest for counterfeits here, because the usual condition evidence is hidden inside a box. Shoot the seals intact, all sides of the packaging, the barcode or serial on the box, any authenticity mark or hologram, and proof of purchase with personal details covered. Where you hold several units, add one shot of the actual stock on hand — it separates a real seller from someone listing a catalogue photo.

**Prepare a device before you shoot it.** Back it up, factory reset it, and remove every account still signed in — Google, Mi, iCloud, Samsung. A phone that reaches a buyer still locked to your account is their worst outcome and your most likely dispute, and buyers ask about it before they ask about anything else. Doing it before the shoot also means the photos show a clean home screen.

**Shooting conditions:** daylight, no flash, a plain uncluttered surface, item in focus and filling the frame.

**Keep the frame clean.** No text overlays, watermarks, price call-outs, or promo graphics. Meta's image guidance prohibits these, and eBay's quality standard explicitly excludes photos with added text.

Photo quality is the one place with real cross-platform evidence: eBay, reviewing 6.8 million listings, reports that **listings with better photo quality are 4.5% more likely to sell**, defining quality as at least 500 px on the longest side with no added text or graphics. Note this measures quality, not count — no platform publishes an optimal photo count. Comparable platforms cap at 10 to 12 photos; Facebook's own cap is not documented, and the "10 photos" figure in circulation is unverified.

## Reading the photos back

When photos arrive, report in this order:

**1. What the photos show.** Describe the item as a stranger would see it — model, colour, materials, what is included. Flag anything that contradicts what the human said.

**2. Every visible flaw, with its photo number.** Scratches, dents, wear, staining, fading, cracks, missing parts, corrosion, pilling, sole wear. These become the listing's flaw list and the `flaws` block in `item.md`. A flaw you can see and don't record becomes a dispute at the meetup.

**3. A condition grade** against Facebook's exact values, using Meta's own definitions:

| Value | Meta's definition | Grade here when |
|---|---|---|
| **New** | Unused, unopened, undamaged | Sealed or never used, with packaging |
| **Used (like new)** | "Excellent condition, but has previously been worn or used. No signs of wear or defect." | You can see no wear at all |
| **Used (good)** | "Minor signs of wear. Item is operational and works as intended." | Light wear visible, everything works |
| **Used (fair)** | "Some signs of wear and tear or minor defects. Item is still usable as intended." | Obvious wear or a defect, still usable |
| **Refurbished** | "Has gone through a refurbishing process... inspecting the product, replacing any parts that don't work, cleaning and repackaging." | Genuinely refurbished, not merely cleaned |

Meta's labels are exactly `Used (like new)`, `Used (good)`, `Used (fair)` — not the `Used - Like New` styling used in most seller guides.

Grade from the photos, not from the human's description. Where they conflict, say so and grade down: **an over-grade is discovered at the meetup, when the buyer is standing there and the price is already agreed.** Under-grading costs a little money; over-grading costs the sale and the trip. Vehicles grade on a separate system — `listing.md` covers what this skill does and does not do for them; do not apply this table to one.

**4. What to reshoot.** Blurry, dark, cropped, or cluttered shots, and any flaw you inferred but cannot actually see. Ask before writing copy — the description depends on this.

Once graded, `listing.md` writes the copy.
