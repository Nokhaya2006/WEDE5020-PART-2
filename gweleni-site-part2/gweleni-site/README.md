# Gweleni Construction — Website

A five-page, responsive website for Gweleni Construction, a Bellville-based
residential and light-commercial building company serving Cape Town's
northern suburbs. Built for **WEDE5020** (IIE Rosebank International).

- **Part 1** — semantic HTML foundation across five linked pages.
- **Part 2** — external CSS stylesheet, desktop styling and responsive
  design for tablet and mobile (this update).

## Pages

| Page | File | Purpose |
|---|---|---|
| Home | `index.html` | Hero, services overview, "why choose us", featured projects, testimonials, quote CTA |
| About | `about.html` | Company story, vision, mission, key stats |
| Services | `services.html` | Six service categories with real project photos, FAQ |
| Get a Quote | `enquiry.html` | Quote request form |
| Contact | `contact.html` | Bellville head office and Durbanville site office details |

Every page shares the same `<header>` navigation and `<footer>`, so all five
pages are reachable from one another at all times.

## Folder structure

```
gweleni-site/
├── index.html
├── about.html
├── services.html
├── enquiry.html
├── contact.html
├── css/
│   └── style.css        ← one external stylesheet, linked from every page
├── images/
│   ├── new-home-build.png
│   ├── kitchen-renovation.png
│   ├── bathroom-renovation.png
│   ├── home-extension.png
│   ├── roof-replacement.png
│   └── retail-fitout.png
├── README.md
└── CHANGELOG.md
```

## Technologies

HTML5, CSS3 (custom properties/design tokens, Grid, Flexbox, `clamp()`
fluid typography, media queries, pseudo-classes/pseudo-elements), Google
Fonts (Oswald, Work Sans, IBM Plex Mono). No JavaScript or build tools are
used anywhere on the site — the mobile navigation menu is implemented with
the CSS-only "checkbox hack" (`:checked` + a sibling selector).

## CSS architecture (Part 2)

All styling lives in one external stylesheet, `css/style.css`, linked from
every page's `<head>`. It is organised top to bottom as:

1. Design tokens (`:root` custom properties for colour and type)
2. Reset / base style
3. Typography
4. Buttons
5. Header / navigation
6. Section-by-section component styles (hero, services, about, FAQ,
   contact/enquiry form, footer)
16. Focus-visibility (accessibility)
17. Responsive media queries (tablet, mobile, small phone)
18. Reduced-motion support

Colour and type are defined once as custom properties so the whole site's
palette can be changed from a single place, taking advantage of CSS's
cascading nature rather than repeating values throughout the sheet.

### Responsive breakpoints

| Breakpoint | Target | What changes |
|---|---|---|
| `max-width: 980px` | Tablet | Grids drop from 3–4 columns to 2, "why us" section stacks, About page stats switch from a column to a wrapped row, heading sizes step down |
| `max-width: 899px` | Tablet (narrow) | Contact/enquiry two-column layout stacks to one column, footer grid re-flows to two columns |
| `max-width: 760px` | Mobile | Header navigation switches to the hamburger/CSS-checkbox menu, all remaining multi-column grids and forms drop to one column, base body font size reduces slightly |
| `max-width: 520px` | Small phone | Grids fall to a single column everywhere, hero/gallery image aspect ratios shrink, heading sizes reduce a further step |

### Responsive testing evidence

*(Add screenshots here before submission — resize the browser or use
DevTools' device toolbar at roughly 1440px/desktop, 820px/tablet and
390px/mobile widths, or test on an actual phone/tablet, and paste the
screenshots below.)*

- Desktop (≥1200px): ...
- Tablet (~768–900px): ...
- Mobile (~375–430px): ...

## Content notes

Project photos in `images/` are real project photography with the
location each project was completed in. The home page uses a small number
of additional Unsplash stock photos (hero background, testimonials
background, "why us" portrait) — see References below for the licence.
Phone numbers and the email address on the Contact and Enquiry pages are
the client's actual current contact details.

## Accessibility & responsiveness

- Semantic landmarks (`header`, `nav`, `main`, `section`, `footer`)
- Meaningful `alt` text on every content image, describing the project and
  location; purely decorative images use an empty `alt` with
  `aria-hidden="true"`
- Visible focus states on all interactive elements via `:focus-visible`
- Responsive from small phones up to desktop, with a collapsible mobile menu
- Respects `prefers-reduced-motion`
- `srcset`/`sizes` on the hero image so phones download a smaller file
  than desktop

## References

All sources are in Harvard style, matching the referencing used in the
Part 1 proposal document.

- Mozilla Developer Network (MDN) (2026) *CSS: Cascading Style Sheets*.
  Available at: https://developer.mozilla.org/en-US/docs/Web/CSS
  (Accessed: September 2026).
- Mozilla Developer Network (MDN) (2026) *CSS Grid Layout* and *Flexbox*.
  Available at: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout
  and https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout
  (Accessed: September 2026).
- Mozilla Developer Network (MDN) (2026) *Using Media Queries*. Available
  at: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries
  (Accessed: September 2026).
- Google Fonts (2026) *Oswald*, *Work Sans*, *IBM Plex Mono*. Available at:
  https://fonts.google.com (Accessed: September 2026).
- Unsplash (2026) *Unsplash License*. Available at:
  https://unsplash.com/license (Accessed: August 2026).
- Rosebank International (2026) *CSS Fundamentals Part 2: Layouts,
  responsive design & polished interfaces*. Web Development module
  slides, Rosebank International, Pretoria Campus. Unpublished lecture
  material.
