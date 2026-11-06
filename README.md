# Aniket Pandey — Portfolio

A responsive, multi-page portfolio built with plain HTML and CSS. This website has no build step, package manager, or JavaScript dependency.

## Open and preview

Open `Aniket-Portfolio.code-workspace` in Visual Studio Code, or open this folder directly. Start at `index.html` and follow its links to the other pages.

To preview locally, open `index.html` in a browser or use VS Code Live Preview / Live Server. A local server is recommended when checking navigation and assets across pages.

## Project map

```text
Aniket Portfolio/
├── index.html                     # Landing page and portfolio directory
├── builder.html                   # Ventures, roles, and work
├── doer.html                      # Leadership, competitions, and achievements
├── learner.html                   # Education timeline, certificates, and awards
├── questioner.html                # Research and policy interests
├── signal.html                    # Features, interviews, and appearances
├── explorer.html                  # Fellowships and development programmes
├── contact.html                   # Email and social contact options
├── sports.html                    # Older, unlinked sports page kept for reference
├── styles.css                     # Shared foundation and most page layouts
├── doer.css                       # The Doer page styling
├── questioner.css                 # The Questioner page colour treatment
├── explorer.css                   # The Explorer page styling
├── contact.css                    # The contact page styling
├── assets/logos/                  # Local organization and social logos
├── docs/DEVELOPMENT_GUIDE.md      # Editable guide to the code and editing workflow
├── Aniket-Portfolio.code-workspace
└── sources/                       # Synced reference material; do not edit
```

## Editing the portfolio

- Keep the HTML pages at the project root. `index.html` is the entry point expected by simple static hosts such as GitHub Pages.
- Shared navigation, base styles, and several page layouts are in `styles.css`. Some pages load an additional page stylesheet for their own refinements.
- Keep internal links and asset paths relative. Open the Development Guide before adding a page or changing where files live.
- Certificates are listed separately from the education timeline in `learner.html`. The Development Guide shows the exact markup to add one.
- Keep the `sources/` folder unchanged; it contains synced reference material.
- `sports.html` is not linked from the current navigation. It is retained as an older design reference; the current research page is `questioner.html`.

## Current state

The website is not hosted yet. After publishing, will add the live website URL to this README. 