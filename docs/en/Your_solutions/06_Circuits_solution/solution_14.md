# Task 14 – Differential Equation of a Series RLC Circuit

## Problem Statement

Write the differential equation for a series RLC circuit with source voltage

$$
V(t)
$$

resistor

$$
R
$$

inductor

$$
L
$$

and capacitor

$$
C
$$

Assume the current is

$$
I(t)
$$

and the capacitor voltage is

$$
V_C(t)
$$

Compare the equation with the equation of a damped harmonic oscillator.

## Theory

Kirchhoff's voltage law states that the sum of the voltage drops in a closed loop equals the source voltage.

For the elements:

- resistor:

$$
V_R = RI
$$

- inductor:

$$
V_L = L \frac{dI}{dt}
$$

- capacitor:

$$
V_C = \frac{q}{C}
$$

with

$$
I = \frac{dq}{dt}
$$

## Step-by-Step Solution

### 1. KVL equation in terms of current and capacitor voltage

Kirchhoff's law gives

$$
V(t) = L \frac{dI}{dt} + RI + V_C
$$

This is the series RLC equation in mixed form.

### 2. Equation in terms of charge

Since

$$
I = \frac{dq}{dt}
$$

and

$$
V_C = \frac{q}{C}
$$

substitute into the loop equation:

$$
V(t) = L \frac{d^2 q}{dt^2} + R \frac{dq}{dt} + \frac{q}{C}
$$

Rearranged,

$$
L \frac{d^2 q}{dt^2} + R \frac{dq}{dt} + \frac{1}{C} q = V(t)
$$

### 3. Comparison with a damped harmonic oscillator

The damped harmonic oscillator equation is

$$
m \frac{d^2 x}{dt^2} + b \frac{dx}{dt} + kx = F(t)
$$

Comparing term by term with

$$
L \frac{d^2 q}{dt^2} + R \frac{dq}{dt} + \frac{1}{C} q = V(t)
$$

gives the analogies

$$
L \longleftrightarrow m
$$

$$
R \longleftrightarrow b
$$

$$
\frac{1}{C} \longleftrightarrow k
$$

$$
q \longleftrightarrow x
$$

$$
V(t) \longleftrightarrow F(t)
$$

## Final Result

The series RLC equation is

$$
V(t) = L \frac{dI}{dt} + RI + V_C
$$

or equivalently, in terms of charge,

$$
L \frac{d^2 q}{dt^2} + R \frac{dq}{dt} + \frac{1}{C} q = V(t)
$$

The analogy with the damped oscillator is:

$$
L \leftrightarrow m,\quad R \leftrightarrow b,\quad \frac{1}{C} \leftrightarrow k,\quad q \leftrightarrow x,\quad V(t) \leftrightarrow F(t)
$$

## Interpretation

A series RLC circuit behaves mathematically like a damped driven oscillator. Inductance acts like inertia, resistance acts like damping, and capacitance provides the restoring term.
