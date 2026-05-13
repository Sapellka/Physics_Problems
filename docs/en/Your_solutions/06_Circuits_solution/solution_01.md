# Task 01 – Series and Parallel Circuit

## Problem Statement

Three resistors have values

$$
R_1 = 15\,\Omega
$$

$$
R_2 = 30\,\Omega
$$

$$
R_3 = 50\,\Omega
$$

They are connected to a

$$
12 \text{ V}
$$

battery.

Determine:

- the equivalent resistance when all three are in series,
- the battery current in the series case,
- the equivalent resistance when all three are in parallel,
- the battery current in the parallel case.

## Theory

For resistors in series,

$$
R_{\text{eq}} = R_1 + R_2 + R_3
$$

For resistors in parallel,

$$
\frac{1}{R_{\text{eq}}} = \frac{1}{R_1} + \frac{1}{R_2} + \frac{1}{R_3}
$$

The current from the battery is found from Ohm's law:

$$
I = \frac{V}{R_{\text{eq}}}
$$

## Step-by-Step Solution

### 1. Series connection

$$
R_{\text{eq,series}} = 15 + 30 + 50 = 95\,\Omega
$$

Then

$$
I_{\text{series}} = \frac{12}{95} \approx 0.126 \text{ A}
$$

### 2. Parallel connection

$$
\frac{1}{R_{\text{eq,parallel}}} = \frac{1}{15} + \frac{1}{30} + \frac{1}{50}
$$

Using a common denominator:

$$
\frac{1}{R_{\text{eq,parallel}}} = \frac{10 + 5 + 3}{150} = \frac{18}{150} = \frac{3}{25}
$$

Hence,

$$
R_{\text{eq,parallel}} = \frac{25}{3}\,\Omega \approx 8.33\,\Omega
$$

Then

$$
I_{\text{parallel}} = \frac{12}{25/3} = \frac{36}{25} = 1.44 \text{ A}
$$

## Final Result

Series case:

$$
R_{\text{eq,series}} = 95\,\Omega
$$

$$
I_{\text{series}} \approx 0.126 \text{ A}
$$

Parallel case:

$$
R_{\text{eq,parallel}} = \frac{25}{3}\,\Omega \approx 8.33\,\Omega
$$

$$
I_{\text{parallel}} = 1.44 \text{ A}
$$

## Interpretation

The series connection gives a much larger equivalent resistance, so the current is small. The parallel connection gives a much smaller equivalent resistance, so the battery supplies a much larger current.
