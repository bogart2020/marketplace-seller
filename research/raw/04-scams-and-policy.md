# Seller Scams & Commerce Policy

Defensive research for a legitimate Facebook Marketplace seller, current as of 2026. Two parts: (A) scams targeting sellers, (B) Meta Commerce Policy compliance. Every claim is tagged: [META-OFFICIAL] = Meta's own policy/help/safety/transparency pages, [GOV] = government/consumer-protection primary source, [SECONDARY] = everything else (blogs, security vendors, news aggregators, forum answers).

---

## PART A — Scams Targeting Sellers

### A1. General framing from official sources

- Meta's own Marketplace safety guidance: sellers should verify payment by checking their own account balance/transaction history directly — "Always check your account to confirm payment, even if they send you a screenshot showing the transaction." Off-platform contact requests ("phone or email, especially early on") are flagged as a red flag; links requiring login with personal info/passwords are called an "immediate red flag." [META-OFFICIAL] https://www.meta.com/safety/scam-protection-center/marketplace-trust-safety/
- Meta's general scam-prevention hub: recommends secure payment methods with buyer/seller protection (Meta Pay, PayPal), warns that Zelle/Venmo/Cash App are "only safe for sending money to people you know and trust" since payments are typically irreversible, and that gift-card payment requests should be reported immediately. [META-OFFICIAL] https://www.meta.com/safety/scam-prevention/spot-scams/ , https://www.meta.com/help/policies/1273750300141929/
- FTC's dedicated seller-side alert covers the same three flagship scams sellers face: fake mobile-payment notifications, overpayment-by-check, and fake verification-code requests, and recommends selling locally for cash where possible and checking a marketplace's own seller protections when shipping. [GOV] https://consumer.ftc.gov/consumer-alerts/2022/07/selling-stuff-online-heres-how-avoid-scam

### A2. Verification code / "Google Voice code" scam

A scammer messages as a buyer, asks for your phone number "to verify you're a real person," then sends you an SMS with a Google Voice (or similar) verification code and asks you to read it back. If you comply, they use the code to register a Google Voice number tied to your phone, which they then use to run scams on others while hiding their identity — and can potentially access other accounts of yours. [GOV] https://consumer.ftc.gov/consumer-alerts/2021/10/google-voice-scam-how-verification-code-scam-works-how-avoid-it

**Tell:** Buyer asks for your phone number "to verify you're not a bot/scammer," then immediately asks you to read back a code that just arrived by text. Never share a verification code with anyone you contacted for the first time — legitimate buyers never need one from you.

### A3. Overpayment + "refund the difference"

Buyer sends a check (or, in modern variants, a mobile-payment "confirmation") for more than the agreed price and asks the seller to wire back, gift-card, or Zelle the difference. The original payment is later reversed/bounces, leaving the seller out both the item and the "refunded" difference. FTC: "Never accept a check for more than your selling price, and never agree to wire back funds to a buyer." [GOV] https://www.ftc.gov/news-events/news/press-releases/2004/12/ftc-warns-consumers-about-check-overpayment-scams

**Tell:** Payment (check or claimed transfer) arrives for more than your asking price, paired with a request to send back the "extra" via wire, gift card, or crypto before the original payment has actually cleared/settled in your account.

### A4. Fake payment-confirmation screenshots (general, non-PH)

A buyer claims to have paid via a payment app, then sends a screenshot or a fake "payment notification" email instead of the money actually landing. FTC groups this as one of the three main seller-targeted scam types. [GOV] https://consumer.ftc.gov/consumer-alerts/2022/07/selling-stuff-online-heres-how-avoid-scam

**Tell:** Any "proof of payment" that is a screenshot, PDF, or emailed receipt rather than money visible in your own account/app balance.

### A5. Zelle / PayPal "business account upgrade" scam

Buyer says they've paid via Zelle and asks for the seller's email. Seller then receives a spoofed email (impersonating Zelle) claiming the buyer's payment is "held" until the seller upgrades to a Zelle business account for a fee. The "buyer" then claims they already paid the fee too and asks the seller to refund them for it — the seller loses the refunded "fee" and nothing was ever actually paid. Key fact: Zelle does not hold payments, charge upgrade fees, or require a business profile to release money. [SECONDARY] https://www.aura.com/learn/zelle-scams , https://paymentcloudinc.com/blog/zelle-business-account-scams/

