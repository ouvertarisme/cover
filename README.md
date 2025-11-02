# 🎨 Pixelated Gradient Book Cover Designer

An interactive web tool to **design a pixelated book cover** with a 4-corner gradient background.  
Control the **aspect ratio**, **tile size**, and **colors** from the interface — then **export your creation as an SVG**.

---

## 🚀 Features

- 🎛️ Adjustable **aspect ratio** (`0.5 → 2.0`)
- 🧱 Adjustable **pixel / tile size**
- 🎨 Independent **corner colors** (top-left / top-right / bottom-left / bottom-right)
- 🔄 **Live preview** of the generated cover
- 💾 **Export as SVG** or **Copy to clipboard**
- 🎲 **Randomize colors** for inspiration
- ⚡ Pure HTML + CSS + Vanilla JS — no dependencies

---

## 🧩 How It Works

The cover is drawn as a grid of **square tiles**, each tile’s color being the **bilinear interpolation** of the four corner colors at its center.

Mathematically:

```
color(x, y) = lerp(
    lerp(TL, TR, x),
    lerp(BL, BR, x),
    y
)
```

Each tile is then rendered as a `<rect>` in SVG, ensuring **crisp edges** and perfect export fidelity.

---

## 🛠️ Usage

### 1. Open in browser
Just open **`index.html`** — everything runs locally.

No build step, no server needed.

### 2. Tweak the controls
Use the sliders and color pickers to customize:
- Aspect ratio (width / height)
- Tile size (in pixels)
- Cover width (resolution)
- Corner colors

### 3. Export your cover
Click **Download SVG** or **Copy SVG** to get your final design.

---

## 📁 Project Structure

```
cover/
│
├── CoverGradientGenerator.html  # Main HTML + JS app
└── README.md                    # You're reading it
```

---

## 🧠 Technical Notes

- Each render rebuilds the SVG dynamically.
- Uses **bilinear color interpolation** for smooth gradients.
- The average color of each tile = the gradient sampled at the tile center.
- Exported SVGs are **resolution-independent** — perfect for print.

---

## 💡 Ideas for Extension

- 🖌️ Add title text overlay and typography controls  
- 📐 Add common book ratios (A5, 6x9, etc.) presets  
- 🧾 Export to PNG (using `canvas.toDataURL()`)  
- 🌀 Animate gradients over time  
- 🎚️ Integrate color harmonies (complementary, triadic)

---

## 📜 License

**Unlicense** — This is free and unencumbered software released into the public domain.  
See [UNLICENSE](https://unlicense.org) for details.

---

## ✨ Author

**Yann Lechelle**  
[probabl.ai](https://probabl.ai) • [ouvertarisme.fr](https://ouvertarisme.fr)

---

> “Every pixel is a vote for openness.”
