# AES Collective — Marketing Website

Static, no-build marketing site for **AES Collective Pte. Ltd.** (Singapore-registered energy trading firm). Built with plain HTML and a small custom CSS layer.

## Stack

- Plain HTML (one file per page) — no build, no bundler
- Custom CSS (`assets/css/site.css`) with CSS variables for brand tokens
- ~30 lines of vanilla JS (`assets/js/site.js`) for mobile nav, scroll reveal, year stamp
- Google Fonts: Cormorant Garamond (display) + Inter (UI)
- Inline SVG hexagon motif faithful to the logo
- Mailto-based CTAs (no form backend)

## Pages

| Page | File |
|---|---|
| Home | `index.html` |
| Products | `products.html` |
| Process & Trade Finance | `process.html` |
| Global Reach | `reach.html` |
| Compliance | `compliance.html` |
| Contact | `contact.html` |

## Brand Tokens

| Token | Hex | Role |
|---|---|---|
| `--navy` | `#2D2E30` | Headings, nav, primary text |
| `--gold` | `#D2AC47` | Accents, CTAs, dividers |
| `--taupe` | `#CFCBBF` | Subtle backgrounds, footer text |
| `--bg` | `#FFFFFE` | Page background |
| `--bg-alt` | `#F7F5F0` | Section variation |
| `--ink` | `#1A1B1D` | Body copy |

## Local Preview

From this folder:

```powershell
# Python (any version 3.x)
python -m http.server 8000
```

Then open <http://localhost:8000>.

> Opening `index.html` via `file://` mostly works but the Google Maps embed and Google Fonts require an HTTP server for full fidelity.

## Editing Header / Footer

Header and footer markup is duplicated into every page so the site has zero build step. The canonical source lives in `partials/_header.html` and `partials/_footer.html`. Each page wraps those regions in:

```html
<!-- @partial:header -->
…
<!-- @endpartial -->
```

When changing the nav or footer:

1. Edit the partial file under `partials/`.
2. Paste the updated content into every page between the `@partial` / `@endpartial` markers.
3. On any non-home page, set `class="active"` on the matching `<a data-nav="…">` link.

## Deployment

Drag-and-drop the folder into:

- **Netlify** → drop `aes-collective/` on app.netlify.com/drop
- **Cloudflare Pages** → "Direct upload" project, upload the folder
- **Vercel** → `vercel deploy --static` from this directory
- **Any static host / S3 / nginx** — copy the folder, serve `index.html` at root

Point the `www.aescollective.sg` DNS to the chosen host.

## Folder Layout

```
aes-collective/
├── index.html                      # Home
├── products.html                   # Diesel EN590, LNG, LPG, Crude
├── process.html                    # 6-step settlement + trade finance
├── reach.html                      # Asia-Pacific / Europe / Africa + world map
├── compliance.html                 # ACRA, KYC/AML, inspectorates
├── contact.html                    # Office, email, embedded map
├── assets/
│   ├── css/site.css                # All custom styling
│   ├── js/site.js                  # Nav, reveal, year stamp
│   ├── img/
│   │   ├── logo.png                # Brand mark (from CIS)
│   │   └── favicon.svg             # Hex motif favicon
│   └── svg/
│       └── hexmark.svg             # Logo motif for reuse
├── partials/
│   ├── _header.html                # Canonical header source
│   └── _footer.html                # Canonical footer source
└── README.md
```

## Accessibility & Performance Notes

- Semantic landmarks (`<header>`, `<nav>`, `<main>`, `<footer>`)
- Focus-visible ring in gold
- IntersectionObserver-based reveals with graceful fallback
- No third-party JS frameworks; total payload well under 200 KB excluding the logo PNG and Google Fonts
- Mobile breakpoint at 900px; drawer-style mobile nav

## Content Sources

All copy is derived from the company's branded materials:

- `AES_Collective_CIS_Branded V2.docx` — Corporate identity, voice, regulatory data
- `Energy Profile (AES Collective) v1 13.05.2026.pptx` — Product specs, process, reach, compliance

No fabricated numbers, certifications, or counterparty claims.
