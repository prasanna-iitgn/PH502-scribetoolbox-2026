✍️ **Added by:** Ayush Kumar, <03/10/2026>

# Types of Branch Points

## 1. Classification of Branch Points

A point $z_0$ is called a **branch point** of a complex function if, after making a complete circuit around $z_0$, the function does not return to its original value. In other words, analytic continuation of the function around $z_0$ takes us from one branch of the function to another.

The essential idea is that a branch point is a point around which the function becomes **multivalued**. The behavior after repeated circuits determines the type of branch point.

Branch points can be classified mainly into:

1. **Algebraic Branch Points**
2. **Winding Points**
3. **Logarithmic Branch Points**

---

### (i) Algebraic Branch Points

**Definition:**  

A point $z_0$ is called an **algebraic branch point** if, after going around $z_0$ a **finite number of times**, say $q$ times, the function returns to its original value.

Thus, if one circuit takes the function from one branch to another, repeated circuits eventually bring it back to the starting branch.

For a function of the form

$$
f(z)=(z-z_0)^{p/q},
$$

where $p$ and $q$ are integers and $p/q$ is in its lowest terms, $z_0$ is an algebraic branch point.

#### General form

Functions such as

$$
f(z)=z^{p/q}
$$

or

$$
f(z)=(z-z_0)^{p/q}
$$

have algebraic branch points.

Writing

$$
z-z_0=re^{i\theta},
$$

we obtain

$$
(z-z_0)^{p/q}
=
r^{p/q}e^{i(p/q)\theta}.
$$

When we make one complete counter-clockwise circuit around $z_0$,

$$
\theta\rightarrow\theta+2\pi.
$$

Therefore,

$$
(z-z_0)^{p/q}
\rightarrow
(z-z_0)^{p/q}e^{i2\pi p/q}.
$$

Thus, one complete circuit changes the phase by

$$
\boxed{\Delta\phi=\frac{2\pi p}{q}}.
$$

After $q$ complete circuits, the accumulated phase change is

$$
q\left(\frac{2\pi p}{q}\right)=2\pi p,
$$

and hence

$$
e^{i2\pi p}=1.
$$

Therefore, the function returns to its original branch after a finite number of circuits.

#### Riemann Surface

An algebraic branch point with denominator $q$ generally requires **$q$ Riemann sheets** when $p/q$ is in lowest terms.

Each complete $2\pi$ loop around the branch point moves the function from one sheet to the next:

$$
1\rightarrow2\rightarrow3\rightarrow\cdots\rightarrow q
\rightarrow1.
$$

Hence, after $q$ circuits, we return to the original sheet.

---

### Example: $f(z)=z^{1/3}$

Consider

$$
f(z)=z^{1/3}.
$$

Writing

$$
z=re^{i\theta},
$$

we have

$$
w=z^{1/3}
=
r^{1/3}e^{i\theta/3}.
$$

More generally,

$$
w
=
r^{1/3}
e^{i(\theta+2\pi n)/3},
\qquad n\in\mathbb Z.
$$

The possible values differ by a phase of

$$
\frac{2\pi}{3}.
$$

Therefore, each complete circuit around $z=0$ moves the function to the next branch.

#### Successive circuits around $z=0$

- **Initial branch:** $n=0$

$$
w=r^{1/3}e^{i\theta/3}.
$$

- **After the first loop:**

$$
\theta\rightarrow\theta+2\pi
$$

and the phase changes by

$$
\frac{2\pi}{3}.
$$

The function moves to the second sheet.

- **After the second loop:**

The accumulated phase change is

$$
\frac{4\pi}{3},
$$

and the function moves to the third sheet.

- **After the third loop:**

The accumulated phase change is

$$
2\pi,
$$

so

$$
e^{i2\pi}=1.
$$

The function therefore returns to its original value.

Thus,

$$
\boxed{\text{Number of Riemann sheets}=3}.
$$

The branch points of $z^{1/3}$ are

$$
\boxed{z=0\quad\text{and}\quad z=\infty}.
$$

---

### (ii) Winding Points

**Definition:**  

A **winding point** is a branch point for a function such as

$$
f(z)=z^\alpha,
$$

where $\alpha$ is an **irrational number**.

Writing

$$
z=re^{i\theta},
$$

we obtain

$$
z^\alpha=r^\alpha e^{i\alpha\theta}.
$$

After one complete counter-clockwise circuit around $z=0$,

$$
\theta\rightarrow\theta+2\pi.
$$

Therefore,

