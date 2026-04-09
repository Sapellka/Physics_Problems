# Task 08 – Checking the Wave Equation

## Problem Statement

Determine which of the following functions can describe a traveling wave by checking whether they satisfy

$$
\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2}\frac{\partial^2 y}{\partial t^2}
$$

Functions:

a)

$$
y(x,t) = A \cos(kx^2 - \omega t)
$$

b)

$$
y(x,t) = A(x - vt)^2
$$

c)

$$
y(x,t) = A \log(x + vt)
$$

## Theory

A standard traveling wave has the form

$$
y(x,t) = f(x - vt)
$$

or

$$
y(x,t) = f(x + vt)
$$

Any sufficiently smooth function of these combinations satisfies the one-dimensional wave equation.

## Step-by-Step Solution

### a) Function $y(x,t) = A \cos(kx^2 - \omega t)$

Let

$$
\phi = kx^2 - \omega t
$$

Then

$$
\frac{\partial y}{\partial x} = -A \sin(\phi)\cdot 2kx = -2Akx \sin(\phi)
$$

Differentiate again:

$$
\frac{\partial^2 y}{\partial x^2} = -2Ak \sin(\phi) - 4Ak^2x^2 \cos(\phi)
$$

Now differentiate with respect to time:

$$
\frac{\partial y}{\partial t} = -A \sin(\phi)(-\omega) = A\omega \sin(\phi)
$$

$$
\frac{\partial^2 y}{\partial t^2} = -A\omega^2 \cos(\phi)
$$

The $x$-derivative contains both $\sin(\phi)$ and $x^2 \cos(\phi)$ terms, so it cannot be proportional to $\frac{\partial^2 y}{\partial t^2}$ for all $x$ and $t$.

Therefore, this function does not satisfy the wave equation.

### b) Function $y(x,t) = A(x - vt)^2$

Differentiate with respect to $x$:

$$
\frac{\partial y}{\partial x} = 2A(x - vt)
$$

$$
\frac{\partial^2 y}{\partial x^2} = 2A
$$

Differentiate with respect to $t$:

$$
\frac{\partial y}{\partial t} = 2A(x - vt)(-v) = -2Av(x - vt)
$$

$$
\frac{\partial^2 y}{\partial t^2} = 2Av^2
$$

Then

$$
\frac{1}{v^2}\frac{\partial^2 y}{\partial t^2} = \frac{1}{v^2}(2Av^2) = 2A
$$

Hence,

$$
\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2}\frac{\partial^2 y}{\partial t^2}
$$

So this function satisfies the wave equation.

### c) Function $y(x,t) = A \log(x + vt)$

Differentiate with respect to $x$:

$$
\frac{\partial y}{\partial x} = \frac{A}{x + vt}
$$

$$
\frac{\partial^2 y}{\partial x^2} = -\frac{A}{(x + vt)^2}
$$

Differentiate with respect to $t$:

$$
\frac{\partial y}{\partial t} = \frac{Av}{x + vt}
$$

$$
\frac{\partial^2 y}{\partial t^2} = -\frac{Av^2}{(x + vt)^2}
$$

Then

$$
\frac{1}{v^2}\frac{\partial^2 y}{\partial t^2} = -\frac{A}{(x + vt)^2}
$$

Thus,

$$
\frac{\partial^2 y}{\partial x^2} = \frac{1}{v^2}\frac{\partial^2 y}{\partial t^2}
$$

So this function also satisfies the wave equation.

## Final Result

The functions that can describe traveling waves are:

- **b)**

$$
y(x,t) = A(x - vt)^2
$$

- **c)**

$$
y(x,t) = A \log(x + vt)
$$

The function

- **a)**

$$
y(x,t) = A \cos(kx^2 - \omega t)
$$

does not satisfy the wave equation.

## Interpretation

Any function of $x-vt$ or $x+vt$ is a traveling-wave solution. The first function fails because its argument is not linear in $x$, so its derivatives do not match the required structure of the wave equation.