**Tell:** An email claiming to be from your payment provider says you must pay a fee or "upgrade" to receive funds already sent, and/or the buyer independently pressures you to refund a fee. Verify directly with the payment provider's official app/site/support — never via a link in the email.

### A6. Phishing links posing as payment confirmation

Scammers send a link claiming to show a payment confirmation, shipping-label status, or "you've received money" notice; the link leads to a fake login page designed to harvest payment-app or bank credentials. Meta explicitly calls out login-requiring links as "an immediate red flag." [META-OFFICIAL] https://www.meta.com/safety/scam-protection-center/marketplace-trust-safety/

**Tell:** Any message-embedded link asking you to "log in to confirm/view" a payment. Go directly to the official app/site instead of clicking through.

### A7. Courier / shipping-label scams ("I'll send my own label/courier")

A "buyer" insists on shipping via their own pre-made label or private courier rather than letting the seller arrange shipping. The label may be stolen/fraudulent or the address gets changed after pickup so the package is redirected; the buyer then denies receiving it and reverses or never sends payment — seller loses both item and payment. [SECONDARY] https://blog.gridinsoft.com/facebook-marketplace-scams/ , https://www.omniwatch.com/blog/facebook-marketplace-scams/

**Tell:** Buyer supplies their own shipping label/courier instead of paying you and letting you ship, especially for a large/expensive item; legitimate buyers do not have private couriers on standby for a Marketplace purchase.

### A8. "I'll send my agent/driver to pick it up" (proxy pickup)

Buyer claims they cannot meet in person and will send a representative (relative, "driver," employee) to collect the item instead — commonly used as a stall/setup tactic feeding into overpayment or fake-check schemes, and it removes the seller's ability to verify the real buyer's identity or get paid face-to-face. [SECONDARY] https://www.omniwatch.com/blog/facebook-marketplace-scams/ , https://us.norton.com/blog/online-scams/facebook-marketplace

**Tell:** Buyer avoids meeting you personally and proposes a third-party pickup, often combined with urgency ("need it tonight," "leaving the country tomorrow") and payment by check/money order for more than the asking price.

### A9. QR-code payment scams

FTC and FBI/IC3 warn of QR codes used to redirect victims to fraudulent payment pages, malware downloads, or crypto-ATM scams; a scammer's own embedded QR code can silently substitute their payment address for yours. [GOV] https://www.ftc.gov (via PCWorld summary of FTC alert) — primary FTC alert referenced at https://consumer.ftc.gov/new-crypto-payment-scam-alert ; FBI/IC3 advisory: https://www.ic3.gov/PSA/2025/PSA250731

**Tell:** A buyer sends/shows you a QR code to "complete payment" rather than paying through the platform or app you control; inspect any resulting URL for misspellings before entering anything, and prefer generating your own receiving QR code rather than scanning one someone else hands you.

### A10. Philippines-specific: GCash fake payment screenshots

Widely reported pattern (amplified by AI photo-editing tools) where a "buyer" sends a convincing but fabricated GCash "payment successful" screenshot/SMS as proof of payment; the seller ships or hands over the item before checking their actual GCash balance, and no money ever arrives. GCash's own transaction history cannot be user-edited, but a screenshot of it can be faked trivially. This is prosecutable as Estafa under Philippine law. [SECONDARY] https://techpipino.com/fake-receipt-scams-how-ai-is-fueling-gcash-scams-in-the-philippines/ ; legal-remedies overview [SECONDARY] https://www.lawyer-philippines.com/articles/how-to-trace-and-address-a-fake-payment-received-via-gcash-in-the-philippines

**Tell:** "Proof of payment" is a screenshot/forwarded SMS, not money you can see and confirm inside your own GCash app balance or transaction history right now. Never release goods on a screenshot alone; if possible, have the buyer pay via a QR code you generate yourself rather than a number/name you can't independently confirm.

### A11. Philippines-specific: COD (cash-on-delivery) scams against sellers/couriers

