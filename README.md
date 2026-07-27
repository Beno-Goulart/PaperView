<p align="center">
  <strong>Visualize paper sizes at real scale on your monitor.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white" alt="HTML5">
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white" alt="CSS3">
  <img src="https://img.shields.io/badge/JavaScript-ES6-F7DF1E?style=flat&logo=javascript&logoColor=black" alt="JavaScript">
  <img src="https://img.shields.io/badge/Zero_Dependencies-None-4CAF50?style=flat" alt="Zero Dependencies">
</p>

<p align="center">
  <a href="#preview">Preview</a> ·
  <a href="#features">Features</a> ·
  <a href="#quick-start">Quick Start</a> ·
  <a href="#paper-sizes">Paper Sizes</a> ·
  <a href="#calibration">Calibration</a> ·
  <a href="#how-it-works">How It Works</a>
</p>

---

PaperView is a single-file HTML tool that renders **real-scale paper sizes** (A0–A6, B4–B5, Carta, Ofício) directly on your monitor. It calculates your screen's DPI from its physical dimensions and resolution, then draws each paper at its exact mm size in pixels.

## Preview

```
┌──────────────────────────────────────────────────┐
│                                                  │
│             PaperView                            │
│  Visualize tamanhos de papel em escala real      │
│                                                  │
│  1. Tamanho da tela em polegadas:                │
│  ┌──────────────────────────┐                    │
│  │         24               │                    │
│  └──────────────────────────┘                    │
│                                                  │
│  2. Formato da tela:                             │
│  ┌──────────────┬──────────────┐                 │
│  │ 1920x1080    │ 16:9         │                 │
│  └──────────────┴──────────────┘                 │
│                                                  │
│  Ecrã detectado: 1920x1080px | Proporção: 16:9   │
│                                                  │
│              [ Iniciar ]                         │
└──────────────────────────────────────────────────┘
```

## Features

| Feature | Description |
|---|---|
| Welcome Wizard | First-time setup guides you through monitor configuration |
| Auto-Detection | Detects screen resolution, DPI, and aspect ratio from browser |
| Real-Scale Rendering | Paper sizes drawn at exact mm dimensions on screen |
| DPI Calculator | Computes monitor DPI from diagonal size and resolution |
| 12 Paper Sizes | A0, A1, A2, A3, A4, A5, A6, B4, B5, Carta, Ofício, Ofício-R |
| Portrait / Landscape | Toggle orientation for any paper size |
| Print Margins | Dashed overlay showing standard print margins |
| Rulers | cm rulers on top and left edges of the paper |
| Dual-Axis Calibration | Independent X/Y scale correction for accurate sizing |
| Fullscreen Display | Paper fills the entire viewport with floating controls |
| Zero Dependencies | Pure HTML + CSS + JS, single file, no build step |

## Quick Start

### 1. Open the file

Double-click `tamanho-papel.html` or open it in your browser:

```
# Windows
start tamanho-papel.html

# macOS
open tamanho-papel.html

# Linux
xdg-open tamanho-papel.html
```

### 2. First-time setup (Welcome screen)

On first open, a setup wizard appears:

1. **Enter your monitor size** — the diagonal in inches (e.g. 17, 22, 24)
2. **Select resolution** — or let the browser auto-detect your screen
3. **Choose aspect ratio** — auto-detected based on your resolution
4. Click **Iniciar**

> Screen resolution and aspect ratio are auto-detected from your browser. You only need to enter the physical monitor size.

### 3. Select a paper size

Click any paper button (A4, A3, etc.) to display it at real size.

### 4. Calibrate (recommended)

Place a real sheet of A4 paper on your screen and adjust the on-screen paper until it matches. Then enter your measured dimensions in the calibration panel.

## Paper Sizes

| Size | Dimensions (mm) | Typical Use |
|---|---|---|
| A0 | 841 × 1189 | Posters, engineering drawings |
| A1 | 594 × 841 | Posters, flip charts |
| A2 | 420 × 594 | Posters, diagrams |
| A3 | 297 × 420 | Spreadsheets, drawings |
| **A4** | **210 × 297** | **Standard documents** |
| A5 | 148 × 210 | Notebooks, booklets |
| A6 | 105 × 148 | Postcards, index cards |
| B4 | 250 × 353 | Journals, large notebooks |
| B5 | 176 × 250 | Books, notebooks |
| Carta | 216 × 279 | US Letter |
| Ofício | 216 × 356 | Brazilian legal |
| Ofício-R | 356 × 216 | Brazilian legal (landscape) |

## Calibration

The DPI calculation assumes standard monitor dimensions. For precise sizing, PaperView offers **dual-axis calibration**:

### Automatic calibration

1. Place a real A4 sheet on your screen
2. Adjust the on-screen paper until it matches the physical sheet
3. Enter your measured width and height in mm
4. The tool auto-calculates X and Y scale factors independently

### Manual calibration

Use the X and Y sliders to fine-tune each axis separately:

| Measurement | Action |
|---|---|
| On-screen paper is wider than real | Decrease X scale |
| On-screen paper is taller than real | Decrease Y scale |
| On-screen paper is narrower than real | Increase X scale |
| On-screen paper is shorter than real | Increase Y scale |

### Why dual-axis?

Monitor DPI is not always uniform. A 17" 16:9 monitor may have slightly different physical dimensions than the theoretical calculation assumes, and the error can differ between width and height. Separate X/Y calibration handles this.

## How It Works

```
1. Input      →  User enters monitor size + resolution
2. DPI        →  diagonal_px / diagonal_inches = DPI
3. pxPerMM    →  DPI / 25.4
4. Paper px   →  paper_mm × pxPerMM × scaleAdjust
5. Render     →  White div at exact pixel dimensions, centered in viewport
6. Calibration→  user_measured / actual → correction factor
```

## Project Structure

```
papel/
├── tamanho-papel.html    # Single-file app (HTML + CSS + JS)
└── README.md             # This file
```

## Browser Support

| Browser | Status |
|---|---|
| Chrome / Edge | Full support |
| Firefox | Full support |
| Safari | Full support |

Any modern browser with CSS Grid and ES6 support.

## License

MIT
