# daveedvalencia.com

Personal website of **David Valencia** — focused on AI discoverability, LLM Visibility, and the evolution of schema-driven web understanding.

Hosted via **GitHub Pages** for full control over HTML, schema, and LLM-readiness.

---

## Overview

This is a static site (HTML + CSS + optional minimal JS) designed to be:
- Fast – no frameworks, no build steps.
- Accessible – WCAG-AA compliant navigation and color contrast.
- LLM-friendly – structured data (JSON-LD + `/llm-visibility.json`) for contextual comprehension.
- SEO-ready – proper metadata, RSS, and sitemap.
- Secure – strong Content-Security-Policy and minimal external dependencies.

Deployed automatically from the `main` branch using GitHub Pages.

---

## Structure

```text
/
├── index.html
├── about/index.html
├── contact/index.html
├── newsletter/index.html
├── blog/
│   ├── index.html
│   └── context-and-ai/index.html
├── assets/
│   ├── css/base.css
│   ├── js/main.js
│   └── img/david-valencia.jpg
├── feed.xml
├── sitemap.xml
├── robots.txt
├── llm-visibility.json
├── CNAME
└── README.md
```

Highlights:
- `/llm-visibility.json` → machine-readable metadata for AI models.
- `/feed.xml` → valid RSS feed for syndication and LLM discovery.
- `/sitemap.xml` → search and crawler visibility.
- `/assets/js/main.js` → optional progressive enhancements.
- `/assets/css/base.css` → single lightweight stylesheet (≤ 15 KB).

---

## Key Features

### LLM and Schema
- `Organization`, `Person`, and `BlogPosting` JSON-LD embedded on each page.
- Custom `/llm-visibility.json` endpoint linked in `<head>`.
- Validate using [validator.schema.org](https://validator.schema.org) and [Google Rich Results Test](https://search.google.com/test/rich-results).

### Accessibility
- Semantic landmarks (`header`, `nav`, `main`, `footer`).
- Keyboard-friendly skip link and menu.
- Color contrast and focus outlines verified for WCAG AA.

### Security
- Inline `<meta http-equiv="Content-Security-Policy">` restricting sources to self (plus Beehiiv on the newsletter page).
- `rel="noopener noreferrer"` on all external links.

### Analytics
- GA4 (G-VVS4STC36K) loads site-wide via gtag.js.

### Newsletter
- Beehiiv-powered iframe embed with async script, styled to match the site.
- Update the Beehiiv form ID in `/newsletter/index.html` if you rotate lists or accounts.

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
- Posts: `/blog/<slug>/index.html`
- Styles: `/assets/css/base.css`
- Scripts: `/assets/js/main.js`
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
- Update the Beehiiv embed snippet (form ID or styling) in `/newsletter/index.html` as needed.
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