Reported pattern where a fraudulent "buyer" books a COD order (often to a different delivery address or under a false name), and either the courier or the seller ends up unpaid or holding a returned/undeliverable parcel; a related consumer-facing variant is boxes containing wrong/low-value items instead of what was ordered. DTI has urged shifting toward online/prepaid payment specifically to reduce fake COD bookings (context: food delivery, but cited as a general COD fraud mitigation), and DTI mediates seller/buyer commerce complaints under RA 7394 (Consumer Act), with fines up to ₱300,000–₱3,000,000 for violations depending on the provision. [GOV] https://newsinfo.inquirer.net/1419459/dti-urges-online-payment-to-avoid-fake-food-delivery-bookings (reporting on a DTI advisory — treat the underlying DTI statement as primary, this article as the accessible record) ; courier-side advisory [SECONDARY] https://www.ninjavan.co/en-ph/parcel-scams-advisory

**Tell:** Buyer insists on COD to an address that doesn't match their stated location, changes the delivery address last-minute, or is unreachable at delivery time — all raise the risk of an uncollected/fraudulent COD order.

**Note on BSP/PNP-ACG official advisories:** BSP's confirmed official warnings (2026) focus on fraudsters impersonating BSP itself with fake documents/logos/OTP-renewal requests to extract banking credentials — not a Marketplace-seller-specific advisory, but confirms the general "never share OTPs/credentials, verify independently" doctrine BSP applies across all digital-payment fraud. [GOV] https://www.gmanetwork.com/news/money/economy/970508/bsp-warns-of-scams-using-fake-documents-logos-and-signature/story/ (reporting on BSP statement) BSP also coordinates with GCash on merchant verification and flags fake QR codes, impersonation, fake seller activity, and fraudulent payment screenshots as adapted digital-channel scam tactics. [GOV/SECONDARY-mixed] https://www.pna.gov.ph/articles/1274949
PNP Anti-Cybercrime Group's confirmed official advisory in this research pass was about scammers impersonating PNP-ACG itself (fake Telegram "recovery agents" demanding payment) — genuinely useful ("PNP-ACG does not accept payments, does not process online case filings, and does not promise return of scammed money") but not a GCash-scam-specific bulletin. Report channels: hotline (02) 8414-1560 / 0998-598-8116, email acg@pnp.gov.ph. [GOV] https://bitpinas.com/regulation/pnp-acg-telegram/ (reporting on PNP-ACG statement)

I was not able to locate, within this pass, a single BSP or PNP-ACG bulletin titled specifically "GCash seller scam advisory" — see Confidence & Gaps.

### A12. Meta's stated payment-verification and protection guidance

- Verify payment in your own account, not via screenshot. [META-OFFICIAL] https://www.meta.com/safety/scam-protection-center/marketplace-trust-safety/
- The safest built-in payment method Meta names is Meta Pay for onsite-checkout transactions. [SECONDARY summary of META-OFFICIAL guidance] https://onerep.com/blog/facebook-marketplace-scams-how-to-spot-and-avoid-them — the underlying Meta Pay claim should be treated as directionally accurate but I could not independently re-confirm the exact phrase from a Meta-owned page in this pass; flagged in Gaps.
- **Seller Protection / Purchase Protection (official Merchant Policies)**: Coverage exists **only for shipped items sold through Marketplace's onsite checkout**, using **Meta-provided prepaid shipping labels**, on orders of **$500 or less**, and is currently **US-only**. Requirements: valid tracking on every order, ship within 7 calendar days of sale or Meta may auto-cancel the order, and compliance with the Onsite Checkout Payments Terms, Community Standards, and Commerce Product Merchant Agreement. Covered scenarios include lost/stolen/delayed packages (if shipped on time with valid tracking to the correct address), "item not as described" claims (if seller responds within 2 days), and unauthorized-chargeback/return-abuse protection. Excluded categories include perishables, vehicles, precious metals/gemstones, and antiques/collectibles. [META-OFFICIAL] https://www.facebook.com/legal/merchant_policies
- **Local pickup has no equivalent official seller protection** — the Merchant Policies page addresses shipped/onsite-checkout transactions only; nothing in Meta's official Seller Protection policy covers cash/local-pickup deals. This is consistent with why Meta's general safety advice for local meetups is about physical/personal safety rather than payment-recovery guarantees (see A13).

