# sarahymurphy.github.io

Personal academic and professional website for Sarah Y. Murphy, PhD — Physical Scientist at the USGS New England Water Science Center. Research areas include Arctic atmospheric science, hydrology, and data science education. Built with Jekyll 4.3.3 and deployed to [www.sarahymurphy.com](https://www.sarahymurphy.com) via GitHub Pages.

The site is based on the [Moonrise theme](https://github.com/TolgaTatli/Moonrise) (a fork of the Moon theme by Tolga Tatlı), but all layouts, includes, and SCSS are managed directly in this repo — it does **not** use a gem-based theme.

---

## Running Locally

```bash
bundle install
bundle exec jekyll serve
```

Visit `http://localhost:4000` in your browser.

---

## Project Structure

```
.
├── _config.yml              # Site configuration, plugins, social links
├── _data/
│   └── navigation.yml       # Top navigation bar links
├── _includes/               # Reusable HTML partials
├── _layouts/                # Page layout templates
├── _pages/                  # Standalone content pages
│   ├── about.markdown
│   ├── findme.md
│   ├── weather.md
│   └── wxstation.md
├── _posts/                  # Blog posts (Markdown)
├── _sass/                   # Theme-level SCSS partials
│   ├── pages/               # Page-specific SCSS partials
│   └── vendor/              # Third-party SCSS (fonts, animate, etc.)
├── assets/
│   ├── css/main.scss        # SCSS entry point
│   ├── img/
│   │   ├── site/            # Background, profile photos, cat photos
│   │   ├── weather/         # Weather station equipment photos
│   │   ├── posts/           # Blog post images
│   │   └── favicons/        # Apple touch icons
│   ├── js/                  # JavaScript files
│   ├── fonts/               # Fira Sans + Font Awesome web fonts
│   └── pdfs/                # All downloadable PDFs (CV + publications)
├── pubs/                    # Publications section index
├── talks/                   # Talks and presentations section
├── posts/                   # Blog post list page
├── workshops/               # Workshop tutorial HTML files
├── tags/                    # Tag archive page
├── index.html               # Home page
└── robots.txt               # Search crawler rules
```

---

## Navigation

Navigation is driven by `_data/navigation.yml`. The current nav links are:

| Label | URL |
|---|---|
| About | /about/ |
| Publications | /pubs/ |
| Talks | /talks/ |
| CV | /assets/pdfs/CV_SYMurphy.pdf (direct PDF) |
| Posts | /posts/ |
| Weather Station | /weather/ |
| Photo Gallery | https://sarahymurphy.myportfolio.com/ (external) |

The home page quick-link buttons (`_layouts/home.html`) loop over `site.data.navigation`, so adding or reordering entries in `navigation.yml` updates both the nav sidebar and the home page buttons automatically.

Note: the nav sidebar (`_includes/nav.html`) keeps About as a hardcoded first item with a special submenu showing the profile photo and social links. That entry is intentional theme behavior and is separate from the `navigation.yml`-driven links that appear below it.

---

## Adding Content

### Layouts

The site has seven layouts in `_layouts/`. Here's what each one does and when to use it.

| Layout | Used by | Back button goes to |
|---|---|---|
| `home` | `index.html` only | — |
| `page` | General content pages | Site root (`/`) |
| `post` | Blog posts in `_posts/` | `/posts/` (or `/projects/` if `project: true`) |
| `post-list` | `posts/index.md` | Site root (`/`) |
| `wxpage` | `wxstation.md` | `/weather/` |
| `project` | Unused — see note below | Site root (`/`) |
| `compress` | Base layout for all others; not used directly | — |

**`page`** is the default choice for any new standalone content page. It renders the page title, your Markdown/HTML content, and a back-arrow button to the site root.

**`post`** is for dated blog posts. It adds optional reading time, tag metadata at the bottom, and a back-arrow to `/posts/`. If the post has `project: true` in its front matter, the back button points to `/projects/` instead.

**`wxpage`** is identical to `page` except the back button points to `/weather/` rather than the site root. It exists specifically for `wxstation.md` as a sub-page of the weather section. Use it for any future page that should be navigated back to from `/weather/`.

**`post-list`** generates the listing at `/posts/`. It loops over all posts where `project` is not set and renders title, excerpt, and a "Read More" link. This layout is only needed for index-style listing pages.

**`project`** loops over posts where `project: true` and renders them as a project list. No posts currently use `project: true`, so this layout produces an empty page. It also loads `wow.min.js` for scroll animations. If a projects section is planned, set `project: true` in the front matter of the relevant posts to activate it.

---

### New blog post

Create a file in `_posts/` following the `YYYY-MM-DD-title.md` naming convention:

```yaml
---
layout: post
title: "Post Title"
tags: [tag1, tag2]
---
```

Optional front matter:
- `feature: /assets/img/posts/some-image.png` — displays a header image
- `project: true` — routes the back button to `/projects/` instead of `/posts/`

### New page

Create a `.md` or `.html` file in `_pages/` with `layout: page`. Add it to `_data/navigation.yml` if it should appear in the nav.

Pages in `_pages/` **must declare an explicit `permalink`** in their front matter. The site's global `permalink: /:title/` rule only applies to posts — without a `permalink`, a page would build to `/_pages/your-page/` instead of a clean top-level URL, and any links pointing at `/your-page/` would 404.

```yaml
---
layout: page
title: "Page Title"
permalink: /page-title/
comments: false
---
```

### Styles

All styles compile from `assets/css/main.scss`, which imports partials from `_sass/` in order. The partials are grouped:

- **Theme-level** (`_sass/*.scss`) — `variables`, `mixins`, `normalize`, `site`, `typography`, `elements`, `syntax`, `nav`, `print`. Shared structure and base styling.
- **Vendor** (`_sass/vendor/`) — third-party styles (fonts, Font Awesome, animate.css, magnific-popup).
- **Page-specific** (`_sass/pages/`) — `publications`, `presentations`, `post-list`, `workshops`, `page-styles`. Styles scoped to a single page or section.

To add styles for a new page, create a partial in `_sass/pages/` and add an `@import "pages/your-file";` line to the page-specific block in `main.scss`.

---

## Organization Notes

These are not bugs — the site works as-is. These are suggestions for keeping the repo easier to navigate and maintain over time.

### `favicon.ico` and `favicon.png` at root vs. `assets/img/favicons/`

There are two favicon files at the repo root (`favicon.ico`, `favicon.png`) and a `favicons/` subdirectory inside `assets/img/` that holds Apple touch icon PNGs. The root `.ico`/`.png` files are there because browsers request `/favicon.ico` automatically without being told — that placement is intentional and correct. But it's worth knowing these are separate from the `favicons/` folder; they serve different purposes and should stay where they are.

### `_layouts/project.html` and `assets/js/wow.min.js`

No posts currently use `layout: project` or have `project: true` in their front matter, so this layout renders an empty list and `wow.min.js` (which it loads) is never executed. If a projects section is not planned, both can be removed. If it is planned, a note in the front matter of any future "project" post is all that's needed to activate it.

### `workshops/` contains standalone self-contained HTML files

`GithubPages.html` and `Intro-to-Python-programming.html` bundle their own Bootstrap, jQuery, and tocify dependencies inline. They are intentionally self-contained (likely for distribution as standalone tutorials), so this is by design. Just worth noting that they don't share the site's theme or SCSS.

---

## Dependencies

Key gems (see `Gemfile` for full list):

| Gem | Purpose |
|---|---|
| `jekyll ~> 4.3.3` | Static site generator |
| `jekyll-feed` | Generates `feed.xml` |
| `jekyll-sitemap` | Generates `sitemap.xml` for all pages |
| `jekyll-seo-tag` | Injects SEO meta tags into page `<head>` |
| `jekyll-mentions` | Converts `@username` to GitHub profile links |
| `jekyll-gist` | Embeds GitHub Gists |
| `jekyll-paginate` | Pagination support |
| `jekyll-include-cache` | Caches `{% include %}` calls for build speed |
| `webrick` | Required for Jekyll dev server on Ruby 3+ |

---

## Theme Attribution

Based on [Moonrise](https://github.com/TolgaTatli/Moonrise) by Tolga Tatlı, which is itself a fork of [Moon](https://github.com/TaylanTatli/Moon) by Taylan Tatlı. Uses [Jekyll Compress HTML](https://github.com/penibelst/jekyll-compress-html) (v3.0.2 by Anatol Broder) to minify HTML output via the `compress` layout.