$$
z^\alpha
\rightarrow
z^\alpha e^{i2\pi\alpha}.
$$

After $n$ complete circuits, the phase factor becomes

$$
e^{i2\pi\alpha n}.
$$

For the function to return to its original value, we would require

$$
e^{i2\pi\alpha n}=1.
$$

This requires

$$
\alpha n=m,
$$

where $m$ is an integer.

However, when $\alpha$ is irrational, no non-zero integer $n$ can make $\alpha n$ an integer.

Therefore,

$$
e^{i2\pi\alpha n}\neq1
\qquad
\text{for every finite }n\neq0.
$$

Hence, the function never returns exactly to its starting branch after any finite number of circuits.

Therefore, an irrational power requires an **infinite number of Riemann sheets**.

#### Important result

For

$$
f(z)=z^\alpha,
$$

- $\alpha$ rational $\Rightarrow$ finite number of sheets $\Rightarrow$ algebraic branch point.
- $\alpha$ irrational $\Rightarrow$ infinitely many sheets $\Rightarrow$ winding point.

---

### (iii) Logarithmic Branch Points

**Definition:**  

A point $z_0$ is called a **logarithmic branch point** when analytic continuation around it causes the function to acquire an additional constant value after every circuit, and the function never returns to its original value after any finite number of circuits.

The standard example is

$$
f(z)=\ln(z-z_0).
$$

For simplicity, consider

$$
f(z)=\ln z.
$$

Writing

$$
z=re^{i\theta},
$$

the complex logarithm is

$$
\ln z
=
\ln r+i\theta+2\pi ni,
\qquad n\in\mathbb Z.
$$

Thus, $\ln z$ is a multivalued function.

After one complete counter-clockwise circuit around $z=0$,

$$
\theta\rightarrow\theta+2\pi.
$$

Hence,

$$
\ln z
\rightarrow
\ln z+2\pi i.
$$

After $n$ complete circuits,

$$
\boxed{\ln z\rightarrow\ln z+2\pi ni}.
$$

Since

$$
2\pi ni\neq0
$$

for any non-zero integer $n$, the function never returns to its original value after a finite number of circuits.

Thus, infinitely many Riemann sheets are required.

The logarithmic function has branch points at

$$
\boxed{z=0\quad\text{and}\quad z=\infty}.
$$

#### Example: $\ln(1)$

On the principal sheet,

$$
\ln(1)=0.
$$

However, on different sheets,

$$
\ln(1)=2\pi ni.
$$

Therefore,

$$
\boxed{\ln(1)=2\pi ni,\qquad n\in\mathbb Z}.
$$

The value $0$ corresponds only to the **principal branch** ($n=0$).

---

> > ✍️ **Added by:** Garvita Bajpai, <03/10/2026>

## 2. Multi-Point Branch Cuts

When a function possesses more than one branch point, a suitable **branch cut** can be introduced to prevent the function from becoming multivalued in the remaining region.

A branch cut is a curve drawn in the complex plane connecting branch points, or connecting a finite branch point to infinity, such that the function becomes **single-valued** in the remaining domain.

The exact choice of branch cut is not unique. Different choices can be made depending on convenience, but the locations of the branch points themselves are fixed by the function.

---

### Worked Example: $f(z)=\sqrt{z^2-1}$

Consider

$$
f(z)=\sqrt{z^2-1}.
$$

Factorizing,

$$
z^2-1=(z-1)(z+1),
$$

so that

$$
f(z)
=
\sqrt{(z-1)(z+1)}
=
(z-1)^{1/2}(z+1)^{1/2}.
$$

The square-root factors indicate that the points where the arguments vanish must be examined.

#### Branch points

For the first factor,

$$
(z-1)^{1/2},
$$

the branch point occurs at

$$
z=1.
$$

For the second factor,

$$
(z+1)^{1/2},
$$

the branch point occurs at

$$
z=-1.
$$

Therefore,

$$
\boxed{\text{Branch points: }z=1,\,-1}.
$$

---

### Checking the point at infinity

To determine whether $z=\infty$ is also a branch point, examine the behavior as

$$
z\rightarrow\infty.
$$

We have

$$
\sqrt{z^2-1}
=
z\sqrt{1-\frac{1}{z^2}}.
$$

For large $z$,

$$
\sqrt{1-\frac{1}{z^2}}
\approx1,
$$

so

$$
f(z)\approx z.
$$

Since $z$ is single-valued, there is no additional branching at infinity in this case.

Therefore,

