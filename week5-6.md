
> > ✍️ **Added by:** Ayush Kumar, <03/10/2026>

# Types of Branch Points & Branch Cuts

## 1. Classification of Branch Points

A point $z_0$ is called a **branch point** if going around it in a small closed loop brings you to a different branch instead of returning to the original function value[cite: 3].

---

### (i) Algebraic Branch Points

**Definition:** A branch point where going around $z_0$ a **finite number of times** ($q$ times) brings the function back to where it started[cite: 1, 2].

* **General form:** Functions like $f(z) = z^{p/q}$ or $(z-z_0)^{p/q}$[cite: 1].
* **Riemann Surface:** Made of $q$ sheets joined together[cite: 2]. Every full $2\pi$ loop adds a phase of $2\pi (p/q)$ and moves you down from one sheet to the next ($1 \to 2 \to \dots \to q$), until the $q$-th loop takes you back to Sheet 1[cite: 1, 2].

**Example:** $f(z) = z^{1/3}$
* Branch points are at $z = 0$ and $z = \infty$[cite: 1].
* Here $w = r^{1/3} e^{i(\theta + 2\pi n)/3}$[cite: 1, 4]. Going around $z=0$ once ($\Delta\theta = 2\pi$) changes the phase by $2\pi/3$[cite: 1].
  * Loop 1 ($n=0$): Phase goes from $0$ to $2\pi/3$ (Sheet 1)[cite: 1, 3].
  * Loop 2 ($n=1$): Phase goes from $2\pi/3$ to $4\pi/3$ (Sheet 2)[cite: 1, 3].
  * Loop 3 ($n=2$): Phase goes from $4\pi/3$ to $2\pi$ (Sheet 3)[cite: 1, 3].
  * Loop 4 ($n=3$): Returns back to Sheet 1[cite: 2]. So we need **3 Riemann sheets**[cite: 1].

---

### (ii) Winding Points

**Definition:** A branch point for $f(z) = z^\alpha$ where $\alpha$ is an **irrational number**[cite: 2].

* Each $2\pi$ loop around $z=0$ multiplies the phase by $e^{i 2\pi \alpha}$[cite: 2].
* Since $\alpha$ is irrational, $e^{i 2\pi \alpha n}$ is never equal to 1 for any integer $n$[cite: 2].
* You can loop infinitely many times and never return to the starting sheet, so it requires an **infinite number of Riemann sheets**[cite: 2].

---

### (iii) Logarithmic Branch Points

**Definition:** A branch point where going around $z_0$ keeps adding a constant value to the function, so it never returns to the original value[cite: 3].

* **General form:** $f(z) = \ln(z - z_0)$[cite: 3].
* Branch points for $\ln z$ are at $z = 0$ and $z = \infty$[cite: 3].
* Formula: $\ln z = \ln r + i\theta + 2\pi n i$[cite: 3].
* Every counter-clockwise loop around $z=0$ adds $+2\pi i$ to the function value and moves it to the next sheet[cite: 3].
* Note: $\ln(1) = 0$ is true **only on the principal sheet** ($n=0$)[cite: 3]. On sheet $n$, $\ln(1) = 2\pi n i$[cite: 3].

---
> > ✍️ **Added by:** Garvita , <03/10/2026>

## 2. Multi-Point Branch Cuts

When a function has two branch points, we can connect them with a line segment called a **branch cut** so that the function stays single-valued outside this cut[cite: 4, 6].

### Worked Example: $f(z) = \sqrt{z^2 - 1} = (z-1)^{1/2}(z+1)^{1/2}$

* **Branch points:** $z = 1$ and $z = -1$[cite: 4].
* **At infinity:** As $z \to \infty$, $f(z) \approx z$, which is single-valued[cite: 4, 6]. So $z = \infty$ is **not** a branch point[cite: 4].
* **Branch cut:** We can just draw a cut on the real axis between $[-1, 1]$[cite: 4, 5].

* ```markdown
## 2. Multi-Point Branch Cuts

When a function has two branch points, we can connect them with a line segment called a **branch cut** so that the function stays single-valued outside this cut[cite: 4, 6].

### Worked Example: $f(z) = \sqrt{z^2 - 1} = (z-1)^{1/2}(z+1)^{1/2}$

* **Branch points:** $z = 1$ and $z = -1$[cite: 4].
* **At infinity:** As $z \to \infty$, $f(z) \approx z$, which is single-valued[cite: 4, 6]. So $z = \infty$ is **not** a branch point[cite: 4].
* **Branch cut:** We can just draw a cut on the real axis between $[-1, 1]$[cite: 4, 5].


```

```
            Phase behavior of f(z) = (z-1)^(1/2) * (z+1)^(1/2)

                         Phase = π/2 + 0 = π/2
                        -----------------------

```

Phase = π/2 + π/2 = π                            Phase = 0 + 0 = 0
-----------------------●=========================●---------------------> Re(z)
(Left of -1)       -1       (Branch Cut)      +1      (Right of +1)
-----------------------
Phase = π + π/2 = 3π/2

```

| Region on Real Axis | Phase of $(z-1)^{1/2}$ | Phase of $(z+1)^{1/2}$ | Total Phase | Function Value $f(z)$ |
| :--- | :---: | :---: | :---: | :---: |
| **Right of $+1$** ($x > 1$) | $0$ | $0$ | $0$ | $+\sqrt{x^2 - 1}$[cite: 5] |
| **Between $-1$ and $+1$ (Top edge)** | $\pi/2$ | $0$ | $\pi/2$ | $+i\sqrt{1 - x^2}$[cite: 5] |
| **Between $-1$ and $+1$ (Bottom edge)** | $\pi/2$ | $\pi$ | $3\pi/2$ | $-i\sqrt{1 - x^2}$[cite: 5] |
| **Left of $-1$** ($x < -1$) | $\pi/2$ | $\pi/2$ | $\pi$ | $-\sqrt{x^2 - 1}$[cite: 5] |

* **Phase Jump across the cut:**
  * Crossing the segment $[-1, 1]$ gives a jump of $(+i\sqrt{1-x^2}) - (-i\sqrt{1-x^2}) = 2i\sqrt{1-x^2}$[cite: 5].
* **Outside the cut:**
  * For $x > 1$ and $x < -1$, the total phase is the same above and below the axis, which shows that the function is continuous outside $[-1, 1]$[cite: 5, 6].

---

### Important Things to Remember

* A branch cut must connect at least two branch points (which can include $z = \infty$)[cite: 3].
* The choice of branch cut line is up to us, but the branch points themselves never change.
* To check if infinity is a branch point, replace $z = 1/w$ and see if $w = 0$ is a branch point.

```
