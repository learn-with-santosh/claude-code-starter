---
name: seo-audit
description: Run a full SEO audit on a website or codebase. Triggers on "seo", "audit", "ranking", "meta tags", "search visibility", "google", "traffic", "improve site".
allowed-tools: Read, Bash, Grep, Glob
---

# SEO Audit Skill

## Audit Checklist

### 1. On-Page SEO
- [ ] `<title>` tag — unique, 50-60 chars, keyword-first
- [ ] `<meta name="description">` — 150-160 chars, compelling
- [ ] H1 present and unique per page (only one H1)
- [ ] H2/H3 hierarchy logical
- [ ] Images have descriptive `alt` attributes
- [ ] Internal links use descriptive anchor text

### 2. Technical SEO
- [ ] `robots.txt` exists and is correct
- [ ] `sitemap.xml` exists and submitted to Google Search Console
- [ ] Canonical tags on duplicate/paginated content
- [ ] No broken links (check with `grep -r "href=" src/`)
- [ ] HTTPS enforced
- [ ] No mixed content warnings

### 3. Performance (Core Web Vitals)
- [ ] LCP < 2.5s (Largest Contentful Paint)
- [ ] CLS < 0.1 (Cumulative Layout Shift)
- [ ] FID / INP < 200ms
- [ ] Images use modern formats (WebP/AVIF)
- [ ] Images lazy-loaded below the fold
- [ ] CSS/JS minified and compressed

### 4. Schema Markup
- [ ] `Organization` or `LocalBusiness` schema on homepage
- [ ] `Article` or `BlogPosting` schema on blog posts
- [ ] `BreadcrumbList` schema on inner pages
- [ ] `FAQPage` schema where applicable

### 5. Mobile & UX
- [ ] Viewport meta tag present
- [ ] Font size >= 16px for body text
- [ ] Touch targets >= 48px
- [ ] No intrusive interstitials

## Output Format

```
## SEO Audit Report — <site/page>

### 🔴 Critical Issues (fix immediately)
- <issue> — <location> — <fix>

### ⚠️ Warnings (fix soon)
- <issue> — <location> — <fix>

### ✅ Passing
- <list of what's working>

### 📋 Quick Wins (high ROI, low effort)
1. <action>
2. <action>
3. <action>

### 📈 Estimated Impact
- <what fixing these issues could improve>
```
