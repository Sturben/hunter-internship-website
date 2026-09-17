# Counting the Invisible Ocean

A single-page retrospective of my 2024 high school internship at the
**J. Craig Venter Institute (JCVI)**, where I worked on the image classification of
phytoplankton — identifying and counting diatoms, and helping monitor algal blooms.

**Live site:** https://sturben.github.io/hunter-internship-website/

## What's here

| Section | Contents |
| --- | --- |
| **Internship** | How I ended up at a genomics institute while still in high school |
| **Project** | Diatoms, the IFCB imaging instrument, and building the cell counter |
| **Results** | Version 1 vs Version 2, and why the lower score was the better model |
| **Gallery** | IFCB captures and Roboflow annotation screens |
| **My mentor** | Three things Vivian told me |

The trained model and its annotated dataset are public:
[centric-diatom-counting on Roboflow Universe](https://universe.roboflow.com/allen-lab-mzqbb/centric-diatom-counting/dataset/2).

## Running it locally

There is no build step — it's one static HTML file with inlined CSS and JS.

```bash
git clone https://github.com/sturben/hunter-internship-website.git
cd hunter-internship-website
python3 -m http.server 8000
```

Then open <http://localhost:8000>. Opening `index.html` directly in a browser also
works; a server is only needed so relative image paths behave exactly as they do
when deployed.

## Structure

```
index.html          the whole site — markup, styles, and scripts
images/
  ocean-hero.jpg            header background (phytoplankton, NOAA via Unsplash)
  diatoms.jpg               diatom microscopy, used in the project section
  jcvi-campus.jpg           the institute
  ifcb-diatom.jpg           a centric diatom chain as captured by the IFCB
  roboflow-dataset.jpg      the annotated dataset
  roboflow-annotating.jpg   annotating a chain cell by cell
  model-v1.jpg              Version 1 inference: no predictions
  model-v2.jpg              Version 2 inference: cells detected
```

## Adding content

To add a gallery image, drop the file in `images/` and copy an existing `<li>` inside
`.gallery` in `index.html`, updating the `src`, `width`, `height`, `alt`, `data-zoom`
and `data-caption`. The `width`/`height` attributes matter: without them a lazy-loaded
image reserves no layout space.

Colors, spacing, and fonts are CSS custom properties on `:root` at the top of the
`<style>` block, so the palette can be retuned in one place.

## Credits

Header photograph by [NOAA](https://unsplash.com/@noaa) on
[Unsplash](https://unsplash.com/). The microscopy captures and Roboflow screenshots are
from the internship project.

## License

See [LICENSE](LICENSE).
