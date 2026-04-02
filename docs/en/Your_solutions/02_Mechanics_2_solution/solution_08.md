# Task 08 – Work of a Variable Force

## Problem Statement

A one-dimensional force is given by

$$
F(x) = -kx
$$

Required:

- write down the equation of motion and solve it,
- calculate the work done during the displacement from $0$ to $x_0$,
- interpret the result as potential energy,
- verify the relation $F = -\frac{dU}{dx}$,
- describe the graphs of $F(x)$ and $U(x)$.

## Theory

The force

$$
F(x) = -kx
$$

is the restoring force of a spring. It always points toward the equilibrium position $x=0$.

Newton's second law gives

$$
m\ddot{x} = -kx
$$

which is the differential equation of simple harmonic motion.

For conservative forces, the work and potential energy are related by

$$
W_{A \to B} = -\Delta U
$$

## Step-by-Step Solution

### 1. Equation of motion and its solution

Use Newton's second law:

$$
m\ddot{x} = -kx
$$

or

$$
\ddot{x} + \frac{k}{m}x = 0
$$

Define

$$
\omega = \sqrt{\frac{k}{m}}
$$

Then the equation becomes

$$
\ddot{x} + \omega^2 x = 0
$$

Its general solution is

$$
x(t) = A \cos(\omega t) + B \sin(\omega t)
$$

where $A$ and $B$ are determined by the initial conditions.

### 2. Work done from $0$ to $x_0$

The work is

$$
W_{0 \to x_0} = \int_0^{x_0} F(x)\,dx
$$

Substitute

$$
F(x) = -kx
$$

Then

$$
W_{0 \to x_0} = \int_0^{x_0} (-kx)\,dx
$$

$$
W_{0 \to x_0} = -k \int_0^{x_0} x\,dx
$$

$$
W_{0 \to x_0} = -k \left[ \frac{x^2}{2} \right]_0^{x_0}
$$

$$
W_{0 \to x_0} = -\frac{1}{2} kx_0^2
$$

### 3. Interpretation as potential energy

For a conservative force,

$$
W_{0 \to x_0} = -\bigl(U(x_0) - U(0)\bigr)
$$

Choose

$$
U(0) = 0
$$

Then

$$
U(x_0) = \frac{1}{2} kx_0^2
$$

Thus, the potential energy function is

$$
U(x) = \frac{1}{2} kx^2
$$

### 4. Verify the relation $F = -\frac{dU}{dx}$

Differentiate the potential:

$$
\frac{dU}{dx} = \frac{d}{dx} \left( \frac{1}{2} kx^2 \right)
$$

$$
\frac{dU}{dx} = kx
$$

Therefore,

$$
-\frac{dU}{dx} = -kx = F(x)
$$

which confirms the required relation.

## Final Result

The equation of motion is

$$
m\ddot{x} = -kx
$$

Its general solution is

$$
x(t) = A \cos \left( \sqrt{\frac{k}{m}}\, t \right) + B \sin \left( \sqrt{\frac{k}{m}}\, t \right)
$$

The work done from $0$ to $x_0$ is

$$
W_{0 \to x_0} = -\frac{1}{2} kx_0^2
$$

The potential energy is

$$
U(x) = \frac{1}{2} kx^2
$$

and the identity

$$
F = -\frac{dU}{dx}
$$

is satisfied.

## Interpretation

The force is linear and restoring, so the motion is oscillatory. The work done by the force from $0$ to $x_0$ is negative because the force opposes the displacement. The potential energy increases quadratically with distance from equilibrium.

The graph of $F(x)$ is a straight line through the origin with slope $-k$.

The graph of $U(x)$ is an upward-opening parabola with minimum at

$$
x = 0
$$
