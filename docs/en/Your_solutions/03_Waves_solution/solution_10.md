# Task 10 – Animation of Multiple Wave Sources

## Problem Statement

Create an HTML animation in which the user can place point sources of waves described by

$$
u(\vec{r},t) = \frac{A}{|\vec{r}-\vec{r_0}|^\alpha} \sin\left( k|\vec{r} - \vec{r_0}| - \omega t \right)
$$

where $\vec{r_0}$ is the source position and

$$
\alpha \in [0,2]
$$

The animation must show the superposition of waves from all sources.

## Theory

If there are many sources, the total displacement is the sum of all contributions:

$$
u_{\text{tot}}(\vec{r},t) = \sum_i \frac{A}{|\vec{r}-\vec{r_i}|^\alpha} \sin\left( k|\vec{r} - \vec{r_i}| - \omega t \right)
$$

The parameter $\alpha$ controls how strongly the amplitude decreases with distance:

- $\alpha = 0$ gives no radial decay,
- larger $\alpha$ gives faster decay.

## Step-by-Step Solution

### 1. Spatial model

For each source at position

$$
\vec{r_i}
$$

compute the distance

$$
d_i = |\vec{r} - \vec{r_i}|
$$

Then evaluate the contribution from each source and sum them.

### 2. Numerical stabilization

At the source position, the denominator becomes very small. In numerical animation this is handled by replacing

$$
d_i
$$

with a small cutoff value when needed.

### 3. Visualization

A practical visualization maps positive and negative displacement to different colors, while zero displacement is shown by a neutral color.

### 4. Interactivity

The user should be able to:

- click on the canvas to place new sources,
- change $\alpha$ with a slider,
- clear the sources.

## Final Result

The total field is

$$
u_{\text{tot}}(\vec{r},t) = \sum_i \frac{A}{|\vec{r}-\vec{r_i}|^\alpha} \sin\left( k|\vec{r} - \vec{r_i}| - \omega t \right)
$$

The animation in `solution_10_animation.html` implements this model in real time.

## Interpretation

This animation visualizes the superposition principle directly. With multiple sources, interference patterns emerge from constructive and destructive addition of the local displacements.

## Interactive HTML Source

Copy the HTML code from `solution_10_animation.html` into a separate file to run the animation locally.

























