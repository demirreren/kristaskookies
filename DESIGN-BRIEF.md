# Design brief — Krista's Kookies

Self-contained brief for Claude Design (or any design tool). Copy this whole file in.
Everything needed is inline — no external references.

---

## The project

Krista's Kookies is a home-based cookie business run by one person, Krista, serving Western University's campus in London, Ontario. Right now people order through a link in her Instagram bio that goes to a Google Form, and pay by e-transfer. We're replacing that with a real website.

**Design a complete website mockup, mobile-first.**

## Audience and device

Almost every visitor arrives from the Instagram bio link, on a phone, already knowing the brand. **Design at 390px wide first.** Desktop is secondary — treat it as a widened version of the mobile layout, not a separate design.

Visitors don't need convincing that Krista's Kookies exists. They need to pick cookies and pay. Keep the path to ordering short.

## Visual direction

**Warm, homemade, a little playful. Not corporate, not minimal-white.** A real person bakes these in her kitchen, and the site should feel that way.

**The circle is the core shape.** The logo is a circular tag and every cookie photo on their existing menu is a circular crop. Carry that through the whole site: circular flavour photos, circular slots in the box builder, circular avatars. This is the single strongest visual idea the brand has.

**There's a playful mascot layer available.** The brand's existing menu has a page where cookies are given googly eyes, sunglasses and little sneakers, and the logo itself is a smiling cookie in a chef's hat. It's charming and very much the brand's voice. Use it **sparingly** — an empty box-builder state, the order confirmation, a 404. Keep it **out of the flavour grid**, where it competes with the photography.

**Reference — structure only:** crumblcookies.com. Take its *structure* — the rotating weekly lineup as the hero, one card per cookie with photo + name + short description, a consistently available order button, generous whitespace. **Do not take its palette.** Crumbl is bright white and pink and corporate. This brand is warm cream and navy and hand-made.

## Colours — use these exactly

| Role | Hex |
|---|---|
| Page background (everywhere) | `#f4e7d1` warm cream |
| Body text | `#3c2519` warm brown |
| Headings **and** flavour labels | `#000b3d` navy |
| Cards, modals, form fields, the box tray | `#e1cfb3` tan |
| Seasonal promos **only** | `#ffd6d6` soft pink |

