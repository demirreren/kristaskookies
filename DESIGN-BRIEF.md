# Design brief — Krista's Kookies

Brief for Claude Design (or any design tool). Copy this whole file in.
Everything needed is inline — no external references.

**Read this first:** the goal is a website with a strong point of view, not a compliant one. Most of this document is context and facts. Only the short "Locked" list is fixed. Everything else is yours to invent, and inventing is the job.

---

## The project

Krista's Kookies is a home-based cookie business run by Krista, with a partner, Elson, serving Western University's campus in London, Ontario. Today people order through a link in her Instagram bio that goes to a Google Form, and pay by e-transfer. This website replaces that.

The brand is warm, homemade, and a little playful — a real person bakes these in her kitchen at 2am and delivers them across campus herself. It should never look like a template, a SaaS landing page, or a generic bakery site.

**Design a complete website with real personality.**

---

## Start by proposing directions — do this before building

Do **not** go straight to one design. First propose **three genuinely different visual directions** for this brand. Make them actually distinct — different enough that someone would have a real preference, not three shades of the same idea.

For each, give:
- A name and a one-line concept
- The palette (hex values), including how it extends beyond the base brand colors
- Typography pairing
- The organizing visual idea — what makes this direction *this* direction
- One sentence on how the homepage hero works

Then ask which to build. Build only that one, in full.

If you find yourself producing three variations on "cream background with navy headings," push harder. That's the safe answer and it's the one to avoid.

---

## Locked — do not change these

Short list. Everything not on it is open.

1. **The logo** (`brand/logo.png`) — a circular cream tag with sprinkles, the wordmark, and a smiling cookie mascot in a chef's hat. Use it as-is.
2. **Flavour names and box prices** — exactly as listed in the Facts section.
3. **The box-builder rule** — flavour picks must always sum exactly to the chosen box size, enforced by the interaction itself. Non-negotiable; it's the reason the site exists.
4. **Canadian spelling** — "Flavour", not "Flavor".
5. **The allergy notice** must appear before payment, with a required acknowledgement.

That's it. Everything below is context, not constraint.

---

## Yours to invent — please do

**Layout and structure.** Invent sections. Add things I haven't thought of — a "this week's rotation" countdown, a behind-the-bake strip, a delivery map of campus, a wall of Instagram comments, a cookie-of-the-week spotlight, a fresh-out-the-oven timestamp. Decide what a visitor should feel in the first three seconds and build toward that.

**Motion and interaction.** Scroll-triggered reveals, parallax, hover states with real payoff, a hero that does something. This is a cookie site — it can be joyful. Restraint is not the goal.

**Type.** Go big. Oversized display headings, dramatic scale contrast, type that overlaps imagery, curved or rotated text. The brand's own menu uses a fat retro script — lean into that energy rather than setting it politely at 32px.

**Color.** The base palette below is the *starting point*, not the ceiling. Extend it: give each flavour its own accent, introduce deeper shades for contrast sections, use full-bleed color blocks. A page that is one flat cream from top to bottom is the failure mode to avoid — build rhythm through alternating bands, dark sections, saturated moments.

**Texture and detail.** Grain, paper texture, sticker badges, hand-drawn arrows, torn edges, crumbs, sprinkle confetti, dotted delivery routes. The kind of small touches that make something feel handmade rather than generated.

**Illustration.** The brand already has a mascot layer — its menu gives cookies googly eyes, sunglasses, and little sneakers. That's a real asset. Use it more boldly than a single 404 easter egg.

---

## The ambition bar

Reference: **crumblcookies.com**. What's worth taking is the *scale of the experience* — full-bleed photography, a rotating weekly lineup treated as an event, big confident type, sections that each do something different, real motion, a proper footer. A site that feels like a brand, not a page.

What's **not** worth taking is Crumbl's specific look — corporate pink-and-white minimalism. This brand is warmer, scrappier, more handmade. Match Crumbl's *ambition*, not its aesthetic.

Other useful reference points for energy: modern DTC food brands, retro diner and ice-cream signage, zine and sticker culture, 70s food packaging.

**Do not present this as a phone mockup.** Design the full web experience — wide hero, full-bleed sections, a real navigation and footer. Show it at desktop width *and* mobile, since most real traffic arrives from an Instagram bio link on a phone. But the phone frame should not be the presentation.

---

## Pages

Build a complete site, not three screens:

**Home** · **Flavours** · **Build a box** · **About** · **Events / catering** · **FAQ** · **Contact** · plus **order confirmation**, an **empty-box state**, and a **404**.

Nav order: Home · About · Flavours · Events · FAQ · Contact. Ordering is *not* a nav tab — give it a persistent, always-reachable presence of your own design, showing progress once a box is started.

Home leads with the current rotation. Pricing is not prominent on the home page — it belongs on Flavours.

---

## The box builder — the one thing that must be right

The current Google Form lets people pick flavour quantities that don't add up to their box size, so every order gets checked by hand. **The design must make an invalid order impossible.**

- Pick a size: 1 / 3 / 6 / 12 cookies
- Show the box as that many slots — visually, so "how full am I" is instant
- Adding a flavour fills the next slot; a filled slot can be emptied
- The remaining count is always visible
- Checkout stays **disabled until the box is exactly full** — never an error after the fact
- When full, adding more is refused at the source rather than erroring
- The same flavour can repeat — 6 of one flavour is valid
- Reducing box size mid-build warns before discarding picks

