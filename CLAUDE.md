# AlexNet, Explained

A free mini-course that explains AlexNet (2012) to a curious 15-year-old, then has them build one.
Hosted on GitHub Pages: https://fernfant.github.io/alexnet-explained/ (repo `Fernfant/alexnet-explained`, branch `main`, site served from root).

## Files

- `index.html` — the whole site. Single file, no build step, no dependencies beyond Google Fonts.
  - Six animated episodes drawn on one `<canvas>`. Each episode is an entry in the `EPS` array: `{title, scenes:[{d, cap, draw(p,t)}]}` where `d` is seconds, `cap` is the caption (also read aloud by narration), `p` is scene progress 0..1, `t` is elapsed seconds.
  - Canvas helpers: `txt`, `arrow`, `rr`, `alpha`, `seg`, `ease`, `drawCat`, `slab`. Canvas is a fixed 960×540 logical size.
  - Episode 7 ("Build It Yourself") is static HTML mirroring the notebook's key cells.
- `build_your_own_alexnet.ipynb` — the hands-on notebook, designed for Google Colab on a free T4 GPU.
- `.nojekyll` — keeps GitHub Pages from running Jekyll.

## Conventions

- Audience is 15 years old: short sentences, British spelling ("colour", "recognise"), plain words ("knobs" for parameters) with the real term introduced once.
- Facts must match the 2012 paper (Krizhevsky, Sutskever & Hinton, NeurIPS 2012). Note torchvision's AlexNet is the single-GPU variant with 64 first-layer filters, not 96.
- Keep the site dependency-free and working offline apart from fonts. Colours are CSS tokens on `:root` with a dark-mode override; canvas uses its own `C` palette.
- Browser storage (`localStorage`) is only for per-viewer conveniences such as progress; always wrap it in try/catch.
- When changing notebook code, update the matching snippet in `index.html` Episode 7 so they stay in sync.
- Notebook must run top to bottom on Colab with no edits; keep total GPU time around 15 minutes.

## Checking changes

- Open `index.html` directly in a browser (or `python3 -m http.server`) and play through the episodes; check the browser console for errors.
- Validate the notebook JSON: `python3 -c "import json;json.load(open('build_your_own_alexnet.ipynb'))"`.