### A13. Official safe-meetup guidance

Meta's own consumer advice funnels toward using secure payment methods and meeting safely, but the specific "meet at a police station safe-exchange zone" recommendation in this research pass is documented primarily via US local-police-department programs and news coverage, not a Meta-branded page. Multiple police departments (reported via local news) operate camera-monitored "Safe Exchange Zones," often at the station itself, for online marketplace transactions — recommended especially for higher-value items, during daylight, ideally not alone. [SECONDARY, reporting on GOV/local-police programs] https://www.nbcdfw.com/news/local/fatal-facebook-marketplace-police-safe-exchange-zones/3799642/ , https://cbsnews.com/amp/detroit/news/police-stations-become-safe-havens-for-online-marketplaces
I did not find a Meta-published page that names "police station" specifically as its recommended meetup location — see Confidence & Gaps.

---

## PART B — Meta Commerce Policy Compliance

### B1. Official prohibited-content categories (Commerce Policies)

Fetched directly from Meta's official Commerce Policies page. Meta states these policies apply to **any attempt to buy, sell, trade, or exchange (even for free) products or services on Facebook, Instagram, WhatsApp, or Messenger**, and rely on both Community Standards and this dedicated Commerce Policy layer. [META-OFFICIAL] https://www.facebook.com/policies_center/commerce

The prohibited-content categories, as officially listed:

