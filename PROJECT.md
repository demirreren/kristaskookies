# Krista's Kookies — Project Context

Source-of-truth spec for the website build. Supersedes earlier notes.

---

## Overview

Krista's Kookies is a home-based cookie business serving Western University's campus. Ordering today is fully manual — Instagram bio link → Google Form → e-transfer, with form responses and e-transfer notifications reconciled by hand.

The website replaces that with a real ordering flow: browse the current rotation, build a box, pay online, get a confirmation. Orders land somewhere the business can actually manage them without a spreadsheet.

**Payments and order management run entirely through Square.** The Square account already exists and is set up; dashboard access is in place. There is no Stripe in this project.

---

## Business details

**Current flavor lineup** (rotates):

1. Cosmic Brownie
2. Strawberry Buttered Toast
3. Lemon Blueberry Streusel
4. Chocolate Toffee
5. Chocolate Chip
6. Sticky Date Toffee
7. Mini Matcha Shortbread

Display order on the site matches the order above.

**Seen but not on the current menu** — handwritten labels in the flat-lay photo (`assets/photos/_reference-flatlay-labelled.jpg`) name three more: **Dirty Chai**, **Mini Egg**, **Lotus Biscoff**. Partial recovery of the "master flavor list"; needs confirming as retired, seasonal, or returning.

**Gift box:** the menu PDF also sells a **6-cookie gift box at $23** — decorated box, bow, personalized message. This sits outside the 1/3/6/12 flat-rate model and was presented as a Mother's Day special. Unresolved whether gifting is permanent, seasonal, or retired; a personalized-message field would change the checkout flow.

**Pricing:**

| Box | Price |
|---|---|
| 1 cookie | $5 |
| 3 cookies | $10 |
| 6 cookies | $18 |
| 12 cookies | $36 |

Pricing is a per-box flat rate, not per-flavor. Flavor choice does not affect price.

**Payment methods:** Online via Square (card + Apple Pay / Google Pay). In person, Square already handles tap debit/credit and exact cash. E-transfer is retired once the site is live.

**Delivery:** Free across Western University's campus, included with every order. Larger orders may go beyond campus on request.

**Turnaround:** Orders taken on a rolling basis, ready in 3–5 days.

**Capacity:** No cap, no order windows, no delivery-date picker. Rolling orders with a 3–5 day lead time, exactly as today — confirmed as fine as-is. The site does not need a sold-out state for v1. (Revisit if volume grows; a frictionless site removes the throttle the Google Form provided.)

**Storage/freshness:** Airtight at room temperature, 3–4 days, best fresh.

**Allergens:** Made in a home kitchen that handles peanuts and tree nuts. Nut-free cannot be guaranteed. This must be surfaced *before* the customer completes an order — not only in the FAQ.

