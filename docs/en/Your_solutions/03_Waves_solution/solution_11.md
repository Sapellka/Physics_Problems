# Task 11 – Animation of Two-Slit Interference

## Problem Statement

Create an HTML animation of Young's experiment in which two slits act as coherent point sources:

$$
u(\vec{r},t) = \frac{A}{|\vec{r}-\vec{r_1}|} \sin\left( k|\vec{r} - \vec{r_1}| - \omega t \right) + \frac{A}{|\vec{r}-\vec{r_2}|} \sin\left( k|\vec{r} - \vec{r_2}| - \omega t \right)
$$

The user must be able to change:

- slit separation

$$
d = |\vec{r_1} - \vec{r_2}|
$$

- wavelength $\lambda$.

The animation should show the interference pattern in real time.

## Theory

The total displacement at each point is the sum of the displacements coming from the two coherent sources.

Constructive interference occurs when the path difference is an integer multiple of the wavelength.

Destructive interference occurs when the path difference is a half-integer multiple of the wavelength.

## Step-by-Step Solution

### 1. Source positions

Choose two source points

$$
\vec{r_1}, \qquad \vec{r_2}
$$

with adjustable separation

$$
d = |\vec{r_1} - \vec{r_2}|
$$

### 2. Field evaluation

At every point $\vec{r}$ on the screen, compute

$$
r_1 = |\vec{r} - \vec{r_1}|
$$

and

$$
r_2 = |\vec{r} - \vec{r_2}|
$$

Then evaluate the total displacement using the given formula.

### 3. Visualization

A time-dependent color map can show the instantaneous displacement, while a static brightness pattern can be obtained from the time-averaged intensity. For a real-time animation, the instantaneous field is sufficient.

### 4. User controls

The animation should provide sliders for:

- slit distance $d$,
- wavelength $\lambda$.

## Final Result

The total field is

$$
u(\vec{r},t) = \frac{A}{r_1} \sin\left( kr_1 - \omega t \right) + \frac{A}{r_2} \sin\left( kr_2 - \omega t \right)
$$

where

$$
r_1 = |\vec{r} - \vec{r_1}|, \qquad r_2 = |\vec{r} - \vec{r_2}|
$$

The animation in `solution_11_animation.html` implements this model.

## Interpretation

Changing the slit distance changes the spacing of the interference fringes. Changing the wavelength also changes the fringe spacing, because the relative phase difference across the observation region depends directly on $\lambda$.

## Interactive HTML Source

Copy the HTML code from `solution_11_animation.html` into a separate file to run the animation locally.
























<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Young Two-Slit Interference</title>
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
    <h1>Young's Two-Slit Interference</h1>

    <div class="controls">
      <div class="card">
        <label for="dSlider">slit distance d</label>
        <input id="dSlider" type="range" min="20" max="220" step="1" value="90">
        <div>d = <span id="dValue">90</span> px</div>
      </div>

      <div class="card">
        <label for="lambdaSlider">wavelength lambda</label>
        <input id="lambdaSlider" type="range" min="10" max="100" step="1" value="36">
        <div>lambda = <span id="lambdaValue">36</span> px</div>
      </div>

      <div class="card">
        <label for="omegaSlider">omega</label>
        <input id="omegaSlider" type="range" min="0.5" max="8" step="0.1" value="3.0">
        <div>omega = <span id="omegaValue">3.0</span></div>
      </div>

      <div class="card">
        <label for="ampSlider">amplitude A</label>
        <input id="ampSlider" type="range" min="0.2" max="4.0" step="0.1" value="1.4">
        <div>A = <span id="ampValue">1.4</span></div>
      </div>
    </div>

    <canvas id="canvas" width="1000" height="650"></canvas>

    <div class="footer">
      The two slits are shown as bright points on the left. The color pattern represents the instantaneous resultant displacement.
    </div>
  </div>

  <script>
    const canvas = document.getElementById("canvas");
    const ctx = canvas.getContext("2d");
    const width = canvas.width;
    const height = canvas.height;

    const dSlider = document.getElementById("dSlider");
    const lambdaSlider = document.getElementById("lambdaSlider");
    const omegaSlider = document.getElementById("omegaSlider");
    const ampSlider = document.getElementById("ampSlider");

    const dValue = document.getElementById("dValue");
    const lambdaValue = document.getElementById("lambdaValue");
    const omegaValue = document.getElementById("omegaValue");
    const ampValue = document.getElementById("ampValue");

    let time = 0;

    function updateLabels() {
      dValue.textContent = dSlider.value;
      lambdaValue.textContent = lambdaSlider.value;
      omegaValue.textContent = parseFloat(omegaSlider.value).toFixed(1);
      ampValue.textContent = parseFloat(ampSlider.value).toFixed(1);
    }

    function clamp(v, min, max) {
      return Math.max(min, Math.min(max, v));
    }

    function drawBarrier(x, y1, y2) {
      ctx.strokeStyle = "#94a3b8";
      ctx.lineWidth = 6;

      ctx.beginPath();
      ctx.moveTo(x, 0);
      ctx.lineTo(x, y1 - 14);
      ctx.moveTo(x, y1 + 14);
      ctx.lineTo(x, y2 - 14);
      ctx.moveTo(x, y2 + 14);
      ctx.lineTo(x, height);
      ctx.stroke();
    }

    function draw() {
      const image = ctx.createImageData(width, height);
      const data = image.data;

      const d = parseFloat(dSlider.value);
      const lambda = parseFloat(lambdaSlider.value);
      const omega = parseFloat(omegaSlider.value);
      const A = parseFloat(ampSlider.value);
      const k = 2 * Math.PI / lambda;

      const sx = 180;
      const sy1 = height / 2 - d / 2;
      const sy2 = height / 2 + d / 2;

      const step = 3;

      for (let y = 0; y < height; y += step) {
        for (let x = 0; x < width; x += step) {
          const dx1 = x - sx;
          const dy1 = y - sy1;
          const dx2 = x - sx;
          const dy2 = y - sy2;

          let r1 = Math.sqrt(dx1 * dx1 + dy1 * dy1);
          let r2 = Math.sqrt(dx2 * dx2 + dy2 * dy2);

          if (r1 < 3) r1 = 3;
          if (r2 < 3) r2 = 3;

          const u =
            (A / r1) * Math.sin(k * r1 - omega * time) +
            (A / r2) * Math.sin(k * r2 - omega * time);

          const mapped = clamp(Math.tanh(3.5 * u), -1, 1);
          const red = mapped > 0 ? Math.floor(255 * mapped) : 0;
          const blue = mapped < 0 ? Math.floor(255 * (-mapped)) : 0;
          const green = Math.floor(25 + 90 * (1 - Math.abs(mapped)));

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

      drawBarrier(sx, sy1, sy2);

      ctx.fillStyle = "white";
      ctx.beginPath();
      ctx.arc(sx, sy1, 5, 0, 2 * Math.PI);
      ctx.fill();

      ctx.beginPath();
      ctx.arc(sx, sy2, 5, 0, 2 * Math.PI);
      ctx.fill();
    }

    function animate() {
      time += 0.06;
      draw();
      requestAnimationFrame(animate);
    }

    [dSlider, lambdaSlider, omegaSlider, ampSlider].forEach(el => {
      el.addEventListener("input", updateLabels);
    });

    updateLabels();
    animate();
  </script>
</body>
</html>
