# Skylight sign-up page

This is a plain-HTML copy of the sign-up modal anonymous visitors see when they land on
[Skylight](https://app.skylight.earth). The purpose is to use this as the starting point
for design exercises.

## Running it

Open `index.html` in a browser. That is the whole setup.

If you would rather serve it over HTTP:

```bash
python3 -m http.server 8000
```

Then visit http://localhost:8000.

## What is here

| File                 |                                                                 |
| -------------------- | --------------------------------------------------------------- |
| `index.html`         | the markup — a backdrop div, then the modal                     |
| `styles.css`         | all the styling, Skylight's palette as CSS variables at the top |
| `app-background.png` | a screenshot of the app, used as the backdrop                   |

Both source files are commented into labelled sections. In `styles.css` those are the design
tokens, then the modal, then the app behind it; `index.html` is the backdrop, then the modal, then
the script. Only one part is the exercise:

- **The modal** — the welcome panel and the sign-in form. This is what to edit.
- **The app behind the modal** — a screenshot of Skylight, backdrop only; it exists so the modal sits in context.

## Design tokens

The `:root` block at the top of `styles.css` is the colour, spacing and motion part of Skylight's
real token set, lifted from the app's theme file. Most of them
this page never uses; they are there to design from rather than to invent a hex. A handful of
`--mui-*` and page-local names are added at the end and marked as such.

- **Colour** — `--dark-teal`, `--skylight-blue` and its `-hover` / `-active` / `-inactive`
  variants, the greys, the `-rgb` triples for tints.
- **Spacing** — `--spacing-xs` through `--spacing-6xl`, all multiples of the 8px base that MUI
  uses, so spacing stays on the same grid as the components.
- **Motion** — `--duration-shortest` … `--duration-complex` and the four easings, which mirror
  MUI's `theme.transitions`. Matching them is what keeps a CSS transition and a component
  animation on the same interaction finishing together.

Panel geometry is variables too — `--panel-width`, `--panel-height` and `--panel-gap` — so the
layout can be retuned without hunting through the file.
