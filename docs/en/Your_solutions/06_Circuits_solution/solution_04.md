# Task 04 – Mixed Circuit

## Problem Statement

Determine the equivalent resistance of the circuit shown in `image-r2.png`, where every resistor has value

$$
R = 10\,\Omega
$$

## Theory

A mixed circuit is reduced by replacing simple series and parallel groups with their equivalents until only one equivalent resistance remains.

## Step-by-Step Solution

Let the left terminal be node $A$ and the junction before the final right resistor be node $B$.

### 1. Top branch from $A$ to $B$

The two upper resistors are in series:

$$
R_{\text{top}} = 10 + 10 = 20\,\Omega
$$

### 2. Lower branch from $A$ to $B$

The first lower-left resistor is in series with a parallel pair.

The two right-lower resistors connect the same two nodes, so they are in parallel:

$$
R_{\text{parallel}} = 10 \parallel 10
$$

$$
R_{\text{parallel}} = \frac{10 \cdot 10}{10 + 10} = 5\,\Omega
$$

Therefore the whole lower branch is

$$
R_{\text{bottom}} = 10 + 5 = 15\,\Omega
$$

### 3. Equivalent resistance from $A$ to $B$

The top and bottom branches are in parallel:

$$
R_{AB} = 20 \parallel 15
$$

$$
R_{AB} = \frac{20 \cdot 15}{20 + 15} = \frac{300}{35} = \frac{60}{7}\,\Omega
$$

### 4. Final right resistor

There is one more resistor of

$$
10\,\Omega
$$

in series between node $B$ and the right terminal.

Hence,

$$
R_{\text{eq}} = \frac{60}{7} + 10
$$

$$
R_{\text{eq}} = \frac{60}{7} + \frac{70}{7} = \frac{130}{7}\,\Omega
$$

## Final Result

The equivalent resistance is

$$
R_{\text{eq}} = \frac{130}{7}\,\Omega \approx 18.57\,\Omega
$$

## Interpretation

The lower branch is smaller than the upper branch because of the parallel pair. After combining those two branches in parallel, the remaining right-hand resistor increases the final equivalent resistance by a full series contribution of $10\,\Omega$.
