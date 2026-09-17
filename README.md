# Counting the Invisible Ocean

A single-page retrospective of my 2024 high school internship at the
**J. Craig Venter Institute (JCVI)**, where I worked on the image classification of
phytoplankton — identifying and counting diatoms, and helping monitor algal blooms.

**Live site:** https://sturben.github.io/hunter-internship-website/

## What's here

| Section | Contents |
| --- | --- |
| **Internship** | How I ended up at a genomics institute while still in high school |
| **Project** | Diatom classification, cell counting, and algal bloom monitoring |
| **Field notes** | The weekly log I kept during the internship, reproduced as written |

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
  ocean-hero.jpg    header background (phytoplankton, NOAA via Unsplash)
  diatoms.jpg       diatom microscopy, used in the project section
  jcvi-campus.jpg   the institute
```

## Adding content

Both extension points are marked with comments in `index.html`:

- **A new weekly entry** — copy the commented `<article class="entry">` template inside
  `#journal` and fill it in.
- **A gallery** — the commented `<section id="gallery">` block near the end shows the
  markup, including the click-to-enlarge wrapper. Drop images into `images/` first.

Colors, spacing, and fonts are CSS custom properties on `:root` at the top of the
`<style>` block, so the palette can be retuned in one place.

## Credits

Header photograph by [NOAA](https://unsplash.com/@noaa) on
[Unsplash](https://unsplash.com/).

## License

See [LICENSE](LICENSE).
