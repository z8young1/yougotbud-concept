# YouGotBud website redesign

A redesign of https://www.yougotbud.com/, built by Increasing Customers as a pitch for the You Got Bud partnership meeting (Scottsdale, November 2026). It keeps YouGotBud's real logo, its exact monochrome palette and its Geist type family, and carries over every piece of content on the current site.

Plain HTML and CSS with a few lines of vanilla JS (mobile menu and the placeholder form). No framework, no build step.

## View it locally

```bash
cd ygb-site && python3 -m http.server 8787
```

Then open http://127.0.0.1:8787/ in Chrome. Opening `index.html` straight from disk also works; only the Google Fonts load needs a network connection.

## What's in this folder

| Path | What it is |
|---|---|
| `index.html` | The site. The current yougotbud.com is a single page, so the redesign is too. |
| `styles.css` | The one stylesheet |
| `site.js` | Mobile menu toggle; stops the placeholder form from posting |
| `assets/` | Logo mark (SVG, extracted from the live header), favicon, icon, share image, dashboard screenshot, kiosk photo, client logos, integration logos, product photos. All downloaded from yougotbud.com and its imgix bucket. |
| `source/home.md` | Full text capture of the live site, section by section, typos included |
| `source/home.raw.html` | Raw server HTML of the live home page |
| `BRAND.md` | Colors, fonts and logo files pulled from the live DOM |
| `screenshots/` | Full-page captures at 1440px and 375px |

## Design notes

- Palette is only what the live site uses: ink `#0a0a0a`, graphite `#171717`, slate `#262626`, paper `#fafafa`, silver buttons `#e5e5e5`, muted text `#a1a1a1` / `#737373`, and emerald `#00bc7d` as the single accent (taken from the site's "Sync Successful" badge). Dark and paper sections alternate for rhythm.
- Type is Geist for headlines and body, Geist Mono for labels, numbers and code, matching the live site.
- Services are an editorial ruled list instead of icon cards. The product mockups (inventory sync, chat, discounts, SEO editor) are rebuilt in HTML with the original sample data and product photos, so they stay sharp and readable.
- Responsive from 360px up. The site checks clean at 1440px, 375px and 360px with no horizontal scroll.

## Content map

The live site has one page. Its menu items are anchors into that page, and the redesign keeps the same menu, in the same order, pointing at the same content.

| Original (yougotbud.com) | Original anchor | Where it lives now |
|---|---|---|
| Page title and meta description | `<head>` | `<head>`; the meta description's "marketing, licensing and consulting ... analytics, POS integration, industry guidance" line is also the Services intro |
| Header: logo, menu (Home, Licensing, Marketing, Consulting, Point of Banking, SEO, Integrations, Universal API, Book a demo), Book a demo button | header | Header nav, same order. Licensing and Marketing now jump to their own rows; Consulting goes to the Services section as before |
| Hero headline, subline, Book a demo | top | Hero |
| Dashboard screenshot | top | Hero image (`assets/dashboard-dark.png`) |
| Client logo strip (Ript, B leaf, Trees, Cannabis of Worcester, Canna Corner, The Verb is Herb, Anja) | top | Logo row under the hero |
| Stats: 2000+ marketing campaigns, $150M+ cannabis sold, 18+ licenses obtained | `#stats` | Stats band, `#stats` |
| Services: Marketing, Software Development, E-Commerce (with Kind Pen link), TV Menu, Licensing, Lending & Financing | `#learn-more` | Services list, `#learn-more` (rows `#marketing`, `#software`, `#ecommerce`, `#tv-menu`, `#licensing`, `#financing`) |
| Inventory table (4 products, prices), Sync Successful toast, Realtime Point of Sale Sync | `#features` | Platform section, `#features` |
| Enhanced Kiosk Ordering and kiosk photo | `#features` | Platform section |
| Customer chat example and Customer Chat | `#features` | Platform section |
| Discount examples (Standard, BOGO, Bundle) and Advanced discounts | `#features` | Platform section |
| Integrations: Alpine IQ and Springbig, Google Analytics and Tag Manager, Flowhub, Metrc | `#integrations` | Integrations, `#integrations` |
| SEO that scales: template editor, Greenleaf preview, Inline Template Variables, Individual page editing | `#seo` | SEO section, `#seo` |
| Payment services: intro and six offerings (Point of Banking, Free Debit Terminals, Tap to Pay, Tipping Options, Competitive Rebates, Live Backend) | `#payments` | Payments, `#payments` |
| Universal API: headline, intro, full "Fetching products" curl and JSON sample | `#api` | API section, `#api` (full sample, unchanged) |
| Free demo form (First Name, Last Name, Business Name, Business Location, Email, Phone Number) | `#demo` | Demo section, `#demo`, same six fields |
| Footer: © YouGotBud 2026, GitHub, LinkedIn, X, large wordmark | footer | Footer, plus a repeat of the menu |

## Edits to the original copy

Light edits only, no new facts:

- Fixed typos: "Weather" to "Whether", "vaporizors" to "vaporizers", "Competative" to "Competitive", "Were all out" / "Ill take" to "We're all out" / "I'll take", "wednesday" to "Wednesday".
- The six payment cards each ended with "We offer a range of payment options to help you grow your business." That sentence now appears once, in the payments intro.
- Section headlines that the live site doesn't have ("Everything a dispensary runs on, from one team.", "Connected to the systems your store already uses.", "Every menu page, written for search.") are framing lines over the site's own content. The Platform headline reuses the site's own E-Commerce sentence.
- The API sample is code and is reproduced exactly, including its own spellings ("wizzards", "ranbow", "stainType").

## Known gaps and things to confirm with YouGotBud

- The live site has no phone number, email, street address, hours, pricing, team, testimonials, FAQ, privacy policy or terms page, so the redesign has none either. A privacy policy and a contact block are worth adding once YouGotBud supplies them.
- The footer GitHub link (`github.com/yougotbud/yougotbud`) returns 404 on GitHub, and so does the `yougotbud` account. It's kept because it's on the live site, but it should be fixed or removed.
- The demo form posts nowhere. Its `action` is the placeholder `#demo-request-endpoint-placeholder`, and `site.js` intercepts submit and shows a "not connected yet" note. Point it at YouGotBud's real endpoint before launch.
- The client logo images come in mixed colors; two (Canna Corner, The Verb is Herb) are inverted with CSS, just as on the live site.
