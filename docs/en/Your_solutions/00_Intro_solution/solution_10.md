# Task 10 – Infinite Series Motion

## Problem Statement

An ant begins at the origin and moves according to the sequence

- 1 m east
- 1/2 m north
- 1/3 m west
- 1/4 m south
- 1/5 m east
- ...

Determine the final position.

## Theory

The motion separates into horizontal and vertical components.

Horizontal motion forms an alternating series

$$
x = 1 - \frac{1}{3} + \frac{1}{5} - \frac{1}{7} + ...
$$

Vertical motion forms

$$
y = \frac{1}{2} - \frac{1}{4} + \frac{1}{6} - \frac{1}{8} + ...
$$

These are known alternating series.

The first series equals

$$
\frac{\pi}{4}
$$

The second equals

$$
\frac{1}{2}\ln 2
$$

## Step-by-Step Solution

### Horizontal Position

$$
x = \frac{\pi}{4}
$$

Approximate value

$$
x \approx 0.785
$$

### Vertical Position

$$
y = \frac{1}{2}\ln 2
$$

Approximate value

$$
y \approx 0.346
$$

## Final Result

Final position of the ant

$$
(x,y) =
\left(
\frac{\pi}{4},
\frac{1}{2}\ln 2
\right)
$$

Approximate numerical position

$$
(x,y) \approx (0.785,0.346)
$$

## Interpretation

Even though the ant moves indefinitely, the alternating series converges, producing a finite final displacement from the origin.