# CSS removed when the layout moved to Bootstrap

This lists every rule that used to live in `akerke.css` (Assignment 2) and the
Bootstrap class that now does the same job.

| Removed rule | Where it was | Bootstrap replacement |
|---|---|---|
| `.visit-layout` (`display: grid; grid-template-columns: repeat(2, ...)`) | visit.html main layout | `.row` + `.col-12 .col-md-6 .col-lg-8` grid |
| `.visit-layout > hr` (`display: none`) | visit.html divider | `d-none` utility class on the `<hr>` directly |
| `.info-block` (padding, border, border-radius) | every visit.html section | `p-3 border rounded-3` utilities |
| `#location`, `#contact-form` (`border-left: 6px solid`) | visit.html accent borders | `border-start border-5 border-primary` utilities |
| `.photo-gallery` (`display: flex; flex-wrap: wrap; gap`) | visit.html photo section | `.row.row-cols-1.row-cols-md-3.g-3` |
| `.photo-gallery h2` (`flex: 0 0 100%`) | visit.html photo heading | no longer needed - the heading is a normal sibling above the nested row |
| `.photo-card` (flex column, border, padding, `position: relative`) | visit.html photo cards | `position-relative border rounded-3 p-2 h-100` utilities |
| `.photo-card::before` (badge pseudo-element) | visit.html photo cards | Bootstrap Badge (`span.badge`) + `position-absolute top-0 end-0 m-2` |
| `.jump-link` (bold, margin-right) | visit.html "Go to ..." links | `btn btn-sm btn-outline-primary` |
| `.form-label` (bold, margin-right) | visit.html form | Bootstrap's own `.form-label` class |
| `.phone-link` (`white-space: nowrap`, bold) | visit.html phone numbers | `text-nowrap fw-bold` utilities |
| `.contact-panel` (`position: fixed; bottom; right; padding; border; border-radius`) | visit.html floating panel | `position-fixed bottom-0 end-0 m-3 p-3 border rounded-3` utilities (only the exact width and the translucent background stayed as custom CSS) |
| `h2 + p` (`font-size: 18px` / `20px` in the inline `<style>` override) | every page | `lead` class added to the relevant intro paragraphs |
| `input[type="email"]` (border, padding) | visit.html form | `.form-control` on every input |
| `input:focus` (background colour, outline) | visit.html form | `.form-control:focus` custom rule kept, rewritten to fit Bootstrap's focus ring instead of fighting it |
| `nav li:first-child a` (bold "Home" link) | every page nav | Bootstrap's `.nav-link.active` on whichever page is actually current |
| `header { display: flex; flex-direction: column; align-items: center; }` | every page header | `text-center` on the header, `justify-content-center` on the navbar collapse |
| `footer { display: grid; place-items: center; }` | every page footer | `text-center` on the footer |
| `.info-block .jump-link` / `.info-block a` (specificity demo for underline) | visit.html | no longer needed - the links are now buttons, not underlined text |

## What stayed, and why

- `:root { --bs-primary-rgb, --bs-border-color }`, `body`, `h1/h2/h3`, `.site-header/.site-footer` - the Zebra Coffee palette and fonts; Bootstrap has no idea what our brand colours are.
- `.btn-primary` variable override - Bootstrap compiles button colours at build time, so retinting `btn-primary` needs this local override rather than fighting it with a hand rule.
- `.form-control:focus` - a brand-coloured focus ring instead of Bootstrap's default blue one.
- `.contact-panel` width + translucent background - Bootstrap has no utility for an exact pixel width or a semi-transparent brand colour.
