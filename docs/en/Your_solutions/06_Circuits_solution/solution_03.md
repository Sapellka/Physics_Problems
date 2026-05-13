# Task 03 – Mixed Circuit

## Problem Statement

Determine the equivalent resistance of the circuit shown in `image-r1.png`, where every resistor has value

$$
R = 5\,\Omega
$$

## Theory

A mixed circuit is simplified by identifying series groups and parallel groups step by step.

Two resistors are in series if the same current must pass through both.

Two branches are in parallel if they connect the same two nodes.

## Step-by-Step Solution

Let the left terminal be node $A$ and the right terminal be node $B$.

### 1. Upper-left branch

From node $A$ to the top junction, the left vertical resistor and the top horizontal resistor are in series:

$$
R_{A \to C}^{(1)} = 5 + 5 = 10\,\Omega
$$

### 2. Middle branch

From node $A$ to the same top junction, the lower horizontal resistor and the two central vertical resistors are in series:

$$
R_{A \to C}^{(2)} = 5 + 5 + 5 = 15\,\Omega
$$

### 3. Parallel combination between node $A$ and the top junction

These two branches connect the same pair of nodes, so they are in parallel:

$$
R_{AC} = 10 \parallel 15
$$

$$
R_{AC} = \frac{10 \cdot 15}{10 + 15} = \frac{150}{25} = 6\,\Omega
$$

### 4. Right branch

From the top junction to node $B$, the two right-side vertical resistors are in series:

$$
R_{CB} = 5 + 5 = 10\,\Omega
$$

So the entire upper network between $A$ and $B$ is

$$
R_{\text{upper}} = R_{AC} + R_{CB} = 6 + 10 = 16\,\Omega
$$

### 5. Bottom branch

There is also one direct bottom resistor between $A$ and $B$:

$$
R_{\text{bottom}} = 5\,\Omega
$$

This is in parallel with the whole upper network, so

$$
R_{\text{eq}} = 16 \parallel 5
$$

$$
R_{\text{eq}} = \frac{16 \cdot 5}{16 + 5} = \frac{80}{21}\,\Omega
$$

## Final Result

The equivalent resistance is

$$
R_{\text{eq}} = \frac{80}{21}\,\Omega \approx 3.81\,\Omega
$$

## Interpretation

The direct bottom branch provides a relatively low-resistance path, so the total equivalent resistance is much smaller than the resistance of the upper part of the circuit.
