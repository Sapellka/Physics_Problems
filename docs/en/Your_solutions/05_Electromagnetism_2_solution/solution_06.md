# Task 06 – Electric Field from Two Point Charges

## Problem Statement

Two point charges are placed at:

- $+q$ at $(-a,0)$,
- $+2q$ at $(a,0)$.

Required:

1. determine the field vector $\vec{E}(0,y)$, $\vec{E}(x,0)$, and the general field $\vec{E}(x,y)$,
2. determine the conditions for which $E_x = 0$, $E_y = 0$, and $\vec{E} = 0$,
3. calculate the field for

$$
a = 0.2 \text{ m}, \qquad y = 0.3 \text{ m}, \qquad q = 2\,\mu\text{C}
$$

4. investigate the limit

$$
y \gg a
$$

## Theory

The electric field of a point charge is

$$
\vec{E} = kq \frac{\vec{r} - \vec{r_0}}{|\vec{r} - \vec{r_0}|^3}
$$

For several charges, the total field is the vector sum of the individual fields.

## Step-by-Step Solution

### 1. General field $\vec{E}(x,y)$

Let

$$
\vec{r} = (x,y)
$$

The first charge is at

$$
\vec{r}_1 = (-a,0)
$$

and the second at

$$
\vec{r}_2 = (a,0)
$$

Therefore,

$$
\vec{E}(x,y) = kq \frac{(x+a)\hat{i} + y\hat{j}}{\left((x+a)^2 + y^2\right)^{3/2}} + 2kq \frac{(x-a)\hat{i} + y\hat{j}}{\left((x-a)^2 + y^2\right)^{3/2}}
$$

So the components are

$$
E_x(x,y) = kq \frac{x+a}{\left((x+a)^2 + y^2\right)^{3/2}} + 2kq \frac{x-a}{\left((x-a)^2 + y^2\right)^{3/2}}
$$

and

$$
E_y(x,y) = kq \frac{y}{\left((x+a)^2 + y^2\right)^{3/2}} + 2kq \frac{y}{\left((x-a)^2 + y^2\right)^{3/2}}
$$

### 2. Field on the $y$-axis

Set

$$
x = 0
$$

Then both distances are equal:

$$
R = \sqrt{a^2 + y^2}
$$

Thus,

$$
\vec{E}(0,y) = kq \frac{a\hat{i} + y\hat{j}}{R^3} + 2kq \frac{-a\hat{i} + y\hat{j}}{R^3}
$$

Hence,

$$
\vec{E}(0,y) = kq \frac{-a\hat{i} + 3y\hat{j}}{(a^2 + y^2)^{3/2}}
$$

So,

$$
E_x(0,y) = -kq \frac{a}{(a^2 + y^2)^{3/2}}
$$

$$
E_y(0,y) = 3kq \frac{y}{(a^2 + y^2)^{3/2}}
$$

### 3. Field on the $x$-axis

Set

$$
y = 0
$$

Then

$$
\vec{E}(x,0) = \left[ kq \frac{x+a}{|x+a|^3} + 2kq \frac{x-a}{|x-a|^3} \right] \hat{i}
$$

and

$$
E_y(x,0) = 0
$$

### 4. Conditions for $E_x = 0$, $E_y = 0$, and $\vec{E} = 0$

#### Condition for $E_y = 0$

From the general expression,

$$
E_y(x,y) = y \, kq \left[ \frac{1}{\left((x+a)^2 + y^2\right)^{3/2}} + \frac{2}{\left((x-a)^2 + y^2\right)^{3/2}} \right]
$$

The bracket is always positive, so

$$
E_y = 0 \quad \Longrightarrow \quad y = 0
$$

#### Condition for $E_x = 0$

In general, $E_x = 0$ means

$$
\frac{x+a}{\left((x+a)^2 + y^2\right)^{3/2}} + 2 \frac{x-a}{\left((x-a)^2 + y^2\right)^{3/2}} = 0
$$

This defines the locus where the horizontal components cancel.

#### Condition for $\vec{E} = 0$

