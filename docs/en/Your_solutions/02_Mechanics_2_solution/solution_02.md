# Task 02 – Harmonic Motion of a Mass-Spring System

## Problem Statement

A mass of $10$ kg oscillates according to

$$
x(t) = 0.2 \cos(10\pi t)
$$

where $x$ is measured in meters.

Determine:

- the spring constant $k$,
- the total mechanical energy of the system.

## Theory

For simple harmonic motion of a spring-mass system,

$$
x(t) = A \cos(\omega t + \phi)
$$

where:

- $A$ is the amplitude,
- $\omega$ is the angular frequency.

The relation between angular frequency and spring constant is

$$
\omega = \sqrt{\frac{k}{m}}
$$

so

$$
k = m\omega^2
$$

The total mechanical energy is constant and equal to

$$
E = \frac{1}{2} k A^2
$$

## Step-by-Step Solution

From

$$
x(t) = 0.2 \cos(10\pi t)
$$

the amplitude is

$$
A = 0.2 \text{ m}
$$

and the angular frequency is

$$
\omega = 10\pi \text{ rad/s}
$$

### 1. Spring constant

Use

$$
k = m\omega^2
$$

Substitute the data:

$$
k = 10(10\pi)^2
$$

$$
k = 10 \cdot 100\pi^2
$$

$$
k = 1000\pi^2 \text{ N/m}
$$

Numerically,

$$
k \approx 9869.6 \text{ N/m}
$$

### 2. Total mechanical energy

Use

$$
E = \frac{1}{2} k A^2
$$

Substitute

$$
k = 1000\pi^2
$$

and

$$
A = 0.2
$$

Then

$$
E = \frac{1}{2} \cdot 1000\pi^2 \cdot (0.2)^2
$$

$$
E = \frac{1}{2} \cdot 1000\pi^2 \cdot 0.04
$$

$$
E = 20\pi^2 \text{ J}
$$

Numerically,

$$
E \approx 197.4 \text{ J}
$$

## Final Result

The spring constant is

$$
k = 1000\pi^2 \text{ N/m} \approx 9869.6 \text{ N/m}
$$

The total mechanical energy is

$$
E = 20\pi^2 \text{ J} \approx 197.4 \text{ J}
$$

## Interpretation

The motion is simple harmonic with a large angular frequency, which implies a very stiff spring. The total energy remains constant because no damping or friction is included in the model.