$$
\boxed{z=\infty\text{ is not a branch point}.}
$$

---

### Choice of Branch Cut

Since there are two finite branch points, $z=-1$ and $z=1$, we can connect them by a line segment along the real axis.

Thus, a convenient branch cut is

$$
\boxed{[-1,1]}.
$$

The complex plane is then considered with the line segment $[-1,1]$ removed.

The function can be made single-valued in this cut plane.

---

### Behavior on the Real Axis

Let

$$
z=x,
$$

where $x$ is real.

We examine different regions of the real axis.

| Region on Real Axis | Phase of $(z-1)^{1/2}$ | Phase of $(z+1)^{1/2}$ | Total Phase | Function Value $f(z)$ |
| :--- | :---: | :---: | :---: | :---: |
| **Right of $+1$** ($x>1$) | $0$ | $0$ | $0$ | $+\sqrt{x^2-1}$ |
| **Between $-1$ and $+1$ (Top edge)** | $\pi/2$ | $0$ | $\pi/2$ | $+i\sqrt{1-x^2}$ |
| **Between $-1$ and $+1$ (Bottom edge)** | $\pi/2$ | $\pi$ | $3\pi/2$ | $-i\sqrt{1-x^2}$ |
| **Left of $-1$** ($x<-1$) | $\pi/2$ | $\pi/2$ | $\pi$ | $-\sqrt{x^2-1}$ |

---

### Region I: $x>1$

For $x>1$,

$$
x-1>0,\qquad x+1>0.
$$

Both factors are positive real numbers. Therefore, their phases are

$$
\arg(x-1)=0,
\qquad
\arg(x+1)=0.
$$

Hence the total phase is

$$
0.
$$

Therefore,

$$
f(x)=+\sqrt{x^2-1}.
$$

---

### Region II: $-1<x<1$ — Upper Edge

For points approaching the branch cut from above, the arguments of the factors must be considered carefully.

In this region,

$$
x-1<0,
$$

so the factor $(x-1)^{1/2}$ contributes a phase of

$$
\frac{\pi}{2}.
$$

The factor $x+1$ remains positive and therefore contributes zero phase.

Hence,

$$
\text{Total phase}
=
\frac{\pi}{2}.
$$

Therefore,

$$
f(x)
=
i\sqrt{1-x^2}.
$$

Thus,

$$
\boxed{f(x+i0)=+i\sqrt{1-x^2}}.
$$

---

### Region III: $-1<x<1$ — Lower Edge

When approaching the branch cut from below, the phase assignment changes.

The total phase becomes

$$
\frac{3\pi}{2}.
$$

Therefore,

$$
f(x)
=
e^{i3\pi/2}\sqrt{1-x^2}.
$$

Since

$$
e^{i3\pi/2}=-i,
$$

we obtain

$$
\boxed{f(x-i0)=-i\sqrt{1-x^2}}.
$$

Thus, the function has different limiting values on the two sides of the branch cut.

---

### Region IV: $x<-1$

For $x<-1$, both $x-1$ and $x+1$ are negative.

The corresponding phases combine to give a total phase of

$$
\pi.
$$

Therefore,

$$
f(x)
=
e^{i\pi}\sqrt{x^2-1}.
$$

Since

$$
e^{i\pi}=-1,
$$

we obtain

$$
\boxed{f(x)=-\sqrt{x^2-1}}.
$$

---

## Phase Jump Across the Branch Cut

For

$$
-1<x<1,
$$

the limiting values from the upper and lower sides are

$$
f(x+i0)=+i\sqrt{1-x^2},
$$

and

$$
f(x-i0)=-i\sqrt{1-x^2}.
$$

Therefore, the difference between the two values is

$$
f(x+i0)-f(x-i0)
=
i\sqrt{1-x^2}
-
\left(-i\sqrt{1-x^2}\right).
$$

Hence,

$$
\boxed{
f(x+i0)-f(x-i0)
=
2i\sqrt{1-x^2}
}.
$$

This difference is called the **jump across the branch cut**.

The function therefore has different boundary values on the two sides of the cut.

---

## Behavior Outside the Branch Cut

For

$$
x>1
$$

and

$$
x<-1,
$$

the function has the same limiting value when approached from above or below the real axis.

Therefore, there is no discontinuity across the real axis outside the interval $[-1,1]$.

The discontinuity is confined to the chosen branch cut.

---

# Important Things to Remember

1. A **branch point** is a point around which analytic continuation changes the branch of a multivalued function.

