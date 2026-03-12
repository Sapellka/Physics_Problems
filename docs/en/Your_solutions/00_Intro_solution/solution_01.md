# Task 01 – Vector Algebra

## Problem Statement

Two vectors in three-dimensional space are given

$$
\vec{a} = [2,1,-3]
$$

$$
\vec{b} = [4,-2,1]
$$

Determine:

- the magnitude of each vector
- the dot product
- the cross product
- the angle between the vectors

## Theory

For a vector

$$
\vec{v} = [v_x, v_y, v_z]
$$

its magnitude is

$$
|\vec{v}| = \sqrt{v_x^2 + v_y^2 + v_z^2}
$$

The dot product of two vectors is

$$
\vec{a} \cdot \vec{b} = a_x b_x + a_y b_y + a_z b_z
$$

The cross product is

$$
\vec{a} \times \vec{b} =
\begin{pmatrix}
a_y b_z - a_z b_y \\
a_z b_x - a_x b_z \\
a_x b_y - a_y b_x
\end{pmatrix}
$$

The angle between two vectors follows from

$$
\vec{a}\cdot\vec{b} = |\vec{a}| |\vec{b}| \cos\theta
$$

## Step-by-Step Solution

### Magnitudes

For vector $\vec a$

$$
|\vec a| = \sqrt{2^2 + 1^2 + (-3)^2}
$$

$$
|\vec a| = \sqrt{4 + 1 + 9}
$$

$$
|\vec a| = \sqrt{14}
$$

For vector $\vec b$

$$
|\vec b| = \sqrt{4^2 + (-2)^2 + 1^2}
$$

$$
|\vec b| = \sqrt{16 + 4 + 1}
$$

$$
|\vec b| = \sqrt{21}
$$

### Dot Product

$$
\vec a \cdot \vec b =
2(4) + 1(-2) + (-3)(1)
$$

$$
\vec a \cdot \vec b =
8 - 2 - 3
$$

$$
\vec a \cdot \vec b = 3
$$

### Cross Product

$$
\vec a \times \vec b =
\begin{pmatrix}
1\cdot1 - (-3)(-2) \\
(-3)(4) - 2(1) \\
2(-2) - 1(4)
\end{pmatrix}
$$

$$
\vec a \times \vec b =
\begin{pmatrix}
1 - 6 \\
-12 - 2 \\
-4 - 4
\end{pmatrix}
$$

$$
\vec a \times \vec b =
\begin{pmatrix}
-5 \\
-14 \\
-8
\end{pmatrix}
$$

### Angle Between the Vectors

$$
\cos\theta =
\frac{\vec a \cdot \vec b}{|\vec a||\vec b|}
$$

$$
\cos\theta =
\frac{3}{\sqrt{14}\sqrt{21}}
$$

$$
\cos\theta =
\frac{3}{\sqrt{294}}
$$

$$
\theta =
\cos^{-1}\left(\frac{3}{\sqrt{294}}\right)
$$

$$
\theta \approx 80^\circ
$$

## Final Result

Vector magnitudes:

$$
|\vec a| = \sqrt{14}, \quad |\vec b| = \sqrt{21}
$$

Dot product:

$$
\vec a \cdot \vec b = 3
$$

Cross product:

$$
\vec a \times \vec b =
\begin{pmatrix}
-5 \\
-14 \\
-8
\end{pmatrix}
$$

Angle between vectors:

$$
\theta \approx 80^\circ
$$

## Interpretation

The small dot product indicates that the vectors are nearly orthogonal.  
The cross product produces a vector perpendicular to both original vectors, which is fundamental in mechanics and electromagnetism when determining rotational directions and torques.