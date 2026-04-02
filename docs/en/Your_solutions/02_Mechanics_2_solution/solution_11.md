# Task 11 – Dynamics with a Time-Dependent Force

## Problem Statement

A particle of mass

$$
m = 3 \text{ kg}
$$

moves under the force

$$
\vec{F}(t) = \begin{pmatrix} 15t \\ 3t - 12 \\ -6t^2 \end{pmatrix} \text{ N}
$$

with initial conditions

$$
\vec{r}(0) = \begin{pmatrix} 5 \\ 2 \\ -3 \end{pmatrix} \text{ m}
$$

and

$$
\vec{v}(0) = \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix} \text{ m/s}
$$

Determine the position and velocity as functions of time.

## Theory

Newton's second law gives

$$
\vec{F}(t) = m\vec{a}(t)
$$

so the acceleration is

$$
\vec{a}(t) = \frac{\vec{F}(t)}{m}
$$

Velocity is found by integrating acceleration, and position is found by integrating velocity. The constants of integration are determined from the initial conditions.

## Step-by-Step Solution

### 1. Acceleration

Divide the force by the mass $m=3$:

$$
\vec{a}(t) = \frac{1}{3} \begin{pmatrix} 15t \\ 3t - 12 \\ -6t^2 \end{pmatrix}
$$

Thus,

$$
\vec{a}(t) = \begin{pmatrix} 5t \\ t - 4 \\ -2t^2 \end{pmatrix}
$$

### 2. Velocity

Integrate each component.

For the $x$-component:

$$
v_x(t) = \int 5t\,dt = \frac{5}{2} t^2 + C_x
$$

Since

$$
v_x(0) = 2
$$

it follows that

$$
C_x = 2
$$

So,

$$
v_x(t) = \frac{5}{2} t^2 + 2
$$

For the $y$-component:

$$
v_y(t) = \int (t - 4)\,dt = \frac{1}{2} t^2 - 4t + C_y
$$

Using

$$
v_y(0) = 0
$$

gives

$$
C_y = 0
$$

Hence,

$$
v_y(t) = \frac{1}{2} t^2 - 4t
$$

For the $z$-component:

$$
v_z(t) = \int (-2t^2)\,dt = -\frac{2}{3} t^3 + C_z
$$

Using

$$
v_z(0) = 1
$$

gives

$$
C_z = 1
$$

Thus,

$$
v_z(t) = -\frac{2}{3} t^3 + 1
$$

Therefore,

$$
\vec{v}(t) = \begin{pmatrix}
\frac{5}{2} t^2 + 2 \\
\frac{1}{2} t^2 - 4t \\
-\frac{2}{3} t^3 + 1
\end{pmatrix}
$$

### 3. Position

Integrate the velocity components.

For the $x$-component:

$$
x(t) = \int \left( \frac{5}{2} t^2 + 2 \right) dt = \frac{5}{6} t^3 + 2t + C_1
$$

Using

$$
x(0) = 5
$$

gives

$$
C_1 = 5
$$

Hence,

$$
x(t) = \frac{5}{6} t^3 + 2t + 5
$$

For the $y$-component:

$$
y(t) = \int \left( \frac{1}{2} t^2 - 4t \right) dt = \frac{1}{6} t^3 - 2t^2 + C_2
$$

Using

$$
y(0) = 2
$$

gives

$$
C_2 = 2
$$

Thus,

$$
y(t) = \frac{1}{6} t^3 - 2t^2 + 2
$$

For the $z$-component:

$$
z(t) = \int \left( -\frac{2}{3} t^3 + 1 \right) dt = -\frac{1}{6} t^4 + t + C_3
$$

Using

$$
z(0) = -3
$$

gives

$$
C_3 = -3
$$

Thus,

$$
z(t) = -\frac{1}{6} t^4 + t - 3
$$

Therefore,

$$
\vec{r}(t) = \begin{pmatrix}
\frac{5}{6} t^3 + 2t + 5 \\
\frac{1}{6} t^3 - 2t^2 + 2 \\
-\frac{1}{6} t^4 + t - 3
\end{pmatrix}
$$

## Final Result

The velocity is

$$
\vec{v}(t) = \begin{pmatrix}
\frac{5}{2} t^2 + 2 \\
\frac{1}{2} t^2 - 4t \\
-\frac{2}{3} t^3 + 1
\end{pmatrix}
$$

The position is

$$
\vec{r}(t) = \begin{pmatrix}
\frac{5}{6} t^3 + 2t + 5 \\
\frac{1}{6} t^3 - 2t^2 + 2 \\
-\frac{1}{6} t^4 + t - 3
\end{pmatrix}
$$

## Interpretation

The time-dependent force produces a time-dependent acceleration, so neither the velocity nor the position has a simple linear dependence on time. Each coordinate evolves independently according to the corresponding force component.