2. For an **algebraic branch point**, a finite number of circuits returns the function to its original branch.

3. For a **winding point**, infinitely many circuits are required because the exponent is irrational.

4. For a **logarithmic branch point**, every circuit adds a constant multiple of $2\pi i$ to the function.

5. A branch cut is introduced to make a multivalued function **single-valued** in the remaining domain.

6. A branch cut can be chosen conveniently; its exact path is not unique.

7. The branch points themselves are determined by the function and **do not change** merely because we choose a different branch cut.

8. A branch cut generally connects two branch points, or connects a finite branch point to

$$
z=\infty.
$$

9. To check whether infinity is a branch point, make the substitution

$$
\boxed{z=\frac{1}{w}}
$$

and examine the behavior near

$$
w=0.
$$

If $w=0$ is a branch point of the transformed function, then

$$
\boxed{z=\infty}
$$

is a branch point of the original function.

10. For

$$
f(z)=\sqrt{z^2-1},
$$

the finite branch points are

$$
\boxed{z=\pm1},
$$

and a convenient branch cut is

$$
\boxed{[-1,1]}.
$$
> > ✍️ **Added by:** Ayush Kumar, <03/10/2026>

# Types of Branch Points

## 1. Classification of Branch Points

A point $z_0$ is called a **branch point** if going around it in a small closed loop brings you to a different branch instead of returning to the original function value 

---

### (i) Algebraic Branch Points

**Definition:** A branch point where going around $z_0$ a **finite number of times** ($q$ times) brings the function back to where it started.

* **General form:** Functions like $f(z) = z^{p/q}$ or $(z-z_0)^{p/q}$.
* **Riemann Surface:** Made of $q$ sheets joined together. Every full $2\pi$ loop adds a phase of $2\pi (p/q)$ and moves you down from one sheet to the next ($1 \to 2 \to \dots \to q$), until the $q$-th loop takes you back to Sheet 1.

**Example:** $f(z) = z^{1/3}$
* Branch points are at $z = 0$ and $z = \infty$.
* Here $w = r^{1/3} e^{i(\theta + 2\pi n)/3}$. Going around $z=0$ once ($\Delta\theta = 2\pi$) changes the phase by $2\pi/3$.
  * Loop 1 ($n=0$): Phase goes from $0$ to $2\pi/3$ (Sheet 1).
  * Loop 2 ($n=1$): Phase goes from $2\pi/3$ to $4\pi/3$ (Sheet 2).
  * Loop 3 ($n=2$): Phase goes from $4\pi/3$ to $2\pi$ (Sheet 3).
  * Loop 4 ($n=3$): Returns back to Sheet 1. So we need **3 Riemann sheets**.

---

### (ii) Winding Points

**Definition:** A branch point for $f(z) = z^\alpha$ where $\alpha$ is an **irrational number**.

* Each $2\pi$ loop around $z=0$ multiplies the phase by $e^{i 2\pi \alpha}$.
* Since $\alpha$ is irrational, $e^{i 2\pi \alpha n}$ is never equal to 1 for any integer $n$.
* You can loop infinitely many times and never return to the starting sheet, so it requires an **infinite number of Riemann sheets**.

---

### (iii) Logarithmic Branch Points

**Definition:** A branch point where going around $z_0$ keeps adding a constant value to the function, so it never returns to the original value.

* **General form:** $f(z) = \ln(z - z_0)$.
* Branch points for $\ln z$ are at $z = 0$ and $z = \infty$.
* Formula: $\ln z = \ln r + i\theta + 2\pi n i$.
* Every counter-clockwise loop around $z=0$ adds $+2\pi i$ to the function value and moves it to the next sheet.
* Note: $\ln(1) = 0$ is true **only on the principal sheet** ($n=0$). On sheet $n$, $\ln(1) = 2\pi n i$.

---
> > ✍️ **Added by:** Garvita Bajpai, <03/10/2026>



## 2. Multi-Point Branch Cuts

When a function has two branch points, we can connect them with a line segment called a **branch cut** so that the function stays single-valued outside this cut.

### Worked Example: $f(z) = \sqrt{z^2 - 1} = (z-1)^{1/2}(z+1)^{1/2}$

* **Branch points:** $z = 1$ and $z = -1$.
* **At infinity:** As $z \to \infty$, $f(z) \approx z$, which is single-valued. So $z = \infty$ is **not** a branch point.
* **Branch cut:** We can just draw a cut on the real axis between $[-1, 1]$.

