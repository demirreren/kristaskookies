# Design direction & site structure

How the site should look and how it's organized. Copy lives in [`COPY.md`](COPY.md); business rules in [`PROJECT.md`](PROJECT.md).

---

## Art direction

Two inputs: the existing Flavour Menu PDF (what the brand already is) and [crumblcookies.com](https://crumblcookies.com/) (where it's going).

### From the existing menu — keep

**The circle is the brand's core shape.** Every cookie on the menu is a circular crop, and the logo is a circular tag. That rhyme is the strongest visual idea the brand already has, and it should carry the whole site: circular flavor images, circular slots in the box builder, circular avatars in the footer.

It also does real work. The source photos are cluttered kitchen shots, and a tight circular crop throws away background. Keep it even once the photography improves.

**Navy on cream.** The menu sets script headings and flavor labels in navy `#000b3d` on cream `#f4e7d1`. Note this contradicts `BRAND.md`, which reserves navy for "script-style headings only" — in practice the flavor labels are navy too. The site should follow the menu: navy for headings *and* flavor labels, warm brown `#3c2519` for body copy.

**Pink means seasonal, nothing else.** The Mother's Day page is the only pink surface in the whole PDF. That rule is already being followed and should stay.

**The mascot layer is optional seasoning.** One menu page gives cookies googly eyes, sunglasses, and sneakers. It's charming and very on-brand for Instagram, but it doesn't scale to a product grid — it fights the photography. Use it sparingly: an empty box-builder state, a 404, the confirmation page. Not the flavor grid.

### From Crumbl — borrow

- **The rotation is the hero.** Crumbl's homepage leads with this week's lineup as large photo cards, each with a name, a short description, and a direct order action. That is exactly the model here.
- **One cookie per card, isolated, shot from above,** on a plain background with generous whitespace.
- **A consistent, always-available order CTA.**

### From Crumbl — don't borrow

Their palette is bright white and pink with a corporate, minimal feel. This brand is warm, cream, hand-made, and a little scrappy. Adopt Crumbl's *structure*, not its coldness. Krista's should read like a person bakes these, because one does.

---

## Typography

Two of the three brand fonts are commercial and cannot be used on the web without a purchased license (see `PROJECT.md`). These substitutes are all SIL Open Font License, free for commercial use, and self-hostable — no licensing exposure and no third-party request at render time.

| Role | Brand font | Substitute | Why |
|---|---|---|---|
| Headings | Candice (URW, commercial) | **Oleo Script Bold** | Closest match tested — bold retro script with the same thick strokes and looped swashes |
| Flavor labels | Loubag (Creative Media Lab, commercial) | **Chewy** | Keeps the menu's hand-drawn bounce. **Fredoka 600** is the cleaner, less comic alternative |
| Body | Open Sauce | **Open Sauce** — unchanged | Already OFL and self-hostable |

**Open Sauce is not on Google Fonts** — it must be self-hosted from [github.com/marcologous/Open-Sauce-Fonts](https://github.com/marcologous/Open-Sauce-Fonts) (SIL OFL, verified). Oleo Script and Chewy are both on Google Fonts. For mockups in tools that only load Google Fonts, **Nunito Sans** is a reasonable stand-in for Open Sauce; production should self-host the real thing.

I rendered candidates side by side against the PDF's type before choosing; Oleo Script was clearly nearest for headings. Lobster, Pacifico, Grand Hotel and Kaushan Script were all too light or too brushy.

If Krista or Elson want the exact brand fonts, both are purchasable — just make sure it's a **webfont** license, not desktop, and scoped to the final domain.

---

## Color roles

Tokens live in `brand/design-tokens.json`. How they map to the UI:

| Token | Hex | Used for |
|---|---|---|
| `background` | `#f4e7d1` | Page background everywhere |
| `text` | `#3c2519` | Body copy, descriptions, form labels |
| `textAccent` | `#000b3d` | Script headings **and** flavor labels |
| `modalBackground` | `#e1cfb3` | Cards, the box builder tray, modals, form fields |
| `accentPink` | `#ffd6d6` | Seasonal promos only — never everyday UI |

The logo carries its own colors (`#774a2d` ink, `#bb7d44` outline) that aren't in the token set. Fine for a fixed mark, but don't sample them for UI.

---

## Page structure

### Home
1. Nav — fades out on scroll down, returns on scroll up
2. Hero — logo, one-line positioning, **Build a box** CTA. No pricing here
3. **This week's flavours** — circular photo grid, hover/tap reveals the description
4. How it works — three steps: pick a size, fill it, free campus delivery
5. Freshness + allergy strip — two lines, links to FAQ
6. Events teaser — one line, links to Events
7. Footer

### Flavors & Pricing
Full flavor grid with descriptions → box pricing table → build-a-box entry → allergy notice. This is the only page where pricing is prominent.

### Order (build a box)
Its own route, not buried in a tab. Pick size → fill slots → allergy acknowledgement → delivery details → Square checkout.

### About · Events · FAQ · Contact
Standard single-column pages. Events carries the collapsible inquiry form.

---

## The ordering CTA

The agreed six-tab nav has no "Order" entry, yet ordering is the entire point of the site. Rather than break the agreed structure, ordering gets a **persistent CTA outside the nav** — sticky at the bottom of the viewport on mobile, always one tap away, showing the box state once a box is started ("3 of 6 chosen").

This is worth confirming, since it affects every page's layout.

---

## Box builder

The one interaction that must not be got wrong. Rules:

- Slots are drawn as empty circles matching the chosen size — 1, 3, 6, or 12
- Tapping a flavor fills the next empty slot; tapping a filled slot empties it
- Remaining count always visible ("3 more to go")
- Checkout is **disabled** until the box is exactly full — never an error message after the fact
- Adding to a full box is refused at the source: flavors go visually inert rather than erroring
- Same flavor repeatable — 6 of one flavor is a valid box
- Changing size down mid-build must warn before discarding picks

Drag-and-drop is the eventual ideal. Tap-to-fill is the v1, and it satisfies the constraint completely.

---

## Mobile behavior

Everything is designed at 390px first. Six nav items go behind a hamburger; the order CTA never does. Hover states need tap equivalents — on touch, first tap reveals a flavor's description, second adds it, or the description sits permanently visible under the label.

---

## Photography brief

The single biggest gap between where the site is and the Crumbl-inspired look. Current placeholders are phone snaps with kitchen backgrounds, uneven lighting, and three flavors with no dedicated shot at all.

What the shoot needs:

- **One cookie per flavor, alone in frame**
- **Top-down**, straight overhead, consistent for every flavor
- **Plain background** — parchment or a cream surface close to `#f4e7d1` so the crop blends into the page
- **Soft, even, indirect light.** Near a window, no direct sun, no flash, no harsh shadow
- **Consistent distance and framing** so the cookie occupies the same fraction of every circle
- **Square, roughly 1200×1200 or better**, since everything gets circle-cropped
- Shoot all seven in one session — consistency between shots matters more than any individual shot

Optional but worth it: one wide "hero" shot of a full open box for the homepage, and one of Krista baking for the About page. Hands and process shots are what make a home business read as real rather than generic.
