# Online Qibla Compass

A free, browser-based Qibla compass that points toward the Kaaba in Makkah from anywhere in the world, built on the embeddable compass widget from [QiblaFind](https://qiblafind.net/).

**Live site:** https://erfanmola.github.io/qibla-compass/

![Online Qibla Compass](public/og.png)

## Features

- Live compass that follows your phone as you turn, with a gold highlight when you face the Qibla
- Great-circle Qibla bearing and distance to the Kaaba for your location
- Manual city search if you prefer not to share your location
- Works on phones, tablets and desktops, in light and dark mode
- Copy-paste embed code for your own website

## Embed it on your own site

Paste this where you want the widget to appear. It is free, needs no API key, and works on any
page that allows iframes:

```html
<iframe src="https://qiblafind.net/embed/qibla" title="Qibla compass" width="100%" height="860" style="border:0;max-width:100%" loading="lazy" allow="geolocation; accelerometer; gyroscope; magnetometer"></iframe>
<p style="font-size:13px"><a href="https://qiblafind.net/">Qibla compass</a> by QiblaFind</p>
```

The full version of this tool is at **[QiblaFind](https://qiblafind.net/)**.

## How this repository works

This is a small static site with no dependencies:

- `src/index.html` holds the page, with `{{PLACEHOLDERS}}` that are filled at build time.
- `scripts/build.mjs` renders it into `dist/`, along with `robots.txt` and `sitemap.xml`.
- `.github/workflows/pages.yml` builds and deploys to GitHub Pages on every push to `main`,
  and rebuilds monthly so date-based text stays current.

The site URL comes from GitHub Pages itself, so a fork or a copy under another account deploys
correctly without edits:

1. Push the repository to GitHub.
2. Open **Settings → Pages** and set **Source** to **GitHub Actions**.
3. Push to `main`, or run the workflow manually.

To build locally, run `node scripts/build.mjs` (Node 18 or newer). The output goes to `dist/`.

Optional repository variables:

- `EMBED_ORIGIN` loads the widget from another deployment.
- `LINK_ORIGIN` changes where the tool links point.

Both default to `https://qiblafind.net`.

## More free tools from QiblaFind

- [Online Qibla Finder](https://qiblafind.net/)
- [Prayer times](https://qiblafind.net/prayer-times)
- [Hijri calendar](https://qiblafind.net/hijri-calendar)
- [Ramadan 2027](https://qiblafind.net/ramadan-2027)
- [Mosque finder](https://qiblafind.net/mosque-finder)
- [Qibla direction by city](https://qiblafind.net/qibla-direction)

## License

MIT. See [LICENSE](LICENSE). The embedded widget is provided by
[QiblaFind](https://qiblafind.net).
