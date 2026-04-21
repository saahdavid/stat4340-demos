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

$$\text{p-value} < \alpha \iff \text{test statistic falls in the rejection region}$$

Features four test types selectable by tab:

| Tab | Condition | Test statistic | Validity |
|-----|-----------|---------------|----------|
| $Z$-test ($\sigma$ known, exact) | Normal population, $\sigma$ known, any $n$ | $Z = \dfrac{\bar{X} - \mu_0}{\sigma/\sqrt{n}} \sim N(0,1)$ | Exact |
| $Z$-test ($n > 40$, $\sigma$ unknown) | Any population, $n > 40$ | $Z = \dfrac{\bar{X} - \mu_0}{S/\sqrt{n}} \approx N(0,1)$ | Approximate (CLT) |
| $t$-test ($n \leq 40$, $\sigma$ unknown) | Normal population, $n \leq 40$ | $T = \dfrac{\bar{X} - \mu_0}{S/\sqrt{n}} \sim t_{n-1}$ | Exact |
| $Z$-test (proportion) | $np_0 \geq 10$ and $n(1-p_0) \geq 10$ | $Z = \dfrac{\hat{p} - p_0}{\sqrt{p_0(1-p_0)/n}} \sim N(0,1)$ | Approximate |

Interactive sliders for the test statistic, degrees of freedom $\nu = n - 1$, and $\alpha$. A "when to use" panel and decision guide help students identify the correct test before computing.

---

### 2. Type I & II Errors — Power Analysis
**File:** `type_i_ii_explorer.html`  
**Covers:** Devore §8.1 – §8.2

Two simultaneous canvases show the $H_0$ distribution and the true distribution overlapping, with $\alpha$, $\beta$, and power shaded as areas in distinct colors. A live power curve plots Power vs. $\delta$ for the current settings and marks the operating point.

The non-centrality parameter is $\delta = d\sqrt{n}$, where $d = (\mu' - \mu_0)/\sigma$ is the standardized effect size. Sliders for $d$ and $n$ make the key relationships concrete:

- Increasing $n$ squeezes both curves $\rightarrow$ less overlap $\rightarrow$ higher power
- Shrinking $\alpha$ pushes the critical value out $\rightarrow$ $\beta$ increases (the $\alpha$–$\beta$ trade-off)
- Conventional power targets of $0.80$ and $0.90$ are marked on the power curve

The Type II error probability for an upper-tailed test at the true mean $\mu'$ is:

$$\beta(\mu') = \Phi\!\left(z_\alpha - \frac{\mu' - \mu_0}{\sigma/\sqrt{n}}\right)$$

---

### 3. Confidence Interval Simulator
**File:** `ci_simulator.html`  
**Covers:** Devore §7.2 – §7.3

Repeatedly samples from a population and draws each confidence interval as a horizontal bar. Green bars capture the true mean $\mu$; red bars miss it. A running coverage counter tracks the proportion of intervals that contained $\mu$, converging to the nominal confidence level over many trials.

Each interval is computed as:

$$\bar{X} \pm z_{\alpha/2} \cdot \frac{\sigma}{\sqrt{n}}$$

Controls for confidence level ($90\%$, $95\%$, $99\%$), sample size $n$, and animation speed. Step through one interval at a time or run hundreds automatically.

---

### 4. Test Selection Guide
**File:** `test_selector.html`  
**Covers:** Devore §8.2 – §8.4

A step-by-step interactive decision tree. Students answer questions about their data to arrive at the correct test:

1. Are you testing a mean $\mu$ or a proportion $p$?
2. Is $\sigma$ known?
   - If **yes** $\rightarrow$ is the population approximately normal? If so, use the exact $Z$-test for any $n$.
   - If **no** $\rightarrow$ is $n > 40$? If so, use the large-sample $Z$-test with $S$. Otherwise check normality for the $t$-test.
3. For proportions: do $np_0 \geq 10$ and $n(1 - p_0) \geq 10$ hold?

Each path resolves to the correct test with its formula, conditions, and Devore section reference. Warning cards are shown when standard test conditions are not met. A breadcrumb trail tracks the path taken, and a back button allows correction.

---

## Test Selection Summary

$$\boxed{\sigma \text{ known, normal population, any } n \;\longrightarrow\; Z\text{-test (exact)}}$$

$$\boxed{\sigma \text{ unknown, } n > 40 \;\longrightarrow\; Z\text{-test with } S \text{ (approximate, CLT)}}$$

$$\boxed{\sigma \text{ unknown, } n \leq 40 \text{, normal population} \;\longrightarrow\; t\text{-test}}$$

$$\boxed{np_0 \geq 10 \text{ and } n(1-p_0) \geq 10 \;\longrightarrow\; Z\text{-test for proportion}}$$

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

Created for instructional use in STAT 4340 / CS 4340 / OREM 3340 at SMU. Free to adapt for educational purposes with attribution.
