# Portfolio Development Guide

This is the working guide I keep for continuing the portfolio in VS Code. I have intentionally kept the site simple to run: each route is its own HTML file, the styling lives in CSS files, and all images are local assets. This working guide has been genereated with the help of VS Inbuilt agents

## 1. How the site is organized

### Pages

| Visitor route | File | Main content |
| --- | --- | --- |
| Home | `index.html` | Introduction and route cards for the six portfolio areas |
| The Builder | `builder.html` | Toornify, other roles, earlier work, and volunteering |
| The Doer | `doer.html` | VBYLD, IIT competitions, other achievements, and school communities |
| The Learner | `learner.html` | Four-part education timeline, certificates, and awards |
| The Questioner | `questioner.html` | Research in progress and policy interests |
| The Signal | `signal.html` | Press features, interviews, and appearances |
| The Explorer | `explorer.html` | Fellowships and additional programmes |
| Say Hello | `contact.html` | Email, LinkedIn, Instagram, and WhatsApp links |

`sports.html` is an older page that is not linked from the current navigation. My current research route is `questioner.html`.

### Styles and assets

- `styles.css` defines the shared design tokens, page foundation, navigation, responsive rules, and most page layouts. It has grown through several design iterations, so I always read the page selectors and the later overrides before changing a shared rule.
- `doer.css`, `questioner.css`, `explorer.css`, and `contact.css` are loaded after `styles.css` on their matching pages. I keep new page-only refinements in those files.
- The Builder, Learner, and Signal pages currently use their page-specific selectors in `styles.css` alongside the shared components.
- `assets/logos/` holds the local logos used on the Signal and Contact pages. I keep their paths relative to the HTML files.
- `sources/` is synced reference material. I do not modify those files.

The root-level HTML files are deliberate: they keep navigation simple and let `index.html` work as a static-host entry point without a build process.

## 2. Run and preview

1. I open `Aniket-Portfolio.code-workspace` in Visual Studio Code.
2. I open `index.html` and use the navigation to move through the site.
3. For a local preview, I open the page in a browser or use Live Preview / Live Server.
4. I check the layout at desktop width and at narrow phone widths (around 360–390 px). I make sure the navigation can scroll horizontally, cards stack or shrink cleanly, and no text or buttons are clipped.

There is no `package.json`, build step, or automated test command in this project.

## 3. Design system

The shared CSS custom properties at the top of `styles.css` define my base palette and type:

| Token | Use |
| --- | --- |
| `--night` / `--night-soft` | Dark backgrounds and navigation |
| `--paper` / `--paper-dark` | Warm light surfaces |
| `--lime` | High-contrast highlight and current-page state |
| `--rust` | Secondary emphasis and focus outline |
| `--sans` | Manrope body and interface text |
| `--serif` | Playfair Display editorial headings |
| `--mono` | DM Mono labels, dates, and small metadata |

I prefer these tokens for shared updates. If a page needs a distinct visual direction, I define its own scoped variables rather than forcing a global change.

## 4. Add or edit content

### Add a certificate

I open `learner.html` and find the **01 / CERTIFICATES & PROGRAMMES** board. Inside its `.credential-tags` container, I add one `<span>` per item:

```html
<span>2026 · Certificate name — Issuing organisation</span>
```

Awards go in the neighboring **02 / AWARDS & COMPETITIONS** board. If the credential has a public verification page, I link the certificate text to that page.

### Add a portfolio page

1. I create a root-level file such as `new-page.html` and copy the shared header and footer from an existing current page.
2. I set a unique `<title>` and meta description, then add the page to the navigation in each current HTML page and to the route cards on `index.html` if it is a main portfolio area.
3. I reuse shared components wherever possible. I only add a page stylesheet when the page needs a distinct design, and I load it after `styles.css`.
4. I add a page entry to the tables in `README.md` and this guide.
5. I check every local link, asset path, keyboard focus, and phone layout before I consider the addition complete.

### Add an image or logo

I place the optimized image in `assets/` (organization logos belong in `assets/logos/`). I use a descriptive filename, a relative `src`, and meaningful `alt` text. For decorative images, I use `alt=""`.

### Add an external link

I use a descriptive link label. For links that open in a new tab, I include both `target="_blank"` and `rel="noreferrer"` just as the existing pages do.

## 5. Mobile and accessibility conventions

- Each page includes a viewport meta tag. I keep responsive rules grouped in media queries, mainly around 850 px, 700 px, 600 px, and 540–580 px.
- I keep navigation usable on narrow screens; the multi-page navigation is horizontally scrollable on phones.
- I prefer flexible grids, `minmax()`, and `clamp()` over fixed widths for content.
- I keep body text readable and preserve strong contrast. I reserve tiny mono labels for short metadata only.
- I keep a visible `:focus-visible` outline on interactive controls and links.
- I keep descriptive `alt` text on meaningful images and `aria-label` where a linked card needs a clear accessible name.
- I preserve the reduced-motion rule in `styles.css` whenever I add animation.

## 6. Publishing

This site is not currently hosted.

## 7. Review notes

This project currently has no build system. A static review showed that all local HTML links and asset references resolve, IDs are unique, images have `alt` attributes, new-tab links include `rel` protection, and the CSS files have balanced braces. I re-run the review after changing page paths, IDs, or stylesheets.
