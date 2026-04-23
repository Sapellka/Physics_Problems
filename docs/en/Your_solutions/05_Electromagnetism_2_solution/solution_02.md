# Task 02 – Electric Potential at the Center of a Square

## Problem Statement

Point charges

$$
+1 \text{ C}, \quad -2 \text{ C}, \quad +3 \text{ C}, \quad -4 \text{ C}
$$

are placed at the corners of a square of side length

$$
1.0 \text{ m}
$$

Determine the electric potential at the center of the square.

## Theory

Electric potential is a scalar quantity. For a system of point charges,

$$
V = k \sum_i \frac{q_i}{r_i}
$$

At the center of a square, all four corner charges are at the same distance from the center, so the potentials add algebraically.

## Step-by-Step Solution

### 1. Distance from the center to any corner

For a square of side length

$$
a = 1.0 \text{ m}
$$

the distance from the center to a corner is half the diagonal:

$$
r = \frac{a\sqrt{2}}{2} = \frac{1}{\sqrt{2}} \text{ m}
$$

### 2. Sum of the charges

The total charge contribution is

$$
q_{\text{sum}} = 1 - 2 + 3 - 4 = -2 \text{ C}
$$

### 3. Potential at the center

Thus,

$$
V = k \frac{q_{\text{sum}}}{r}
$$

Substitute:

$$
V = k \frac{-2}{1/\sqrt{2}}
$$

$$
V = -2\sqrt{2}\,k
$$

Using

$$
k \approx 8.99 \times 10^9 \text{ N m}^2 \text{/C}^2
$$

gives

$$
V \approx -2.54 \times 10^{10} \text{ V}
$$

## Final Result

The electric potential at the center is

$$
V = -2\sqrt{2}\,k \approx -2.54 \times 10^{10} \text{ V}
$$

## Interpretation

Potential is a scalar, so only the algebraic sum of the charges matters here. Since the total effective contribution is negative, the potential at the center is negative.
