# AES Collective — Website Development Plan

**Date:** 2026-01-14 (updated from AES Collective project)
**Status:** PLANNED
**Project Root:** `~/projects/aes-collective/`

---

## 1. Brand Identity — Extracted from CIS_Branded_v2.docx

### Logo
- **Geometry:** Hexagon outer shape, dashed inner hexagon, gray diamond core
- **Text:** "AES" bold black + yellow underline; "COLLECTIVE" in yellow below; "SINGAPORE" in light gray
- **Extracted asset:** `logo.jpg` (1568×756, 43KB) — saved to `~/projects/aes-collective/logo.jpg`
- **Aspect ratio:** ~2:1 (wide rectangular logo — works well as header banner)

### Color Palette (from docx theme)
| Name | Hex | Use |
|---|---|---|
| Navy | `#0E2841` | Primary backgrounds, headers, nav |
| Teal Blue | `#156082` | Primary accent, buttons, links |
| Burnt Orange | `#E97132` | CTAs, highlights, energy sector accent |
| Light Gray | `#E8E8E8` | Backgrounds, dividers |
| Light Blue | `#0F9ED5` | Secondary links, highlights |
| Green | `#196B24` / `#4EA72E` | Success, approvals, certification badges |
| Purple | `#A02B93` | Sparse accent use |

### Typography (from docx styles)
- Headers: Bold, likely sans-serif (to confirm from final logo font)
- Body: Clean professional sans-serif
- Tagline: "Strictly Private & Confidential" — watermark-style, understated

---

## 2. Website Scope

### Goal
A modern, professional corporate website for AES Collective Pte. Ltd. — an international commodity trading company specializing in Oil & Gas, Energy, Metals, and Agriculture.

### Target Audience
- Counterparties (buyers/sellers of Diesel, LNG, LPG, Crude Oil)
- Banks & financial institutions (KYC reference)
- Regulatory / compliance teams

### Tone
Professional, authoritative, discreet. "Strictly Private & Confidential" as a brand value, not just a document watermark.

---

## 3. Proposed Site Architecture

```
/ (Home)
/about          — Company profile, registration info
/commodities    — Product lines (Energy, Metals, Agriculture)
/trade-process  — ICPO → SPA → PPOP → Shipment → Settlement
/credentials    — KYC/AML, certifications, SGS/BV/Intertek
/contact        — Singapore office, email
```

**Single page options** (landing page with anchor sections) also viable given small team.

---

## 4. Section Content Plan

### Nav Bar
- Logo (left) + AES wordmark
- Links: About · Commodities · Trade Process · Credentials · Contact
- Tagline: "Strictly Private & Confidential" (small, top-right or footer)

### Hero Section
- Full-width banner with company name + tagline
- Navy background (`#0E2841`) with teal/white text
- Burnt orange CTA: "View Our Commodities" or "Contact Us"
- Background texture: subtle geometric / hexagonal (echo logo shape)

### About Section
- Company name: AES Collective Pte. Ltd.
- Entity: Exempt Private Company, Singapore · UEN: 202135481Z
- Director: Lim Chin Poh
- Registered: 37 Lorong 23 Geylang, #07-04, Yu Li Industrial Building, Singapore 388371
- Capital: SGD 100,000 fully paid
- Status: Live, ACRA verified 30 March 2026

### Commodities Section
**3 cards:** Energy | Metals | Agriculture

**Energy — Primary focus (SSIC 46610)**
- Diesel EN590 10 PPM
- LNG (Liquefied Natural Gas)
- LPG (Liquefied Petroleum Gas)
- Crude Oil (Spot & Contract)

**Metals**
- TBD — define specific products

**Agriculture**
- TBD — define specific products

### Trade Process Section
Flow visualization: ICPO → SPA → PPOP → Shipment → Settlement
- 2% Performance Bond
- 12–36 month SPA options
- SGS / BV / Intertek certified at every delivery point

