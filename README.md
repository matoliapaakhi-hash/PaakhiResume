# Paakhi Matolia | Portfolio

A personal portfolio website for **Paakhi Matolia**, a BBA (Digital Business and Entrepreneurship) student at IIM Bangalore. It covers her education, experience, achievements, interests and skills, with a 3D line-art basketball that follows the page as you scroll.

The project is split into three files: `index.html` (structure and content), `style.css` (styling) and `script.js` (behaviour and libraries). There is no build step, no package manager and no server needed.

## Project structure

```
portfolio/
├── index.html   # Page markup and content
├── style.css    # All styles, themes and responsive rules
├── script.js    # Three.js, GSAP + ScrollTrigger (bundled) and the site's own code
└── README.md
```

`index.html` also keeps one tiny inline script in the `<head>` that applies the saved theme before the page paints, which prevents a flash of the wrong theme.

## Features

- **Scroll-driven 3D hero element**: a wireframe basketball (Three.js) that moves and rotates as you scroll, and tilts slightly with the pointer.
- **Scroll animations**: reveal-on-scroll text, animated stat counters and a progress bar at the top (GSAP + ScrollTrigger).
- **Light and dark themes**: follows the system preference on first visit, with a manual toggle.
- **Animations on/off toggle**: turns off all motion, including the 3D animation, for people who prefer a calmer page.
- **Interactive content**:
  - Expandable "Details" rows in Education, Experience and Achievements, plus "Expand all".
  - Achievements filtered by category: Leadership, Debate, Business, Academics.
  - Interests filtered by category (Sport, Creative, Mind) and switchable between list and grid layouts.
  - Skill chips that show where each skill appears in the portfolio.
- **Contact helpers**: "Email me" link, "Copy email address" button with a toast confirmation, and a LinkedIn link.
- **Responsive layout** with a full-screen menu for small screens.
- **Accessibility touches**: skip-to-content link, ARIA labels and states on interactive controls, visible focus outlines, and live regions for status messages.

## Page sections

| # | Section | Content |
|---|---------|---------|
| – | Home | Name, intro, call-to-action buttons and headline stats (50+ basketball tournaments, 92 CUET GAT percentile, 223/400 CA Foundation) |
| 01 | About | Short personal introduction |
| 02 | Education | IIM Bangalore, CUET GAT and CA Foundation, Class XII, Class X |
| 03 | Experience | Content Research Intern, Euro International School |
| 04 | Achievements | Leadership roles, MUN and debate, case competition, Olympiads |
| 05 | Beyond the classroom | Basketball, rollball, swimming, calligraphy, films, mysteries |
| 06 | Skills | Communication, analysis, leadership, AI-assisted research |
| 07 | Contact | Email and LinkedIn |

## Tech stack

- **HTML, CSS and vanilla JavaScript**, in three separate files.
- **[Three.js](https://threejs.org/)** (MIT) for the 3D basketball, bundled in `script.js`.
- **[GSAP 3.12.5](https://gsap.com/) with ScrollTrigger** for scroll animations, bundled in `script.js`. See the [GSAP standard license](https://gsap.com/standard-license).
- **Google Fonts**: Newsreader (headings) and Instrument Sans (body), loaded from the web.

## Getting started

1. Keep `index.html`, `style.css` and `script.js` together in the same folder.
2. Open `index.html` in a modern browser (double-click, or drag it into a browser window).

To preview it over a local server instead:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

### Deploying

It is a static site, so it works on any static host: GitHub Pages, Netlify, Vercel, Cloudflare Pages or a plain web server. Upload the whole `portfolio` folder contents to the site root.

## Customizing

| What | Where |
|------|-------|
| Name, intro, stats | `#home` section near the top of `<body>` in `index.html` |
| Content for each section | The matching `<section id="...">` blocks inside `<main>` |
| Contact email and LinkedIn | Search for `mailto:` and `linkedin.com` links (they appear in the hero, About, Contact and footer) |
| Colors | `style.css`, CSS variables in `:root` (light theme) and `[data-theme=dark]` (dark theme): `--bg`, `--panel`, `--ink`, `--mute`, `--line`, `--acc` |
| Fonts | `--fd` (display) and `--fb` (body) variables, plus the Google Fonts `<link>` in `<head>` |
| Page title and description | `<title>` and `<meta name="description">` in `<head>` |
| Favicon | Inline SVG data URI in the `<link rel="icon">` tag |

New Education, Experience or Achievement entries follow the existing `<li class="row">` pattern. For achievements, set `data-c="Category"` on the row so the category filter picks it up.

## Browser storage

The page saves two preferences in `localStorage`, wrapped in try/catch so it still works if storage is blocked:

- `pm-theme`: `light` or `dark`
- `pm-motion`: `off` when animations are disabled

## Notes and limitations

- **WebGL**: the 3D basketball needs WebGL. If it is unavailable, the page still works, just without the 3D element.
- **Internet connection**: Three.js and GSAP are bundled in the file, but the fonts come from Google Fonts. Offline, the page falls back to Georgia and system sans-serif fonts.
- **File size**: `script.js` is roughly 700 KB because Three.js and GSAP are bundled into it. If that matters, load them from a CDN instead.
- **Print**: the stylesheet includes print rules that hide interactive elements.

## Credits

Design and content: Paakhi Matolia.
Libraries: Three.js and GSAP, each under their own licenses.

## License

© 2026 Paakhi Matolia. All rights reserved. Add a license of your choice here if you want others to reuse the code.
