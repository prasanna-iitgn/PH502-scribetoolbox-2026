> ✍️ **Added by:** Garvita Bajpai, 2026-10-03

# Types of Branch Points

## 1. Classification of Branch Points

A point $z_0$ in the complex plane is called a **branch point** if evaluating a multi-valued function along a small closed loop encircling $z_0$ prevents the function from returning to its original value. Instead, the function transitions onto a different **branch** (or Riemann sheet).

Branch points are topological features of multi-valued complex functions; unlike isolated singularities (such as poles or removable singularities), they cannot be removed by local algebraic transformations.

### (i) Algebraic Branch Points

**Definition:** A branch point where encircling $z_0$ a **finite number of times** ($q$ times) brings the multi-valued function back to its original value on the starting sheet.

* **General Form:** Functions like $f(z) = (z - z_0)^{p/q}$, where $p$ and $q$ are coprime integers ($q > 1$).
* **Branch Order & Phase Shift:** The integer $q$ defines the order or sheet-count. Encircling $z_0$ once alters the argument by $2\pi$, which shifts the overall phase of the function by $2\pi (p/q)$.
* **Riemann Surface Structure:** Consists of $q$ distinct sheets joined cross-wise along branch cuts:
  * **Loop 1 ($0 \to 2\pi$):** Phase shifts by $+2\pi(p/q) \to$ transitions from Sheet 1 to Sheet 2.
  * **Loop 2 ($2\pi \to 4\pi$):** Phase shifts by $+4\pi(p/q) \to$ transitions from Sheet 2 to Sheet 3.
  * $\dots$
  * **Loop $q$ ($2\pi(q-1) \to 2\pi q$):** Phase shifts by $+2\pi p$ (an integer multiple of $2\pi$), returning back to Sheet 1.

#### Worked Example: $f(z) = z^{1/3}$

* **Identifying Branch Points:**
  * **At $z = 0$:** Writing $z = r e^{i\theta}$, we have $f(z) = r^{1/3} e^{i(\theta + 2\pi n)/3}$. Encircling $z = 0$ once ($\Delta\theta = 2\pi$) changes the phase factor by $e^{i 2\pi/3} \neq 1$. Hence, $z = 0$ is a branch point.
  * **At $z = \infty$:** Substituting $z = 1/w$ gives $g(w) = w^{-1/3}$. Encircling $w = 0$ shifts the phase of $g(w)$ by $-2\pi/3 \neq 0 \pmod{2\pi}$. Thus, $w = 0 \implies z = \infty$ is also an algebraic branch point.

* **Tracking the 3 Riemann Sheets:**
  * **Loop 1 ($n = 0$):** Phase goes from $0$ to $2\pi/3$ (Sheet 1).
  * **Loop 2 ($n = 1$):** Phase goes from $2\pi/3$ to $4\pi/3$ (Sheet 2).
  * **Loop 3 ($n = 2$):** Phase goes from $4\pi/3$ to $2\pi$ (Sheet 3).
  * **Loop 4 ($n = 3$):** Phase shift equals $e^{i 6\pi / 3} = e^{i 2\pi} = 1$, which returns back to Sheet 1. So $f(z) = z^{1/3}$ requires **3 Riemann sheets**.

---

### (ii) Winding Points (Irrational Power Branch Points)

**Definition:** A branch point for $f(z) = (z - z_0)^\alpha$ where the exponent $\alpha$ is an **irrational real number** (or a complex number with a non-zero imaginary part).

* **Phase Factor:** Encircling $z_0$ once ($\Delta\theta = 2\pi$) multiplies the function value by $e^{i 2\pi \alpha}$.
* **Infinite Sheet Structure:** After $n$ full turns around $z_0$, the phase factor becomes $e^{i 2\pi n \alpha}$. Because $\alpha$ is irrational, $n\alpha$ can never be an integer for any non-zero integer $n$.
* Since $e^{i 2\pi n \alpha} \neq 1$ for all $n \in \mathbb{Z} \setminus \{0\}$, you can loop infinitely many times and never return to the initial starting sheet.
* **Riemann Surface:** Requires an **infinite number of Riemann sheets** spiraling endlessly in both directions (like a helical staircase).

---

### (iii) Logarithmic Branch Points

**Definition:** A branch point where going around $z_0$ continuously adds a constant non-zero value to the function during every full loop, so it never returns to its starting value.

* **General Form:** $f(z) = \ln(z - z_0)$.
* **Complex Logarithm Formula:** 
  $$\ln(z - z_0) = \ln r + i(\theta + 2\pi n), \quad n \in \mathbb{Z}$$
* **Behavior Around $z_0$:** Every counter-clockwise loop around $z_0$ increases $\theta$ by $2\pi$, adding $+2\pi i$ to the function value:
  $$f(z \cdot e^{2\pi i}) = \ln r + i(\theta + 2\pi) = f(z) + 2\pi i$$
