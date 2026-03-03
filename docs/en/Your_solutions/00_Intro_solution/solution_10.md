# 10. Infinite Series — Full Solution

An ant starts at the origin:

$$
(x_0, y_0) = (0,0)
$$

It moves in the following pattern:

- $1$ m east  
- $\frac12$ m north  
- $\frac13$ m west  
- $\frac14$ m south  
- $\frac15$ m east  
- $\frac16$ m north  
- $\frac17$ m west  
- $\frac18$ m south  
- and so on.

Observe:

- Odd denominators ($1,3,5,7,\dots$) correspond to horizontal motion.
- Even denominators ($2,4,6,8,\dots$) correspond to vertical motion.
- Directions alternate (east/west and north/south).

We compute horizontal and vertical displacements separately.

---

## Step 1: Horizontal displacement

The horizontal motion is:

$$
+1,\; -\frac13,\; +\frac15,\; -\frac17,\; +\frac19,\dots
$$

Thus the total horizontal displacement is:

$$
x = 1 - \frac13 + \frac15 - \frac17 + \frac19 - \cdots
$$

---

## Step 2: Recognize the series

We use the Taylor expansion:

$$
\arctan(z) = z - \frac{z^3}{3} + \frac{z^5}{5} - \frac{z^7}{7} + \cdots
$$

For $z = 1$:

$$
\arctan(1) = 1 - \frac13 + \frac15 - \frac17 + \cdots
$$

But we know:

$$
\arctan(1) = \frac{\pi}{4}
$$

Therefore:

$$
x = \frac{\pi}{4}
$$

---

## Step 3: Vertical displacement

The vertical motion is:

$$
+\frac12,\; -\frac14,\; +\frac16,\; -\frac18,\; +\frac1{10},\dots
$$

Thus:

$$
y = \frac12 - \frac14 + \frac16 - \frac18 + \frac1{10} - \cdots
$$

Factor out $\frac12$:

$$
y = \frac12\left(1 - \frac12 + \frac13 - \frac14 + \frac15 - \cdots\right)
$$

Define:

$$
S = 1 - \frac12 + \frac13 - \frac14 + \frac15 - \cdots
$$

So:

$$
y = \frac12 S
$$

---

## Step 4: Recognize the alternating harmonic series

We use the Taylor expansion:

$$
\ln(1+z) = z - \frac{z^2}{2} + \frac{z^3}{3} - \frac{z^4}{4} + \cdots
$$

For $z = 1$:

$$
\ln(2) = 1 - \frac12 + \frac13 - \frac14 + \cdots
$$

Therefore:

$$
S = \ln(2)
$$

Thus:

$$
y = \frac12 \ln(2)
$$

---

## Step 5: Final position

$$
\boxed{
(x,y) = \left(\frac{\pi}{4}, \frac12 \ln(2)\right)
}
$$

---

## Step 6: Numerical approximation

$$
\frac{\pi}{4} \approx 0.7854
$$

$$
\frac12 \ln(2) \approx 0.3466
$$

Therefore:

$$
(x,y) \approx (0.785,\; 0.347)
$$
