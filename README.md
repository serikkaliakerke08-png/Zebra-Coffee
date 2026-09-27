# Zebra Coffee Website

A four-page website for Zebra Coffee, a coffee shop in Astana, built for the
Web Technologies course.

## Author

| | |
|---|---|
| Name | Serikkali Akerke |
| Group | SE-2537 |
| Course | Web Technologies |

## Pages

- `index.html` — Home
- `menu.html` — Menu (prices table, categories, popular items, glossary)
- `visit.html` — Visit (location, hours, photos, visitor contact form)
- `colophon.html` — Colophon (project info, sources, author, reflection)

## Assignment history

- **Assignment 1** — semantic HTML structure only, no CSS (see `sketches/` for the original wireframes).
- **Assignment 2** — hand-written CSS: a two-column grid on `visit.html`, a
  flex photo gallery, a fixed-position contact panel, custom typography and
  button styling.
- **Assignment 3 (current)** — the layout was rebuilt with **Bootstrap
  5.3.3** (loaded from the jsdelivr CDN, see the comment at the top of each
  page's `<head>`). Bootstrap now provides the grid, the responsive
  navigation, typography, buttons and one documented component (an
  Accordion on the Menu Terms glossary in `menu.html`). Our own CSS in
  `css/base.css` and `css/akerke.css` was cut down to a small correction
  layer — brand colours, fonts, and the few details Bootstrap doesn't cover.
  See [`css/removed-rules.md`](css/removed-rules.md) for the full list of
  what was deleted and which Bootstrap class replaced it.

## Technologies

- HTML5 (semantic elements)
- Bootstrap 5.3.3 (CSS + JS bundle, via CDN)
- A small amount of custom CSS (~60 lines total, see `css/`)
- No JavaScript of our own, no other CSS framework, no templates

## Structure

```
index.html, menu.html, visit.html, colophon.html   – the four pages
css/base.css, css/akerke.css                       – our CSS correction layer
css/removed-rules.md                               – what Assignment 2's CSS Bootstrap replaced
images/                                             – photos used on visit.html
screenshots/bootstrap/                              – responsive screenshots for this assignment
sketches/                                           – original Assignment 1 wireframes (unchanged)
```

## Running locally

The site uses only local files and a CDN link for Bootstrap — no build step,
no server required. Open `index.html` in a browser (an internet connection
is needed the first time so Bootstrap can load from the CDN).

## Validation

All four pages pass the [W3C Nu HTML checker](https://validator.w3.org/nu/)
with zero errors.