<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Wave Sources Superposition</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #0f172a;
      color: #e2e8f0;
    }
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 18px;
    }
    .controls {
      display: grid;
      grid-template-columns: repeat(4, minmax(180px, 1fr));
      gap: 12px;
      margin-bottom: 16px;
    }
    .card {
      background: #111827;
      border: 1px solid #334155;
      border-radius: 12px;
      padding: 12px;
    }
    label {
      display: block;
      font-weight: bold;
      margin-bottom: 6px;
    }
    input[type="range"] {
      width: 100%;
    }
    button {
      background: #2563eb;
      color: white;
      border: none;
      border-radius: 8px;
      padding: 10px 12px;
      cursor: pointer;
      margin-right: 8px;
    }
    button:hover {
      background: #1d4ed8;
    }
    canvas {
      display: block;
      width: 100%;
      max-width: 1000px;
      height: auto;
      border: 1px solid #334155;
      border-radius: 12px;
      background: black;
      image-rendering: pixelated;
    }
    .footer {
      margin-top: 12px;
      font-size: 14px;
      color: #cbd5e1;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Wave Sources – Superposition</h1>
    <p>Click on the canvas to add wave sources.</p>

    <div class="controls">
      <div class="card">
        <label for="alphaSlider">alpha</label>
        <input id="alphaSlider" type="range" min="0" max="2" step="0.01" value="1.0">
        <div>alpha = <span id="alphaValue">1.00</span></div>
      </div>

      <div class="card">
        <label for="lambdaSlider">wavelength</label>
        <input id="lambdaSlider" type="range" min="10" max="120" step="1" value="45">
        <div>lambda = <span id="lambdaValue">45</span> px</div>
      </div>

      <div class="card">
        <label for="omegaSlider">omega</label>
        <input id="omegaSlider" type="range" min="0.5" max="8" step="0.1" value="3">
        <div>omega = <span id="omegaValue">3.0</span></div>
      </div>

      <div class="card">
        <label for="ampSlider">amplitude</label>
        <input id="ampSlider" type="range" min="0.2" max="4" step="0.1" value="1.2">
        <div>A = <span id="ampValue">1.2</span></div>
      </div>
    </div>

    <div style="margin-bottom: 12px;">
      <button id="clearBtn">Clear all</button>
      <button id="removeLastBtn">Remove last</button>
      <span>Sources: <span id="sourceCount">0</span></span>
    </div>

    <canvas id="fieldCanvas" width="1000" height="650"></canvas>

    <div class="footer">
      Bright red and blue regions indicate positive and negative displacement. White dots mark the source positions.
    </div>
  </div>

  <script>
    const canvas = document.getElementById("fieldCanvas");
    const ctx = canvas.getContext("2d");
    const width = canvas.width;
    const height = canvas.height;

    const alphaSlider = document.getElementById("alphaSlider");
    const lambdaSlider = document.getElementById("lambdaSlider");
    const omegaSlider = document.getElementById("omegaSlider");
    const ampSlider = document.getElementById("ampSlider");

    const alphaValue = document.getElementById("alphaValue");
    const lambdaValue = document.getElementById("lambdaValue");
    const omegaValue = document.getElementById("omegaValue");
    const ampValue = document.getElementById("ampValue");
    const sourceCount = document.getElementById("sourceCount");

    const clearBtn = document.getElementById("clearBtn");
    const removeLastBtn = document.getElementById("removeLastBtn");

    const sources = [];
    let time = 0;

    function updateLabels() {
      alphaValue.textContent = parseFloat(alphaSlider.value).toFixed(2);
      lambdaValue.textContent = lambdaSlider.value;
      omegaValue.textContent = parseFloat(omegaSlider.value).toFixed(1);
      ampValue.textContent = parseFloat(ampSlider.value).toFixed(1);
      sourceCount.textContent = sources.length;
    }

    function clamp(v, min, max) {
      return Math.max(min, Math.min(max, v));
    }

    function draw() {
      const image = ctx.createImageData(width, height);
      const data = image.data;

      const alpha = parseFloat(alphaSlider.value);
      const lambda = parseFloat(lambdaSlider.value);
      const omega = parseFloat(omegaSlider.value);
      const A = parseFloat(ampSlider.value);
      const k = 2 * Math.PI / lambda;

      const step = 3;

      for (let y = 0; y < height; y += step) {
        for (let x = 0; x < width; x += step) {
          let u = 0;

          for (const s of sources) {
            const dx = x - s.x;
            const dy = y - s.y;
            let r = Math.sqrt(dx * dx + dy * dy);
            if (r < 3) r = 3;

            const decay = alpha === 0 ? 1 : Math.pow(r, alpha);
            u += (A / decay) * Math.sin(k * r - omega * time);
          }

          const mapped = clamp(Math.tanh(2.8 * u), -1, 1);
          const red = mapped > 0 ? Math.floor(255 * mapped) : 0;
          const blue = mapped < 0 ? Math.floor(255 * (-mapped)) : 0;
          const green = Math.floor(30 + 100 * (1 - Math.abs(mapped)));

          for (let yy = 0; yy < step; yy++) {
            for (let xx = 0; xx < step; xx++) {
              const px = x + xx;
              const py = y + yy;
              if (px >= width || py >= height) continue;
              const idx = (py * width + px) * 4;
              data[idx] = red;
              data[idx + 1] = green;
              data[idx + 2] = blue;
              data[idx + 3] = 255;
            }
          }
        }
      }

      ctx.putImageData(image, 0, 0);

      for (const s of sources) {
        ctx.fillStyle = "white";
        ctx.beginPath();
        ctx.arc(s.x, s.y, 4, 0, 2 * Math.PI);
        ctx.fill();
      }
    }

    function animate() {
      time += 0.06;
      draw();
      requestAnimationFrame(animate);
    }

    canvas.addEventListener("click", (e) => {
      const rect = canvas.getBoundingClientRect();
      const scaleX = width / rect.width;
      const scaleY = height / rect.height;
      const x = (e.clientX - rect.left) * scaleX;
      const y = (e.clientY - rect.top) * scaleY;
      sources.push({ x, y });
      updateLabels();
    });

    clearBtn.addEventListener("click", () => {
      sources.length = 0;
      updateLabels();
    });

    removeLastBtn.addEventListener("click", () => {
      sources.pop();
      updateLabels();
    });

    [alphaSlider, lambdaSlider, omegaSlider, ampSlider].forEach(el => {
      el.addEventListener("input", updateLabels);
    });

    updateLabels();
    animate();
  </script>
</body>
</html>
