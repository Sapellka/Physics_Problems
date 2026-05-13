# Task 05 – Kirchhoff's Laws

## Problem Statement

Determine the currents in the circuit shown in `image-k1.png`.

The figure labels differ slightly from the earlier text description, so the currents are defined directly from the diagram:

- $I_1$ is the current through the right-hand resistor

$$
R_1 = 10\,\Omega
$$

- $I_2$ is the current through the inner resistor

$$
R_2 = 20\,\Omega
$$

- $I_3$ is the current through the upper branch resistor

$$
r_w = 1\,\Omega
$$

which is in series with the source

$$
\mathcal{E}_2 = 4.5\,\text{V}
$$

The lower source branch contains

$$
\mathcal{E}_1 = 9\,\text{V}
$$

and another internal resistance

$$
r_w = 1\,\Omega
$$

## Theory

Kirchhoff's current law states that the algebraic sum of currents at a node is zero.

Kirchhoff's voltage law states that the algebraic sum of potential differences around a closed loop is zero.

A convenient method here is to assign node voltages and express each branch current using Ohm's law.

## Step-by-Step Solution

Let the left node have potential

$$
V_A = 0
$$

Let the upper-right node be

$$
V_B
$$

and the lower-right node be

$$
V_C
$$

### 1. Branch currents

#### Upper source branch

The source

$$
\mathcal{E}_2 = 4.5\,\text{V}
$$

has its positive terminal on the left, so the current from left to right in the upper branch is

$$
I_3 = \frac{V_A - V_B - 4.5}{1}
$$

Since

$$
V_A = 0
$$

this becomes

$$
I_3 = -(V_B + 4.5)
$$

#### Inner resistor branch

The current through

$$
R_2 = 20\,\Omega
$$

from left to right is

$$
I_2 = \frac{V_A - V_B}{20} = -\frac{V_B}{20}
$$

#### Right resistor branch

The current through

$$
R_1 = 10\,\Omega
$$

from top to bottom is

$$
I_1 = \frac{V_B - V_C}{10}
$$

#### Lower source branch

The current from left to right in the lower branch is

$$
I_{\text{bottom}} = \frac{V_A - V_C - 9}{1} = -(V_C + 9)
$$

### 2. Kirchhoff current law at the upper-right node

At node $B$, currents leaving the node are:

- through the upper source branch toward the left,
- through the inner resistor toward the left,
- through the right resistor downward.

Thus,

$$
(V_B + 4.5) + \frac{V_B}{20} + \frac{V_B - V_C}{10} = 0
$$

### 3. Kirchhoff current law at the lower-right node

At node $C$, currents leaving the node are:

- through the lower branch toward the left,
- through the right resistor upward.

Hence,

$$
(V_C + 9) + \frac{V_C - V_B}{10} = 0
$$

### 4. Solve the node equations

The system is

$$
(V_B + 4.5) + \frac{V_B}{20} + \frac{V_B - V_C}{10} = 0
$$

$$
(V_C + 9) + \frac{V_C - V_B}{10} = 0
$$

Solving gives

$$
V_B = -\frac{1170}{251} \approx -4.66 \text{ V}
$$

$$
V_C = -\frac{2160}{251} \approx -8.61 \text{ V}
$$

### 5. Compute the currents

#### Current through $R_1 = 10\,\Omega$

$$
I_1 = \frac{V_B - V_C}{10}
$$

$$
I_1 = \frac{-1170/251 + 2160/251}{10}
$$

$$
I_1 = \frac{99}{251} \text{ A} \approx 0.394 \text{ A}
$$

This is downward through the right-hand resistor.

#### Current through $R_2 = 20\,\Omega$

$$
I_2 = -\frac{V_B}{20}
$$

$$
I_2 = \frac{117}{502} \text{ A} \approx 0.233 \text{ A}
$$

This is from left to right through the inner resistor.

#### Current through the upper $1\,\Omega$ branch resistor

$$
I_3 = -(V_B + 4.5)
$$

$$
I_3 = \frac{81}{502} \text{ A} \approx 0.161 \text{ A}
$$

This is from left to right through the upper source branch.

A useful check is

$$
I_1 = I_2 + I_3
$$

Numerically,

$$
0.394 \approx 0.233 + 0.161
$$

which is correct.

## Final Result

Using the resistor branches visible in the figure:

- current through the right-hand resistor

$$
R_1 = 10\,\Omega
$$

is

$$
I_1 \approx 0.394 \text{ A}
$$

downward,

- current through the inner resistor

$$
R_2 = 20\,\Omega
$$

is

$$
I_2 \approx 0.233 \text{ A}
$$

from left to right,

- current through the upper branch resistor

$$
r_w = 1\,\Omega
$$

is

$$
I_3 \approx 0.161 \text{ A}
$$

from left to right.

## Interpretation

The two source branches both drive current into the right-hand part of the circuit, and the current through the vertical $10\,\Omega$ resistor is the sum of the two currents arriving at the upper-right node.
