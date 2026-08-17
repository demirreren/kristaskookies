# kristaskookies

Website for Krista's Kookies — a home-based cookie business serving Western University's campus.

> **Designing from this repo?** [`DESIGN-BRIEF.md`](DESIGN-BRIEF.md) is the authoritative spec — brand, colours, type, page structure, copy, and the box-builder rules, all decided. Assets are in `brand/logo.png` and `assets/photos/`.
>
> Ignore [`PROJECT.md`](PROJECT.md) (payments and business operations, not design) and `content/ordering.json` (contains a disputed second price list). Where docs disagree, `DESIGN-BRIEF.md` wins.

## Project docs
- [`PROJECT.md`](PROJECT.md) — business details, site structure, the build-a-box requirement, and the Square payments/orders approach
- [`DESIGN.md`](DESIGN.md) — art direction, typography, page structure, photography brief
- [`COPY.md`](COPY.md) — all site copy, page by page
- [`DESIGN-BRIEF.md`](DESIGN-BRIEF.md) — self-contained brief to paste into a design tool
- [`assets/photos/`](assets/photos/) — placeholder photography extracted from the Flavour Menu PDF

## Brand guidelines
See [`brand/BRAND.md`](brand/BRAND.md) for fonts, colors, and usage notes, and [`brand/design-tokens.json`](brand/design-tokens.json) for the machine-readable token values (use this as the source of truth when wiring up CSS variables / theme config).

## Ordering content (pricing & allergy notice)
See [`content/ORDERING.md`](content/ORDERING.md) for pricing and the allergy notice copy, and [`content/ordering.json`](content/ordering.json) for the machine-readable source of truth when wiring these into the site's order form / FAQ.