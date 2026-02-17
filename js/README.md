[README.md](https://github.com/user-attachments/files/25371284/README.md)
# 🌊 גלים — Galim Nonprofit Website

Static website for the Galim sea education nonprofit. Built for Vercel deployment.

## Stack
- Pure HTML5 + CSS3 + Vanilla JS
- No frameworks, no build tools, no dependencies
- Google Fonts (Frank Ruhl Libre + Assistant) loaded via CDN
- RTL (Hebrew) with i18n structure ready for future English

## Folder Structure
```
/
├── index.html              # Home page (hero, story, values, instagram, donation)
├── vercel.json             # Vercel deployment config
├── css/
│   └── main.css            # Design system + all styles
├── js/
│   ├── main.js             # Nav, scroll, form validation, animations
│   └── blog.js             # Blog data + rendering logic
├── about/
│   └── index.html          # About page
├── blog/
│   ├── index.html          # Blog list page
│   └── post.html           # Single post template
└── images/                 # Place optimized images here (WebP preferred)
```

## Deployment (Vercel)
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel deploy
```
Or connect the GitHub repo to Vercel for automatic deployments.

## Adding Blog Posts
Edit `js/blog.js` — add an object to the `POSTS` array:
```js
{
  id: 'unique-id',
  slug: 'unique-id',         // used in URL ?id=unique-id
  category: 'stories',       // see CATEGORIES array
  title: 'כותרת הפוסט',
  excerpt: 'תקציר קצר...',
  author: 'שם הכותב',
  authorInitials: 'שכ',
  date: '12 בינואר 2025',
  readTime: '5 דקות',
  emoji: '🌊',
  featured: false,           // true = shown in featured slot on blog list
  content: `<p>HTML content here...</p>`
}
```

## Future i18n
- All visible text lives in HTML files or `js/blog.js`
- CSS has `[lang="en"]` and `[lang="he"]` direction overrides ready
- To add English: duplicate pages into `/en/` folder, set `lang="en" dir="ltr"`

## Images
- Place optimized images in `/images/`
- Use WebP format where possible
- Add `loading="lazy"` attribute to all `<img>` tags
- Recommended: use Squoosh (squoosh.app) for compression

## Payment Integration
- Placeholder section is in `index.html` around line 230
- Comment marked: `<!-- TODO: Integrate payment gateway -->`
- Recommended Israeli gateways: Tranzila, Cardcom, iCount

## Performance Checklist
- [x] Lazy loading images (native `loading="lazy"`)
- [x] Minimal JavaScript (no frameworks)
- [x] Google Fonts with `display=swap`
- [x] CSS variables for easy theming
- [x] Optimized CSS with no unused rules
- [x] Vercel headers for caching
- [x] Semantic HTML for SEO

## Accessibility
- Semantic HTML (`<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- ARIA labels on key interactive elements
- Focus-visible styles (browser default + custom)
- Color contrast meets WCAG AA
- RTL properly set with `dir="rtl"` on `<html>`
