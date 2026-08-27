# Ranking & Visibility

Research date: 2026-08-27. Scope: how Facebook Marketplace decides which listings are shown (search ranking, feed/recommendation surfacing), based on Meta's own official sources first, secondary sources labeled and separated.

Legend:
- **[META-OFFICIAL]** = direct claim from a facebook.com/help, facebook.com/business/help, about.fb.com, engineering.fb.com, ai.meta.com, or developers.facebook.com page (fetched and quoted/paraphrased below with URL).
- **[META-RESEARCH]** = a technical paper authored by Meta/Facebook researchers, published on arXiv (not a Meta-owned domain, but Meta's own published research on the exact system in question). Treated as strong-but-once-removed primary evidence.
- **SECONDARY / UNVERIFIED** = seller forums, SEO blogs, resale-tool marketing sites, community posts. Never blended with the above without this label.

---

## 1. Signals affecting search ranking and feed/recommendation surfacing

**[META-OFFICIAL]**
- Meta's Marketplace Insights help page states: "Your shipping performance and history might impact the distribution of your listings on Marketplace." (https://www.facebook.com/help/937527940168419) — this is the clearest direct Meta statement that a specific, named signal (shipping performance/history) affects how widely a listing is shown.
- Meta does not publish a list of ranking signals or their weights anywhere in its Marketplace seller Help Center. The general "Selling on Marketplace" hub page (https://www.facebook.com/help/153832041692242) links only to listing-creation, policy, badge, and dispute-resolution articles — none titled or framed as "how ranking works."

**[META-RESEARCH]**
- Meta's 2018 engineering blog post "Facebook Marketplace, powered by AI" describes the underlying ML architecture (not a public seller-facing policy, but a technical account of what the system actually optimizes for):
  - A retrieval stage uses FAISS (Facebook AI similarity search) to narrow millions of products to a candidate set by embedding similarity between buyer query/profile and product data. (https://engineering.fb.com/2018/10/02/ml-applications/under-the-hood-facebook-marketplace-powered-by-artificial-intelligence/)
  - A final ranking stage uses "a Sparse Neural Network model with online training" that incorporates "real-time signals (such as the counters of the real-time events that happened on each of the products)" — i.e., live engagement counters feed ranking. (same URL)
  - Buyer-side personalization embeddings are built from "demographic information from the person's Facebook profile and keywords from searches within Marketplace." (same URL)
  - A separate multimodal product model combines a text embedding with a 50-layer ResNet image encoder, and computes cosine similarity between buyer and product embeddings as a ranking score. (same URL)
- Meta's 2023 research paper "Que2Engage: Embedding-based Retrieval for Relevant and Engaging Products at Facebook Marketplace" (published by Meta researchers on arXiv) states Marketplace search is a multi-stage system where "retrieval focuses on matching search queries with relevant products, while search ranking puts more emphasis on contextual signals to up-rank the more engaging products," and that end-to-end searcher experience is explicitly a function of both **relevance** and **engagement**. (https://arxiv.org/abs/2302.11052) The abstract does not enumerate which specific engagement events (clicks vs. messages vs. saves vs. purchases) are used or how they are weighted.

**Not documented / explicitly missing from official sources:** recency, distance/location radius, price, and category as discrete named ranking factors are NOT stated in any fetched Meta help page or blog post. Recency is addressed only indirectly through the renewal mechanic (see §3), which is framed as a user action rather than a disclosed ranking signal. **Meta does not publicly document the relative weighting of any of these signals against one another.**

**SECONDARY / UNVERIFIED**
- Numerous seller blogs and forums claim Marketplace ranks "active" or fast-responding sellers higher and that engagement (views/saves/messages) directly boosts a listing's rank (e.g., https://themarketingsquad.com/does-facebook-response-rate-and-time-matter/, general SEO-blog commentary). These are plausible given the Que2Engage abstract's "engagement" framing, but no Meta source directly confirms response rate or badges as a ranking input — see §5.

---

## 2. Text matching: title vs. description weighting, keyword guidance

**[META-OFFICIAL]**
- No fetched Meta help page states that title text is weighted more heavily than description text in Marketplace search matching, or gives any explicit guidance on keyword density/placement for search purposes. The "Selling on Marketplace" and "Sell something on Facebook Marketplace" help pages (https://www.facebook.com/help/153832041692242, https://www.facebook.com/help/561376580709359) describe only the listing-creation UI flow (add photos, enter item info, set price) with no search-optimization guidance.
- The Meta Business Help Center's Catalog field specs (a *different* product surface — the Commerce/Catalog API used by businesses feeding Shops/Marketplace, not the peer-to-peer "sell something" flow) do give structural guidance: Meta's developer docs state a catalog `title` field has a 200-character technical limit but recommends "a maximum of 65 to avoid longer titles being cut off," and a catalog `description` field allows up to 9,999 characters and should contain "specific and unique product features, such as material or color" and remain "different than the title." (https://developers.facebook.com/docs/commerce-platform/catalog/fields/) This is catalog-API guidance, not a documented statement about P2P Marketplace search-ranking weight of title vs. description text.

**Not documented:** Whether Marketplace's embedding-based text matching (per the Que2Engage/engineering.fb.com research above) treats title and description asymmetrically is not stated anywhere Meta publishes. **Meta does not publicly document how title text vs. description text is weighted in search matching or ranking.**

**SECONDARY / UNVERIFIED**
- Widespread seller-blog claims that titles should be "keyword rich," repeat likely search terms, and are weighted more heavily than descriptions (e.g., blog.vendoo.co, various "how to sell on Facebook Marketplace" guides surfaced in search). Unverified by Meta.

---

## 3. Listing recency and the "renew" mechanic

**[META-OFFICIAL]**
- Meta's own "Edit your Facebook Marketplace listing" help page (https://www.facebook.com/help/514314075439323) covers editing item details, deleting listings, and marking items sold/pending, but in the fetched content **does not mention a "renew" feature, how often it can be used, or any effect on ranking/visibility.**
- A separate official page exists titled "How to boost Facebook Marketplace listings" (https://m.facebook.com/help/304288543633513), but the fetched content was a stub/redirect page with no substantive text (only "this feature isn't available on Basic Mobile Browser" navigation copy). It could not be used to verify renewal mechanics.
- **No Meta help page fetched in this research states the exact renewal cadence (e.g., "every 7 days"), a numeric cap on renewals, or exactly what renewing changes about a listing's position.** This is a documentation gap, not a confirmed absence — Meta may document this on a page not surfaced by search/fetch in this session (e.g., inside the live in-app UI itself, which is not crawlable).

**SECONDARY / UNVERIFIED**
- Seller blogs/forums (e.g., blog.vendoo.co "Facebook Marketplace Delete and Relist," closo.co, socialoapp.com) commonly claim: a listing becomes eligible to "Renew" after ~7 days unsold; renewing "refreshes its position in search results and the newsfeed"; some sources claim a cap of "up to five" renewals; renewing preserves the listing's accumulated views/saves/history. **None of these specific numbers (7-day eligibility window, 5-renewal cap) were found on any facebook.com/help or facebook.com/business/help page during this research** — treat them as folklore until confirmed against Meta's own UI copy or a help page.

---

## 4. Relisting (delete + re-create) vs. renewing

**[META-OFFICIAL]**
- No Meta help page fetched in this research directly compares "delete and relist" to "renew," recommends one over the other, or documents that a brand-new listing (new listing ID) receives different initial visibility treatment than a renewed one. This comparison does not appear to be an officially documented topic at all.

**SECONDARY / UNVERIFIED**
- Seller-strategy blogs claim: deleting and re-creating a listing gives it a "new Listing ID and URL" so it "re-enters Marketplace as fresh inventory" with "stronger initial visibility" than a renewal, at the cost of losing accumulated views/saves attached to the old listing (blog.vendoo.co, closo.co). Some sources describe this as workaround behavior for "zombie" (stale, unsold) listings once renewal stops producing engagement. **This entire comparison is unverified by Meta** — it is inferred seller folklore about how the system likely behaves, not a documented mechanic.

---

## 5. "Response rate" / "Very Responsive" badge

**[META-OFFICIAL]**
- Meta's official "Get seller badges on Facebook" help page (https://www.facebook.com/help/1684084458520855) confirms Marketplace has (as of this research) **five named seller badges**: Top Seller, Top Category Seller, Very Responsive, Highly Rated, and Top Shipper. The page states: "Seller badges help us and our community identify sellers with good selling history on Facebook." Each badge has a "How do I get the [X] badge?" FAQ entry, but the fetched page content did not render the collapsed FAQ answer text (likely a JS accordion not captured by static fetch), so **exact numeric thresholds for each badge could not be confirmed directly from this page.**
- A separate official page, "Tips for learning about a seller on Facebook Marketplace" (https://www.facebook.com/help/2912273018986831), confirms buyers are told to look for badges including "Very Responsive, Reliable Shipper, Super Seller or Highly Rated" on a seller's Marketplace profile, and that "Positive ratings are considered 4-5 stars. Negative ratings are considered 3 stars or below." Badge naming is inconsistent across Meta's own pages (e.g., "Top Shipper" vs. "Reliable Shipper" vs. "Super Seller"), suggesting these have changed over time or vary by page/locale — flagging as a real ambiguity in Meta's own documentation, not an error in this research.
- **No Meta page fetched in this research states that the Very Responsive badge, or response rate generally, affects Marketplace search ranking or feed distribution.** The only officially documented distribution-affecting signal found is shipping performance (§1), not responsiveness.
- A related, separate Meta Business Help Center page, "About the Very Responsive Badge for Facebook Messenger" (https://www.facebook.com/business/help/201893553741970), documents a **Page-level Messenger badge** (90%+ response rate, under-15-minute response time) — this is for Facebook Pages/Messenger, a different product from an individual Marketplace seller profile, and should not be conflated with a Marketplace-specific response-rate badge.

**SECONDARY / UNVERIFIED**
- Multiple seller-blog sources (tools.oneshop.com, e-marketingassociates.com, edesk.com) state the Marketplace "Very Responsive" badge specifically requires responding to "most messages" within the last 30 days "within one hour," and that a "Highly Rated"/"Community Recommended" badge requires either 4+ reviews averaging 4–5 stars in the last 30 days, or at least 3 ratings with 75%+ positive. **These specific numeric thresholds are not confirmed on any Meta-owned page fetched in this research** (the official page's FAQ answers were not retrievable as static text). Claims that any badge affects search ranking/visibility are likewise unverified — they are seller inference, not a Meta statement.

---

## 6. Category selection and structured attributes (condition, brand, size)

**[META-OFFICIAL]**
- Meta's "Meanings of item conditions on Facebook Marketplace" page (https://www.facebook.com/help/2004996079797091) defines condition values sellers can select (New, Used (like new), Used (good), Used (fair), Refurbished) with exact wording, e.g., New = "Brand new, never worn or used, undamaged item." The fetched content states only that "buyers can see it on the listing" — **it does not state that condition selection affects search filtering, discoverability, or ranking.**
- The general Marketplace hub page (https://www.facebook.com/help/1713241952104830) confirms buyers can find items "by searching for a specific item or browsing categories," confirming category browsing exists as a discovery surface, but does not describe how a seller's category choice affects whether/how often a listing surfaces.
- On the separate Commerce/Catalog API (developers.facebook.com, used by Shops/business catalogs, not the individual "sell something" P2P flow), Meta documents structured fields including `condition` (values: new, refurbished, used), `brand` (max 100 characters), `google_product_category`, and `product_type`, explicitly stating the Google product category should be "the most specific... possible" and that it "influences tax calculations and eligibility determinations." (https://developers.facebook.com/docs/commerce-platform/catalog/fields/) This confirms structured attributes are functionally used by Meta's systems for at least tax/eligibility logic in the catalog product; it does not confirm a discoverability effect for individual P2P Marketplace listings specifically.

**Not documented:** Meta does not state anywhere in the fetched official sources that choosing a more specific category or filling in more structured attributes (for a personal "sell something" listing, as opposed to a business catalog) improves discoverability or ranking. This is a plausible mechanism (categories and attributes are literally the retrieval/filter surface described in the Que2Engage/engineering.fb.com research) but Meta does not explicitly connect the dots for sellers in help documentation.

**SECONDARY / UNVERIFIED**
- SEO/reseller blogs assert that picking "Miscellaneous" or vague categories suppresses discovery and that filling in every optional attribute (brand, size, etc.) "helps you show up in filtered searches." Plausible but unverified by Meta for the P2P listing flow.

---

## 7. Documented limits (photos, title/description length, active listings, posting frequency, cross-posting)

**[META-OFFICIAL]**
- Meta's own "Facebook Marketplace listing limits" help page (https://www.facebook.com/help/811082570742714) exists and confirms posting-frequency limits are a real, Meta-documented mechanic that **vary by country/market**. The only concrete figure retrievable from the fetched (geolocation-served, Philippines-market) version of this page was: "In the Philippines, you can post up to 10 listings per week on Facebook Marketplace." The page gave no other country's figures, no photo-count limit, no title/description character limit, no active-listing cap, and no cross-posting rule in the content actually retrieved — these may exist elsewhere on the same page for other markets/locales that this research could not access (the page appears to serve region-specific content and repeated attempts, including an explicit `en_US` locale parameter, kept returning the Philippines-specific text).
- For the separate Commerce/Catalog API (business catalogs, not personal listings): Meta's developer docs state a catalog title field has a 200-character hard limit (65 recommended) and a description field allows up to 9,999 characters. (https://developers.facebook.com/docs/commerce-platform/catalog/fields/) These figures apply to the Catalog API product, not confirmed to apply to the personal "sell something" listing form.
- No official page fetched in this research states a maximum photo count for a personal listing, a maximum number of simultaneously active personal listings per account, or explicit rules/limits for cross-posting a listing into Buy/Sell groups.

**SECONDARY / UNVERIFIED**
- Seller forums/blogs commonly cite: up to 10 photos per personal listing; a ~100-character title limit for the personal listing form; new accounts capped at very low active-listing counts (sometimes cited as 1) that rise with selling history, up to commonly-cited ceilings of 50–100 active listings; and cross-posting caps of roughly 3 groups shown in the sharing UI at a time. **None of these numbers could be confirmed against an official Meta page in this research** — they are treated here strictly as unverified secondary claims.

---

## 8. Marketplace Insights / seller-facing analytics

**[META-OFFICIAL]**
- Meta's "Insights on Facebook Marketplace" help page (https://www.facebook.com/help/937527940168419) documents a real, named seller analytics feature with four specific metrics: **"Clicks on listings," "Listing saves," "Listing shares,"** and **"Marketplace profile follows."** The page states: "Insights provide information to help you understand how your listings are performing on Marketplace." It also contains the direct statement quoted in §1: "Your shipping performance and history might impact the distribution of your listings on Marketplace."
- Meta's "Access Insights on Facebook Marketplace" help page (https://www.facebook.com/help/265775098821464) documents the access path (Feed → Marketplace → Selling → Seller Dashboard, or per-listing via Your listings → the listing) and confirms Insights can be filtered "by the last 7 days, last 14 days, or last 30 days."
- Meta Newsroom's announcement of the new standalone "Seller" app for Marketplace sellers (launched for US users July 24, 2026) states the app surfaces "performance data like views, clicks, message threads, and sold listings to price competitively and make smarter decisions about your inventory," alongside AI-assisted listing creation ("Upload photos and Meta AI will fill in the details like title, description, price suggestion, and category") and unified listing/inbox management. (https://about.fb.com/news/2026/07/introducing-seller-app-facebook-marketplace/) Note this Newsroom article's metric list ("views, clicks, message threads, sold listings") differs slightly from the older Insights help page's list ("clicks, saves, shares, follows") — both are genuine Meta statements but from different pages/eras and are not fully reconciled in Meta's own documentation.

**Not documented:** Meta does not state, on any page fetched here, how (or whether) a seller's own Insights numbers (views/clicks/saves) feed back into that listing's own future ranking — Insights are presented purely as after-the-fact seller-facing reporting, not as a documented ranking input.

---

## Confidence & Gaps

**High confidence (directly quoted from Meta-owned pages):**
- The existence and metric list of Marketplace Insights, and the statement that shipping performance/history can impact listing distribution (https://www.facebook.com/help/937527940168419).
- The existence of five named Marketplace seller badges (https://www.facebook.com/help/1684084458520855) and the ratings scale definition (https://www.facebook.com/help/2912273018986831).
- The existence of a country-varying posting-frequency limit mechanic, with a Philippines-specific figure of 10 listings/week (https://www.facebook.com/help/811082570742714).
- Meta's own published ML architecture for Marketplace retrieval/ranking circa 2018 (FAISS retrieval + sparse neural-net ranking with real-time engagement counters) and circa 2023 (Que2Engage: relevance + engagement as the two named optimization axes).
- Catalog API field definitions and character limits (developers.facebook.com) — but these apply to the Commerce/Catalog (Shops/business) product, not confirmed to apply to personal P2P listings.

**Explicitly NOT documented by Meta (confirmed absence in fetched sources, not just "we didn't look"):**
- No public ranking-signal weighting/formula for Marketplace search or feed — Meta does not publish this, consistent with typical practice for anti-gaming reasons.
- No official confirmation that response rate, the Very Responsive badge, or any seller badge affects search ranking/visibility (only shipping performance is officially tied to "distribution").
- No official description of what exactly the "renew" action does mechanically, its eligibility window, or any renewal cap/limit.
- No official comparison of delete-and-relist vs. renew, or guidance on which is better.
- No official statement connecting category/attribute completeness to discoverability for personal listings (only inferable from the general architecture research, and explicit only for tax/eligibility in the Catalog API).
- No official photo-count limit, personal-listing title/description character limit, active-listing cap, or Buy/Sell group cross-posting rule was located.

**Gaps caused by this research session's access limitations (may exist on Meta's site but were not reachable):**
- The "Marketplace listing limits" page (https://www.facebook.com/help/811082570742714) appears to serve region-specific content based on the fetch tool's apparent locale/IP (repeatedly returned Philippines-specific text even with an explicit `en_US` locale parameter). Its content for the US or other markets, and any photo/title/description/active-listing figures it may contain for other regions, could not be retrieved.
- The seller-badge FAQ page's per-badge answer text (exact thresholds for Very Responsive, Highly Rated, Top Seller, Top Category Seller, Top Shipper) rendered as collapsed accordion content not present in the static fetch — thresholds commonly cited by seller blogs (e.g., "90% response rate," "respond within 1 hour," "75% positive of 3+ ratings") remain **unverified against Meta's own page** despite the page structure confirming these badges exist.
- "How to boost Facebook Marketplace listings" (https://m.facebook.com/help/304288543633513) returned only a device-availability stub in this session; its substantive content (if any) on renewal/boosting mechanics was not retrieved.

**Single most important gap:** Meta does not publicly document the renewal mechanic's actual rules (eligibility timing, frequency cap, or exact visibility effect), nor does it document whether responsiveness/badges influence ranking at all — these are exactly the two mechanics sellers most want to know about for a seller-facing knowledge base, and both are currently sourced only from unverified seller folklore, not from any Meta-owned page located in this research.