The pink is for seasonal moments (a Mother's Day special) and nothing else. Do not use it for buttons, links, or accents.

The logo carries its own browns — `#774a2d` ink, `#bb7d44` outline. Don't sample those for UI.

## Typography

| Role | Font | Source |
|---|---|---|
| Headings and titles | **Oleo Script**, weight 700 — bold retro script | Google Fonts |
| Flavour names under photos | **Chewy** — hand-drawn bounce | Google Fonts |
| Body text, buttons, forms | **Nunito Sans** | Google Fonts |

The brand's real body font is **Open Sauce**, which is free (SIL OFL) but **not on Google Fonts** — it has to be self-hosted from github.com/marcologous/Open-Sauce-Fonts. Use **Nunito Sans** as the stand-in for the mockup; it's a similar friendly, slightly rounded grotesque. The production site will self-host Open Sauce.

Headings and flavour names both in navy `#000b3d`. Body in brown `#3c2519`.

## Assets

Upload these from the repo:

- `brand/logo.png` — 461×461, transparent background, circular tag with a smiling cookie mascot in a chef's hat
- `assets/photos/*.jpg` — four flavour photos

**The photography is placeholder.** They're phone snaps in kitchen context and a proper shoot is coming. Three flavours (Chocolate Chip, Chocolate Toffee, Sticky Date Toffee) have no photo at all — use a circular tan `#e1cfb3` placeholder for those. Design as though good square top-down photos will arrive later; don't design around the current ones being bad.

---

## Pages

Nav order: **Home · About · Flavours · Events · FAQ · Contact**

The nav fades out as you scroll down and returns when you scroll up.

There is **no "Order" tab.** Instead a persistent "Build a box" button sits outside the nav — sticky at the bottom of the viewport on mobile, always one tap away. Once a box is started it shows progress: "Build a box · 3 of 6".

### 1. Home
1. Hero — logo, headline, Build a box button. **No pricing on this page.**
2. This week's flavours — circular photo grid, tap/hover reveals the description
3. How it works — three steps
4. Freshness + allergy line
5. Events teaser
6. Footer

### 2. Flavours
Full flavour grid with descriptions → pricing table → build-a-box entry → allergy notice. This is the only page where pricing is prominent.

### 3. Build a box
The most important screen. Spec below.

### 4. About · 5. Events · 6. FAQ · 7. Contact
Single column, text-led. Events has a collapsible "Get a quote" enquiry form.

---

## The box builder — the critical interaction

This is the whole reason the site exists. The current Google Form lets people pick flavour quantities that don't add up to their box size, so every order gets checked by hand. **The design must make an invalid order impossible.**

**Step 1 — pick a size:** 1 cookie $5 · 3 cookies $10 · 6 cookies $18 · 12 cookies $36

**Step 2 — fill it:**
- Draw the box as that many **empty circular slots**
- Tapping a flavour fills the next empty slot; tapping a filled slot empties it
- The remaining count is always visible — "3 more to go"
- The checkout button is **disabled until the box is exactly full**. Never show an error after the fact
- When the box is full, flavours go visually inert rather than erroring
- The same flavour can be picked repeatedly — 6 of one flavour is valid
- Reducing the box size mid-build warns before discarding picks

**Step 3 — allergy acknowledgement**, before payment, with a required checkbox.

**Step 4 — delivery details:** name, email, phone, building/residence, room, notes.

**Step 5 — payment**, then a confirmation screen.

---

## Copy — use this, don't invent

**Tagline:** Small-batch cookies, baked in London and delivered free across Western.

**Hero headline:** Cookies worth the walk
**Hero sub:** Small batch, baked to order, delivered free anywhere on Western's campus.
**Button:** Build a box

**Section — This week's flavours:** The lineup rotates. Here's what's baking right now.

**Section — How it works:**
1. **Pick your box** — 1, 3, 6 or 12 cookies.
2. **Fill it** — mix and match any flavours you like. Six of the same? Go for it.
3. **We deliver** — free, anywhere on campus, usually within 3–5 days.

**Freshness + allergy line:** Baked fresh to order and best within 3–4 days. Made in a home kitchen that handles peanuts and tree nuts.

**Events teaser:** Cookies for your event? We've baked for club fundraisers, charity sales and markets. Tell us what you need and we'll quote it.

### Flavours (display in this order)

*Descriptions below are provisional — written from the flavour names and photos, not confirmed against the actual recipes. Fine for a mockup; they'll be rewritten before launch, so don't design a layout that depends on their exact length.*

| Flavour | Description |
|---|---|
| Cosmic Brownie | A fudgy brownie of a cookie under a slick of chocolate ganache, scattered with rainbow candy chips. |
| Strawberry Buttered Toast | Brown butter dough with strawberry jam and buttery toasted crumbs. |
| Lemon Blueberry Streusel | Bright lemon dough packed with blueberries, piled with buttery streusel and a lemon drizzle. |
| Chocolate Toffee | Deep brown sugar dough, dark chocolate and shards of buttery toffee, with flaky salt. |
| Chocolate Chip | Brown butter dough, pools of dark chocolate, flaky salt, crisp edge, soft middle. |
| Sticky Date Toffee | Sticky toffee pudding as a cookie — dates, warm spice, white chocolate and toffee chunks. |
| Mini Matcha Shortbread | Buttery checkerboard shortbread with matcha. Delicate, not too sweet. |

### Prices
1 cookie $5 · 3 cookies $10 · 6 cookies $18 · 12 cookies $36
Delivery is free, always. Mix and match any flavours.

> ⚠️ **These prices are disputed.** A second source in the repo lists 3 for $13, 6 for $24, 12 for $40, with no single-cookie option. Use the numbers above for layout purposes, but treat them as placeholder — they may change before launch, so don't build a layout that only works with four price tiers.

### Box builder microcopy
- Empty: *Your box is looking a little empty.*
- In progress: *3 more to go*
- Full: *That's a full box. Nice picks.*
- Tapping when full: *Your box is full — remove one to swap.*

### Allergy notice (before payment)
> These cookies are made in a home kitchen that handles peanuts and tree nuts. We can't guarantee anything is nut-free. If you have a severe allergy, please don't order — your safety matters more than the sale.
> ☐ I've read and understood this

### Confirmation
> **Order in!** Thanks {name} — your {6} cookies are booked. We'll be in touch by email within a day or so to sort out delivery. Usually ready in 3–5 days.

### FAQ (verbatim — do not reword)
**Do your cookies contain allergens?**
Our cookies are made in a home kitchen that handles common allergens, including peanuts and tree nuts. While we take care in our preparation, we cannot guarantee that our products are completely nut-free. If you have a severe allergy, we recommend not ordering for your safety. (Fun fact: I'm allergic to all nuts! So I understand how important this is)

**Where do you deliver and how much is it?**
We currently offer delivery across Western University's campus. For larger orders, we may be able to accommodate deliveries beyond campus. Feel free to reach out! Delivery is included with every order.

**How should I store the cookies and how long do they stay fresh?**
We recommend storing your cookies in an airtight container at room temperature for optimal freshness. They can last up to 3–4 days, but we definitely recommend enjoying them fresh for the best experience.

### Events — past events
- **Western Biochemistry Club** — plant and cookie sale
- **SickKids** — charity fundraiser
- **Distillery District** — market

### Contact
Instagram @Kristas.Kookies · krista.kookies@gmail.com

---

## Don'ts

- No pricing on the homepage
- No pink outside seasonal promos
- Don't put ordering in the nav — keep the persistent button
- Don't make About or FAQ prominent; visitors already know the brand
- Don't use stock cookie photography — placeholders are fine, but don't design around images we can't reproduce
- Don't add a cart icon or multi-item cart. One box, one order
- Canadian spelling: **"Flavour"**, not "Flavor"
