# Circle Containment Probability Visualizer

An interactive visualization tool for estimating the probability that a randomly positioned circle is fully contained within a set of allowed circle positions.

---

## Overview

This project explores a geometric probability problem:

> A circle has a center whose position follows a 2D normal (Gaussian) distribution.
> Another circle can be placed at one of N equally spaced positions on a ring.
>
> What is the probability that the randomly positioned circle is fully contained within one of those possible positions?

This application provides an intuitive, visual, and simulation-based answer using Monte Carlo methods.

---

## Key Idea

Instead of checking full circle containment directly, we transform the problem:

* Let the random variable be the **center of the uncertain circle**
* For each allowed position of the second circle, define a **containment region**
* These regions represent all points where the random center must land for full containment

The problem becomes:

> What fraction of the Gaussian distribution lies inside the union of these regions?

---

## Method: Monte Carlo Simulation

The probability is estimated by:

1. Sampling random points from a 2D Gaussian distribution
2. Checking whether each sampled point falls inside any containment region
3. Computing:

[
\hat{P} = \frac{\text{# of successful samples}}{\text{total samples}}
]

This approach works for:

* any number of positions (N)
* arbitrary Gaussian parameters
* overlapping or non-overlapping regions

---

## Visualization

The app displays:

* **Gaussian density (heatmap)**
  Likelihood of the random center’s position

* **Allowed circle positions**
  Equally spaced locations on a ring

* **Containment regions**
  Areas where full containment occurs

* **Sampled centers**
  Monte Carlo samples:

  * green = success
  * gray = failure

---

## Mathematical Condition

Containment occurs when:

[
|X - c_k| \le R - r
]

Where:

* (X) = random center (Gaussian)
* (c_k) = allowed position
* (r, R) = circle radii

---

## Why Monte Carlo?

A closed-form solution exists only in special cases.

In general (multiple regions, overlap, arbitrary Gaussian), the probability requires integrating a 2D Gaussian over a union of regions.

Monte Carlo provides:

* a simple
* flexible
* and scalable solution

---

## Use Cases

This type of problem appears in:

* Robotics and localization uncertainty
* Target acquisition systems
* Sensor coverage modeling
* Manufacturing tolerances
* Wireless signal coverage
* Probabilistic geometry

---

## Running the Project

This is a static web app.

To run locally:

1. Open `index.html` in a browser

To host:

* Deploy via GitHub Pages

---

## Future Improvements

* Analytical solutions for special cases
* Convergence plots for Monte Carlo estimates
* Parameter sharing via URL
* Additional geometric configurations

---

## Author

Built as an interactive tool for understanding probabilistic geometry and Monte Carlo simulation.
