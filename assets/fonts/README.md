# DABAB Brand Fonts

The original design specifies the commercial **29LT Bukra** (display/headings)
and **29LT Zeyn** (body) typefaces. These are licensed fonts from the 29LT
foundry and are **not** bundled with this project.

To keep both Arabic and English text rendering correctly, the site uses close,
freely-licensed substitutes:

- **Cairo** — substitute for 29LT Bukra (geometric display sans)
- **Tajawal** — substitute for 29LT Zeyn (clean text sans)

## Self-hosted (no external CDN)

The substitute fonts are **self-hosted**, not loaded from Google Fonts, so the
site loads instantly and works offline. The woff2 files live in
`src/assets/fonts/` and the `@font-face` declarations are in `src/fonts.css`
(Vite fingerprints the files and rewrites the URLs with the app base path).

To regenerate the files: fetch the Google `css2` stylesheet for
`Cairo:wght@400;500;600;700` and `Tajawal:wght@300;400;500;700` with a modern
browser User-Agent, download each woff2 it references, and recreate the
`@font-face` blocks in `src/fonts.css` pointing at the local files.

## Using the licensed 29LT fonts

If you have a license for the 29LT fonts, place valid font files in
`src/assets/fonts/`, add matching `@font-face` blocks to `src/fonts.css`, and
prepend the families (`'29LT Bukra'`, `'29LT Zeyn'`) to the `--app-font-*`
stacks in `src/index.css` so they take priority over the substitutes.
