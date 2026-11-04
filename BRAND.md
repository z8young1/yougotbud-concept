# YouGotBud brand, as found on yougotbud.com

Pulled from the live DOM in Chrome on 2026-11-03 (computed styles and the `.dark` CSS custom properties; the site always renders in dark mode).

## Colors

The brand is monochrome. The only chromatic color the site uses on purpose is an emerald green for success and growth signals (the "Sync Successful" badge, the green percent chips in the dashboard).

| Role | Hex | Source |
|---|---|---|
| Page background | `#0a0a0a` | `--background`, body background |
| Text | `#fafafa` | `--foreground`, body color |
| Card / raised surface | `#171717` | `--card`, `--popover` |
| Secondary surface, inputs | `#262626` | `--secondary`, `--muted`, `--accent` |
| Muted text | `#a1a1a1` | `--muted-foreground` |
| Section labels (mono) | `#9e9e9e` approx | h2 computed color lab(66.1) |
| Primary button fill | `#e5e5e5` | `--primary` (button text `#171717`) |
| Hairline border | `#ffffff` at 10% | `--border` |
| Input border | `#ffffff` at 15% | `--input` |
| Focus ring | `#737373` | `--ring` |
| Signal green | `#00bc7d` | sync badge background (emerald 500) |
| Signal green, deep | `#004f3b` | sync badge icon |
| Light theme ink (unused live) | `#0a0a0a` on `#ffffff`, primary `#171717` | `:root` values |

Also defined but not part of the visible brand: chart colors `#1447e6`, `#00bb7f`, `#f99c00`, `#ac4bff`, `#ff2357` and destructive `#ff6568` (stock shadcn/ui tokens).

## Fonts

- **Geist** (Vercel), weights 400 to 600: all headings and body. H1 is 60px, weight 500.
- **Geist Mono**: section labels ("INTEGRATIONS", "SEO THAT SCALES"), 14px, weight 600, slight negative tracking.
- **JetBrains Mono**: code sample in the API section.
- Also loaded but not visibly used: Inter, Super Sans VF.

The redesign uses Geist (display and body) and Geist Mono (labels, data, code), both from Google Fonts.

## Logo files (`assets/`)

| File | What it is |
|---|---|
| `logo-mark.svg` | The Y-and-leaf mark, extracted from the header's inline SVG, `fill="currentColor"` so it takes the text color |
| `icon.png` | 640x640 mark, from `/icon.png` |
| `favicon.ico` | 32x32 favicon |
| `og-image.png` | Social share image (mark in a device frame), resized to 1200x630 |

There is no separate wordmark file; the site sets "YouGotBud" in Geist next to or beneath the mark.

## Other images reused

- `dashboard-dark.png`: product dashboard screenshot (hero)
- `kiosk.jpg`: branded kiosk with plants (kiosk ordering)
- `clients/`: Ript, B leaf, Trees, Cannabis of Worcester, Canna Corner, The Verb is Herb, Anja (mostly white artwork for dark backgrounds; Canna Corner and The Verb is Herb are dark artwork that the live site inverts with CSS)
- `integrations/`: Alpine IQ, Springbig, Google Tag Manager, Google Analytics, Flowhub, Metrc
- `products/`: four product photos from the inventory table (Simply Herb Jupiter, Pioneer Valley Guava OG, Fernway Sour PUTS, Fernway Mountain Girl)
