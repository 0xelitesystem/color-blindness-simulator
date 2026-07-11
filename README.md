# Color Blindness Simulator

Preview how an image or a set of colors reads under common color-vision deficiencies, all in your browser. No server, no tracking, no third-party scripts.

**Live demo:** https://0xelitesystem.github.io/color-blindness-simulator/

## Use

Open `index.html` in any modern browser, or visit the GitHub Pages link in the repo description.

Two modes:

- **Image:** drag an image onto the drop zone, or click to pick a file. You get the original plus four simulated versions side by side.
- **Colors:** paste colors (one per line or comma separated) as hex, `rgb(...)`, or CSS color names. Each simulation shows the transformed swatches with their resulting HEX values.

Simulated deficiency types:

- **Protanopia** (missing long-wavelength, red, cones)
- **Deuteranopia** (missing medium-wavelength, green, cones)
- **Tritanopia** (missing short-wavelength, blue, cones)
- **Achromatopsia** (no color vision, grayscale by luminance)

Each transform is a 3x3 matrix applied per pixel on a canvas. The protanopia, deuteranopia, and tritanopia matrices are the commonly cited Vienot/Machado style approximations; achromatopsia uses standard luminance weights (0.299, 0.587, 0.114).

## Why this exists

Designers and developers need a quick way to sanity check whether a chart, a UI, or a palette still communicates when color perception changes. This does it locally in one file, so you can drop it into a design review without shipping the image anywhere.

These are approximations meant for quick checks, not a clinical diagnostic tool.

## Privacy

Everything runs in your browser. Images are read into a canvas with FileReader and colors are parsed locally. Nothing is uploaded. You can verify by viewing the page source or by opening DevTools and watching the network tab, no requests are made.

## Run locally

```bash
git clone https://github.com/0xelitesystem/color-blindness-simulator
cd color-blindness-simulator
# Open index.html in your browser, or:
python -m http.server 8000
```

## Build

There is no build. It's a single HTML file.

## License

MIT.

## Related

- [color-contrast-checker](https://github.com/0xelitesystem/color-contrast-checker)
- [color-format-converter](https://github.com/0xelitesystem/color-format-converter)
- [color-palette-from-image](https://github.com/0xelitesystem/color-palette-from-image)
