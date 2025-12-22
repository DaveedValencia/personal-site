# daveedvalencia.com

Personal website of **David Valencia** — an ecommerce operator publishing AI Visibility playbooks and ecommerce audits that explain how brands show up across AI search, web, and retention.

Hosted via **GitHub Pages** for full control over HTML, schema, and LLM-readiness.

---

## Overview

This is a static site (HTML + CSS) designed to be:
- Fast – no frameworks, no build steps.
- Accessible – WCAG-AA compliant navigation and color contrast.
- Search/LLM-friendly – structured data (JSON-LD + `/llm-visibility.json`).
- SEO-ready – proper metadata, RSS, and sitemap.
- Secure – strong Content-Security-Policy and minimal external dependencies.

Deployed automatically from the `main` branch using GitHub Pages.

---

## Structure

```text
/
├── index.html
├── contact/index.html
├── ai-visibility/
│   ├── index.html
│   ├── feeds-vs-structure-llm-visibility/index.html
│   ├── how-to-optimize-for-ai-search/index.html
│   ├── what-is-llm-visibility/index.html
│   ├── what-is-llm-philosophy/index.html
│   ├── context-and-ai/index.html
│   ├── weve-mistaken-efficiency-for-evolution/index.html
│   └── how-to-control-chat-bias/index.html
├── assets/
│   ├── css/base.css
│   └── img/david-valencia.jpg
├── feed.xml
├── sitemap.xml
├── robots.txt
├── llm-visibility.json
├── CNAME
└── README.md
```

Highlights:
- `/llm-visibility.json` → machine-readable metadata for AI/search.
- `/feed.xml` → RSS feed.
- `/sitemap.xml` → search and crawler visibility.
- `/assets/css/base.css` → single lightweight stylesheet.

---

## Key Features

### AI Visibility & Schema
- `Organization`, `Person`, and `BlogPosting` JSON-LD embedded on each page.
- Custom `/llm-visibility.json` endpoint linked in `<head>`.
- Validate using [validator.schema.org](https://validator.schema.org) and [Google Rich Results Test](https://search.google.com/test/rich-results).

### Accessibility
- Semantic landmarks (`header`, `nav`, `main`, `footer`).
- Keyboard-friendly skip link and menu.
- Color contrast and focus outlines verified for WCAG AA.

### Security
- Inline `<meta http-equiv="Content-Security-Policy">` restricting sources to self (plus Beehiiv on the contact subscribe embed).
- `rel="noopener noreferrer"` on all external links.

### Analytics
- GA4 (G-VVS4STC36K) loads site-wide via gtag.js.

### Newsletter
- Beehiiv-powered iframe embed lives on the contact page subscribe section (`/contact/#subscribe-title`).

### Performance
- Lighthouse score ≥ 95 (desktop).
- Minimal DOM, optimized assets, no render-blocking scripts.

---

## Local Development

1. Clone the repo.

   ```bash
   git clone https://github.com/yourusername/daveedvalencia.com.git
   cd daveedvalencia.com
   ```

2. Optional: start a local server.

   ```bash
   python3 -m http.server 4000
   ```

   (VS Code Live Server or similar works too.)

3. Edit content as needed:
- AI posts: `/ai-visibility/<slug>/index.html`
- Styles: `/assets/css/base.css`
- JSON context: `/llm-visibility.json`

4. Preview at `http://localhost:4000`.

---

## Deployment

Push to the `main` branch and GitHub Pages will rebuild automatically. Repository settings should map Pages → Branch: `main`, folder: `/` (root). Custom domain is configured via `CNAME` (`daveedvalencia.com`).

---

## Validation and QA

| Check            | Tool                                      |
|------------------|-------------------------------------------|
| HTML validity    | https://validator.w3.org/                 |
| Schema           | https://validator.schema.org/             |
| Lighthouse       | Chrome DevTools → Lighthouse               |
| RSS              | https://validator.w3.org/feed/            |
| Security headers | https://securityheaders.com/              |
| Accessibility    | Wave or Axe browser extensions            |

---

## Customization

- Update GA4 settings in each page head if you rotate properties.
- Update the Beehiiv embed snippet (form ID or styling) in the contact page subscribe section as needed.
- Adjust colors and fonts via `:root` variables in `/assets/css/base.css`.
- Swap `/assets/img/david-valencia.jpg` with the final 1200×630 OG image.
- Refresh `<title>`, `<meta name="description">`, canonical URLs, and `lastUpdated` in `/llm-visibility.json` before publishing.

---

## License

All code © 2025 David Valencia. Content licensed under CC BY-NC 4.0. You may reference or fork for educational purposes with attribution.

---
 
Contact: `david@minnesota.ai`
Twitter/X: `@daveedvalencia`  
GitHub: `github.com/DaveedValencia`
All other socials: `@daveedvalencia`  