| Region on Real Axis | Phase of $(z-1)^{1/2}$ | Phase of $(z+1)^{1/2}$ | Total Phase | Function Value $f(z)$ |
| :--- | :---: | :---: | :---: | :---: |
| **Right of $+1$** ($x > 1$) | $0$ | $0$ | $0$ | $+\sqrt{x^2 - 1}$ |
| **Between $-1$ and $+1$ (Top edge)** | $\pi/2$ | $0$ | $\pi/2$ | $+i\sqrt{1 - x^2}$ |
| **Between $-1$ and $+1$ (Bottom edge)** | $\pi/2$ | $\pi$ | $3\pi/2$ | $-i\sqrt{1 - x^2}$ |
| **Left of $-1$** ($x < -1$) | $\pi/2$ | $\pi/2$ | $\pi$ | $-\sqrt{x^2 - 1}$ |

* **Phase Jump across the cut:**
  * Crossing the segment $[-1, 1]$ gives a jump of $(+i\sqrt{1-x^2}) - (-i\sqrt{1-x^2}) = 2i\sqrt{1-x^2}$.
* **Outside the cut:**
  * For $x > 1$ and $x < -1$, the total phase is the same above and below the axis, which shows that the function is continuous outside $[-1, 1]$.

---

### Important Things to Remember

* A branch cut must connect at least two branch points (which can include $z = \infty$).
* The choice of branch cut line is up to us, but the branch points themselves never change.
* To check if infinity is a branch point, replace $z = 1/w$ and see if $w = 0$ is a branch point.


# Contour Integrals in the Presence of Branch Points



Entries based on handwritten lecture notes, pp. 119–127 (section "Contour Integrals in the Presence of Branch Points"). Each entry follows the same format: statement, condensed derivation, one worked example.

**Conventions used throughout**
- $\mathrm{disc}\,f(x)=f(x+i0)-f(x-i0)$ (value just above minus value just below the cut).
- Contours are traversed counter-clockwise unless stated otherwise.
- $\arg$ is measured in $(0,2\pi)$ when the cut lies on the positive real axis.

---

**Added by:** [your name(s)], 2026-10-02

### 1. Closed contours on a Riemann surface

**Statement:**
Cauchy's theorem and the residue theorem need a contour that is **closed on the Riemann surface**. For a multivalued $f$, a loop that circles a branch point once ends on a different sheet, so it is *not* closed and $f$ does not return to its starting value. Two ways out:

1. **Avoid circling a single branch point:** choose contours that do not cross a cut (equivalently, that enclose no branch point, or enclose cut endpoints in pairs).
2. **Wind enough times:** encircle several branch points, or the same branch point repeatedly, until you return to the starting sheet.

**Derivation / justification (condensed):**
Near an algebraic branch point of order $q$, use the local uniformizing variable $w=(z-z_0)^{1/q}$. One loop in $z$ is only $1/q$ of a loop in $w$, so the path closes only after $q$ loops in $z$. On the $w$-surface, $f$ is single-valued and ordinary Cauchy theory applies.

**Worked example:**
Integrate $f(z)=z^{-1/2}$ around the circle $z=re^{i\theta}$ (principal sheet at $\theta=0$).

$$
\int_0^{\Theta} z^{-1/2}\,dz=\int_0^{\Theta} r^{-1/2}e^{-i\theta/2}\,ire^{i\theta}\,d\theta
= i\,r^{1/2}\int_0^{\Theta}e^{i\theta/2}\,d\theta
= 2r^{1/2}\big(e^{i\Theta/2}-1\big).
$$

- One loop, $\Theta=2\pi$: $2r^{1/2}(e^{i\pi}-1)=-4\sqrt r\neq0$. The path is not closed (it ends on sheet II), so Cauchy's theorem does not apply.
- Two loops, $\Theta=4\pi$: $2r^{1/2}(e^{2\pi i}-1)=0$. The path is closed on the Riemann surface and the integral vanishes, as Cauchy's theorem predicts. (In the variable $w=z^{1/2}$, $z^{-1/2}dz=2\,dw$, which is analytic.)

---

**Added by:** [your name(s)], 2026-10-02

### 2. Contour hugging a finite cut: $\int_0^1 x^{1-p}(1-x)^pQ(x)\,dx$

**Statement:**
Let $0<p<1$ and let $Q(z)$ be rational with no poles on $0\le z\le1$. Put $g(z)=z^{1-p}(z-1)^{p}$, with branch points $z=0,1$ and the cut taken along $[0,1]$. For a thin rectangle $\Gamma$ around the cut (counter-clockwise),


