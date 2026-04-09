# Task 09 – Damped Oscillator

## Problem Statement

Consider the damped harmonic oscillator

$$
m \frac{d^2 x}{dt^2} + b \frac{dx}{dt} + kx = 0
$$

Required:

1. write down the general solution,
2. classify the underdamped, critically damped, and overdamped cases,
3. solve the equation numerically with RK4,
4. investigate the effect of parameter $b$,
5. generate the graph of $x(t)$,
6. generate the phase portrait.

## Theory

The characteristic equation is

$$
mr^2 + br + k = 0
$$

Its roots are

$$
r_{1,2} = \frac{-b \pm \sqrt{b^2 - 4mk}}{2m}
$$

The behavior depends on the discriminant

$$
\Delta = b^2 - 4mk
$$

It is convenient to define

$$
\omega_0 = \sqrt{\frac{k}{m}}
$$

and

$$
\beta = \frac{b}{2m}
$$

## Step-by-Step Solution

### 1. General solution

The differential equation is

$$
m\ddot{x} + b\dot{x} + kx = 0
$$

or equivalently

$$
\ddot{x} + \frac{b}{m}\dot{x} + \frac{k}{m}x = 0
$$

The characteristic equation is

$$
r^2 + \frac{b}{m}r + \frac{k}{m} = 0
$$

Its roots are

$$
r_{1,2} = \frac{-b \pm \sqrt{b^2 - 4mk}}{2m}
$$

### 2. Classification of cases

#### Underdamped case

If

$$
b^2 < 4mk
$$

the roots are complex conjugates, and the solution is

$$
x(t) = e^{-\beta t}\left( C_1 \cos(\omega_d t) + C_2 \sin(\omega_d t) \right)
$$

where

$$
\omega_d = \sqrt{\omega_0^2 - \beta^2}
$$

This case shows oscillation with exponentially decreasing amplitude.

#### Critically damped case

If

$$
b^2 = 4mk
$$

the solution is

$$
x(t) = (C_1 + C_2 t)e^{-\beta t}
$$

This is the threshold case between oscillatory and non-oscillatory motion.

#### Overdamped case

If

$$
b^2 > 4mk
$$

the roots are distinct and real:

$$
r_{1,2} = \frac{-b \pm \sqrt{b^2 - 4mk}}{2m}
$$

The solution is

$$
x(t) = C_1 e^{r_1 t} + C_2 e^{r_2 t}
$$

This case returns to equilibrium without oscillation.

### 3. Numerical form for RK4

Introduce

$$
v = \dot{x}
$$

Then the second-order equation becomes the first-order system

$$
\dot{x} = v
$$

$$
\dot{v} = -\frac{b}{m}v - \frac{k}{m}x
$$

This system is suitable for numerical integration with the classical fourth-order Runge-Kutta method.

### 4. Effect of parameter $b$

The parameter $b$ controls the strength of dissipation.

- Small $b$ gives oscillatory motion with slowly decaying amplitude.
- The critical value

$$
b_c = 2\sqrt{mk}
$$

separates oscillatory motion from non-oscillatory motion.
- Large $b$ suppresses oscillations and causes a slow return to equilibrium.

### 5. Graph of $x(t)$

The graph of $x(t)$ shows:

- decaying oscillations in the underdamped regime,
- fastest non-oscillatory decay at critical damping,
- slower non-oscillatory decay in the overdamped regime.

### 6. Phase portrait

The phase portrait plots

$$
v(t)
$$

against

$$
x(t)
$$

In the underdamped case it forms an inward spiral. In the critically damped and overdamped cases, the trajectory approaches the origin without spiraling.

## Final Result

The solution class depends on the sign of

$$
b^2 - 4mk
$$

Underdamped:

$$
x(t) = e^{-\beta t}\left( C_1 \cos(\omega_d t) + C_2 \sin(\omega_d t) \right)
$$

Critically damped:

$$
x(t) = (C_1 + C_2 t)e^{-\beta t}
$$

Overdamped:

$$
x(t) = C_1 e^{r_1 t} + C_2 e^{r_2 t}
$$

For numerical simulation, use

$$
\dot{x} = v
$$

and

$$
\dot{v} = -\frac{b}{m}v - \frac{k}{m}x
$$

## Interpretation

The damping coefficient controls how mechanical energy is removed from the system. The most visually important transition occurs at the critical value $b_c$, where oscillations disappear.

## Interactive HTML Source

Copy the HTML code from `solution_09_animation.html` into a separate file to run the animation locally.





























