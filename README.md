# Best Gift Ideas

A simple, static gift-recommendation website built around Amazon affiliate links. Visitors browse gift categories (Birthdays, For Her, For Him, Spouse/Partner, Teens, Kids, Tech Lovers, Under $25), and each product links out to Amazon with an affiliate tracking tag.

## Files

- `index.html` — the main gift catalog page, with category tabs and product cards
- `blog.html` — the "Journal" section with gift-giving guide articles (helps with SEO and Amazon Associates approval)

## Setup

### 1. Host the site (free)
- **GitHub Pages:** push this repo to GitHub, then go to **Settings → Pages** and enable Pages for the main branch. Your site will be live at `https://yourusername.github.io/repo-name/`
- **Netlify:** drag-and-drop this folder into Netlify's dashboard for an instant live URL

### 2. Apply for Amazon Associates
- Sign up at [affiliate-program.amazon.com](https://affiliate-program.amazon.com)
- Submit your live site URL during the application
- Note: Amazon requires a minimum number of qualifying sales (often within 180 days) to keep your account active — don't apply until you're ready to start sharing the site

### 3. Add your affiliate tag
Once approved, you'll receive an Associate ID (e.g. `yourname-20`).

Find and replace every instance of:
```
YOURTAG-20
```
with your real Associate ID, across `index.html` (and any future pages with affiliate links).

On most systems you can do this with a find-and-replace in a text editor, or from the command line:
```bash
sed -i 's/YOURTAG-20/yourname-20/g' index.html
```

## Updating content

- **Add a product:** copy an existing `<article class="card">...</article>` block within a category section in `index.html`, then update the price tag, title, description, and Amazon search link.
- **Add a category:** copy an existing `<section class="category">...</section>` block, give it a new `id`, and add a matching `<button data-target="...">` in the nav at the top.
- **Add a blog post:** copy an existing `<article class="post">...</article>` block in `blog.html` and write new content.

## Notes

- Product links currently point to Amazon **search results** (`amazon.com/s?k=...`) rather than specific product pages, since specific products, prices, and availability change frequently. You can swap in direct product links once you've verified them yourself.
- Image placeholders are simple icons — replace with real product photos as you finalize picks.
- Required disclosure text ("As an Amazon Associate, this site earns from qualifying purchases...") is already included near the bottom of `index.html` — keep this visible per Amazon's terms.
