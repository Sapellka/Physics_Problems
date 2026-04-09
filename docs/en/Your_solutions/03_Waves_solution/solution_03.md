# Task 03 – Superposition Principle and Standing Waves

## Problem Statement

Two waves are given by

$$
y_1(x,t) = A \sin(kx - \omega t)
$$

and

$$
y_2(x,t) = A \sin(kx + \omega t)
$$

Determine the equation of the resulting standing wave and identify the node positions.

## Theory

When two waves overlap, the displacement is the sum of the individual displacements.

A useful trigonometric identity is

$$
\sin \alpha + \sin \beta = 2 \sin \left( \frac{\alpha + \beta}{2} \right) \cos \left( \frac{\alpha - \beta}{2} \right)
$$

A standing wave is formed when two waves with the same amplitude and frequency travel in opposite directions.

## Step-by-Step Solution

The total displacement is

$$
y(x,t) = y_1(x,t) + y_2(x,t)
$$

Substitute the given expressions:

$$
y(x,t) = A \sin(kx - \omega t) + A \sin(kx + \omega t)
$$

Factor out $A$:

$$
y(x,t) = A \left[ \sin(kx - \omega t) + \sin(kx + \omega t) \right]
$$

Apply the identity with

$$
\alpha = kx - \omega t, \qquad \beta = kx + \omega t
$$

Then

$$
\frac{\alpha + \beta}{2} = kx
$$

and

$$
\frac{\alpha - \beta}{2} = -\omega t
$$

Since

$$
\cos(-\omega t) = \cos(\omega t)
$$

the result becomes

$$
y(x,t) = 2A \sin(kx)\cos(\omega t)
$$

This is the standing-wave equation.

### Nodes

Nodes occur where the displacement is always zero, so

$$
\sin(kx) = 0
$$

Hence,

$$
kx = n\pi
$$

where $n$ is an integer. Therefore,

$$
x_n = \frac{n\pi}{k}
$$

Using

$$
k = \frac{2\pi}{\lambda}
$$

gives

$$
x_n = \frac{n\lambda}{2}
$$

## Final Result

The standing wave is

$$
y(x,t) = 2A \sin(kx)\cos(\omega t)
$$

The nodes are located at

$$
x_n = \frac{n\pi}{k} = \frac{n\lambda}{2}, \qquad n = 0, \pm 1, \pm 2, \dots
$$

## Interpretation

The factor $\sin(kx)$ determines where the oscillation amplitude is zero or maximum. The nodes remain fixed in space, while each point between nodes oscillates in time with factor $\cos(\omega t)$.