1. Community Standards violations (commerce content must not violate Facebook's Community Standards)
2. Adult content and sexually positioned products
3. Alcohol
4. Body parts and fluids
5. Digital media and electronic devices used to enable unauthorized streaming/access
6. Discrimination (no discriminatory commerce content based on protected characteristics, including in Messenger threads)
7. Documents, currency, and financial instruments (real or fake, plus virtual currency)
8. Gambling (buying/selling/facilitating gambling for money or anything of value, incl. digital currencies)
9. Hazardous goods and materials
10. Human exploitation and sexual services (trafficking, prostitution, escort services)
11. Jobs (job opportunities may not be promoted as commerce content)
12. Land, animals, and animal products (live animals, animal parts, ecologically sensitive land)
13. Medical and healthcare products (medical devices and ingestible supplements)
14. Misleading, violent, or hateful content
15. "No item for sale" content (e.g., news/humor posts with no actual product)
16. Prescription products, drugs, and drug paraphernalia
17. Recalled products (may not promote buying/selling/trading recalled or banned products)
18. Stolen goods
19. Subscriptions and digital products (downloadable digital content, digital subscriptions/accounts)
20. Third-party infringement (counterfeits, IP violations)
21. Tobacco products and related paraphernalia
22. Used cosmetics (sold outside original packaging)
23. Vehicle parts and accessories (certain restricted parts)
24. Weapons, ammunition, and explosives

[META-OFFICIAL] https://www.facebook.com/policies_center/commerce (fetched directly; content localizes by request locale — verify against the English-locale rendering at time of listing, as Meta's page auto-serves a locale-specific version).

### B2. Non-obvious prohibitions that catch honest sellers

- **Digital/downloadable goods and services**: Marketplace is for physical items — "services, subscriptions, digital products, or rentals" and non-physical items generally are not eligible categories, even though this isn't intuitive to a seller used to eBay/Etsy-style digital goods. [META-OFFICIAL] (category 19 above) https://www.facebook.com/policies_center/commerce
- **Ingestible supplements and medical devices**: grouped together and prohibited outright, catching honest sellers of vitamins, supplements, or used medical equipment (e.g., a used blood-pressure monitor) who assume "medical" only means prescription drugs. [META-OFFICIAL] (category 13)
- **Weight-loss products / before-and-after imagery**: even where an item itself might be listable, Meta restricts before/after weight-loss imagery in listing content — a common honest-mistake trigger for supplement or fitness-gear sellers. [SECONDARY, consistent with Meta's broader ads Personal Attributes/misleading-claims policy but not independently re-confirmed on a Marketplace-specific page in this pass] https://www.auditsocials.com/blog/meta-ad-misleading-claims-personal-attributes-prohibited-content-policy-2026
- **Live animals**: prohibited outright (category 12), which surprises sellers of pets, livestock, or "animal lovers" rehoming posts.
- **Alcohol, tobacco, and (by extension) vapes/e-cigarettes**: prohibited under categories 3 and 21 (tobacco products and related paraphernalia) — vapes fall under the tobacco/paraphernalia umbrella.
- **Recalled items**: prohibited even if the seller is unaware of a recall (category 17) — CPSC-flagged used goods (cribs, certain electronics, car seats) are a common accidental violation. [META-OFFICIAL category] cross-referenced with regulator concern reported here: [SECONDARY] https://www.cbsnews.com/amp/news/facebook-marketplace-banned-recalled-products-amazon-walmart-ebay-cpsc
- **Event tickets**: not enumerated as its own named category in the official 24-item list fetched above; ticket resale commonly falls under "documents/financial instruments" or platform-specific ticketing restrictions in practice, but I could not confirm an explicit "event tickets" clause in the official text during this pass — flagged in Gaps.
- **Gift cards**: physical and electronic gift cards/vouchers are restricted except for specially approved sellers, per earlier official-policy summary. [SECONDARY summarizing META-OFFICIAL text] https://grokipedia.com/page/Facebook_Commerce_Policies — not independently re-verified word-for-word against the fetched official page in this pass; treat as likely accurate but unconfirmed primary wording.
- **"In search of" (ISO) posts and jobs**: "No item for sale" (category 15) covers posts with no actual product (which would sweep in pure "looking for X" posts with nothing to sell), and "Jobs" (category 11) explicitly bars job-opportunity postings as commerce content.

### B3. Listing content that causes rejection

- Personal-attributes targeting: content that implies or asserts a protected/personal characteristic about the viewer (e.g., "for overweight women," implying health condition, financial status, etc.) is flagged as a leading cause of rejections. [SECONDARY] https://www.auditsocials.com/blog/meta-ad-misleading-claims-personal-attributes-prohibited-content-policy-2026
- Misleading or low-quality images: overlay text, watermarks, stock/generic photos instead of the actual item, and low-resolution images are commonly cited image-policy rejection triggers. [SECONDARY] https://www.aishoppingfeeds.com/fix/meta/catalog-item-rejected-policy-violation/
- Before/after imagery: restricted even for otherwise-permitted items (see B2).
- Price displayed inside the image itself and other "for sale" text baked into a photo is a commonly cited rejection trigger in secondary seller guides, though I could not confirm the exact clause in Meta's official policy text during this pass — treat as plausible best practice (keep price in the listing field, not the photo) rather than confirmed official rule. [SECONDARY, unconfirmed against primary text]
- Missing or irrelevant photos: listings with no real photo of the item, or photos unrelated to the item described, are flagged by Meta's own automated and manual review as a "no item for sale" / misleading-content issue (categories 14–15 above).
- Meta's own rejection-reason help page confirms counterfeit items as one explicit named rejection example and directs sellers to a "Your listings → Needs attention → See details" flow to view the specific reason for their own rejected listing. [META-OFFICIAL] https://www.facebook.com/help/2193854224216494

### B4. Official appeals process

For a rejected listing: [META-OFFICIAL] https://www.facebook.com/help/2193854224216494
1. Go to your profile → Marketplace (under "Extra features"/Profile status)
2. Go to "See what happened" / "See issue" on the affected listing
3. Select "Request review"

Limitations, per the same official page:
- No review option if it has been **more than 180 days** since the listing was rejected
- No second review request once you've already requested one
- Some policy violations are simply **not eligible for review** at all

For a restricted Marketplace account, the equivalent official path (via Settings & Privacy → Settings → Account Quality) shows the specific restriction and, where available, a "Request Review" control next to the Marketplace entry. [SECONDARY description of the official flow, not independently re-verified against a Meta-owned page directly in this pass] https://outpostalerts.com/blog/facebook-marketplace-listing-rejected — treat the exact navigation path and any stated turnaround times (24–72 hours / 7–14 days) or character limits (1,000-character appeal, 30-day cool-down) as **unconfirmed against primary Meta text**; flagged in Gaps.

### B5. Repeated violations and duplicate listings

- **Repeated violations, general Meta enforcement doctrine**: Meta's Transparency Center confirms enforcement is "proportional to the severity of the violation, the history of violations on the account, and the risk or harm posed," with a strike system (warning on strike 1, feature restrictions building through strikes 2–10+, and account disabling for continued violations after repeated warnings/restrictions). [META-OFFICIAL] https://transparency.meta.com/enforcement/taking-action/restricting-accounts/ — note this page documents Meta's **general Community Standards strike system**; it does not explicitly confirm that Commerce Policy violations feed into the identical numbered-strike ladder, only that persistent violation of any policy area can lead to restriction/disabling. Treat the general "repeated violations → escalating restriction → disable" pattern as confirmed; the specific strike-count thresholds as confirmed for Community Standards but **not independently confirmed to apply 1:1 to Commerce Policy violations**.
- **Duplicate/repeated listings of the same item**: I found no official Meta Commerce Policy or Help Center page in this pass that states a specific numeric or textual duplicate-listing rule. Secondary sources describe informal common practice (identical/near-identical listings with the same photos/price for the same item may be detected and pruned to one active listing), but this is **not confirmed as codified official policy** — flagged in Gaps. [SECONDARY, low-confidence/unsourced-sounding] https://erpstaging.fha.gov.ng/facebook-marketplace-duplicate-listing/ and similar aggregator content.

---

## Confidence & Gaps

**High confidence (directly fetched or clearly primary-sourced):**
- The 24-category official prohibited-content list (B1), fetched directly from `facebook.com/policies_center/commerce`.
- FTC's three flagship seller-scam patterns (verification code, overpayment, fake mobile-payment notification) — direct FTC consumer-alert pages.
- Meta's Seller/Purchase Protection eligibility mechanics (shipped-only, onsite checkout, $500 cap, US-only, 7-day ship window) — fetched from `facebook.com/legal/merchant_policies`.
- Meta's official rejected-listing appeal flow and 180-day / one-request limits — fetched from `facebook.com/help/2193854224216494`.
- Meta's general strike/restriction enforcement ladder — fetched from `transparency.meta.com`.

**Gaps / lower confidence, flagged inline above and worth a follow-up pass if precision matters:**
1. **No Meta-branded page explicitly recommending police-station safe-exchange zones** — this practice is well-documented via US local police department programs and news coverage, not a Meta safety page found in this pass.
2. **No single official BSP or PNP-ACG bulletin specifically titled/dedicated to "GCash Marketplace seller scam"** was located; BSP/PNP-ACG official statements found were about (a) BSP-impersonation fraud and (b) PNP-ACG-impersonation "recovery agent" fraud, both of which reinforce the same anti-OTP-sharing/anti-advance-payment doctrine but are not a direct GCash-fake-screenshot advisory from the regulator itself. The GCash-fake-screenshot pattern documentation here is SECONDARY (news/legal-blog).
3. **"Event tickets" and "gift cards" as explicit named prohibited categories** were not both independently re-confirmed word-for-word in the freshly fetched official 24-item list — gift cards appear in an earlier (secondary-summarized) pass of the same policy; event tickets were not confirmed as a distinct named clause at all in this pass.
4. **"Price in image" as an explicit rejection rule** and the **exact account-restriction appeal navigation path / turnaround times / character limits** are sourced from secondary seller-help blogs, not confirmed against Meta's own text.
5. **Duplicate/repeated-listing policy** — no codified official rule found; only informal secondary description of common enforcement behavior. Treat as anecdotal, not policy.
6. The `facebook.com/policies_center/commerce` and `facebook.com/help/...` pages appear to **auto-localize by request context** (one fetch returned Filipino-language content even when an `en_US` locale parameter was requested); the category list itself was consistent across both fetches, which increases confidence in the list's completeness, but exact clause-level English wording should be re-verified against a browser session in the target locale before quoting verbatim in user-facing copy.

Recommended follow-up if higher precision is needed: a manual (logged-in, US-locale) browse of `facebook.com/policies_center/commerce` and the Marketplace-specific seller-help subsection, plus a direct check of official BSP (`bsp.gov.ph`) and PNP-ACG (`pnp.gov.ph` / official social pages) advisory archives for any GCash-Marketplace-specific consumer bulletin issued in 2025–2026.
