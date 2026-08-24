# Leaf Scanner

A browser-based tool for measuring leaf area from a photo. Take a picture of a leaf next to a calibration swatch of known size, and Leaf Scanner works out the leaf's real-world area from the two pixel counts. Everything runs locally in the browser — no photo is ever uploaded anywhere.

## How it works

Area is estimated as:

```
leaf area = (leaf pixel count) × (calibration area ÷ calibration pixel count)
```

This is the same core method described in Easlon & Bloom, *Applications in Plant Sciences* (2014), generalized here to work with any calibration color instead of a fixed formula, and with detection tuned by hand or by auto-suggestion rather than one preset tolerance.

For best accuracy, keep the leaf and the calibration swatch in the same plane, avoid harsh shadows, and prefer a flatbed scan or a straight-down shot over a wide-angle close-up photo.

## Features

- **Calibration-based measurement** — works with any color swatch of known area, not just a fixed reference object.
- **Multi-color matching** — add several include/exclude colors per group (leaf or calibration) to cover a leaf's different shades, or punch out a color that's sneaking into the match.
- **Add color** — tap once inside a leaf piece or the calibration swatch and it detects that region's whole color range from its actual edges, instead of sampling a single pixel.
- **Brush select** — paint exact pixels into the leaf or calibration count by hand, for a spot no color match can reach.
- **Lasso select** — trace the outline of a shape and everything inside it is forced into the leaf or calibration count at once.
- **Move tool** — pan a zoomed-in photo without accidentally painting, tracing, or picking a color.
- **Crop** — trim the photo to just the area you need; the result is refit to the photo panel automatically.
- **Resizable photo panel** — drag the handle below the photo, or use the Collapse/Expand button, to free up screen space for the settings panel. The size is remembered between visits.
- **Undo** covers essentially every action, including brush strokes and lasso fills.
- **Reset image** clears the current photo and all settings back to a clean start, without touching your saved measurement log.
- **Session log** — log each measurement as you go and export it as a CSV.
- **Save image** — exports the original photo and the detected overlay side by side, with the reading and settings baked into a caption footer, so the PNG is self-contained documentation.
- **Original / Detected / Mask views** to check exactly what's being counted.
- **Light and dark themes**, with a Palatino Linotype / Book Antiqua / Georgia serif for readings and a monospace for data.

## Usage

1. Open `index.html` in a browser (or visit the hosted version, if you're using one).
2. Choose a photo containing both the leaf(s) and a calibration swatch of known area.
3. Enter the calibration swatch's known area (defaults to 4 cm²) and its unit.
4. Use **Add color** (or Brush select / Lasso select) to mark the leaf color(s) and the calibration color(s). The app will often auto-suggest a starting point.
5. Adjust tolerance per color if the match is too tight or too loose. Use the Exclude tab to remove a color that's incorrectly matching.
6. Check the reading, switch between Original/Detected/Mask to verify, and log or save the measurement when you're happy with it.

No installation, build step, or server is required — it's a single self-contained HTML file. It also works fully offline once downloaded, since nothing is fetched from the network at runtime.

## Privacy

Photos are processed entirely client-side using the Canvas API. Nothing is uploaded to a server at any point.

## Browser support

Works in modern Chromium, Firefox, and Safari. Requires JavaScript and the HTML5 Canvas API.

## License

MIT — see [LICENSE](LICENSE) for details.

## Citation

If you use Leaf Scanner in your work, please cite it:

Alongi, F. (2026). *Leaf Scanner* (Version 1.0.0) [Computer software]. Zenodo. https://doi.org/10.5281/zenodo.22081530


