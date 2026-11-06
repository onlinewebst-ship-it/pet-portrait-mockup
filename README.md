# Pet Portrait Engine — rescue fundraising mockup

A working design mockup of a **portrait fundraising page for an animal rescue**: donor uploads one
photo, sees three free watermarked previews, then pays a suggested donation for the full-resolution
file or a printed keepsake.

**Fictional charity.** "Salty Paws Rescue" does not exist, no donations are taken, and every figure
on the page is invented. The page says so in a fixed badge and in the footer.

## What is real in it

- The **upload → preview** step genuinely works. The photo is read with `FileReader` in the browser
  and styled locally with CSS filters — nothing is uploaded, no network call is made, and the three
  previews are the visitor's own photo. In production this step is the AI generation call.
- Layout, type, copy, pricing structure and mobile behaviour are production-quality, not a wireframe.
- Print prices and the £15-per-order donation split are modelled on real UK print-on-demand costs
  (Prodigi: mug from £3.54, framed print from £16.00, blanket from £30.00) rather than invented.

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