**Contact:**
- Instagram: [@Kristas.Kookies](https://instagram.com/Kristas.Kookies)
- Email: krista.kookies@gmail.com

---

## The core problem to solve

The current Google Form uses a per-flavor quantity dropdown (1–12) with no validation, so nothing stops a customer's flavor quantities from disagreeing with the box size they picked. Every order has to be manually checked for math errors.

**The site must make invalid orders unrepresentable.** Flavor selections always sum exactly to the chosen box size (1, 3, 6, or 12) — enforced by the interaction itself, not by an error message after the fact. This is the single highest-value thing the site does.

Target interaction: a visual "build a box" flow where the customer taps or drags cookies into a box with a fixed number of slots. Slots remaining is always visible. Checkout stays disabled until the box is full. Drag-and-drop is the ideal; tap-to-add is an acceptable v1 as long as the constraint holds.

---

## Site structure

Nav order:

1. **Home** — current rotation's flavors at the top
2. **About** — the business
3. **Flavors & pricing** — full menu, box pricing, entry point to build-a-box
4. **Events** — catering
5. **FAQ**
6. **Contact**

Keep the main flow lean. Traffic arrives from Instagram already knowing the brand, so About and FAQ exist but stay out of the primary path. Pricing should not be prominent on the home page.

---

## Interaction & content requirements

- **Mobile-first.** Nearly all traffic is Instagram link-in-bio on a phone. Desktop is secondary.
- **Hover interaction** on cookie images (with a tap-equivalent on touch devices).
- **Nav fades on scroll.**
- **Catering:** a "message us for a quote" flow — a form that behaves like sending an email rather than a checkout.
- **Event inquiries:** a collapsible/expandable section dedicated to them.
- **Allergy notice** surfaced in the order flow before completion, and repeated in the FAQ.
- **Square logo asset** needed (square aspect ratio, for favicon / social / Square Dashboard).
- **Per-flavor photography** — build-a-box and the hover interaction both depend on a clean image per flavor. Needed before the flavor UI can be finished.

---

## Payments & order management (Square)

Two viable integration paths, both supporting Apple Pay:

**A. Square-hosted checkout (Checkout API / payment links)** — generate a link to a Square-hosted payment page. Apple Pay, Google Pay, and Cash App Pay are toggleable on the page. Lowest implementation effort and no PCI surface, but limited visual customization, so checkout won't carry the brand styling.

**B. Web Payments SDK (embedded)** — PCI-compliant card fields hosted in our own page, tokenized and charged via the Payments API. Supports Apple Pay and Google Pay with our own branding end to end. More work, including Apple's domain-verification requirements for Apple Pay on the web.

Recommendation: start with **A** to get live and taking money, keep the box-builder as the branded experience, and move to **B** later if the checkout handoff hurts conversion. Decision still open.

**Orders land in Square natively.** Using the Orders API, an order shows up in Square Dashboard and Square Point of Sale once it (a) includes fulfillment details and (b) is paid. That satisfies the "dashboard so orders aren't tracked by hand" requirement without building a custom dashboard — the business uses the Square tools they already have. Building line items from Square Catalog objects also keeps inventory in sync automatically when an order is charged.

**Confirmation emails** are handled by Square's receipts when the customer's email is captured at checkout. A branded confirmation email on top of that is a later enhancement, not v1.

---

## Flavor management

The business needs to update the rotation themselves, without a developer, every time flavors change.

Because flavors can be modeled as Square Catalog items — and catalog items created via the API are immediately visible in Square Dashboard and Point of Sale — much of this may come free by letting them manage items in the Square Dashboard directly.

Open design question: "which flavors are in *this week's* rotation" isn't a native Square concept, so it needs either a convention within the catalog (category, availability, or a custom attribute) or a small internal admin toggle on our side. To be decided at build time.

---

## Brand

Assets live in [`brand/`](brand/) — [`BRAND.md`](brand/BRAND.md) and [`design-tokens.json`](brand/design-tokens.json). `design-tokens.json` is the source of truth for wiring CSS variables.

**Fonts**

| Role | Font |
|---|---|
| Headings / titles | Candice (swirly script) |
| Flavor labels under cookie photos | Loubag |
| Body text | Open Sauce |

**Colors**

| Role | Hex | Notes |
|---|---|---|
| Background (primary) | `#f4e7d1` | Warm cream |
| Text (primary) | `#3c2519` | Warm brown, body copy |
| Text (accent / headers) | `#000b3d` | Navy — script-style headings only |
| Modal / card background | `#e1cfb3` | Tan — cards, order forms, popups |
| Accent (seasonal / promo) | `#ffd6d6` | Soft pink — promos only, not everyday UI |

Earlier Canva materials carried two near-identical creams (`#f4e7d1` / `#f0e8d3`) and two competing text colors. Standardized to the single set above rather than carrying the inconsistency forward.

**Logo:** [`brand/logo.png`](brand/logo.png) — 461×461 RGBA, clean transparency, square. Good for on-screen use; a vector/PDF export is still worth having for large or print use.

Note that this file **has the cartoon cookie face** (a smiling mascot in a chef's hat), which conflicts with the earlier request for a face-free version. Needs confirming which is canonical before the logo goes into the site.

---

## Open decisions

- **Checkout path** — Square-hosted payment links vs. embedded Web Payments SDK (see above).
- **Rotation modeling** — Square Catalog convention vs. internal admin toggle.
- **Domain** — undecided. `kristakookies` or similar, TLD flexible, budget ~$0–20/year.
- **Flavor master list** — need descriptions and ingredients per flavor, including retired/seasonal ones, to populate flavor detail UI.
- **Palette sign-off** — the standardization above hasn't been formally confirmed against any further brand preferences.
- **Logo colors** — the mark's own colors differ from the UI tokens (see `brand/BRAND.md`). Keep it as a fixed mark, or align it.
- **Gift box** — is the $23 personalized gift box permanent, seasonal, or retired? (see Business details)
- **Retired flavors** — Dirty Chai, Mini Egg, Lotus Biscoff: gone, seasonal, or returning?
- **Ordering CTA placement** — the agreed six-tab nav has no "Order" entry. Proposal is a persistent CTA outside the nav (see `DESIGN.md`); needs confirming since it affects every page.
- **Tax** — included in the listed prices, or added at checkout?
- **Refunds / cancellations** — needed for the FAQ and for Square.

## Resolved

- **Capacity & scheduling** — no cap, no windows, no date picker. Rolling as today (see Business details).
- **Font licensing** — Candice (URW) and Loubag (Creative Media Lab) are both commercial and cannot be used on the web without a purchased webfont license. Substituting with OFL fonts instead: **Oleo Script Bold** for headings, **Chewy** (or Fredoka) for flavor labels, **Open Sauce** unchanged for body. All self-hostable, no licensing exposure. See `DESIGN.md`. Buying the real fonts is still an option — it would need a webfont license scoped to the final domain.
- **Square logo asset** — the mark is square already (`brand/logo.png`).

## Out of scope for v1

- SEO and AI-search optimization — later phase.
- Custom branded transactional email beyond Square receipts.
- Custom order dashboard (Square Dashboard covers it).
