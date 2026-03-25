# Task 03 – Path Intersection

## Problem Statement

Determine whether two moving points intersect.

## Step-by-Step Solution

Set coordinates equal:

$$
2 + t = 2t - 1
$$

$$
8 - 3t = 2t + 2
$$

Solve first:

$$
t = 3
$$

Second:

$$
8 - 3t = 2t + 2
$$

$$
6 = 5t
$$

$$
t = \frac{6}{5}
$$

Times differ ⇒ no collision.

---

### Minimum Distance

Distance:

$$
d(t) = \sqrt{(3 - t)^2 + (6 - 5t)^2}
$$

Minimize squared distance:

$$
f(t) = (3 - t)^2 + (6 - 5t)^2
$$

Differentiate:

$$
f'(t) = 2(t - 3) + 10(5t - 6)
$$

$$
= 52t - 66
$$

$$
t = \frac{33}{26}
$$

## Final Result

- No collision
- Minimum distance occurs at $t = \frac{33}{26}$

## Interpretation

Paths cross geometrically but not at the same time.