<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Damped Oscillator – RK4</title>
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
      padding: 20px;
    }
    h1 {
      margin-bottom: 8px;
    }
    .controls {
      display: grid;
      grid-template-columns: repeat(2, minmax(260px, 1fr));
      gap: 14px;
      margin-bottom: 18px;
    }
    .card {
      background: #111827;
      border: 1px solid #334155;
      border-radius: 12px;
      padding: 14px;
    }
    label {
      display: block;
      margin-bottom: 6px;
      font-weight: bold;
    }
    input[type="range"] {
      width: 100%;
    }
    .canvases {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 18px;
    }
    canvas {
      background: #020617;
      border: 1px solid #334155;
      border-radius: 12px;
      width: 100%;
      height: 420px;
    }
    .row {
      display: flex;
      justify-content: space-between;
      gap: 12px;
      font-size: 14px;
      margin-top: 6px;
    }
    .tag {
      display: inline-block;
      padding: 6px 10px;
      border-radius: 999px;
      font-weight: bold;
      background: #1e293b;
    }
    .footer {
      margin-top: 16px;
      font-size: 14px;
      color: #cbd5e1;
    }
    button {
      background: #2563eb;
      color: white;
      border: none;
      border-radius: 8px;
      padding: 10px 14px;
      cursor: pointer;
      margin-top: 10px;
    }
    button:hover {
      background: #1d4ed8;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Damped Harmonic Oscillator</h1>
    <p>
      Numerical solution with RK4 for
      <strong>m x'' + b x' + k x = 0</strong>
    </p>

    <div class="controls">
      <div class="card">
        <label for="bSlider">Damping coefficient b</label>
        <input id="bSlider" type="range" min="0" max="4" step="0.01" value="0.4">
        <div class="row">
          <span>b = <span id="bValue">0.40</span></span>
          <span>critical b<sub>c</sub> = <span id="bcValue">2.00</span></span>
        </div>
        <div class="row">
          <span class="tag" id="regimeTag">Underdamped</span>
        </div>
      </div>

      <div class="card">
        <label>Model parameters</label>
        <div class="row"><span>m = <span id="mValue">1.00</span></span><span>k = <span id="kValue">1.00</span></span></div>
        <div class="row"><span>x(0) = <span id="x0Value">1.00</span></span><span>v(0) = <span id="v0Value">0.00</span></span></div>
        <div class="row"><span>time span = 20 s</span><span>dt = 0.01 s</span></div>
        <button id="resetBtn">Reset view</button>
      </div>
    </div>

    <div class="canvases">
      <canvas id="xtCanvas" width="560" height="420"></canvas>
      <canvas id="phaseCanvas" width="560" height="420"></canvas>
    </div>

    <div class="footer">
      Left: displacement $x(t)$. Right: phase portrait $(x,v)$.
    </div>
  </div>

  <script>
    const xtCanvas = document.getElementById("xtCanvas");
    const phaseCanvas = document.getElementById("phaseCanvas");
    const xtCtx = xtCanvas.getContext("2d");
    const phaseCtx = phaseCanvas.getContext("2d");

    const bSlider = document.getElementById("bSlider");
    const bValue = document.getElementById("bValue");
    const bcValue = document.getElementById("bcValue");
    const regimeTag = document.getElementById("regimeTag");
    const resetBtn = document.getElementById("resetBtn");

    const m = 1.0;
    const k = 1.0;
    const x0 = 1.0;
    const v0 = 0.0;
    const dt = 0.01;
    const tMax = 20.0;

    document.getElementById("mValue").textContent = m.toFixed(2);
    document.getElementById("kValue").textContent = k.toFixed(2);
    document.getElementById("x0Value").textContent = x0.toFixed(2);
    document.getElementById("v0Value").textContent = v0.toFixed(2);

    const bc = 2 * Math.sqrt(m * k);
    bcValue.textContent = bc.toFixed(2);

    function derivatives(state, b) {
      const [x, v] = state;
      return [v, -(b / m) * v - (k / m) * x];
    }

    function rk4Step(state, dt, b) {
      const k1 = derivatives(state, b);
      const s2 = [state[0] + 0.5 * dt * k1[0], state[1] + 0.5 * dt * k1[1]];
      const k2 = derivatives(s2, b);
      const s3 = [state[0] + 0.5 * dt * k2[0], state[1] + 0.5 * dt * k2[1]];
      const k3 = derivatives(s3, b);
      const s4 = [state[0] + dt * k3[0], state[1] + dt * k3[1]];
      const k4 = derivatives(s4, b);

      return [
        state[0] + (dt / 6) * (k1[0] + 2 * k2[0] + 2 * k3[0] + k4[0]),
        state[1] + (dt / 6) * (k1[1] + 2 * k2[1] + 2 * k3[1] + k4[1])
      ];
    }

    function simulate(b) {
      let t = 0;
      let state = [x0, v0];
      const data = [];

      while (t <= tMax + 1e-9) {
        data.push({ t, x: state[0], v: state[1] });
        state = rk4Step(state, dt, b);
        t += dt;
      }
      return data;
    }

    function classify(b) {
      const eps = 1e-6;
      const disc = b * b - 4 * m * k;
      if (disc < -eps) return "Underdamped";
      if (Math.abs(disc) <= eps) return "Critically damped";
      return "Overdamped";
    }

    function drawAxes(ctx, w, h, xLabel, yLabel) {
      ctx.strokeStyle = "#334155";
      ctx.lineWidth = 1;
      ctx.strokeRect(0, 0, w, h);

      ctx.fillStyle = "#cbd5e1";
      ctx.font = "14px Arial";
      ctx.fillText(xLabel, w - 30, h - 10);
      ctx.save();
      ctx.translate(14, 24);
      ctx.rotate(-Math.PI / 2);
      ctx.fillText(yLabel, 0, 0);
      ctx.restore();
    }

    function drawXT(data) {
      const w = xtCanvas.width;
      const h = xtCanvas.height;
      xtCtx.clearRect(0, 0, w, h);
      drawAxes(xtCtx, w, h, "t", "x");

      const pad = 40;
      const xmin = 0;
      const xmax = tMax;
      let ymin = Infinity;
      let ymax = -Infinity;

      for (const p of data) {
        ymin = Math.min(ymin, p.x);
        ymax = Math.max(ymax, p.x);
      }

      const margin = 0.15 * Math.max(1, ymax - ymin);
      ymin -= margin;
      ymax += margin;

      function X(t) {
        return pad + (t - xmin) / (xmax - xmin) * (w - 2 * pad);
      }

      function Y(x) {
        return h - pad - (x - ymin) / (ymax - ymin) * (h - 2 * pad);
      }

      xtCtx.strokeStyle = "#475569";
      xtCtx.beginPath();
      xtCtx.moveTo(pad, Y(0));
      xtCtx.lineTo(w - pad, Y(0));
      xtCtx.stroke();

      xtCtx.strokeStyle = "#38bdf8";
      xtCtx.lineWidth = 2;
      xtCtx.beginPath();
      data.forEach((p, i) => {
        const x = X(p.t);
        const y = Y(p.x);
        if (i === 0) xtCtx.moveTo(x, y);
        else xtCtx.lineTo(x, y);
      });
      xtCtx.stroke();

      xtCtx.fillStyle = "#cbd5e1";
      xtCtx.fillText("x(t)", pad + 8, pad - 12);
    }

    function drawPhase(data) {
      const w = phaseCanvas.width;
      const h = phaseCanvas.height;
      phaseCtx.clearRect(0, 0, w, h);
      drawAxes(phaseCtx, w, h, "x", "v");

      const pad = 40;
      let xmin = Infinity, xmax = -Infinity, ymin = Infinity, ymax = -Infinity;

      for (const p of data) {
        xmin = Math.min(xmin, p.x);
        xmax = Math.max(xmax, p.x);
        ymin = Math.min(ymin, p.v);
        ymax = Math.max(ymax, p.v);
      }

      const xmargin = 0.15 * Math.max(1, xmax - xmin);
      const ymargin = 0.15 * Math.max(1, ymax - ymin);
      xmin -= xmargin; xmax += xmargin;
      ymin -= ymargin; ymax += ymargin;

      function X(x) {
        return pad + (x - xmin) / (xmax - xmin) * (w - 2 * pad);
      }

      function Y(v) {
        return h - pad - (v - ymin) / (ymax - ymin) * (h - 2 * pad);
      }

      phaseCtx.strokeStyle = "#475569";
      phaseCtx.beginPath();
      phaseCtx.moveTo(X(0), pad);
      phaseCtx.lineTo(X(0), h - pad);
      phaseCtx.moveTo(pad, Y(0));
      phaseCtx.lineTo(w - pad, Y(0));
      phaseCtx.stroke();

      phaseCtx.strokeStyle = "#f59e0b";
      phaseCtx.lineWidth = 2;
      phaseCtx.beginPath();
      data.forEach((p, i) => {
        const x = X(p.x);
        const y = Y(p.v);
        if (i === 0) phaseCtx.moveTo(x, y);
        else phaseCtx.lineTo(x, y);
      });
      phaseCtx.stroke();

      phaseCtx.fillStyle = "#cbd5e1";
      phaseCtx.fillText("Phase portrait", pad + 8, pad - 12);
    }

    function update() {
      const b = parseFloat(bSlider.value);
      bValue.textContent = b.toFixed(2);

      const regime = classify(b);
      regimeTag.textContent = regime;

      if (regime === "Underdamped") regimeTag.style.background = "#14532d";
      else if (regime === "Critically damped") regimeTag.style.background = "#78350f";
      else regimeTag.style.background = "#7f1d1d";

      const data = simulate(b);
      drawXT(data);
      drawPhase(data);
    }

    bSlider.addEventListener("input", update);
    resetBtn.addEventListener("click", update);

    update();
  </script>
</body>
</html>
