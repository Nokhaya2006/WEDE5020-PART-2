# Changelog

All notable changes to the Gweleni Construction website are recorded here,
in chronological order.

## 2026-08-14 — Part 1: initial build

- Created project folder structure (`css/`, `images/`) and a first shared
  stylesheet, `css/style.css`.
- Built `index.html`, `about.html`, `services.html`, `projects.html` and
  `contact.html` with semantic `header`/`nav`/`main`/`footer` on every page.
- Linked navigation across all pages with `aria-current="page"` on the
  active link.
- Added descriptive `alt` text to all images and HTML comments explaining
  each major section.
- Sourced placeholder project photography from Unsplash and added
  `README.md`.

## 2026-08-21 — Part 1 feedback implementation

Implements the corrections requested after Part 1 marking.

- **Fixed incorrect location details**: the site previously referenced
  Pretoria/Gauteng in error; all copy, the hero, the about page and the
  contact details were corrected to Gweleni Construction's real location,
  Bellville, Cape Town.
- **Replaced placeholder photography** with six real project photos,
  renamed from messy uploaded filenames (spaces, inconsistent casing) to
  descriptive lowercase-hyphenated names (`new-home-build.png`,
  `kitchen-renovation.png`, `bathroom-renovation.png`,
  `home-extension.png`, `roof-replacement.png`, `retail-fitout.png`), each
  captioned with the Cape Town suburb the project was completed in
  (Durbanville, Bellville, Brackenfell, Tyger Valley, Parow, Century City).
- **Restructured the site** from a single anchor-linked `index.html` with
  broken image references into five properly linked pages: `index.html`,
  `about.html`, `services.html` (six service categories + FAQ),
  `enquiry.html` (dedicated quote-request form, replacing `projects.html`),
  and `contact.html` (two real locations: Bellville head office and
  Durbanville site office).
- Updated all contact details across the site to the client's real phone,
  alternate phone and email.

## 2026-09-05 — Home page visual redesign

- Redesigned `index.html` to a navy/gold palette with a full hero, "why
  choose us" section, featured-projects gallery and client testimonials,
  matching an agreed design reference.
- At this stage the new design was implemented as an embedded `<style>`
  block on `index.html` only, while the other four pages still linked the
  older `css/style.css` — flagged below as the first item corrected for
  Part 2.

## 2026-09-17 — Part 2: CSS styling and responsive design

- **Consolidated to one external stylesheet.** Removed the embedded
  `<style>` block from `index.html` (Part 1/interim feedback: an external
  stylesheet must be correctly implemented on *every* page, not just some)
  and rebuilt `css/style.css` around the navy/gold design, so all five
  pages now share exactly one stylesheet and one consistent look.
- **Design tokens**: added a full set of CSS custom properties for colour
  and typography (`--navy`, `--gold`, `--paper`, `--font-display`, etc.)
  so the palette/type pairing is defined once and reused everywhere.
- **Default/base style**: global box-sizing reset, base font, line-height,
  background and link/heading defaults applied consistently across pages.
- **Typography**: fluid `clamp()`-based heading sizes, a mono/display/body
  three-font system, plus explicit responsive typography overrides at each
  breakpoint (heading size and letter-spacing on tablet, base body font
  size on mobile, a further heading reduction on small phones).
- **Layout structure**: CSS Grid for all major grids (services, service
  tiles, gallery, testimonials, about/stats, contact/quote form, footer —
  the footer specifically uses `grid-template-areas`) and Flexbox for the
  header, hero actions, nav and card internals.
- **Decoration and colour**: consistent card/button/border treatment,
  rounded corners, hover elevation on cards, and background colour blocks
  (navy/paper/white) used to separate sections.
- **Pseudo-classes/pseudo-elements**: `:hover`, `:active` and
  `:focus-visible` on all interactive elements, `:not()` to exclude the
  CTA button from the plain nav-link hover style, `:first-child`/
  `:last-child` on nav links, `:checked` (the CSS-only mobile menu),
  `details[open]` and `::marker` for the new FAQ styling.
- **Added missing component styles**: brought the About page
  (`.about-grid`, `.mission-vision`, `.about-stats`), the Services page's
  photo cards (renamed to `.service-tile` to avoid clashing with the home
  page's icon cards) and the FAQ `<details>` elements into the shared
  stylesheet with the new palette — previously unstyled or styled only in
  the old palette.
- **Responsive design**: added tablet (`980px`, `899px`), mobile (`760px`)
  and small-phone (`520px`) breakpoints covering layout, typography,
  navigation-menu and image adjustments (see the breakpoint table in
  `README.md`).
- **Responsive images**: added `srcset`/`sizes` to the home page hero image
  so phones download a smaller file than desktop.
- **Navigation consistency**: added the missing "Projects" link (pointing
  to `index.html#projects`) and matched the gold "Request a Quote" button
  style across all five pages' navigation, which had drifted to an
  outline style on four of the five pages.
- **Footer consistency**: added the contact-details column to the footer
  on About, Services, Enquiry and Contact (previously only on the home
  page), and unified the footer sign-off text across all pages.
- Updated `README.md` (CSS architecture, breakpoint table, references) and
  this changelog.

## 2026-09-17 — Checked against CSS Fundamentals Part 2 course material

Cross-checked the existing `css/style.css` against the module's *CSS
Fundamentals Part 2: Layouts, responsive design & polished interfaces*
slides (display, Flexbox, Grid, positioning, interface styling, responsive
units/media queries, polish, debugging). No missing techniques were found —
everything the slides cover is already present in the stylesheet:

- **display**: block/inline/inline-block used correctly across nav links,
  buttons and inline tags (no layout change needed).
- **Flexbox**: header/nav, hero actions, card internals and the mobile nav
  menu all use `display: flex` with `justify-content`/`align-items`/
  `flex-wrap`/`gap`, matching the slides' row-vs-column guidance.
- **Grid**: `.services-grid`, `.service-tiles`, `.gallery-grid`,
  `.testimonial-grid`, `.about-grid`, `.mission-vision`, `.contact-grid`,
  `.form-row-split` and the footer (`grid-template-areas`) all use CSS
  Grid for two-dimensional layout, as recommended over Flexbox for that
  case.
- **Positioning**: `position: sticky` on the header, `position: relative`
  + `position: absolute` used correctly for the hero background/overlay
  and the mobile nav panel (the "reference box + badge" pattern from the
  slides) — no layout-by-`position: absolute` anti-pattern present.
- **Interfaces**: consistent `input`/`select`/`textarea` styling on the
  quote form, with `:focus` outlines kept rather than removed.
- **Responsive**: relative units (`rem`, `%`, `clamp()`), `@media` breakpoints
  at 980/899/760/520px, and a responsive nav that switches from a row to a
  stacked/collapsible menu on small screens.
- **Polish**: `box-shadow` on cards, `transition`/`transform` on hover and
  focus states, used selectively rather than on every element.
- Added the course slide deck to References below.

## Planned for later parts

- Wire the quote request form to a real submission endpoint / email
  service.
- Any JavaScript-based enhancements agreed for later parts of the module.
