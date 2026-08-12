# The Three-Axis Framework — Interactive Model

An interactive visualisation of the three-axis framework
(**Kind ↔ Wicked**, **Simple ↔ Complex**, **AI ↔ Human**) set out in
Section 2.1 / Figure 2.1 of the paper below. Three sliders move a live
3D cube; the tool reports a plain-language tier verdict and a hedged
pointer note for the position selected.

**Live demo:** once hosted on GitHub Pages, this is `index.html` at the
repo root — e.g. `https://<your-username>.github.io/<repo-name>/`.

## Citation

> Grice-Lloyd, D. (2026). *Accountability in Action: Exploring Ethical
> and Legal Risks in AI-Supported Employee Relations in the UK Railway
> Industry.* https://doi.org/10.31235/osf.io/h42ef_v1
>
> ORCID: [0009-0002-1212-322X](https://orcid.org/0009-0002-1212-322X)

The three-axis framework itself is a conceptual aid presented in the
paper and **is not an empirically validated model** — this tool does not
present it as one.

## What this is / isn't

- The **cube** is a literal 3D rendering of the paper's own eight-cell
  structure, coloured with the exact palette sampled from Figure 2.1.
- The **tier verdict** and **pointer note** are an interpretive extension
  built on top of the framework, clearly labelled as such in the tool —
  not paper content.
- Only 4 of the 8 corners have a paper-given example (Kind/Simple/AI,
  Kind/Complex/AI, Wicked/Simple/Human, Wicked/Complex/Human). The other
  four are labelled as having no source example — none is invented.
- No data leaves the browser: no analytics, no storage, no runtime
  network calls. Slider state resets on reload.
- This tool was built using AI and has been checked for accuracy by a
  human subject matter expert (see the in-tool footer for the same note).

## Deployment

**GitHub Pages:** enable Pages on this repo (Settings → Pages → Deploy
from branch → `main` / root). The tool needs no build step — `index.html`
is fully self-contained, including a vendored copy of Three.js r128.

**SharePoint (iframe embed):**

```html
<iframe
  src="https://<your-username>.github.io/<repo-name>/"
  style="width:100%; min-height:720px; border:0;"
  title="The Three-Axis Framework — interactive model">
</iframe>
```

**Demo / GIF capture mode:** append `?demo=1` to the URL to run a scripted,
non-interactive sequence of slider journeys — useful for screen-recording
a clean GIF for sharing (e.g. LinkedIn). Journeys are configured in
`CONFIG.demoJourneys` inside `index.html`.

## Accessibility

Built to WCAG 2.1 AA: the tier verdict, pointer note, and octant caption
are genuine DOM text (not canvas-rendered), sliders are native
`<input type="range">` elements operable by keyboard, and the 3D canvas
is marked `aria-hidden` since everything it shows is also stated in text.

## Licence

CC BY 4.0 — see [LICENSE](./LICENSE). Three.js is bundled under its own
MIT licence (Copyright 2010–2021 Three.js Authors).

## Editing

Almost everything content-related — the colour palette, axis phrase
banks, tier verdict wording, sourced examples, and demo journeys — lives
in a single `CONFIG` object near the top of the vendored scripts inside
`index.html`.
