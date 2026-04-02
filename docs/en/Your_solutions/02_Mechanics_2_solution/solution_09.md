# Task 09 – Vertical Throw with Linear Drag

## Problem Statement

The equation of motion is

$$
m\frac{dv}{dt} = -mg - kv
$$

with initial conditions

$$
v(0) = v_0
$$

and

$$
x(0) = 10
$$

Required:

- solve the equation analytically,
- determine the maximum height,
- compare with the case without drag,
- provide a numerical simulation in Python.

## Theory

The given differential equation is a first-order linear equation for the velocity.

Linear drag means the resistive force is proportional to the velocity and opposite to the motion.

After obtaining $v(t)$, the position is found by integration:

$$
x(t) = x(0) + \int_0^t v(\tau)\,d\tau
$$

The maximum height occurs when

$$
v(t) = 0
$$

## Step-by-Step Solution

### 1. Solve the velocity equation

Start with

$$
m\frac{dv}{dt} = -mg - kv
$$

Divide by $m$:

$$
\frac{dv}{dt} + \frac{k}{m} v = -g
$$

Let

$$
\alpha = \frac{k}{m}
$$

Then the equation becomes

$$
\frac{dv}{dt} + \alpha v = -g
$$

The solution of this linear equation is

$$
v(t) = Ce^{-\alpha t} - \frac{g}{\alpha}
$$

Since

$$
\frac{g}{\alpha} = \frac{mg}{k}
$$

one may write

$$
v(t) = Ce^{-\frac{k}{m}t} - \frac{mg}{k}
$$

Use the initial condition

$$
v(0) = v_0
$$

Then

$$
v_0 = C - \frac{mg}{k}
$$

so

$$
C = v_0 + \frac{mg}{k}
$$

Therefore,

$$
v(t) = \left( v_0 + \frac{mg}{k} \right)e^{-\frac{k}{m}t} - \frac{mg}{k}
$$

### 2. Position as a function of time

Now integrate:

$$
x(t) = 10 + \int_0^t \left[ \left( v_0 + \frac{mg}{k} \right)e^{-\frac{k}{m}\tau} - \frac{mg}{k} \right] d\tau
$$

This gives

$$
x(t) = 10 + \frac{m}{k} \left( v_0 + \frac{mg}{k} \right)\left( 1 - e^{-\frac{k}{m}t} \right) - \frac{mg}{k} t
$$

### 3. Time to maximum height

At maximum height,

$$
v(t_{\max}) = 0
$$

So,

$$
\left( v_0 + \frac{mg}{k} \right)e^{-\frac{k}{m}t_{\max}} = \frac{mg}{k}
$$

Hence,

$$
e^{-\frac{k}{m}t_{\max}} = \frac{mg}{kv_0 + mg}
$$

Taking the natural logarithm,

$$
t_{\max} = \frac{m}{k} \ln \left( 1 + \frac{kv_0}{mg} \right)
$$

### 4. Maximum height

Insert $t_{\max}$ into $x(t)$.

A simplified expression is

$$
x_{\max} = 10 + \frac{mv_0}{k} - \frac{m^2 g}{k^2} \ln \left( 1 + \frac{kv_0}{mg} \right)
$$

### 5. Comparison with the case without drag

Without drag,

$$
\frac{dv}{dt} = -g
$$

so

$$
v_{\text{no drag}}(t) = v_0 - gt
$$

and

$$
x_{\text{no drag}}(t) = 10 + v_0 t - \frac{1}{2} gt^2
$$

The maximum height without drag is

$$
x_{\max,\text{no drag}} = 10 + \frac{v_0^2}{2g}
$$

Because drag always removes upward speed, the dragged motion reaches a smaller maximum height and reaches it sooner.

## Final Result

The velocity is

$$
v(t) = \left( v_0 + \frac{mg}{k} \right)e^{-\frac{k}{m}t} - \frac{mg}{k}
$$

The position is

$$
x(t) = 10 + \frac{m}{k} \left( v_0 + \frac{mg}{k} \right)\left( 1 - e^{-\frac{k}{m}t} \right) - \frac{mg}{k} t
$$

The time to maximum height is

$$
t_{\max} = \frac{m}{k} \ln \left( 1 + \frac{kv_0}{mg} \right)
$$

The maximum height is

$$
x_{\max} = 10 + \frac{mv_0}{k} - \frac{m^2 g}{k^2} \ln \left( 1 + \frac{kv_0}{mg} \right)
$$

Without drag, the maximum height would be

$$
x_{\max,\text{no drag}} = 10 + \frac{v_0^2}{2g}
$$

## Interpretation

Linear drag causes the upward velocity to decay exponentially toward the terminal value associated with the force balance. Compared with the ideal case, the projectile rises for a shorter time and reaches a smaller maximum height.
















## Numerical Simulation in Python

The following script can be run externally to compare the motion with and without drag.

~~~python
import numpy as np
import matplotlib.pyplot as plt

m = 1.0
g = 9.81
k = 0.4
v0 = 20.0
x0 = 10.0

t = np.linspace(0, 5, 1000)

v_drag = (v0 + m*g/k) * np.exp(-(k/m)*t) - m*g/k
x_drag = x0 + (m/k) * (v0 + m*g/k) * (1 - np.exp(-(k/m)*t)) - (m*g/k) * t

v_nodrag = v0 - g*t
x_nodrag = x0 + v0*t - 0.5*g*t**2

plt.figure(figsize=(8, 5))
plt.plot(t, x_drag, label="With drag")
plt.plot(t, x_nodrag, label="Without drag", linestyle="--")
plt.xlabel("t")
plt.ylabel("x(t)")
plt.title("Vertical motion with and without linear drag")
plt.legend()
plt.grid(True)
plt.show()
~~~
