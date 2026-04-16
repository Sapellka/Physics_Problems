# Task 09 – Vector Lorentz Force on a Proton

## Problem Statement

A proton moves with velocity

$$
\vec{v} = (2\hat{i} - 4\hat{j} + \hat{k}) \text{ m/s}
$$

in a magnetic field

$$
\vec{B} = (\hat{i} + 2\hat{j} - \hat{k}) \text{ T}
$$

Determine the magnitude of the magnetic force acting on the proton.

## Theory

The magnetic force on a charged particle is

$$
\vec{F} = q \, \vec{v} \times \vec{B}
$$

Its magnitude is

$$
F = q |\vec{v} \times \vec{B}|
$$

For a proton,

$$
q = e \approx 1.60 \times 10^{-19} \text{ C}
$$

## Step-by-Step Solution

### 1. Compute the cross product

Write the vectors in component form:

$$
\vec{v} = \begin{pmatrix} 2 \\ -4 \\ 1 \end{pmatrix}
$$

$$
\vec{B} = \begin{pmatrix} 1 \\ 2 \\ -1 \end{pmatrix}
$$

Then

$$
\vec{v} \times \vec{B} = \begin{pmatrix}
(-4)(-1) - (1)(2) \\
(1)(1) - (2)(-1) \\
(2)(2) - (-4)(1)
\end{pmatrix}
$$

So,

$$
\vec{v} \times \vec{B} = \begin{pmatrix} 2 \\ 3 \\ 8 \end{pmatrix}
$$

### 2. Magnitude of the cross product

$$
|\vec{v} \times \vec{B}| = \sqrt{2^2 + 3^2 + 8^2}
$$

$$
|\vec{v} \times \vec{B}| = \sqrt{4 + 9 + 64} = \sqrt{77}
$$

### 3. Force magnitude

Multiply by the proton charge:

$$
F = e\sqrt{77}
$$

Using

$$
e \approx 1.60 \times 10^{-19} \text{ C}
$$

gives

$$
F \approx 1.40 \times 10^{-18} \text{ N}
$$

## Final Result

The magnitude of the magnetic force is

$$
F = e\sqrt{77} \approx 1.40 \times 10^{-18} \text{ N}
$$

## Interpretation

The force depends only on the part of the velocity perpendicular to the magnetic field. The cross product automatically extracts that perpendicular contribution.