### Credentials Section
- No PEP / No Sanctions
- Full KYC package available on request
- 100% beneficial ownership disclosed
- SGS / BV / Intertek third-party inspections

### Contact Section
- Email: energy@aescollective.sg
- Website: www.aescollective.sg
- Address: 37 Lorong 23 Geylang, #07-04, Yu Li Industrial Building, Singapore 388371
- Director: Lim Chin Poh

---

## 5. Technical Approach

### Option A: Static HTML/CSS/JS (Simplest — recommended)
- Single `index.html` with CSS sections
- Mobile responsive
- No backend needed — purely informational
- Deploy: Netlify / Vercel / Cloudflare Pages (free tier)

### Option B: Next.js / React
- Better for future dynamic content
- Components for: Hero, CommodityCard, ProcessFlow, ContactForm

### Option C: WordPress (if client needs CMS)
- WPCrawler / elementor workflow

### Recommended Stack
- **Astro** or **plain HTML + Tailwind** — fast, clean, professional
- Domain: www.aescollective.sg (or placeholder until domain ready)
- Hosting: Vercel (recommended for speed + Singapore edge nodes)

---

## 6. Design System

### Colors (CSS variables)
```css
--navy:    #0E2841;
--teal:    #156082;
--orange:  #E97132;
--ltgray:  #E8E8E8;
--ltblue:  #0F9ED5;
--green:   #196B24;
--white:   #FFFFFF;
```

### Typography
- Headings: Inter or Poppins (bold, clean)
- Body: Inter (400/500 weight)
- Accent font: Monospace for UEN/registration numbers (professional, document-like)

### Layout
- Container: max-width 1200px, centered
- Section padding: 80px vertical (desktop), 48px (mobile)
- Card grid: 3-col commodities, 2-col process steps
- Hexagon motif as decorative backgrounds (SVG pattern overlay at low opacity)

---

## 7. Assets Available

| File | Description |
|---|---|
| `logo.jpg` | Full logo banner (1568×756, extracted from CIS docx) |
| `CIS_AES_Collective_Pte_Ltd.pdf` | Original KYC PDF |
| `CIS_Branded_v2.docx` | Branded client information sheet |
| `SKILL.md` | Company playbook (all identity data) |

---

## 8. Implementation Phases

### Phase 1: Foundation
- [ ] Create `website/` folder in `~/projects/aes-collective/`
- [ ] Set up HTML skeleton with nav, hero, all sections
- [ ] Apply CSS design system (colors, typography, layout)
- [ ] Add `logo.jpg` as hero background or header logo
- [ ] Mobile responsive breakpoint testing

### Phase 2: Content
- [ ] Populate About section with company registration data
- [ ] Write Commodities section (Energy primary, list all products)
- [ ] Build Trade Process flow diagram (SVG or CSS steps)
- [ ] Populate Credentials section
- [ ] Add Contact section with email + address

### Phase 3: Polish
- [ ] Hexagon SVG pattern overlay on navy sections
- [ ] Burnt orange CTA button hover effects
- [ ] Smooth scroll between sections
- [ ] Favicon (hexagon icon)
- [ ] Meta tags (SEO: "AES Collective Singapore — International Commodity Trading")

### Phase 4: Launch
- [ ] Domain pointing (www.aescollective.sg or placeholder)
- [ ] Vercel/Netlify deploy
- [ ] Test across browsers
- [ ] Google Search Console submission

---

## 9. Open Items (from SKILL.md — still relevant)

- [ ] Define specific commodity lines to prioritize (Energy vs Metals vs Agriculture) — Energy confirmed as primary
- [ ] Identify target buyers/sellers in Asia-Pacific, Europe, Africa — leave blank for now, contact form captures leads
- [ ] Draft ICPO / SPA templates — not needed for website
- [ ] Confirm branding font from logo file — can infer from logo.jpg analysis
- [ ] Clarify relationship with Invictus SVF / other parent entities — keep separate

---

*Plan prepared by: Hermes Agent (Riley / dc9db953)*
*Files location: `~/projects/aes-collective/website/`*