*How* this looks and feels is entirely open — a physical box filling up, a tray, a wheel, a conveyor, something else. Make it the most delightful part of the site. It's what people will remember.

---

## Assets and photography

`brand/logo.png` and `assets/photos/*.jpg` (four flavour photos).

**The photography is weak placeholder** — phone snaps in a kitchen. A proper shoot is coming, and three flavours have no photo at all (Chocolate Chip, Chocolate Toffee, Sticky Date Toffee).

**Do not let the weak photos define the design.** Treat them boldly: hard circular crops on saturated color blocks, duotone, heavy shadows, stickers and frames layered over them, or drop photography entirely in favour of illustration where it serves the direction better. For the three missing flavours, invent a treatment that looks intentional rather than a grey placeholder. Design as though great square top-down photos are arriving next week.

---

## Facts

### Base palette — the starting point, extend it

| Role | Hex |
|---|---|
| Warm cream | `#f4e7d1` |
| Warm brown | `#3c2519` |
| Navy | `#000b3d` |
| Tan | `#e1cfb3` |
| Soft pink | `#ffd6d6` |

The logo carries its own browns: `#774a2d` ink, `#bb7d44` outline.

### Type — the starting point

The brand's real fonts are Candice (retro script headings) and Loubag (flavour labels), both commercial and unlicensed for web. Free stand-ins on Google Fonts: **Oleo Script** (bold retro script), **Chewy** (hand-drawn bounce), **Nunito Sans** (body). Use these, or propose something better in your directions — the vibe matters more than the specific families.

### The seven flavours, in display order

Cosmic Brownie · Strawberry Buttered Toast · Lemon Blueberry Streusel · Chocolate Toffee · Chocolate Chip · Sticky Date Toffee · Mini Matcha Shortbread

Descriptions (provisional — written from names and photos, not confirmed recipes; rewrite freely if better copy serves the design):

| Flavour | Description |
|---|---|
| Cosmic Brownie | A fudgy brownie of a cookie under a slick of chocolate ganache, scattered with rainbow candy chips. |
| Strawberry Buttered Toast | Brown butter dough with strawberry jam and buttery toasted crumbs. |
| Lemon Blueberry Streusel | Bright lemon dough packed with blueberries, piled with buttery streusel and a lemon drizzle. |
| Chocolate Toffee | Deep brown sugar dough, dark chocolate and shards of buttery toffee, with flaky salt. |
| Chocolate Chip | Brown butter dough, pools of dark chocolate, flaky salt, crisp edge, soft middle. |
| Sticky Date Toffee | Sticky toffee pudding as a cookie — dates, warm spice, white chocolate and toffee chunks. |
| Mini Matcha Shortbread | Buttery checkerboard shortbread with matcha. Delicate, not too sweet. |

The lineup **rotates** — that's a feature worth dramatizing.

### Prices

1 cookie $5 · 3 cookies $10 · 6 cookies $18 · 12 cookies $36. Delivery always free.

> ⚠️ These prices are disputed — a second source lists 3 for $13, 6 for $24, 12 for $40 with no single cookie. Use the numbers above for layout, but don't build a layout that only works with exactly four tiers.

### Voice

First person, warm, playful, never corporate. Krista's own words, from her FAQ: *"Fun fact: I'm allergic to all nuts! So I understand how important this is."* That's the register. **Write better copy than the placeholders below wherever you can** — headlines especially. These are a floor, not a ceiling.

- Tagline: Small-batch cookies, baked in London and delivered free across Western.
- Hero (placeholder — improve on it): Cookies worth the walk
- How it works: Pick your box (1, 3, 6 or 12) → Fill it with any flavours, repeats welcome → Free delivery anywhere on campus, usually 3–5 days
- Freshness: Baked fresh to order, best within 3–4 days.
- Events: We've baked for club fundraisers, charity sales and markets — tell us what you need and we'll quote it. Past events: Western Biochemistry Club plant-and-cookie sale · SickKids charity fundraiser · Distillery District market.
- Contact: Instagram @Kristas.Kookies · krista.kookies@gmail.com

### Allergy notice — before payment, required acknowledgement

> These cookies are made in a home kitchen that handles peanuts and tree nuts. We can't guarantee anything is nut-free. If you have a severe allergy, please don't order — your safety matters more than the sale.

### FAQ answers — verbatim, do not reword

**Do your cookies contain allergens?**
Our cookies are made in a home kitchen that handles common allergens, including peanuts and tree nuts. While we take care in our preparation, we cannot guarantee that our products are completely nut-free. If you have a severe allergy, we recommend not ordering for your safety. (Fun fact: I'm allergic to all nuts! So I understand how important this is)

**Where do you deliver and how much is it?**
We currently offer delivery across Western University's campus. For larger orders, we may be able to accommodate deliveries beyond campus. Feel free to reach out! Delivery is included with every order.

**How should I store the cookies and how long do they stay fresh?**
We recommend storing your cookies in an airtight container at room temperature for optimal freshness. They can last up to 3–4 days, but we definitely recommend enjoying them fresh for the best experience.

---

## The only real failure modes

- A page that is one flat cream from top to bottom with no rhythm or contrast
- Something that could be any bakery with the logo swapped out
- A phone mockup instead of a website
- Playing it safe

Surprise me.
