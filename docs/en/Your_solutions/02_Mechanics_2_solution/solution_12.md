# Task 12 – Work and Energy with a Constant Force

## Problem Statement

A body of mass

$$
m = 2 \text{ kg}
$$

is acted on by a constant force

$$
\vec{F} = \begin{pmatrix} 6 \\ 2 \end{pmatrix} \text{ N}
$$

The initial conditions are

$$
\vec{v}(0) = \begin{pmatrix} 1 \\ -1 \end{pmatrix} \text{ m/s}
$$

and

$$
\vec{r}(0) = \begin{pmatrix} 0 \\ 0 \end{pmatrix} \text{ m}
$$

Required:

- determine $\vec{a}(t)$,
- determine $\vec{v}(t)$,
- determine $\vec{r}(t)$,
- draw or describe the trajectory,
- calculate the work done by the force at $t=3$ s,
- verify the work-energy theorem.

## Theory

For a constant force, the acceleration is constant:

$$
\vec{a} = \frac{\vec{F}}{m}
$$

Then

$$
\vec{v}(t) = \vec{v}_0 + \vec{a}t
$$

and

$$
\vec{r}(t) = \vec{r}_0 + \vec{v}_0 t + \frac{1}{2} \vec{a} t^2
$$

The work-energy theorem states

$$
W = \Delta K
$$

where $K$ is kinetic energy.

## Step-by-Step Solution

### 1. Acceleration

Use Newton's second law:

$$
\vec{a} = \frac{1}{2} \begin{pmatrix} 6 \\ 2 \end{pmatrix}
$$

Hence,

$$
\vec{a}(t) = \begin{pmatrix} 3 \\ 1 \end{pmatrix} \text{ m/s}^2
$$

### 2. Velocity

Use

$$
\vec{v}(t) = \vec{v}_0 + \vec{a}t
$$

So,

$$
\vec{v}(t) = \begin{pmatrix} 1 \\ -1 \end{pmatrix} + t \begin{pmatrix} 3 \\ 1 \end{pmatrix}
$$

Thus,

$$
\vec{v}(t) = \begin{pmatrix} 1 + 3t \\ -1 + t \end{pmatrix}
$$

### 3. Position

Use

$$
\vec{r}(t) = \vec{r}_0 + \vec{v}_0 t + \frac{1}{2} \vec{a} t^2
$$

Since $\vec{r}_0 = (0,0)$,

$$
\vec{r}(t) = t \begin{pmatrix} 1 \\ -1 \end{pmatrix} + \frac{1}{2} t^2 \begin{pmatrix} 3 \\ 1 \end{pmatrix}
$$

Therefore,

$$
\vec{r}(t) = \begin{pmatrix} t + \frac{3}{2} t^2 \\ -t + \frac{1}{2} t^2 \end{pmatrix}
$$

### 4. Trajectory

The motion is planar and non-uniform. The parametric equations are

$$
x(t) = t + \frac{3}{2} t^2
$$

$$
y(t) = -t + \frac{1}{2} t^2
$$

A useful elimination of the parameter is obtained from

$$
x + y = 2t^2
$$

and

$$
x - 3y = 4t
$$

Thus, the trajectory satisfies

$$
8(x + y) = (x - 3y)^2
$$

So the trajectory is a parabola in the $xy$-plane.

### 5. Work done by the force at $t=3$ s

First compute the displacement at $t=3$:

$$
\vec{r}(3) = \begin{pmatrix} 3 + \frac{3}{2} \cdot 9 \\ -3 + \frac{1}{2} \cdot 9 \end{pmatrix}
$$

$$
\vec{r}(3) = \begin{pmatrix} 16.5 \\ 1.5 \end{pmatrix}
$$

Since the initial position is the origin, the displacement is

$$
\Delta \vec{r} = \begin{pmatrix} 16.5 \\ 1.5 \end{pmatrix}
$$

The work done by the constant force is

$$
W = \vec{F} \cdot \Delta \vec{r}
$$

$$
W = \begin{pmatrix} 6 \\ 2 \end{pmatrix} \cdot \begin{pmatrix} 16.5 \\ 1.5 \end{pmatrix}
$$

$$
W = 6 \cdot 16.5 + 2 \cdot 1.5
$$

$$
W = 99 + 3
$$

$$
W = 102 \text{ J}
$$

### 6. Check the work-energy theorem

Initial kinetic energy:

$$
K_0 = \frac{1}{2} m |\vec{v}(0)|^2
$$

Since

$$
\vec{v}(0) = \begin{pmatrix} 1 \\ -1 \end{pmatrix}
$$

one has

$$
|\vec{v}(0)|^2 = 1^2 + (-1)^2 = 2
$$

Thus,

$$
K_0 = \frac{1}{2} \cdot 2 \cdot 2 = 2 \text{ J}
$$

Now find the velocity at $t=3$:

$$
\vec{v}(3) = \begin{pmatrix} 1 + 9 \\ -1 + 3 \end{pmatrix}
= \begin{pmatrix} 10 \\ 2 \end{pmatrix}
$$

Then

$$
|\vec{v}(3)|^2 = 10^2 + 2^2 = 104
$$

So the final kinetic energy is

$$
K_3 = \frac{1}{2} \cdot 2 \cdot 104 = 104 \text{ J}
$$

Therefore,

$$
\Delta K = K_3 - K_0 = 104 - 2 = 102 \text{ J}
$$

This matches the computed work.

## Final Result

The acceleration is

$$
\vec{a}(t) = \begin{pmatrix} 3 \\ 1 \end{pmatrix} \text{ m/s}^2
$$

The velocity is

$$
\vec{v}(t) = \begin{pmatrix} 1 + 3t \\ -1 + t \end{pmatrix}
$$

The position is

$$
\vec{r}(t) = \begin{pmatrix} t + \frac{3}{2} t^2 \\ -t + \frac{1}{2} t^2 \end{pmatrix}
$$

The trajectory is a parabola satisfying

$$
8(x + y) = (x - 3y)^2
$$

The work done by the force by time $t=3$ s is

$$
W = 102 \text{ J}
$$

The work-energy theorem is verified because

$$
\Delta K = 102 \text{ J}
$$

## Interpretation

A constant force produces constant acceleration, so the motion follows the standard uniformly accelerated form. The work done by the force exactly equals the increase in kinetic energy, as required by the work-energy theorem.
