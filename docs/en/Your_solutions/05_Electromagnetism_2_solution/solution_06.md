# Task 06 – Electromagnetic Wave Analysis

## Problem Statement

An electromagnetic wave has electric field component

$$
E_y(x,t) = 100 \sin(10^7 x - \omega t) \text{ V/m}
$$

Determine:

- the direction of propagation,
- the wavelength $\lambda$,
- the angular frequency $\omega$,
- the equation of the magnetic field component.

## Theory

A plane wave of the form

$$
\sin(kx - \omega t)
$$

propagates in the positive $x$-direction.

The wave number is related to wavelength by

$$
k = \frac{2\pi}{\lambda}
$$

For an electromagnetic wave in vacuum,

$$
\omega = ck
$$

and the electric and magnetic field amplitudes satisfy

$$
E_0 = cB_0
$$

Also, the propagation direction is given by

$$
\vec{E} \times \vec{B}
$$

## Step-by-Step Solution

### 1. Direction of propagation

The phase is

$$
10^7 x - \omega t
$$

This has the form

$$
kx - \omega t
$$

so the wave propagates in the positive $x$-direction.

### 2. Wavelength

The wave number is

$$
k = 10^7 \text{ rad/m}
$$

Use

$$
\lambda = \frac{2\pi}{k}
$$

$$
\lambda = \frac{2\pi}{10^7}
$$

$$
\lambda \approx 6.28 \times 10^{-7} \text{ m}
$$

### 3. Angular frequency

Assuming vacuum propagation,

$$
\omega = ck
$$

with

$$
c \approx 3.0 \times 10^8 \text{ m/s}
$$

Thus,

$$
\omega = (3.0 \times 10^8)(10^7)
$$

$$
\omega = 3.0 \times 10^{15} \text{ rad/s}
$$

### 4. Magnetic field component

The electric field is along the $y$-direction. To make the wave propagate in the positive $x$-direction, the magnetic field must be along the positive $z$-direction, because

$$
\hat{j} \times \hat{k} = \hat{i}
$$

The magnetic amplitude is

$$
B_0 = \frac{E_0}{c} = \frac{100}{3.0 \times 10^8}
$$

$$
B_0 \approx 3.33 \times 10^{-7} \text{ T}
$$

Therefore, the magnetic field component is

$$
B_z(x,t) = 3.33 \times 10^{-7} \sin(10^7 x - \omega t) \text{ T}
$$

## Final Result

The wave propagates in the

$$
+x
$$

direction.

The wavelength is

$$
\lambda \approx 6.28 \times 10^{-7} \text{ m}
$$

The angular frequency is

$$
\omega \approx 3.0 \times 10^{15} \text{ rad/s}
$$

The magnetic field component is

$$
B_z(x,t) = 3.33 \times 10^{-7} \sin(10^7 x - \omega t) \text{ T}
$$

## Interpretation

The electric and magnetic fields are perpendicular to each other and to the direction of propagation. The sign pattern fixes the travel direction, while the wave number sets the wavelength.
