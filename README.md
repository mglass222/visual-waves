# Visual Waves

An interactive web app for visualizing the **superposition of two waves**. Pick a shape (sine, triangle, or square) for each wave, dial in amplitude and frequency, slide one wave past the other, and watch the resulting sum update in real time.

**Live demo: https://mglass222.github.io/visual-waves/**

## Features

- Two independent waves, each configurable as **sine, triangle, or square**
- Adjustable **amplitude** and **frequency** per wave
- **Slide offset** measured in wavelengths (λ) of Wave 2 — period is defined crest-to-crest
- **Quick offset buttons** for common phase shifts: `0`, `¼ λ`, `½ λ`, `¾ λ`
- **Auto-slide** toggle for continuous animated motion
- **Sum canvas** showing the superposition, with the two source waves ghosted behind for reference
- **Click-to-place markers** on any canvas — each marker snaps to the wave and shows its `(x, y)` value live as you slide

## Running locally

It's a single self-contained HTML file with no build step or dependencies.

```bash
git clone https://github.com/mglass222/visual-waves.git
cd visual-waves
open index.html        # macOS
# or just double-click index.html in your file browser
```

If you'd rather serve it over HTTP:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Usage

1. **Pick a shape** for each wave using the Sine / Triangle / Square buttons.
2. **Adjust amplitude and frequency** with the sliders in each wave's panel.
3. **Drag the Offset slider** (or click `0`, `¼ λ`, `½ λ`, `¾ λ`) to slide Wave 2 past Wave 1 in units of its own wavelength — the Sum canvas updates instantly. A `½ λ` shift of two equal sines produces full destructive interference.
4. Click **Auto-slide** to animate the offset continuously; click again to stop.
5. **Click on any canvas** to drop a marker that shows the wave's value at that point. Click an existing marker to remove it, or use **Clear all markers**.

Try matching the frequencies of two sine waves and auto-sliding to see beats and full cancellation, or stack a square and a triangle of the same frequency to see how their harmonics interact.

## Tech

Plain HTML, CSS, and vanilla JavaScript. The waves are drawn on `<canvas>` elements with HiDPI-aware scaling. No frameworks, no build tools.
