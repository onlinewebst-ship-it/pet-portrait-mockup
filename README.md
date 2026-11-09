# Pet Portrait Engine — rescue fundraising mockup

A working design mockup of a **portrait fundraising page for an animal rescue**: donor uploads one
photo, sees three free watermarked previews, then pays a suggested donation for the full-resolution
file or a printed keepsake.

**Fictional charity.** "Salty Paws Rescue" does not exist, no donations are taken, and every figure
on the page is invented. The page says so in a fixed badge and in the footer.

## What is real in it

- **The generation is real.** Upload a photo and three portraits are produced by an AI image model
  (Gemini 3.1 Flash Image via OpenRouter), roughly 9–12 seconds for the set. They are not filters.
- The page is static (GitHub Pages), so the API key cannot live in it. The browser posts the photo to
  a small PHP endpoint on the estate's own hosting, which holds the key outside the document root and
  returns one image per style. See `reference/rescue-groomer-engine.md` in the portfolio briefs for
  the endpoint, limits and costs.
- If the service is down or rate-limited, the page falls back to locally-styled previews and says so
  on screen — the demo never shows a broken box.
- Layout, type, copy, pricing structure and mobile behaviour are production-quality, not a wireframe.
- Print prices and the £15-per-order donation split are modelled on real UK print-on-demand costs
  (Prodigi: mug from £3.54, framed print from £16.00, blanket from £30.00) rather than invented.

## Limits on the live demo

- 3 images per upload, 12 images per IP per day, 60 images per day globally (~£4/day ceiling).
- Photos are held in memory for the request and not written to disk.
- Previews are watermarked in CSS; the model is instructed never to add text, frames or watermarks.

## Viewing it

Open `index.html` directly, or serve the folder:

```sh
python3 -m http.server 8080
```

## Photography

Wikimedia Commons and Openverse, CC0 / public domain. No stock licence is required and nothing is
hotlinked — the images are committed in `img/`.

## Why this exists

Built by Online Web Studio as a sales artefact: it is the thing a rescue or groomer is shown when
being offered the portrait engine. Background and market evidence live in the portfolio briefs, not
in this repo.
