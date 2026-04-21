# STAT 4340 — Interactive Statistics Demos

**Statistical Methods for Engineers and Applied Scientists**  
Southern Methodist University · Spring 2026 · Dr. David Saah

🔗 **[Open the demo site](https://saahdavid.github.io/stat4340-demos)**

---

## Overview

A collection of browser-based interactive visualizations for teaching core concepts from Chapters 7–8 of Devore's *Probability and Statistics for Engineering and the Sciences* (9th ed., Cengage).

All demos are fully self-contained HTML files — no installation, no internet connection required after download, and no frameworks or dependencies. Open any file directly in a browser.

---

## Demos

### 1. Rejection Region & p-value
**File:** `rejection_region_demo_v3.html`  
**Covers:** Devore §8.2 – §8.4

Demonstrates the fundamental equivalence between the two hypothesis testing decision methods:

> **p-value < α** ⟺ **test statistic falls in the rejection region**

Features three test types selectable by tab — Z-test for μ (n > 40, σ unknown), one-sample t-test (n ≤ 40, σ unknown), and Z-test for proportion p. Interactive sliders for the test statistic, degrees of freedom, and α. A "when to use" panel and decision guide help students identify the correct test before computing.

---

### 2. Type I & II Errors — Power Analysis
**File:** `type_i_ii_explorer.html`  
**Covers:** Devore §8.1 – §8.2

Two simultaneous canvases show the H₀ distribution and the true distribution overlapping, with α, β, and power shaded as areas in distinct colors. A live power curve plots Power vs. δ for the current settings and marks the operating point.

Sliders for effect size d = (μ′ − μ₀)/σ and sample size n make the key relationships concrete:
- Increasing n squeezes both curves → less overlap → higher power
- Shrinking α pushes the critical value out → β increases (the α–β trade-off)
- Conventional power targets (0.80 and 0.90) are marked on the power curve

---

### 3. Confidence Interval Simulator
**File:** `ci_simulator.html`  
**Covers:** Devore §7.2 – §7.3

Repeatedly samples from a population and draws each confidence interval as a horizontal bar. Green bars capture the true mean μ; red bars miss it. A running coverage counter tracks the proportion of intervals that contained μ, converging to the nominal confidence level over many trials.

Controls for confidence level (90%, 95%, 99%), sample size n, and animation speed. Step through one interval at a time or run hundreds automatically.

---

### 4. Test Selection Guide
**File:** `test_selector.html`  
**Covers:** Devore §8.2 – §8.4

A step-by-step interactive decision tree. Students answer three questions about their data:

1. Are you testing a mean μ or a proportion p?
2. Is σ known? If not, is n > 40?
3. Is the population approximately normal?

Each path resolves to the correct test with its formula, conditions, and Devore section reference. Warning cards are shown when standard test conditions are not met. A breadcrumb trail tracks the path taken and a back button allows correction.

---

## File Structure

```
index.html                    ← Landing page — links to all demos
rejection_region_demo_v3.html ← Demo 1: Rejection region & p-value
type_i_ii_explorer.html       ← Demo 2: Type I & II errors, power
ci_simulator.html             ← Demo 3: CI simulation
test_selector.html            ← Demo 4: Test selection flowchart
```

---

## Course Information

| | |
|---|---|
| **Course** | STAT 4340 / CS 4340 / OREM 3340 |
| **Instructor** | Dr. David Saah |
| **Office** | Heroy 134 |
| **Office Hours** | Mon/Wed 11 AM–12:30 PM, Tue 10 AM–1 PM |
| **TA** | Gloria Hu — Heroy 138, Thu 12–2 PM |
| **Textbook** | Devore, *Probability & Statistics for Engineering and the Sciences*, 9th ed., Cengage |

---

## License

Created for instructional use in STAT 4340/ CS 4340/ OREM 3340 at SMU. Free to adapt for educational purposes with attribution.
