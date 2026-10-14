# Skylight sign-up page

This is a plain-HTML copy of the sign-up modal anonymous visitors see when they land on
[Skylight](https://app.skylight.earth). The purpose is to use this as the starting point
for design exercises. Everything around the map is real markup you can edit; the map itself is a
screenshot and does not move, so view the website if you want to see live map interactions.

## Running it

Sign into github and create a fork of the repository by clicking the Fork button in the top right. Once you have a fork, open your terminal and run the command to clone the repo to your workspace with `git clone <forked-url>`

Open the `index.html` file in a browser

If you would rather serve it over HTTP:

```bash
python3 -m http.server 8000
```

Then visit http://localhost:8000.

## What is here

| File                 |                                                                 |
| -------------------- | --------------------------------------------------------------- |
| `index.html`         | the markup — the app, then the modal, then the script           |
| `styles.css`         | all the styling, Skylight's palette as CSS variables at the top |
| `map-background.png` | a screenshot of the map, the only part that is not real markup  |
| `skylight-logo.svg`  | the logo                                                        |

Both source files are commented into labelled sections. In `styles.css` those are the design
tokens, then the modal, then the app behind it; `index.html` is the backdrop, then the modal, then
the script. Only one part is the exercise:

- **The modal** — the welcome panel and the sign-in form. This is what to focus on editing.
- **The app behind the modal** — the UX's chrome, as real markup: the logo and search pill,
  the revamp banner, the left rail, the legend and the time slider. The rail buttons select,
  the My Skylight panel opens with the product's real support and about links, its Log In button
  brings the modal back, and the legend collapses, otherwise things are marked that they are not
  interactable when clicking.

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
