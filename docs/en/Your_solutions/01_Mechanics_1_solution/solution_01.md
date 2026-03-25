# Task 01 – Projectile Motion

## Problem Statement

A projectile is fired from the ground with an initial velocity of $100 \ \text{m/s}$ at an angle of $37^\circ$ above the horizontal. Neglect air resistance.

Tasks:
- Derive equations of motion
- Time of flight
- Maximum height
- Range

## Theory

Projectile motion under constant gravitational acceleration is described by:

- Horizontal acceleration: $a_x = 0$
- Vertical acceleration: $a_y = -g$

Initial velocity components:

$$
v_{0x} = v_0 \cos\theta, \qquad v_{0y} = v_0 \sin\theta
$$

## Step-by-Step Solution

### Differential Equations

From Newton’s second law:

$$
\frac{d^2 x}{dt^2} = 0
$$

$$
\frac{d^2 y}{dt^2} = -g
$$

Integrating:

$$
\frac{dx}{dt} = v_{0x}
$$

$$
\frac{dy}{dt} = v_{0y} - gt
$$

Position:

$$
x(t) = v_{0x} t
$$

$$
y(t) = v_{0y} t - \frac{1}{2}gt^2
$$

---

### Time of Flight

Set $y(t)=0$:

$$
v_{0y} t - \frac{1}{2}gt^2 = 0
$$

$$
t(v_{0y} - \frac{1}{2}gt) = 0
$$

$$
T = \frac{2v_{0y}}{g}
$$

---

### Maximum Height

At peak: $v_y = 0$

$$
0 = v_{0y} - gt
$$

$$
t = \frac{v_{0y}}{g}
$$

Height:

$$
H = \frac{v_{0y}^2}{2g}
$$

---

### Range

$$
R = v_{0x} T
$$

$$
R = \frac{v_0^2 \sin(2\theta)}{g}
$$

---

### Numerical Values

Using $\sin 37^\circ \approx 0.6$, $\cos 37^\circ \approx 0.8$

$$
v_{0x} = 80 \ \text{m/s}, \quad v_{0y} = 60 \ \text{m/s}
$$

$$
T = \frac{2 \cdot 60}{9.81} \approx 12.2 \ \text{s}
$$

$$
H \approx \frac{60^2}{2 \cdot 9.81} \approx 183.7 \ \text{m}
$$

$$
R \approx 80 \cdot 12.2 \approx 976 \ \text{m}
$$

## Final Result

- Time: $T \approx 12.2$ s  
- Height: $H \approx 184$ m  
- Range: $R \approx 976$ m  

## Interpretation

The motion is symmetric. Horizontal velocity remains constant, while vertical motion is uniformly accelerated.
