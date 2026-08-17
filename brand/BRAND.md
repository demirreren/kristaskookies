# Krista's Kookies — Brand Reference

## Fonts
- **Headings / titles** (e.g. "Flavour Menu", "Ordering"): **Candice**
- **Flavor labels** (under cookie photos): **Loubag**
- **Body text** (paragraphs, FAQ, ordering info): **Open Sauce**

## Colors
| Role | Hex | Notes |
|---|---|---|
| Background (primary) | `#f4e7d1` | Warm cream, used across most pages |
| Background (alt) | `#f0e8d3` | Near-duplicate cream — kept for reference, prefer primary above |
| Text (primary) | `#3c2519` | Warm brown, body copy |
| Text (accent / headers) | `#000b3d` | Navy, used for script headings on flavor menu |
| Modal / card background | `#e1cfb3` | Tan, for cards, order forms, popups |
| Accent (seasonal/promo) | `#ffd6d6` | Soft pink, used for Mother's Day-style promos, not core UI |

## Logo
`logo.png` — 461×461, RGBA with clean antialiased transparency. Circular cream disc scattered with sprinkles, the "Krista's Kookies" wordmark, and a smiling cookie mascot in a chef's hat. The disc runs edge to edge, so apply any padding in layout rather than expecting margin in the file.

**This version includes the cartoon cookie face.** See the note in `PROJECT.md` — a face-free variant was previously requested, and it is unconfirmed which is canonical.

Colors measured from the file. They predate the standardization below and do **not** match the UI tokens:

| Element | Hex |
|---|---|
| Disc | `#f1e9d4` |
| Wordmark ink | `#774a2d` |
| Outline / wordmark shadow | `#bb7d44` |
| Sprinkles | `#d6b38c` |
| Chef's hat | `#f0e3db` |
| Mascot face | `#ffffff` |

Open question: leave these as a fixed brand mark, or nudge them onto the token palette. `#774a2d` and `#bb7d44` are untracked and will appear on every page.

No vector version exists. 461px is comfortable for on-screen use up to roughly 230px displayed at 2× density; anything larger — a hero image, print, stickers — wants an SVG or PDF export from the original design file.

## Notes
- Prior designs mixed two similar creams (`#f4e7d1` / `#f0e8d3`) and two text colors (navy / brown). For the website, standardize on `#f4e7d1` background + `#3c2519` body text, using `#000b3d` navy as an accent for script-style headers only.
- Pink accent is reserved for seasonal/promo moments, not everyday UI.
