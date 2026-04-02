# Task 01 – Gravitational Dependence of a Simple Pendulum

## Problem Statement

A simple pendulum has a period of $4$ s on Earth.

Determine:

- its period on the Moon, where the gravitational acceleration is $\frac{1}{6}$ of Earth's,
- the required pendulum length for a period of exactly $1$ s on Earth.

## Theory

For small oscillations, the period of a simple pendulum is

$$
T = 2\pi \sqrt{\frac{L}{g}}
$$

For a fixed length $L$, the period is proportional to

$$
\frac{1}{\sqrt{g}}
$$

Thus, weaker gravity produces a longer period.

## Step-by-Step Solution

### 1. Period on the Moon

On Earth,

$$
T_E = 4 \text{ s}
$$

For the same pendulum length,

$$
\frac{T_M}{T_E} = \sqrt{\frac{g_E}{g_M}}
$$

Since

$$
g_M = \frac{g_E}{6}
$$

it follows that

$$
\frac{T_M}{T_E} = \sqrt{6}
$$

Hence,

$$
T_M = 4\sqrt{6} \text{ s}
$$

Numerically,

$$
T_M \approx 9.80 \text{ s}
$$

### 2. Length for a $1$ s period on Earth

Start from

$$
T = 2\pi \sqrt{\frac{L}{g}}
$$

Solve for $L$:

$$
L = g \left( \frac{T}{2\pi} \right)^2
$$

For

$$
T = 1 \text{ s}
$$

and

$$
g = 9.81 \text{ m/s}^2
$$

one gets

$$
L = 9.81 \left( \frac{1}{2\pi} \right)^2
$$

$$
L = \frac{9.81}{4\pi^2}
$$

$$
L \approx 0.248 \text{ m}
$$

## Final Result

The period on the Moon is

$$
T_M = 4\sqrt{6} \text{ s} \approx 9.80 \text{ s}
$$

The required pendulum length for a $1$ s period on Earth is

$$
L \approx 0.248 \text{ m}
$$

## Interpretation

The pendulum swings more slowly on the Moon because gravity is weaker. The second result shows that a pendulum with a very short length is needed to achieve a period of only one second.