$$
\boxed{\ \int_0^1 x^{1-p}(1-x)^{p}\,Q(x)\,dx=-\frac{1}{2i\sin(\pi p)}\oint_\Gamma g(z)\,Q(z)\,dz\ }
$$

**Derivation / justification (condensed):**
Let $\theta=\arg z$ and $\phi=\arg(z-1)$, both in $(0,2\pi)$. Then $g=r^{1-p}\rho^{\,p}e^{i[(1-p)\theta+p\phi]}$ with $r=|z|$, $\rho=|z-1|$.

- On the cut, $0<x<1$: $\phi=\pi$ on both sides. Above, $\theta=0$, so $\arg g=p\pi$. Below, $\theta=2\pi$, so $\arg g=2\pi(1-p)+p\pi=2\pi-p\pi\equiv-p\pi$.
- Hence $g(x\pm i0)=x^{1-p}(1-x)^p\,e^{\pm ip\pi}$, and since $Q$ is continuous across $[0,1]$,

$$
\mathrm{disc}\,(gQ)=2i\sin(p\pi)\,x^{1-p}(1-x)^p\,Q(x).
$$

- Take $\Gamma=AB+BC+CD+DA$ with $AB$ just below the cut ($x:0\to1$), $CD$ just above it ($x:1\to0$). The short ends $BC$, $DA$ contribute $\to0$ as the width $\to0$, because the endpoint singularities $x^{1-p}$, $(1-x)^p$ are integrable. So

$$
\oint_\Gamma gQ\,dz=\int_0^1 f(x-i\epsilon)\,dx-\int_0^1 f(x+i\epsilon)\,dx=-\int_0^1\mathrm{disc}\,(gQ)\,dx=-2i\sin(p\pi)\int_0^1 x^{1-p}(1-x)^pQ(x)\,dx .
$$

Dividing by $-2i\sin p\pi$ gives the boxed formula. If $Q$ has poles off the real segment, deform $\Gamma$ outward to a large circle and pick up their residues.

**Worked example:**
Take $Q=1$ to evaluate $\displaystyle J(p)=\int_0^1x^{1-p}(1-x)^p\,dx$. With no poles of $Q$, $\Gamma$ can be blown up to a large circle. For $|z|>1$,

$$
g(z)=z\Big(1-\frac1z\Big)^{p}=z-p+\frac{p(p-1)}{2z}+O(z^{-2}),
$$

so only the $1/z$ term survives: $\oint g\,dz=2\pi i\cdot\dfrac{p(p-1)}2=i\pi p(p-1)$. Then

$$
J(p)=-\frac{i\pi p(p-1)}{2i\sin\pi p}=\frac{\pi\,p(1-p)}{2\sin\pi p}.
$$

Check: this equals the Beta function $B(2-p,1+p)=\dfrac{\Gamma(2-p)\Gamma(1+p)}{\Gamma(3)}$ via $\Gamma(p)\Gamma(1-p)=\pi/\sin\pi p$. At $p=\tfrac12$, $J=\pi/8$, the area of a semicircle of radius $\tfrac12$ ✓. Numerically: $p=\tfrac13$ gives $0.40307$ both from direct integration and from the formula.

---

**Added by:** [your name(s)], 2026-10-02

### 3. Keyhole contour: $\int_0^\infty \dfrac{x^{p-1}}{1+x}\,dx=\dfrac{\pi}{\sin\pi p}$

**Statement:**
For $0<p<1$,

$$
\boxed{\ I=\int_0^\infty\frac{x^{p-1}}{1+x}\,dx=\frac{\pi}{\sin(\pi p)}\ }
$$

Technique: when the integrand has branch points at $0$ and $\infty$, put the cut on $[0,\infty)$ (principal branch $0<\theta<2\pi$) and use a keyhole contour around it. The factor $e^{2\pi i p}$ picked up between the two lips turns the contour integral into $(1-e^{2\pi ip})\,I$.

**Derivation / justification (condensed):**
Let $f(z)=\dfrac{z^{p-1}}{1+z}$. The only pole off the cut is $z=-1=e^{i\pi}$. Contour $C$: $AB$ above the axis ($\theta=0$, $r:\epsilon\to R$), big circle $S$, $DE$ below the axis ($\theta=2\pi$, $r:R\to\epsilon$), small circle $\ell$ (clockwise).

