# Blog Publishing PRD

This document captures the requirements, cross-page dependencies, and QA checks for shipping a new blog post on daveedvalencia.com. Follow it each time you publish to keep the site structured, discoverable, and consistent with current best practices.

## Objectives
- Maintain a repeatable workflow so every post launches with complete metadata, structured data, and cross-page links.
- Ensure the homepage, category landing pages, sitemap, RSS feed, and machine-readable assets stay in sync.
- Preserve analytics, accessibility, and governance standards (CSP, skip links, author attribution, etc.).

## Source of Truth
- Each post lives at `<category>/<slug>/index.html` (e.g., `ai-visibility/how-to-optimize-for-ai-search/index.html`) with canonical URL `https://daveedvalencia.com/<category>/<slug>/`.
- Post metadata (title, description, timestamps, word count, reading time) is encoded in both HTML `<head>` tags and JSON-LD.
- Global feeds: `feed.xml`, `sitemap.xml`, and `llm-visibility.json`.

## Authoring Requirements
### Content
- Write or edit the article in HTML using existing post structure (article header, lead paragraph, section headings, etc.).
- Verify inclusive ASCII punctuation unless curly quotes are intentional (copy existing style where needed).
- Calculate word count and reading time (rounded to nearest minute; 200–250 wpm baseline).

### Metadata
- `<title>` and `<meta name="description">` tuned for search and sharing.
- `<meta property="og:*">` and `<meta name="twitter:*">` mirrors title/description; reuse hero image unless a custom asset exists.
- `<link rel="canonical">` points to live URL with trailing slash.
- `<meta property="article:published_time">` and `article:modified_time` use ISO-8601 with timezone offset (current convention: `T08:00:00-06:00`).
- `<time datetime>` inside the article reflects the same publish date.

### JSON-LD
- Copy the existing schema graph pattern.
- Update `@id`, `headline`, `description`, `datePublished`, `dateModified`, and `wordCount`.
- Include relevant `about` topics and `articleSection` headings (use concise, descriptive phrases).
- Confirm `mainEntityOfPage` matches the canonical URL.

## Cross-Page Updates
1. **Category landing page (`/ai-visibility/`)**
   - Insert the new post at the top of that section’s ordered list.
   - Update summary blurb and reading time.
2. **Homepage (`index.html`)**
   - Refresh any featured card or copy that should highlight the new post (one per category).
   - Ensure category descriptions still reflect available work.
3. **RSS Feed (`feed.xml`)**
   - Update `<lastBuildDate>` to publish date (YYYY-MM-DD).
   - Add a new `<item>` with title, link, GUID (same as link), `pubDate`, and concise description.
4. **Sitemap (`sitemap.xml`)**
   - Add `<loc>` entry for the new post URL (maintain alphabetical or logical order used previously).
5. **LLM Visibility Manifest (`llm-visibility.json`)**
   - Append any new topics introduced by the post.
   - Refresh `"lastUpdated"` (YYYY-MM-DD).
6. **Legacy blog redirect (`/blog/<slug>/index.html`)**
   - Create/update the meta-refresh shim so historical links forward to the new canonical URL.
7. **Canonical Feed References**
   - Verify `<link rel="alternate">` references in the post’s `<head>` still point to `/feed.xml` and `/llm-visibility.json`.

## Structured Content Checklist
- [ ] New folder and `index.html` created under `<category>/<slug>/`.
- [ ] Head metadata reflects post content and publish date.
- [ ] JSON-LD validates against schema.org BlogPosting.
- [ ] Article body uses semantic HTML (headings, lists, paragraphs).
- [ ] All internal links are absolute (start with `/`).

## QA & Validation
- Run manual lint: open in browser or local preview to confirm layout and navigation.
- Validate HTML with a quick pass (e.g., browser dev tools) if time permits.
- Spot-check RSS item formatting (well-formed XML, proper encoding).
- Confirm sitemap remains valid XML (no trailing commas, proper nesting).
- Verify the new post appears on the homepage (if surfaced) and the relevant category page without breaking layout.
- Double-check dates across all surfaces match.

## Release Notes / Versioning
- Update `README.md` (optional) if workflow or requirements change.
- Commit message convention: `Add <slug> blog post` plus summary of ancillary updates.

## Future Enhancements (parking lot)
- Script helper to calculate word count/reading time and inject into template.
- Automated schema and HTML validation as part of pre-commit hook.
- Dedicated metadata manifest to drive landing pages/feed generation programmatically.

Keep this PRD in sync as standards evolve. When a new best practice is adopted, document it here before or during implementation.***
