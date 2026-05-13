# Task 06 – Current Through the Ammeter

## Problem Statement

Determine the current flowing through the ammeter in the circuit shown in `image-k2.png`.

The diagram contains:

- upper resistor

$$
R_1 = 20\,\Omega
$$

- inner vertical resistor

$$
R_2 = 10\,\Omega
$$

- lower source branch with

$$
\mathcal{E}_1 = 4.5\,\text{V}, \qquad r_w = 1\,\Omega
$$

- right inner branch with

$$
\mathcal{E}_2 = 9\,\text{V}, \qquad r_w = 1\,\Omega
$$

## Theory

The ammeter is in series with the outer left branch, so its current is the same as the current through the upper resistor

$$
R_1 = 20\,\Omega
$$

A convenient method is again to use node voltages.

## Step-by-Step Solution

Let the left side of the circuit be node $A$ with potential

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

### 1. Current through the upper resistor

The current from left to right through

$$
R_1 = 20\,\Omega
$$

is

$$
I_A = \frac{V_A - V_B}{20} = -\frac{V_B}{20}
$$

This is also the ammeter current.

### 2. Lower branch current

In the lower branch, the battery

$$
\mathcal{E}_1 = 4.5\,\text{V}
$$

has its positive terminal on the left, so the current from left to right is

$$
I_{\text{bottom}} = \frac{V_A - V_C - 4.5}{1} = -(V_C + 4.5)
$$

### 3. Inner resistor branch

The current from $B$ to $C$ through

$$
R_2 = 10\,\Omega
$$

is

$$
I_{R_2} = \frac{V_B - V_C}{10}
$$

### 4. Right source branch

In the right branch, the battery

$$
\mathcal{E}_2 = 9\,\text{V}
$$

has its positive terminal at the bottom. Therefore, the current from $B$ to $C$ through that branch is

$$
I_{\text{right}} = V_B - V_C + 9
$$

### 5. Kirchhoff current law at the upper-right node

Currents leaving node $B$ are:

- through the upper resistor toward the left,
- through the $10\,\Omega$ resistor downward,
- through the right source branch downward.

So,

$$
\frac{V_B}{20} + \frac{V_B - V_C}{10} + (V_B - V_C + 9) = 0
$$

### 6. Kirchhoff current law at the lower-right node

Currents leaving node $C$ are:

- through the lower branch toward the left,
- through the $10\,\Omega$ branch upward,
- through the right source branch upward.

Hence,

$$
(V_C + 4.5) + \frac{V_C - V_B}{10} + (V_C - V_B - 9) = 0
$$

### 7. Solve for the node voltages

Solving the system gives

$$
V_B = -\frac{2790}{241} \approx -11.58 \text{ V}
$$

$$
V_C = -\frac{945}{241} \approx -3.92 \text{ V}
$$

### 8. Ammeter current

Now compute

$$
I_A = -\frac{V_B}{20}
$$

$$
I_A = \frac{279}{482} \text{ A}
$$

$$
I_A \approx 0.579 \text{ A}
$$

## Final Result

The ammeter current is

$$
I_A = \frac{279}{482} \text{ A} \approx 0.579 \text{ A}
$$

The direction is upward through the ammeter, from the lower branch toward the upper resistor.

## Interpretation

The right-hand source branch strongly drives current through the inner part of the circuit, and part of that current returns through the outer loop, which is why the ammeter shows a nonzero upward current.
