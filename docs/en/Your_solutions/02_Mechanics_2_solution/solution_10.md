# Task 10 – Force Field and Power

## Problem Statement

A particle of mass

$$
m = 0.5 \text{ kg}
$$

moves according to

$$
x = 5t^2 - t, \qquad y = 2t^3, \qquad z = -3t + 2
$$

Determine the time dependence of:

- velocity,
- momentum,
- acceleration,
- force,
- power delivered by the field.

## Theory

For a position vector

$$
\vec{r}(t) = \begin{pmatrix} x(t) \\ y(t) \\ z(t) \end{pmatrix}
$$

the kinematic quantities are obtained by differentiation:

$$
\vec{v}(t) = \frac{d\vec{r}}{dt}
$$

$$
\vec{a}(t) = \frac{d\vec{v}}{dt}
$$

Momentum is

$$
\vec{p}(t) = m\vec{v}(t)
$$

Force is

$$
\vec{F}(t) = m\vec{a}(t)
$$

Power is

$$
P(t) = \vec{F}(t) \cdot \vec{v}(t)
$$

## Step-by-Step Solution

### 1. Position vector

Write the motion as

$$
\vec{r}(t) = \begin{pmatrix} 5t^2 - t \\ 2t^3 \\ -3t + 2 \end{pmatrix}
$$

### 2. Velocity

Differentiate each component:

$$
\vec{v}(t) = \begin{pmatrix} 10t - 1 \\ 6t^2 \\ -3 \end{pmatrix}
$$

### 3. Momentum

Multiply by the mass $m = 0.5$ kg:

$$
\vec{p}(t) = 0.5 \begin{pmatrix} 10t - 1 \\ 6t^2 \\ -3 \end{pmatrix}
$$

Thus,

$$
\vec{p}(t) = \begin{pmatrix} 5t - 0.5 \\ 3t^2 \\ -1.5 \end{pmatrix}
$$

### 4. Acceleration

Differentiate the velocity:

$$
\vec{a}(t) = \begin{pmatrix} 10 \\ 12t \\ 0 \end{pmatrix}
$$

### 5. Force

Use Newton's second law:

$$
\vec{F}(t) = m\vec{a}(t)
$$

Hence,

$$
\vec{F}(t) = 0.5 \begin{pmatrix} 10 \\ 12t \\ 0 \end{pmatrix}
= \begin{pmatrix} 5 \\ 6t \\ 0 \end{pmatrix}
$$

### 6. Power

Compute the dot product:

$$
P(t) = \vec{F}(t) \cdot \vec{v}(t)
$$

$$
P(t) = \begin{pmatrix} 5 \\ 6t \\ 0 \end{pmatrix} \cdot \begin{pmatrix} 10t - 1 \\ 6t^2 \\ -3 \end{pmatrix}
$$

$$
P(t) = 5(10t - 1) + 6t(6t^2) + 0
$$

$$
P(t) = 50t - 5 + 36t^3
$$

So,

$$
P(t) = 36t^3 + 50t - 5
$$

## Final Result

The velocity is

$$
\vec{v}(t) = \begin{pmatrix} 10t - 1 \\ 6t^2 \\ -3 \end{pmatrix}
$$

The momentum is

$$
\vec{p}(t) = \begin{pmatrix} 5t - 0.5 \\ 3t^2 \\ -1.5 \end{pmatrix}
$$

The acceleration is

$$
\vec{a}(t) = \begin{pmatrix} 10 \\ 12t \\ 0 \end{pmatrix}
$$

The force is

$$
\vec{F}(t) = \begin{pmatrix} 5 \\ 6t \\ 0 \end{pmatrix}
$$

The power is

$$
P(t) = 36t^3 + 50t - 5
$$

## Interpretation

The motion is non-uniform because both velocity and acceleration depend on time. The force varies linearly in the $y$-direction but is constant in the $x$-direction. The power is time-dependent because both force and velocity vary during the motion.