* **Branch Points for $\ln z$:** Located at $z = 0$ and $z = \infty$ (verified via $z = 1/w \implies \ln(1/w) = -\ln w$).
* **Principal Sheet vs. Other Sheets:** $\ln(1) = 0$ is true **only on the principal sheet** ($n = 0$, where $\theta \in (-\pi, \pi]$). On sheet $n$, $\ln(1) = 2\pi n i$.

---
> > ✍️ **Added by:** Ayush Kumar, 2026-10-03 

## 2. Multi-Point Branch Cuts

When a function possesses multiple branch points, we construct **branch cuts**—lines or curves connecting the branch points—so that the function remains single-valued and analytic in the remaining region.

### Worked Example: $f(z) = \sqrt{z^2 - 1} = (z-1)^{1/2}(z+1)^{1/2}$

#### 1. Identify Branch Points
* **Finite Branch Points:** $z = 1$ and $z = -1$ are both algebraic branch points of order 2.
* **At Infinity ($z \to \infty$):** Substitute $z = 1/w$:
  $$f(1/w) = \sqrt{\frac{1}{w^2} - 1} = \frac{\sqrt{1 - w^2}}{w}$$
  As $w \to 0$, $\sqrt{1 - w^2}$ is analytic and single-valued around $w = 0$. The factor $1/w$ is just a simple pole, not a branch point. Therefore, $z = \infty$ is **not** a branch point.

#### 2. Choice of Branch Cut
Since $z = \infty$ is not a branch point, the two finite branch points $z = +1$ and $z = -1$ connect directly to each other. We draw a single compact branch cut along the real axis segment $[-1, 1]$.

#### 3. Polar Analysis Across Regions

Expressing factors in polar coordinates centered at their respective branch points:
$$z - 1 = r_1 e^{i\theta_1}, \quad z + 1 = r_2 e^{i\theta_2} \implies f(z) = \sqrt{r_1 r_2} e^{i(\theta_1 + \theta_2)/2}$$

| Region on Real Axis | Phase of $(z-1)^{1/2}$ ($\theta_1/2$) | Phase of $(z+1)^{1/2}$ ($\theta_2/2$) | Total Phase $(\theta_1 + \theta_2)/2$ | Function Value $f(z)$ |
| :--- | :---: | :---: | :---: | :---: |
| **Right of $+1$** ($x > 1$) | $0$ | $0$ | $0$ | $+\sqrt{x^2 - 1}$ |
| **Between $-1$ and $+1$ (Top edge)** | $\pi/2$ | $0$ | $\pi/2$ | $+i\sqrt{1 - x^2}$ |
| **Between $-1$ and $+1$ (Bottom edge)** | $3\pi/2$ | $0$ | $3\pi/2$ | $-i\sqrt{1 - x^2}$ |
| **Left of $-1$** ($x < -1$) | $\pi/2$ | $\pi/2$ | $\pi$ | $-\sqrt{x^2 - 1}$ |

#### 4. Discontinuity & Continuity Verification
* **Phase Jump across the Cut $[-1, 1]$:** 
  Crossing the segment $[-1, 1]$ gives a discontinuous jump of:
  $$f_{\text{top}}(x) - f_{\text{bottom}}(x) = (+i\sqrt{1-x^2}) - (-i\sqrt{1-x^2}) = 2i\sqrt{1-x^2}$$
* **Outside the Cut:** 
  For a closed path surrounding **both** branch points $z = 1$ and $z = -1$ simultaneously, $\Delta\theta_1 = 2\pi$ and $\Delta\theta_2 = 2\pi$. The net phase shift is:
  $$\Delta \text{Phase} = \frac{2\pi + 2\pi}{2} = 2\pi$$
  Since $e^{i 2\pi} = 1$, the function returns to its initial value, confirming that $f(z)$ is continuous and single-valued everywhere outside the segment $[-1, 1]$.

---

### Important Things to Remember

* **Conservation of Cuts:** A branch cut must connect at least two branch points (where infinity $z = \infty$ counts as a valid candidate).
* **Cut Flexibility:** The choice of branch cut path is arbitrary, but the endpoint branch points themselves are invariant properties of the function.
* **Testing Infinity:** To verify if infinity is a branch point, substitute $z = 1/w$ and test whether $w = 0$ is a branch point.
* **Multiple Branch Points:** If a closed contour encloses multiple branch points, sum the phase changes from all enclosed points. If the total phase shift is an integer multiple of $2\pi$, no branch cut needs to extend to infinity through that outer region.

> > ✍️ **Added by:** Mohammed Sahil, 2026-10-03

# Contour Integrals in the Presence of Branch Points


Entries based on handwritten lecture notes, pp. 119–127 (section "Contour Integrals in the Presence of Branch Points"). Each entry follows the same format: statement, condensed derivation, one worked example.

**Conventions used throughout**
- $\mathrm{disc}\,f(x)=f(x+i0)-f(x-i0)$ (value just above minus value just below the cut).
- Contours are traversed counter-clockwise unless stated otherwise.
- $\arg$ is measured in $(0,2\pi)$ when the cut lies on the positive real axis.

---

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

> > ✍️ **Added by:** Vishnuvardhan Balra, 2026-10-03

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

> > ✍️ **Added by:** Nishanth SS, 2026-10-03

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