- Residue: $\mathrm{Res}_{z=-1}f=(e^{i\pi})^{p-1}=e^{i\pi(p-1)}=-e^{i\pi p}$, so $\oint_Cf\,dz=-2\pi i\,e^{i\pi p}$.
- $AB$: $z=r$, so $\int_{AB}\to I$.
- $DE$: $z=re^{2\pi i}$, $z^{p-1}=r^{p-1}e^{2\pi i(p-1)}=r^{p-1}e^{2\pi ip}$, and the direction is reversed, so $\int_{DE}\to-e^{2\pi ip}I$.
- Large circle: $z=Re^{i\theta}$, $|f|\sim R^{p-1}$, so $\left|\int_S\right|\lesssim 2\pi R^{p}\to0$ as $R\to\infty$ since $p<1$.
- Small circle: $\left|\int_\ell\right|\lesssim2\pi\epsilon^{p}\to0$ as $\epsilon\to0$ since $p>0$.

Therefore

$$
(1-e^{2\pi ip})\,I=-2\pi i\,e^{i\pi p}\ \Longrightarrow\ I=\frac{2\pi i\,e^{i\pi p}}{e^{2\pi ip}-1}=\frac{2\pi i}{e^{i\pi p}-e^{-i\pi p}}=\frac{\pi}{\sin\pi p}.
$$

**Worked example:**
Evaluate $\displaystyle K=\int_0^\infty\frac{dx}{1+x^3}$. Put $u=x^3$, $dx=\tfrac13u^{-2/3}du$:

$$
K=\frac13\int_0^\infty\frac{u^{\frac13-1}}{1+u}\,du=\frac13\cdot\frac{\pi}{\sin(\pi/3)}=\frac13\cdot\frac{\pi}{\sqrt3/2}=\frac{2\pi}{3\sqrt3}\approx1.2092 .
$$

The numerical value of the integral is $1.20920$. In general $\int_0^\infty\frac{dx}{1+x^n}=\frac{\pi/n}{\sin(\pi/n)}$. Sanity check at $p=\tfrac12$: $x=t^2$ gives $2\int_0^\infty\frac{dt}{1+t^2}=\pi=\pi/\sin\frac\pi2$.

---

**Added by:** [your name(s)], 2026-10-02

### 4. Integral across a finite cut via a large circle: $\int_a^b\dfrac{dx}{\sqrt{(b-x)(x-a)}}=\pi$

**Statement:**
For $a<b$, with $f(z)=(z-a)^{-1/2}(z-b)^{-1/2}$ and the cut on the straight segment $[a,b]$,

$$
\boxed{\ I=\int_a^b\frac{dx}{\sqrt{(b-x)(x-a)}}=\pi\ }\qquad\text{independent of }a,b.
$$

Technique: a contour hugging the cut gives $2iI$; the same contour can be deformed outward to a large circle, where $f\approx1/z$ gives $2\pi i$.

**Derivation / justification (condensed):**
*Phases on the cut* ($a<x<b$). With $f=(z-a)^{-1/2}(z-b)^{-1/2}$, the first factor has phase $0$ on both sides. The second factor has $\arg(z-b)=\pi$ above and $-\pi$ below (equivalently $3\pi$), giving phase $-\pi/2$ above and $+\pi/2$ below (the notes write $-3\pi/2\equiv+\pi/2$). Hence

$$
f(x+i0)=-i|f(x)|,\qquad f(x-i0)=+i|f(x)|,\qquad |f(x)|=\frac1{\sqrt{(b-x)(x-a)}},
$$

$$
\mathrm{disc}\,f=-2i\,|f(x)|.
$$

*Contour around the cut.* Let $C$ be a thin rectangle $ABCD$ ($AB$ below, $CD$ above). The ends vanish as the widths $\to0$ because $|f|\sim r^{-1/2}$ is integrable, so

$$
\oint_Cf\,dz=-\int_a^b\mathrm{disc}\,f\,dx=2i\int_a^b|f(x)|\,dx=2i\,I .
$$

*Deform to a large circle.* $f$ is analytic outside the cut, so $C$ can be deformed into $|z|=R\to\infty$, where $f\approx1/z$:

$$
\oint_{C_\infty}f\,dz=\lim_{R\to\infty}\int_0^{2\pi}iRe^{i\theta}\,\frac{d\theta}{Re^{i\theta}}=2\pi i .
$$

Equating, $2iI=2\pi i$, so $I=\pi$.

**Worked example (numerical illustration):**
The result is independent of the interval. Direct numerical integration of $\int_a^b\frac{dx}{\sqrt{(b-x)(x-a)}}$ gives:

