# Financial_Modeling


# Seladelpar Monte Carlo Valuation Model

## Overview

This project implements a **Monte Carlo financial model** to estimate the potential valuation of **seladelpar**, a treatment for primary biliary cholangitis (PBC), following its acquisition by Gilead.

Instead of producing a single valuation estimate, the model simulates **thousands of possible commercial scenarios** to capture uncertainty in key assumptions such as:

* market size
* drug pricing
* market penetration
* operating margins
* regulatory approval probability
* exclusivity duration

The result is a **distribution of possible valuations** rather than a single deterministic value.

---

## Model Approach

The model follows these steps:

1. **Sample uncertain inputs**

   * addressable patient population
   * market penetration
   * drug price
   * approval probability
   * operating margin
   * discount rate
   * exclusivity duration

2. **Construct a revenue lifecycle**

   * launch ramp
   * peak revenue plateau during exclusivity
   * revenue erosion after patent expiry

3. **Calculate operating profits**

4. **Discount future cash flows** to present value

5. **Apply regulatory approval probability** to obtain risk-adjusted NPV

This process is repeated **10,000 times** to generate a distribution of possible valuations.

---

## Key Outputs

The simulation produces:

* distribution of risk-adjusted NPV
* probability that valuation exceeds the acquisition price
* sensitivity of valuation to key drivers

Example insights:

* expected valuation range
* likelihood that the acquisition price is justified
* key commercial drivers of value

---

## Repository Structure

```text
seladelpar-valuation/
│
├─ seladelpar_monte_carlo.ipynb     # main notebook containing the model
│
├─ outputs/
│  ├─ seladelpar_monte_carlo_summary.csv
│  ├─ seladelpar_monte_carlo_detailed.csv
│  └─ seladelpar_monte_carlo_results.csv
│
├─ figures/
│  ├─ npv_distribution.png
│  ├─ valuation_cdf.png
│  ├─ revenue_lifecycle.png
│  └─ value_drivers.png
│
└─ README.md
```

---

## Notebook

The notebook contains the full workflow:

* definition of model assumptions
* Monte Carlo simulation
* generation of valuation statistics
* visualization of results

Figures produced include:

* Monte Carlo valuation distribution
* cumulative valuation probability
* revenue lifecycle of the drug
* drivers of valuation

---

## Output Data

### `seladelpar_monte_carlo_detailed.csv`

Full simulation results.

Each row corresponds to **one Monte Carlo scenario** and includes:

* addressable patient population
* peak penetration
* annual price
* approval probability
* ramp years
* exclusivity years
* operating margin
* discount rate
* peak revenue
* NPV if approved
* risk-adjusted NPV
* synergy value

This dataset allows further analysis of valuation drivers.

---

### `seladelpar_monte_carlo_summary.csv`

Summary statistics of the simulated valuations, including:

* mean and median valuation
* percentile ranges
* probability that valuation exceeds the acquisition price

---

### `seladelpar_monte_carlo_results.csv`

Additional model outputs used for analysis and visualization.

---

## Key Visualization Examples

The notebook generates figures that illustrate:

**Monte Carlo valuation distribution**

Shows the range and likelihood of possible valuations.

**Cumulative probability distribution**

Illustrates the probability that the drug’s valuation exceeds the acquisition price.

**Revenue lifecycle**

Shows the modeled commercial trajectory of the drug from launch through patent expiry.

**Drivers of valuation**

Highlights which assumptions have the greatest impact on valuation.

---

## Requirements

Python 3.9+

Libraries used:

```
numpy
pandas
matplotlib
```

Install dependencies with:

```
pip install numpy pandas matplotlib
```

---

## Purpose

This project demonstrates how **probabilistic financial modeling** can be used to evaluate biotechnology acquisitions under uncertainty.

By simulating many potential market outcomes, the model provides a **risk-based perspective on drug valuation** rather than relying on a single estimate.

---

## Author

Marie-Batisse Heite
