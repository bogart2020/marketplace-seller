# Listing Copy & Photos

Research date: 2026-08-27. Scope: what Meta documents officially about Facebook Marketplace photos/copy, plus cross-platform primary evidence from other marketplaces. Two important caveats surfaced repeatedly during research and apply throughout this file:

1. Meta operates **two distinct listing systems** that are often conflated by third-party blogs: (a) the native peer-to-peer Marketplace "Item for sale" flow (personal accounts, no feed required), and (b) the **Commerce Manager / Catalog (Shops) feed system**, which businesses use to bulk-list inventory that can also surface on Marketplace. Field limits and condition enums documented for the Catalog are NOT always identical to the native listing form's UI. Each fact below is labeled with which system it applies to where known.
2. Meta's own consumer-facing help pages (help.facebook.com) are thin on hard numbers (pixel counts, exact photo caps) compared to its developer/Commerce Manager documentation. Several widely-repeated numbers (e.g., "10 photos," "100-character title," "30MB max") could not be verified against a primary Meta page during this research and are flagged SECONDARY/UNVERIFIED below rather than stated as fact.

## Photos: documented requirements and limits

- **Catalog/Commerce Manager image spec (`image_link` / `additional_image_link`)**: JPEG or PNG format, minimum 500×500 px, maximum file size 8 MB, up to 20 additional images supported (separated by comma/semicolon/space/vertical bar). [META-OFFICIAL] https://developers.facebook.com/docs/commerce-platform/catalog/fields/
- **Marketplace ad placement image spec** (from Meta's ad-placement image guidance): recommended ratio 1:1, ratios from 16:9 to 9:16 supported, minimum resolution at least 1080×1080 px. This spec is documented for *ads placed into* the Marketplace surface, not confirmed identical to organic peer-to-peer listing photos. [META-OFFICIAL, ads context] https://www.facebook.com/business/help/376859690417674
- **Native Marketplace "Item for sale" listing flow**: Meta's help page for creating a listing confirms sellers can "Add photos" or "Add Video to upload a video of your item," and states explicitly: **"We may enhance your listing photos and videos to improve their quality"** and that Facebook **may automatically select cover photos based on quality and accuracy** — i.e., Meta reserves the right to auto-pick which uploaded photo becomes the cover/thumbnail rather than always using the seller's first upload. No numeric photo-count cap, resolution minimum, or file-size limit is stated on this page. [META-OFFICIAL] https://www.facebook.com/help/561376580709359
- A specific max photo count of "10 photos" and specifics like "500×500 px minimum, 1200×1200 recommended," "30MB max file size" are repeated across many reseller/SEO blogs but could not be confirmed on a primary Meta page in this research. [SECONDARY/UNVERIFIED] e.g. https://isopeel.com/guides/facebook-marketplace-image-requirements/, https://pixpipe.app/en/guides/facebook-marketplace-photo-size
- Meta has added an optional **video** upload capability alongside photos on some Marketplace listings (rollout is inconsistent/geo-gated per reporting); reported cap is up to 60 seconds. This is not confirmed as universally available. [SECONDARY/UNVERIFIED — reported by trade press, not a Meta help page] https://www.socialmediatoday.com/news/facebook-adds-video-display-elements-to-marketplace-listings/647150/, https://www.valueaddedresource.net/facebook-marketplace-adds-video-capability-for-listings/

### What the first/cover photo does
- Meta's help page states the platform **may automatically select** the cover photo shown in feed/search based on "quality and accuracy" — meaning the seller's literal first upload is not guaranteed to be the thumbnail Meta displays. [META-OFFICIAL] https://www.facebook.com/help/561376580709359
- The common claim that "the first photo you upload is always the thumbnail buyers see" is therefore imprecise per Meta's own language above; it is the common **default/starting assumption** used by most seller guides. [SECONDARY]

## Photo content: official guidance

- Meta's Commerce Policies (Commerce content standards) explicitly prohibit **misleading commerce content** — the policy text (reviewed directly) states commerce content must not be misleading ("Ang commerce content ay hindi maaaring naglalaman ng nakakalito," i.e., "commerce content cannot contain misleading [material]" in the localized version served to this research). [META-OFFICIAL] https://www.facebook.com/policies_center/commerce
- Ad-placement image guidance (applies to Marketplace-surfaced ads) states: don't include text overlays, calls to action, promo codes, watermarks, or time-sensitive information such as temporary price drops on the image itself; show the entire product clearly; include a mix of angles including close-ups of texture/detail. [META-OFFICIAL, ads context] https://www.facebook.com/business/help/376859690417674
- Requirements that photos must show the **actual item** (not stock photos, not images copied from other listings) and must match the description/condition stated in the listing are widely reported as Commerce Policy enforcement behavior (listings pulled when photo doesn't match title/condition/model), but the exact clause could not be located verbatim on a primary Meta page in this research — treat as a documented *pattern of enforcement*, not a quoted rule. [SECONDARY/UNVERIFIED] https://appath.com/resources/common-compliance-violations-on-facebook-marketplace-and-how-to-avoid-them
- No official Meta guidance was found instructing sellers to photograph flaws, use a specific number of angles, or use particular lighting/backgrounds for organic Marketplace listings. Such advice found in seller guides is SECONDARY.

## Titles

- **Catalog (Commerce Manager) title field**: documented maximum 200 characters, with Meta's own developer example/recommendation to keep titles to roughly 65 characters or fewer to avoid truncation in surfaces with limited display space. [META-OFFICIAL] https://developers.facebook.com/docs/marketing-api/catalog/reference/
- **Native Marketplace listing title**: a "100-character limit" is widely cited by third-party guides, but this research could not verify that number against a primary Meta help page — the native listing help page (facebook.com/help/561376580709359) does not state a title character limit. [SECONDARY/UNVERIFIED]
- No official Meta guidance was found prescribing a specific title *structure* (e.g., "Brand + Item + Size + Condition"). Cross-platform primary sources do address this (see Mercari/Carousell below) and are the strongest sourced guidance on title structure available.

## Descriptions

- **Catalog description field**: documented minimum 30 characters, maximum 9,999 characters. Must be plain text (rich_text_description field exists separately for formatted/HTML content on Shops); no ALL CAPS; sentence case required; description should differ from and be longer than the title; must not include contact info, shipping/company details, or links (use the dedicated link field instead). [META-OFFICIAL] https://www.facebook.com/business/help/2302017289821154
- No primary Meta page was found documenting a description character limit specific to the native peer-to-peer Marketplace "Item for sale" flow (as opposed to the Catalog feed above).

## Structured attributes vs. free text

Meta's Catalog schema defines several fields as **structured attributes** (used to power Marketplace/Shops filters), distinct from the free-text title/description:
- `condition` — enum, required. Catalog-level allowed values: `new`, `refurbished`, `used`. [META-OFFICIAL] https://developers.facebook.com/docs/commerce-platform/catalog/fields/ and https://developers.facebook.com/docs/marketing-api/catalog/reference/
- `brand` — free string, max 100 characters. [META-OFFICIAL] https://developers.facebook.com/docs/commerce-platform/catalog/fields/
- `size` — free string (words/abbreviations/numbers, e.g. "Small," "XL," "12," "One size"); guidance says to omit the literal word "size." [META-OFFICIAL] https://developers.facebook.com/docs/commerce-platform/catalog/fields/
- `color` — free string describing color in words (not hex codes), max 200 characters. [META-OFFICIAL] https://developers.facebook.com/docs/commerce-platform/catalog/fields/
- `material` — free string, max 200 characters (e.g. cotton, polyester, leather). [META-OFFICIAL] https://developers.facebook.com/docs/commerce-platform/catalog/fields/
- Apparel-specific structured fields also documented: `age_group`, `gender`, `pattern`, `item_group_id`, `google_product_category`, `product_type`, plus size charts that can be attached in Commerce Manager and shown to shoppers on click. [META-OFFICIAL] https://www.facebook.com/business/help/262477299039517
- `availability` — enum: `in stock` / `out of stock`. [META-OFFICIAL] https://developers.facebook.com/docs/commerce-platform/catalog/fields/

These structured fields are Catalog/Shops concepts. Whether the native peer-to-peer "Item for sale" listing form exposes identically named structured attributes (vs. its own category-specific dropdown fields) is not separately confirmed by a primary source in this research — see Gaps.

## Condition grading — exact official list

Meta's consumer help page "Meanings of item conditions on Facebook Marketplace" documents **five** condition values for general (non-vehicle) Marketplace items, with official definitions (confirmed via direct fetch, English-language version): [META-OFFICIAL] https://www.facebook.com/help/2004996079797091

1. **New** — "Brand new, never worn or used, undamaged item. Ideally in the original package."
2. **Used (like new)** — "Excellent condition, but has previously been worn or used. No signs of wear or defect."
3. **Used (good)** — "Minor signs of wear. Item is operational and works as intended."
4. **Used (fair)** — "Some signs of wear and tear or minor defects. Item is still usable as intended."
5. **Refurbished** — "Has gone through a refurbishing process ... usually include[s] inspecting the product, replacing any parts that don't work, cleaning and repackaging."

Note the exact official labels are **"Used (like new)," "Used (good)," "Used (fair)"** — not "Used - Like New" etc. as commonly written in seller guides.

This is a **different, coarser enum** than the Catalog feed's `condition` field, which only supports three values (`new` / `refurbished` / `used`) — see Structured Attributes section above. Sellers using the native app UI see the 5-value list; sellers/businesses uploading via Catalog feed are constrained to the 3-value enum. [META-OFFICIAL, cross-referenced from two Meta docs]

### Vehicle condition (separate system)
Meta publishes a dedicated page, "What the Different Vehicle Conditions Mean for Cars on Marketplace," confirming vehicles use a **different condition taxonomy** than general items. This research could not retrieve the verbatim page text directly (the page is JS-rendered and blocked automated fetching in every attempt made). Secondary aggregation of search-engine summaries suggests values resembling Excellent / Good / Fair / Poor (possibly aligned to Kelley Blue Book-style condition language, since Meta separately documents a KBB pricing integration for vehicle listings), and one source additionally listed "new," "salvage" as possible values. **None of this vehicle-condition wording is verified verbatim against the primary page** — treat as SECONDARY/UNVERIFIED pending direct confirmation. [META-OFFICIAL page exists, but content UNVERIFIED] https://www.facebook.com/business/help/979881538883930 ; related KBB integration page: https://www.facebook.com/business/help/1545716818882941

## Content documented to reduce buyer trust / cause disputes

- Meta's Commerce Policies (reviewed directly) prohibit misleading commerce content as a standing rule; enforcement documentation and trade coverage describe listings being removed when the photo doesn't match the stated model/color/condition/title. [META-OFFICIAL policy text; SECONDARY for the specific enforcement pattern description] https://www.facebook.com/policies_center/commerce ; https://appath.com/resources/common-compliance-violations-on-facebook-marketplace-and-how-to-avoid-them
- Meta's own Trust & Safety materials flag common scam patterns buyers/sellers should watch for, including prices significantly under market value and sellers who rush buyers or are evasive about item history — published as consumer safety guidance rather than seller-listing rules per se. [META-OFFICIAL, safety context] https://www.meta.com/safety/scam-prevention/marketplace-safety/
- Catalog description rules explicitly forbid including contact information (phone/email), shipping/company details, or embedded links in the description field — framed as a data-quality/spam-prevention rule for Shops feeds. [META-OFFICIAL] https://www.facebook.com/business/help/2302017289821154
- Ad-image guidance separately forbids price call-outs, promo codes, and watermarks baked into the image itself. [META-OFFICIAL, ads context] https://www.facebook.com/business/help/376859690417674

## Cross-platform primary evidence

### Photo count → sell-through / conversion
- **eBay** (confirmed by directly fetching eBay's own seller photo-tips page): "listings with better photo quality are 4.5% more likely to sell," based on an eBay-cited review of 6.8 million listings. eBay defines "better photo quality" as photos measuring 500+ px on the longest side, without added text/graphics, uploaded via eBay's picture service — this is a photo-*quality* metric, not strictly a photo-*count* metric. eBay's photo-tips page does not commit to an optimal photo count, only "at least one" is required and sellers are encouraged to add multiple angles. [OTHER-PLATFORM-PRIMARY] https://export.ebay.com/en/manage-listings/photo-tips/
- **Mercari**: allows up to 12 photos per listing; Mercari's own seller blog post recommends multiple angles and natural lighting. A frequently repeated stat ("listings with 5+ photos sell 2-3x faster") appears in third-party Mercari-selling guides, not confirmed on Mercari's own blog page (blocked/inaccessible during this research). [OTHER-PLATFORM-PRIMARY for photo count and lighting advice; SECONDARY/UNVERIFIED for the "2-3x faster" stat] https://blog.mercari.com/us/5-photography-tips-for-making-more-sales (photo/lighting guidance); stat repeated at e.g. https://merchtitans.com/blog/how-to-sell-on-mercari-guide
- **Carousell**: official help center confirms up to 10 photos per listing and recommends showing different angles, defects, box, and receipt if available; official blog states a paid "Bump" feature gives a 230% increase in views (a paid-boost stat, not an organic photo-count stat), and explicitly frames performance diagnosis around each seller's own Listing Insights dashboard rather than publishing a universal photo-count benchmark. [OTHER-PLATFORM-PRIMARY] https://support.carousell.com/hc/en-us/articles/360000098588-Photo-Tips ; https://blog.carousell.com/carousell-pro-tips/selling-guide/carousell-listing-insights/
- **Etsy**: Seller Help documents up to 10 photos plus 1 video (5–15 sec, up to 100MB) per listing, recommends minimum 2000×2000 px images at a 4:5 aspect ratio (Etsy's search-thumbnail ratio), and provides a 500-character alt-text field per photo for accessibility/search. No specific conversion-lift percentage tied to photo count is published by Etsy in the pages reviewed. [OTHER-PLATFORM-PRIMARY] https://help.etsy.com/hc/en-us/articles/115015663347-Requirements-and-Best-Practices-for-Images-in-Your-Etsy-Shop

### Description length
No primary source (Meta or cross-platform) reviewed in this research publishes a quantified relationship between description length and sell-through or conversion rate. Meta's Catalog rule only requires the description be "longer than the title" as a best practice, without justifying that with performance data. [META-OFFICIAL, no data cited] https://www.facebook.com/business/help/2302017289821154. Etsy explicitly states it has no strict published cap and focuses on "useful product details" over a character target, again without publishing conversion data. [OTHER-PLATFORM-PRIMARY, no data cited] https://help.etsy.com/hc/en-us/articles/115015663347-Requirements-and-Best-Practices-for-Images-in-Your-Etsy-Shop

### Price in image
No primary source found publishing performance data on price-in-image; the only documented position is prohibitive, not data-driven: Meta's ad-image guidance forbids price call-outs/promo codes as a policy rule, not because of a cited conversion study. [META-OFFICIAL, no data cited] https://www.facebook.com/business/help/376859690417674

### Video
No primary source (Meta or cross-platform) reviewed in this research publishes conversion/sell-through data tied to adding video to a listing. eBay documents video as an available listing feature without citing performance data on its own help pages. [OTHER-PLATFORM-PRIMARY, no data cited] https://export.ebay.com/en/listings/how-optimize-your-listings/adding-a-video-to-your-listing

## Category-specific required attributes

- **Vehicles**: Meta's help center documents that sellers must select Year, Make, Model, and Mileage, and choose Automatic/Manual transmission when listing a vehicle; Meta separately integrates Kelley Blue Book to suggest a price range. The precise complete field list (trim, body style, fuel type, exterior/interior color, VIN, condition enum) is reported consistently across secondary guides but could not be confirmed verbatim against Meta's primary vehicle-listing help pages, which returned only page titles during automated fetch attempts in this research. [META-OFFICIAL page exists for the core Year/Make/Model/Mileage/transmission fields — search-engine-summarized, not directly fetched; SECONDARY/UNVERIFIED for the extended field list] https://www.facebook.com/business/help/143800203032002 ; https://www.facebook.com/business/help/442276120199473
- **Property/rentals**: Meta changed rental-listing rules so listings must be created from a personal profile rather than a Facebook Page (effective Jan 30, 2023, per third-party trade coverage, not independently re-verified against a dated Meta page in this research). Required/recommended fields reported: price, address, bedroom/bathroom count, square footage, lease terms, available date, amenities (heating/cooling, parking, laundry, pet policy). [SECONDARY/UNVERIFIED — could not confirm the exact field list against a primary Meta rentals help page in this research] https://www.rentecdirect.com/blog/how-to-list-a-rental-property-on-facebook-marketplace/
- **Electronics**: No category-specific *required* field list is documented on a primary Meta page found in this research. Meta's general Catalog fields (brand, condition, description) apply; Commerce Manager reportedly offers category-specific attribute templates (e.g., an "Electronics" template) but the specific required attributes for electronics were not independently confirmed. [SECONDARY/UNVERIFIED]
- **Clothing**: Structured attributes confirmed at the Catalog level (see Structured Attributes section): `size`, `color`, `material`, `brand`, `age_group`, `gender`, `pattern`, plus size charts. [META-OFFICIAL] https://developers.facebook.com/docs/commerce-platform/catalog/fields/ ; https://www.facebook.com/business/help/262477299039517. Whether the native peer-to-peer Marketplace clothing listing form exposes identical fields was not independently confirmed.

## Confidence & Gaps

**High confidence (directly fetched primary Meta text):**
- The 5-value item condition list and definitions (New / Used (like new) / Used (good) / Used (fair) / Refurbished).
- Catalog description length (30–9,999 chars) and formatting rules.
- Catalog title length (200 char max, ~65 recommended) and `condition`/`brand`/`size`/`color`/`material`/`availability` field definitions.
- Meta's stated ability to auto-enhance photos/video and auto-select the cover photo.
- eBay's own 4.5%-more-likely-to-sell photo-quality statistic (from eBay's photo-tips page).
- Etsy's and Carousell's official photo-count and image-spec guidance.

**Medium confidence (page located and topically correct, but exact verbatim text not retrievable — automated fetch returned only titles/redirects/login walls):**
- Vehicle condition taxonomy and exact vehicle listing required-field list — Meta's own pages exist (`business/help/979881538883930`, `442276120199473`, `143800203032002`) but render client-side JS content that this research's fetch tools could not extract; only search-engine summaries were obtained, which risk paraphrase drift or conflation with Kelley Blue Book's own (separate) condition scale.
- Rental/property listing required fields and the 2023 personal-profile-only rule — sourced to a property-management vendor blog, not a dated primary Meta announcement.

**Low confidence / unverified (repeated across many SEO/reseller blogs, not confirmed against any primary page):**
- "10 photos" as the native Marketplace photo cap.
- "100-character" native listing title limit.
- Specific pixel/file-size numbers (1200×1200 recommended, 30MB max) for native Marketplace photos as opposed to the Catalog feed's documented 500×500 min / 8MB max.
- Mercari's "5+ photos sell 2-3x faster" statistic.
- Any explicit primary-source data (from Meta or any marketplace) quantifying the effect of description length, price-in-image, or video on conversion/sell-through — none was found; only qualitative/policy statements exist.

**Outright gap:**
- No primary source found stating whether the native P2P Marketplace listing form's category-specific attributes (vehicles, electronics, clothing, property) are technically the same structured-attribute schema as the Commerce Manager Catalog, or a separate internal schema. This distinction matters for any tooling that assumes Catalog field names/limits apply 1:1 to consumer listings.
- No primary source (Meta or otherwise) was found that publishes a controlled/causal study of description length or video presence on sell-through; all such claims found during this research were either policy statements (no data) or unverified blog claims.