| $(a,b)$ | numerical value | $\pi$ |
|---|---|---|
| $(0,1)$ | $3.14159$ | $3.14159$ |
| $(-1,1)$ | $3.14159$ | $3.14159$ |
| $(2,5)$ | $3.14159$ | $3.14159$ |

Analytic check for $(0,1)$: $x=\sin^2t$ gives $\int_0^{\pi/2}2\,dt=\pi$; for $(-1,1)$ the integral is $[\arcsin x]_{-1}^{1}=\pi$.

---

**Added by:** [your name(s)], 2026-10-02

### 5. Residue at infinity: $\displaystyle\oint_Cf\,dz=-2\pi i\,\mathrm{Res}_{z=\infty}f$

**Statement:**
If $f$ is analytic outside a contour $C$ (all singularities and cuts lie inside $C$), then

$$
\boxed{\ \oint_Cf\,dz=-2\pi i\,\mathrm{Res}_{z=\infty}f\ },\qquad
\mathrm{Res}_{z=\infty}f=\text{coefficient of }\frac1w\text{ in the Laurent expansion at }w=0\text{ of }-\frac1{w^2}f\Big(\frac1w\Big).
$$

It gives a **second method** for Entry 4 with no need to track the contour at all.

**Derivation / justification (condensed):**
Put $z=1/w$, so $dz=-dw/w^2$. A large circle traversed counter-clockwise in $z$ becomes a small circle traversed *clockwise* in $w$. Reversing it to counter-clockwise gives a sign change:

$$
\oint_{|z|=R}f\,dz=-\oint_{|w|=1/R,\ \circlearrowleft}\Big[-\frac1{w^2}f\Big(\frac1w\Big)\Big]dw=-2\pi i\,\mathrm{Res}_{w=0}\Big[-\frac1{w^2}f\Big(\frac1w\Big)\Big].
$$

Check: $f=1/z$ has $\oint=2\pi i$, and $-\frac1{w^2}\cdot w=-\frac1w$ gives $\mathrm{Res}_\infty=-1$, so $-2\pi i(-1)=2\pi i$.

*Entry 4 again.* For $f=(z-a)^{-1/2}(z-b)^{-1/2}$,

$$
-\frac1{w^2}f\Big(\frac1w\Big)=-\frac1w\,(1-aw)^{-1/2}(1-bw)^{-1/2}=-\frac1w+O(w^0),
$$

so $\mathrm{Res}_\infty f=-1$ and $\oint_Cf\,dz=2\pi i$. With $\oint_C f\,dz=2iI$ from the cut, $I=\pi$.

**Worked example:**
Evaluate $\displaystyle J=\int_a^b\sqrt{(x-a)(b-x)}\,dx$ using $F(z)=\sqrt{(z-a)(z-b)}$, cut $[a,b]$, normalised by $F\sim z$ at $\infty$ (so $F>0$ for $x>b$).

*On the cut.* $F(x+i0)=+iM$ and $F(x-i0)=-iM$ with $M=\sqrt{(x-a)(b-x)}$. Going counter-clockwise (below the cut left to right, above it right to left),

$$
\oint_CF\,dz=\int_a^b(-iM)\,dx-\int_a^b(iM)\,dx=-2i\,J .
$$

*At infinity.* With $F(1/w)=\frac1w\sqrt{(1-aw)(1-bw)}$ and $\sqrt{1-(a+b)w+abw^2}=1-\frac{a+b}2w-\frac{(b-a)^2}8w^2+\cdots$,

$$
-\frac1{w^2}F\Big(\frac1w\Big)=-\frac1{w^3}+\frac{a+b}{2w^2}+\frac{(b-a)^2}{8w}+\cdots\ \Longrightarrow\ \mathrm{Res}_{\infty}F=\frac{(b-a)^2}{8}.
$$

So $\oint_CF\,dz=-2\pi i\,\dfrac{(b-a)^2}8=-\dfrac{i\pi(b-a)^2}4$. Equating with $-2iJ$:

$$
\boxed{\ \int_a^b\sqrt{(x-a)(b-x)}\,dx=\frac{\pi(b-a)^2}{8}\ }
$$

Check: this is the area of a half-disc of radius $\frac{b-a}2$, i.e. $\frac12\pi\big(\frac{b-a}2\big)^2$. Numerically, $(a,b)=(1,4)$ gives $3.53429$ from both the integral and the formula.

---

