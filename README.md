# AI Face Score

Browser-local AI facial harmony analysis. MediaPipe FaceMesh 468-point geometry scoring — your photos never leave your device.

![AI Face Score](https://aifacescore.com/og-cover.webp)

## What is this?

A collection of browser-based facial geometry tools. All processing happens client-side — no images are uploaded to any server.

### [aifacescore.com](https://aifacescore.com) — Facial Harmony Scoring

Upload a front-facing selfie and get a 0–100 Facial Harmony Score in under one second.

**Free tier:**
- Overall harmony score + population percentile
- Four dimensions: Symmetry, Golden Ratio, Feature Proportions, Contour Balance
- Radar chart visualization
- Shareable result card (JPG)

**Premium ($1.99 / $4.99 / $6.99):**
- Multi-page A4 PDF report
- Raw geometric measurements (eye/nose/mouth/jaw ratios)
- Dimension-by-dimension breakdown
- Personalized styling & photography suggestions

### [aifaceanalyze.com](https://aifaceanalyze.com) — Raw Geometry Explorer

Free companion tool. No score, no judgment — just raw facial geometry data.

- 468-point landmark visualization with toggleable layers
- 16+ measurements: symmetry, thirds, fifths, golden ratio, eye/nose/mouth/jaw proportions
- Face type classification (Oval, Round, Square, Heart, Oblong)
- Downloadable share poster
- Angle warning for non-frontal photos

### [nicheaitool.com](https://nicheaitool.com) — AI Tool Comparison & Calculators

AI tool reviews, comparisons, and free SaaS calculators.

- 13+ free calculators: SaaS Revenue, ROAS, CAC, Churn, MRR Growth, ROI, LTV:CAC, and more
- AI tool comparison pages and alternatives guides
- SEO-focused content site

### [hearthveilpress.com](https://hearthveilpress.com) — Digital Publishing

Independent digital publisher. Ebooks, templates, and long-form content.

- 21+ ebooks across fiction and non-fiction
- EPUB + Markdown formats
- Digital templates and guides

## Tech Stack

| Layer | Technology |
|---|---|
| Face detection | MediaPipe FaceMesh (@0.4.1633559619) |
| PDF generation | jsPDF 2.5.1 |
| Styling | Tailwind CSS (static build) |
| Hosting | Cloudflare Pages |
| Backend | None — 100% client-side |
| Payment | PayPal Smart Buttons |

## How It Works

1. User uploads a photo
2. MediaPipe FaceMesh runs in-browser via WebAssembly
3. 468 facial landmarks are extracted
4. Geometry engine computes symmetry, golden ratio, proportions, and contour balance
5. Scores are calibrated against a 5,000+ face dataset
6. Results render instantly — no server round-trip

## Privacy

- **Photos never leave your browser.** All image processing happens locally via WebGL/WebAssembly.
- No accounts, no tracking cookies, no data collection.
- Premium credits are stored in `localStorage`.
- The only external requests are: MediaPipe CDN (model files), PayPal (payment), and Cloudflare Insights (anonymous page stats).

## Local Development

```bash
# Clone
git clone https://github.com/bite-arcade/aifacescore.git
cd aifacescore

# Serve locally (any static server works)
npx serve .
# or
python -m http.server 8080
```

Then open `http://localhost:8080`.

> Note: MediaPipe requires HTTPS or localhost. `file://` protocol will not load the model.

## Project Structure

```
aifacescore-site/
├── index.html          # Main site (scoring + PDF)
├── styles.css          # Tailwind static build
├── logo.png            # Brand logo
├── hero-banner.webp    # Hero visual
└── og-cover.webp       # Social share image

aifaceanalyze-site/
├── index.html          # Analysis tool (landmarks + measurements)
├── styles.css
└── hero-banner.webp
```

## Testing Premium Features

Premium reports can be tested without payment:

1. Open the browser console (F12)
2. Run: `localStorage.setItem('previewMode', '1')`
3. Refresh the page
4. Upload a photo — premium report unlocks automatically

To disable: `localStorage.removeItem('previewMode')`

## License

MIT — free for personal and commercial use. MediaPipe and jsPDF have their own licenses.

## Links

- [aifacescore.com](https://aifacescore.com)
- [aifaceanalyze.com](https://aifaceanalyze.com)
- [nicheaitool.com](https://nicheaitool.com)
- [hearthveilpress.com](https://hearthveilpress.com)