To have zero total field, both components must vanish.

Since

$$
E_y = 0 \Longrightarrow y = 0
$$

we must look on the $x$-axis. Then the condition becomes

$$
\frac{x+a}{|x+a|^3} + 2 \frac{x-a}{|x-a|^3} = 0
$$

The only physical solution lies between the charges, where

$$
-a < x < a
$$

In that region,

$$
\frac{1}{(x+a)^2} = \frac{2}{(a-x)^2}
$$

Taking square roots,

$$
a - x = \sqrt{2}(x+a)
$$

which gives

$$
x = a(2\sqrt{2} - 3)
$$

Thus,

$$
\vec{E} = 0
$$

at

$$
\left( a(2\sqrt{2} - 3),\,0 \right)
$$

### 5. Numerical calculation for $a=0.2 \text{ m}$, $y=0.3 \text{ m}$, $q=2\,\mu\text{C}$

This corresponds to the point

$$
(0,y)
$$

Use

$$
\vec{E}(0,y) = kq \frac{-a\hat{i} + 3y\hat{j}}{(a^2 + y^2)^{3/2}}
$$

First compute

$$
a^2 + y^2 = 0.2^2 + 0.3^2 = 0.13
$$

so

$$
(a^2 + y^2)^{3/2} = 0.13^{3/2} \approx 0.04687
$$

With

$$
k \approx 8.99 \times 10^9, \qquad q = 2 \times 10^{-6} \text{ C}
$$

we obtain

$$
E_x \approx -7.67 \times 10^4 \text{ N/C}
$$

$$
E_y \approx 3.45 \times 10^5 \text{ N/C}
$$

Therefore,

$$
\vec{E}(0,0.3) \approx \left( -7.67 \times 10^4 \hat{i} + 3.45 \times 10^5 \hat{j} \right) \text{ N/C}
$$

Its magnitude is

$$
|\vec{E}| \approx 3.54 \times 10^5 \text{ N/C}
$$

### 6. Limit $y \gg a$

From

$$
\vec{E}(0,y) = kq \frac{-a\hat{i} + 3y\hat{j}}{(a^2 + y^2)^{3/2}}
$$

if

$$
y \gg a
$$

then

$$
(a^2 + y^2)^{3/2} \approx y^3
$$

Hence,

$$
\vec{E}(0,y) \approx -kq \frac{a}{y^3}\hat{i} + 3kq \frac{1}{y^2}\hat{j}
$$

The dominant term is the vertical one:

$$
\vec{E}(0,y) \approx 3kq \frac{1}{y^2}\hat{j}
$$

This is exactly the field of an effective total charge

$$
q_{\text{tot}} = q + 2q = 3q
$$

located near the origin.

## Final Result

The general field is

$$
\vec{E}(x,y) = kq \frac{(x+a)\hat{i} + y\hat{j}}{\left((x+a)^2 + y^2\right)^{3/2}} + 2kq \frac{(x-a)\hat{i} + y\hat{j}}{\left((x-a)^2 + y^2\right)^{3/2}}
$$

On the $y$-axis:

$$
\vec{E}(0,y) = kq \frac{-a\hat{i} + 3y\hat{j}}{(a^2 + y^2)^{3/2}}
$$

On the $x$-axis:

$$
\vec{E}(x,0) = \left[ kq \frac{x+a}{|x+a|^3} + 2kq \frac{x-a}{|x-a|^3} \right] \hat{i}
$$

The zero-field point is

$$
\left( a(2\sqrt{2} - 3),\,0 \right)
$$

For

$$
a = 0.2 \text{ m}, \qquad y = 0.3 \text{ m}, \qquad q = 2\,\mu\text{C}
$$

the field is approximately

$$
\vec{E} \approx \left( -7.67 \times 10^4 \hat{i} + 3.45 \times 10^5 \hat{j} \right) \text{ N/C}
$$

## Interpretation

Far from the two charges, the field behaves like the field of a single charge

$$
3q
$$

because the details of the separation become negligible compared with the observation distance.
