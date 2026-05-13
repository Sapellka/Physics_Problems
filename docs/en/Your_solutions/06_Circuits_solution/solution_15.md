# Task 15 – Equivalent Resistance of a Resistor Cube

## Problem Statement

A cube is formed from 12 identical resistors, each of resistance

$$
R
$$

placed along the edges.

Determine the equivalent resistance between two opposite corners of the cube.

## Theory

This problem is solved most efficiently using symmetry.

If a voltage is applied between two opposite corners, then the three vertices adjacent to the first corner are at the same potential by symmetry. Likewise, the three vertices adjacent to the opposite corner are also at the same potential.

This allows the cube to be reduced to a simpler three-stage network.

## Step-by-Step Solution

Let the opposite corners be labeled

$$
A
$$

and

$$
G
$$

### 1. First group of three resistors

From corner

$$
A
$$

there are three identical edge resistors leading to three equivalent-potential nodes.

Since those three resistors connect the same two potentials, they are in parallel:

$$
R_1 = \frac{R}{3}
$$

### 2. Middle group of six resistors

Between the first equipotential group and the second equipotential group there are six edge resistors.

All six connect the same two potentials, so they are also in parallel:

$$
R_2 = \frac{R}{6}
$$

### 3. Final group of three resistors

From the second equipotential group to corner

$$
G
$$

there are again three identical resistors in parallel:

$$
R_3 = \frac{R}{3}
$$

### 4. Total equivalent resistance

These three reduced parts are in series:

$$
R_{\text{eq}} = \frac{R}{3} + \frac{R}{6} + \frac{R}{3}
$$

Use a common denominator:

$$
R_{\text{eq}} = \frac{2R}{6} + \frac{R}{6} + \frac{2R}{6}
$$

$$
R_{\text{eq}} = \frac{5R}{6}
$$

## Final Result

The equivalent resistance between opposite corners of the cube is

$$
R_{\text{eq}} = \frac{5R}{6}
$$

## Interpretation

The symmetry of the cube reduces a complicated three-dimensional network to a simple series combination of three parallel blocks.
