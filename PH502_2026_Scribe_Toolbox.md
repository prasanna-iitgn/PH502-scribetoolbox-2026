# PH 502 Course Toolbox

A shared, running reference for Mathematical Methods of Physics, built up over the semester by the class itself. Each week, the rotating Scribing/Toolbox team adds one entry under the relevant module below.

## How to use this file

- **Find your module's section** (Module 0–4, matching the course outline) and add your entry under it, at the end of the existing entries.
- **Use the entry template** below — copy it, fill it in, don't skip the sign-off line.
- **Sign every entry you write.** Just above the entry heading, add a line like:
  > ✍️ **Added by:** Jane Doe, Arjun Mehta — 2026-08-14
  This is how we track who contributed what; please don't remove someone else's sign-off.
- **Don't edit or delete another team's entry** without checking with them first (small fixes like typos are fine — just note it in your commit message).
- **Preview before you commit.** Click the "Preview" tab in GitHub's editor to check your formatting and math render correctly before saving.
- **One entry per result/technique.** Keep each entry self-contained — a reader should be able to find what they need without reading the whole file.
- If you're new to Markdown, see `markdown-cheatsheet.md` in this repo.

---

## Entry template

Copy this block for each new entry and fill it in:

```markdown
> ✍️ **Added by:** <your name(s)>, <date>

### <Name of the result / technique>

**Statement:**
<The key result, identity, or technique, stated precisely.>

**Derivation / justification (condensed):**
<The essential steps of the derivation or reasoning — enough to reconstruct
the logic, not a full lecture transcript.>

**Worked example:**
<One worked example applying it. On some weeks, this can instead be a short
numerical illustration — e.g. a quick computation showing the result in
action — in place of an analytic example.>

**Pitfalls / conditions to watch:**
<Any conditions, edge cases, or common mistakes flagged in lecture or
tutorial.>

---
```

---

## Module 0: Foundational Toolkit

*(self-study — add entries here if you find something from the mock quiz worth recording)*

---

## Module 1: Complex Analysis

> ✍️ **Added by:** (example entry — instructor), 2026-01-01

### Cauchy's Integral Theorem

**Statement:**
If $f(z)$ is analytic on and inside a simple closed contour $C$, then
$$\oint_C f(z)\, dz = 0.$$

**Derivation / justification (condensed):**
Follows from Green's theorem applied to the real and imaginary parts of
$f\,dz$, using the Cauchy–Riemann equations to show both resulting area
integrals vanish identically.

**Worked example:**
$\oint_C \frac{1}{z^2+1}\,dz$ over a contour enclosing neither $z = i$ nor
$z = -i$ evaluates to $0$, directly by the theorem — no residue calculation
needed.

**Pitfalls / conditions to watch:**
Fails if $f$ has a singularity *inside* $C$ (that's exactly the case the
residue theorem handles instead). Analyticity is required on and inside
$C$, not just along the contour itself.

---
> ✍️ **Added by:** lokesh sati, <2026-08-16>

### Complex Numbers in Polar (Exponential) Form

**Statement:** 
A complex number $z = x + iy$ in Cartesian coordinates can be uniquely expressed in polar/exponential form as:
$$z = r e^{i\theta}$$
where $r = |z| = \sqrt{x^2 + y^2}$ is the modulus and $\theta = \arg(z) = \tan^{-1}(y/x)$ is the argument.

**Derivation / justification (condensed):** 
Substituting geometric components $x = r \cos\theta$ and $y = r \sin\theta$ into $z = x + iy$ yields $z = r(\cos\theta + i\sin\theta)$. Applying Euler's formula $e^{i\theta} = \cos\theta + i\sin\theta$ gives $z = r e^{i\theta}$.

**Worked example:** 
For $z = 1 + i$: 
Modulus $r = \sqrt{1^2 + 1^2} = \sqrt{2}$, and argument $\theta = \tan^{-1}(1/1) = \frac{\pi}{4}$. 
Thus, the exponential form is $z = \sqrt{2} e^{i\pi/4}$.

**Pitfalls / conditions to watch:** 
The argument $\theta$ is multi-valued ($\theta + 2k\pi$). For a unique representation, the principal argument $\text{Arg}(z) \in (-\pi, \pi]$ must be specified. Additionally, polar form is undefined at the origin $z = 0$ since $\arg(0)$ is indeterminate.

---


### Euler's Formula & Basic Properties

**Statement:** 
For any real angle $\theta$, Euler's identity states:
$$e^{i\theta} = \cos\theta + i\sin\theta$$
Key properties include $|e^{i\theta}| = 1$, $|e^z| = e^x$, and $\arg(e^z) = y$ for $z = x + iy$.

**Derivation / justification (condensed):** 
Expanding $e^{i\theta}$ using Taylor series:
$$e^{i\theta} = \sum_{n=0}^{\infty} \frac{(i\theta)^n}{n!} = \left(1 - \frac{\theta^2}{2!} + \dots\right) + i\left(\theta - \frac{\theta^3}{3!} + \dots\right) = \cos\theta + i\sin\theta$$

**Worked example:** 
Evaluating $e^{i\pi}$: 
$$e^{i\pi} = \cos\pi + i\sin\pi = -1 + 0i = -1 \implies e^{i\pi} + 1 = 0$$

**Pitfalls / conditions to watch:** 
$|e^z|$ depends strictly on the real part $\text{Re}(z) = x$, while the imaginary part $\text{Im}(z) = y$ acts purely as a rotational phase angle. Do not mistake $|e^z|$ for $e^{|z|}$.

---


### De Moivre's Theorem

**Statement:** 
For any real number $\theta$ and integer $n \in \mathbb{Z}$:
$$(\cos\theta + i\sin\theta)^n = \cos(n\theta) + i\sin(n\theta)$$

**Derivation / justification (condensed):** 
Using Euler's exponential form, $(\cos\theta + i\sin\theta)^n = (e^{i\theta})^n = e^{in\theta}$. Expanding $e^{in\theta}$ back via Euler's formula yields $\cos(n\theta) + i\sin(n\theta)$.

**Worked example:** 
Expanding $(\cos\theta + i\sin\theta)^2$:
$$(\cos\theta + i\sin\theta)^2 = \cos(2\theta) + i\sin(2\theta)$$
Equating real and imaginary parts with $(\cos^2\theta - \sin^2\theta) + i(2\sin\theta\cos\theta)$ yields trigonometric identities $\cos(2\theta) = \cos^2\theta - \sin^2\theta$ and $\sin(2\theta) = 2\sin\theta\cos\theta$.

**Pitfalls / conditions to watch:** 
De Moivre's theorem in the form $(z)^n = z^n$ is straightforward for integer $n$. For non-integer powers, $z^n$ becomes multi-valued, and all branches must be considered using $e^{n \log z}$.

---


### Equations of Curves in Complex Plane

**Statement:** 
Geometric curves in $\mathbb{R}^2$ represented by $\Phi(x, y) = 0$ can be succinctly written using complex variable $z$ and conjugate $z^*$:
- **Circle:** $|z - z_0| = a$ (Center $z_0$, radius $a$)
- **Ray:** $\arg(z - z_0) = \theta_0$
- **Apollonius Circle:** $|z - z_1| = k |z - z_2|$ (where $k \neq 1$)

**Derivation / justification (condensed):** 
Distance between two points $z$ and $z_0$ in the complex plane is given by the modulus $|z - z_0| = \sqrt{(x-x_0)^2 + (y-y_0)^2}$. Setting this distance equal to radius $a$ yields the Cartesian circle equation $(x - x_0)^2 + (y - y_0)^2 = a^2$.

**Worked example:** 
Given equation $|z - 2i| = 3$:
Substituting $z = x + iy$ gives $|x + i(y-2)| = 3 \implies x^2 + (y-2)^2 = 9$, which represents a circle centered at $(0, 2)$ with radius $3$.

**Pitfalls / conditions to watch:** 
For Apollonius circle $|z - z_1| = k |z - z_2|$, if $k = 1$, the curve degenerates into a straight line (the perpendicular bisector of segment joining $z_1$ and $z_2$), not a circle.


### Powers and Roots of Complex Numbers

**Statement:** 
For any complex number $z = r e^{i\theta} \neq 0$ and any positive integer $n \in \mathbb{N}$:
* **Integer Powers:** $z^n = r^n e^{in\theta} = r^n \big(\cos(n\theta) + i\sin(n\theta)\big)$
* **$n$-th Roots:** The $n$ distinct $n$-th roots of $z$ are given by:
$$z^{1/n} = \sqrt[n]{r} \exp\left(i \frac{\theta + 2k\pi}{n}\right) = \sqrt[n]{r} \left[ \cos\left(\frac{\theta + 2k\pi}{n}\right) + i\sin\left(\frac{\theta + 2k\pi}{n}\right) \right]$$
where $k = 0, 1, 2, \dots, n-1$.

**Derivation / justification (condensed):** 
Expressing $z$ in polar form with its multi-valued angle gives $z = r e^{i(\theta + 2k\pi)}$. Applying fractional exponent laws:
$$z^{1/n} = \left( r e^{i(\theta + 2k\pi)} \right)^{1/n} = \sqrt[n]{r} e^{i \left(\frac{\theta + 2k\pi}{n}\right)}$$
Since $e^{i2\pi} = 1$, incrementing $k$ beyond $n-1$ shifts the argument by a multiple of $2\pi$, causing the root values to repeat periodically. Thus, there are exactly $n$ unique roots distributed symmetrically on a circle of radius $\sqrt[n]{r}$.

**Worked example:** 
Find all cube roots ($n = 3$) of $z = -8$:
1. Convert to polar form: $r = |-8| = 8$, $\theta = \arg(-8) = \pi \implies z = 8 e^{i\pi}$.
2. Apply the roots formula: $z^{1/3} = \sqrt[3]{8} e^{i\frac{\pi + 2k\pi}{3}} = 2 e^{i\frac{(2k+1)\pi}{3}}$ for $k = 0, 1, 2$.
3. Compute individual roots:
   * **$k = 0$:** $w_0 = 2 e^{i\pi/3} = 2\left(\cos\frac{\pi}{3} + i\sin\frac{\pi}{3}\right) = 1 + i\sqrt{3}$
   * **$k = 1$:** $w_1 = 2 e^{i\pi} = 2(\cos\pi + i\sin\pi) = -2$
   * **$k = 2$:** $w_2 = 2 e^{i5\pi/3} = 2\left(\cos\frac{5\pi}{3} + i\sin\frac{5\pi}{3}\right) = 1 - i\sqrt{3}$

**Pitfalls / conditions to watch:** 
* **Multi-valued nature:** Unlike real numbers, complex exponentiation for non-integer powers yields multiple values (e.g., a number always has $n$ distinct $n$-th roots). Always include the $2k\pi$ term before dividing by $n$.
* **Geometric interpretation:** The $n$-th roots of a complex number always form the vertices of a regular $n$-gon centered at the origin in the Argand plane, spaced equally at angular intervals of $\frac{2\pi}{n}$.


> ✍️ **Added by:** < souryadeep Lenka >, <16/08/2026>


1. Elementary Complex Functions
Suppose a function $w(z)$ can be expressed as:
$$w(z) = u(x,y) + iv(x,y)$$
where, $u(x,y) = \text{real part}$, $v(x,y) = \text{imaginary part}$
Complex conjugate:
$$\overline{w(z)} = u(x,y) - iv(x,y)$$

1. Exponential, Trigonometric and Hyperbolic Functions
All these three functions play a pivotal role in the study of complex analysis and variables. There are a lot of problems designed on the basis of these concepts. And the most intriguing part is that all of them can be expressed into other forms of the function (i.e., the exponential function can be expressed in terms of trigonometric functions etc.) or vice-versa. This has been stated below:

a) Principal Trigonometric Function and Exponential Functions
$$\sin z = \frac{e^{iz} - e^{-iz}}{2i} \qquad \text{and} \qquad \cos z = \frac{e^{iz} + e^{-iz}}{2}$$
(trigonometric to exponential)
$$e^{iz} = \sin z + i\cos z$$
(exponential to trigonometric)
NOTE: Remember, $z$ is a complex term, which has been considered as a generalised case.
Point of confusion: Many students consider that trigonometric identities don't hold within the complex plane. It can be verified that this assumption is incorrect. Trigonometric identities do hold within the complex plane.
Further, these formulae can be derived by using the power series expansion.

b) Relation Between Exponential Function and Hyperbolic Function
$$\sinh z = \frac{e^{z} - e^{-z}}{2} \qquad \text{and} \qquad \cosh z = \frac{e^{z} + e^{-z}}{2}$$
(hyperbolic function to exponential function)
Similarly, we can express other trigonometric and hyperbolic functions in terms of exponential functions.
c) Relation Between Hyperbolic and Trigonometric Function
$$i\sin z = \sinh iz \qquad \cos z = \cosh iz \qquad \text{[Hindley's theorem]}$$
$$\sin iz = i\sinh z \qquad \cos iz = \cosh z$$
For this you can refer to the book "Advanced Engineering Mathematics" by Erwin Kreyszig, and "Mathematical Methods for Physicist" by Arfken, Weber and Harris.


3. Multi-Valued Functions
A mathematical rule that links one input to two or more different outputs.
There are many such examples of multivalued functions in complex analysis which can be attempted and require a considerable amount of mathematical rigour. But, for the sake of simplicity, mainly three multivalued functions i.e., logarithmic function, inverse trigonometric/hyperbolic functions, and functions related to power series and roots have been discussed. They are represented as follows:
i) Logarithmic Function
$z \in \mathbb{C}$
$$\ln z = \ln r + i(\theta + 2\pi n) \qquad \text{where, } n \in \mathbb{Z}^+$$
(★) Problem Solving Strategy: Remember, whenever their question asks — where it's possible there's an application of logarithmic function — first convert the complex number into polar form, and then only apply the logarithmic function.
→ Most of these related formulae — be firm with the approach and concept. Don't directly just try to put in the formula and get the answer.


ii) Inverse Trigonometric Functions & Hyperbolic Functions
→ To determine the complex equations related to these inverse trigonometric functions is a tricky part.
(★) Point to Remember: Most students make mistakes while solving problems related to the inverse trigonometric formulae, in that they try to put in values and get the correct answer — but that's not always applicable. Rather, it's better if we focus on the derivation of how these formulae have been derived from scratch!! Go through the approach.
Some principal inverse trigonometric functions that are required to be known before going for the exams:
$$1.\quad \sin^{-1}(z) = -i\log_e\left[iz + \sqrt{1-z^2}\right]$$
$$2.\quad \cos^{-1}(z) = -i\log_e\left[z \pm \sqrt{z^2-1}\right]$$
$$3.\quad \tan^{-1}(z) = \frac{1}{2i}\log_e\left[\frac{1+iz}{1-iz}\right] = -\frac{i}{2}\log_e\left[\frac{1+iz}{1-iz}\right]$$


> ✍️ **Added by:** < shravani >, <16/08/2026>


# Basis of Analysis / Calculus

### i) Neighborhood of $z_0$
A neighborhood of a point $z_0$ in the complex plane is the set of all points $z$ such that $|z - z_0| < \varepsilon$, where $\varepsilon$ is a small positive real number.

Thus a neighborhood of a point $z_0$ is the set of all points lying inside a circle $C$ (but not on the circle) of radius $\varepsilon$ with centre at $z_0$.

---

### ii) Open set
A subset $S$ of a complex plane is said to be open set if it contains only the inner points (i.e. it contains none of its boundary points).

> **for ex -** $|z| < 1$ is an open set

A set $S$ is called a **closed set**.

---

### iii) Connected set
An open set is said to be connected if any two of its points can be joined by a finite number of line segments all of whose points belong to the set.

> **for ex :-**
> $|z| < 2$ is connected set.

---

# Limit of a Function

A function $w = f(z)$ is said to tend to limit $l$ as $z$ tends to $z_0$ if every $\varepsilon > 0$, there exists a $\delta > 0$ such that
$$|f(z) - l| < \varepsilon \quad \text{for all } |z - z_0| < \delta$$

The above definition implies that the value of $f(z)$ can be made arbitrarily close to $l$ for all $z$ in the neighbourhood of $z_0$ except perhaps at $z = z_0$.

We write this as $\lim_{z \to z_0} f(z) = l$

$$\lim_{z \to z_0} f(z) = a_0, \quad \lim_{z \to z_0} g(z) = b_0 \quad \& \quad \text{further}$$

$$f(z) = u(x, y) + i v(x, y), \quad z_0 = x_0 + i y_0 \quad \& \quad a_0 = u_0 + i v_0$$

- **a)** $\lim_{z \to z_0} f(z) = a_0 \implies \lim_{(x, y) \to (x_0, y_0)} u(x, y) = u_0 \quad \& \quad \lim_{(x, y) \to (x_0, y_0)} v(x, y) = v_0$
- **b)** $\lim_{z \to z_0} [f(z) + g(z)] = a_0 \pm b_0$
- **c)** $\lim_{z \to z_0} [f(z) \cdot g(z)] = a_0 \cdot b_0$
- **d)** $\lim_{z \to z_0} \left[ \frac{f(z)}{g(z)} \right] = \frac{a_0}{b_0} \quad \text{provided that } b_0 \neq 0$

---

# Continuity

A function $f(z)$ of complex variable $z$ is said to be continuous at a point $z_0$, if:
- **i)** $f(z)$ is defined at $z = z_0$
- **ii)** $\lim_{z \to z_0} f(z)$ exists.
- **iii)** $\lim_{z \to z_0} f(z) = f(z_0)$

The sum, difference and product of continuous functions of a complex variable are continuous. Also the quotient of two continuous functions is continuous at points where the denominator function does not vanish.

A function $f(z)$ is said to be continuous in a domain $D$ if it is continuous at every point of $D$.

It can be easily seen that the functions:
$$f(z) = z, \quad f(z) = \text{Re}(z), \quad f(z) = \text{Im}(z), \quad f(z) = \bar{z}$$
are continuous in the entire complex plane.

The polynomial function:
$$f(z) = c_0 z^n + c_1 z^{n-1} + c_2 z^{n-2} + \dots + c_n$$
where $c_0, c_1, c_2, \dots, c_n$ are complex constants, is continuous in the entire complex plane.

---

# Differentiation

A function $f(z)$ is said to be differentiable at a point $z = z_0$ if
$$\lim_{z \to z_0} \frac{f(z) - f(z_0)}{z - z_0} \quad \text{exists}$$

This limit is then called the derivative of $f(z)$ at $z = z_0$ and is denoted by $f'(z_0)$.

Putting $z = z_0 + \delta z$, we have $\delta z = z - z_0$.
Thus we may also write:
$$f'(z_0) = \lim_{\delta z \to 0} \frac{f(z_0 + \delta z) - f(z_0)}{\delta z}$$

---

### Example :- 
Find the derivative of $f(z) = z^3$ at $z = z_0$

**Sol$^{n}$ :-** 
Consider,
$$\begin{aligned}
\lim_{\delta z \to 0} \frac{f(z_0 + \delta z) - f(z_0)}{\delta z} &= \lim_{\delta z \to 0} \frac{(z_0 + \delta z)^3 - (z_0)^3}{\delta z} \\
&= \lim_{\delta z \to 0} \frac{3 z_0^2 \delta z + 3 z_0 (\delta z)^2 + (\delta z)^3}{\delta z} \\
&= \lim_{\delta z \to 0} \left( 3 z_0^2 + 3 z_0 \delta z + (\delta z)^2 \right) = 3 z_0^2
\end{aligned}$$

---

# Cauchy Riemann Condition

### Necessary Condition :-
A necessary condition that $f(z) = u(x, y) + i v(x, y)$ be analytic in a domain $D$ is that the first order derivative of $u$ & $v$ w.r.t $x$ and $y$ must exist and must satisfy the equations.

$f(z) = u(x, y) + i v(x, y)$ to be differentiable at point $z_0 = x_0 + i y_0$ if $f'(z_0)$ exists,

The C-R eq$^n$:
$$\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \quad \& \quad \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}$$

Or in subscript notation $u_x = v_y$ and $u_y = -v_x$.

If $f(z) = u(x, y) + i v(x, y)$ is differentiable at $z_0 = x_0 + i y_0$, then:

* The first order partial derivatives $u_x, u_y, v_x, v_y$ exist at $(x_0, y_0)$.
* Then satisfy:
  $$\begin{aligned}
  u_x &= v_y \\
  u_y &= -v_x
  \end{aligned}$$
  at $(x_0, y_0)$.

The derivative is defined as:
$$f'(z_0) = \lim_{\Delta z \to 0} \frac{f(z_0 + \Delta z) - f(z_0)}{\Delta z}$$

Since $f'(z_0)$ exists, the limit must yield the same result regardless of the path along which $\Delta z = \Delta x + i \Delta y$.

* $\Delta y = 0, \Delta z = \Delta x$
  $$f'(z_0) = \lim_{\Delta x \to 0} \frac{u(x_0 + \Delta x, y_0) + i v(x_0 + \Delta x, y_0) - [u(x_0, y_0) + i v(x_0, y_0)]}{\Delta x}$$

* $\Delta x = 0, \Delta z = i \Delta y$
  $$f'(z_0) = \lim_{\Delta y \to 0} \frac{u(x_0, y_0 + \Delta y) + i v(x_0, y_0 + \Delta y) - [u(x_0, y_0) + i v(x_0, y_0)]}{i \Delta y}$$

Eq$^n$ the real & imaginary parts from path 1 and path 2 gives:
$$\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \quad \text{and} \quad \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}$$

---

* The eq$^n$ $\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y}$ and $\frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}$ are called **Cauchy-Riemann equations**.

$\Rightarrow$ Thus the Cauchy-Riemann eq$^n$ (CR eq$^n$) are necessary conditions for a function $f(z) = u(x, y) + i v(x, y)$ to be analytic at a point. However these are not sufficient conditions for $f(z)$ to be analytic. Thus these can be used to locate points at which $f(z)$ is not analytic.

---

### Key Points:

- **i)** $f(z) \text{ analytic} \implies \frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \quad \text{and} \quad \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}$
- **ii)** $\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \quad \text{and} \quad \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}$ need not imply $f(z)$ analytic.
- **iii)** CR eq$^n$ are not satisfied at a point $z_0 \implies f'(z_0)$ does not exist & hence not analytic at $z_0$.
- **CR eq$^n$ not sufficient condition for $f(z)$ to be analytic.**



> ✍️ **Added by:** < Dhani Sangwan >, <16/08/2026>

# Complex Differentiability & the Cauchy-Riemann Equations

## Definition of derivative

For a single-valued complex function $f(z) = u(x,y) + iv(x,y)$, the derivative at $z_0$ is defined as:

$$\left.\frac{df}{dz}\right|_{z=z_0} = \lim_{\delta z \to 0} \frac{f(z_0 + \delta z) - f(z_0)}{\delta z}$$

where, $\delta z = \delta x + i \delta y$. For the derivative to exist, this limit must be independent of the path / dirⁿ along which $\delta z \to 0$.

## Cauchy-Riemann conⁿ

* **Cartesian form:**

$$\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \quad \text{and} \quad \frac{\partial v}{\partial x} = -\frac{\partial u}{\partial y}$$

* **Polar form:**

$$\frac{\partial u}{\partial r} = \frac{1}{r} \frac{\partial v}{\partial \theta} \quad \text{and} \quad \frac{\partial v}{\partial r} = -\frac{1}{r} \frac{\partial u}{\partial \theta}$$

* **Wirtinger Derivative / Compact form:**

$$\frac{\partial f}{\partial z^*} = 0$$

> **Key Insight:** If a funⁿ explicitly depends on $z^* = x - iy$, $\text{Re}(z)$, $\text{Im}(z)$, $|z|$ or $\text{Arg}(z)$, it cannot satisfy C-R universally and is non-analytic.

---

### Derivative Expressions

If $f(z)$ is differentiable:

$$\frac{df}{dz} = \frac{\partial u}{\partial x} + i \frac{\partial v}{\partial x} = \frac{\partial v}{\partial y} - i \frac{\partial u}{\partial y} = \frac{\partial u}{\partial x} - i \frac{\partial u}{\partial y}$$

## Necessary v/s Sufficient conditions

* **Necessary conⁿ:** If $f(z) = u + iv$ is differentiable at $z_0$, then the CR equations must hold at $z_0$.
* **Sufficient conⁿ:** For $f(z)$ to be differentiable at $z_0$, the CR eqⁿ must hold at $z_0$ and the first partial derivatives $\left(\frac{\partial u}{\partial x}, \frac{\partial u}{\partial y}, \frac{\partial v}{\partial x}, \frac{\partial v}{\partial y}\right)$ must be continuous at $z_0$.
* **Cautionary Note:** CR equations holding at a point without continuous partial derivatives is not sufficient for differentiability (e.g. path dependent limits).

---

# 2. Analyticity & Entire Functions

## Definitions & Properties

* A funⁿ $f(z)$ is analytic at a point $z_0$ if it is differentiable at $z_0$ and in a neighbourhood around $z_0$.
* Analyticity is a regional property not an isolated point property.
* **Entire funⁿ:** A funⁿ that is analytic everywhere in the finite complex plane ($\mathbb{C}$).
* **Singularity:** A point $z_0$ where $f(z)$ fails to be analytic.

## Fundamental theorems

* **Liouville's theorem:** Every bounded entire funⁿ must be constant.
  *(Implication: Any non-constant entire funⁿ must blow up / have a singularity at $z = \infty$.)*
* **Infinite Differentiability:** If $f(z)$ is analytic in a domain, it possesses derivatives of all orders, and all higher derivatives are also analytic.
* **Taylor series Representation:** Every analytic funⁿ can be represented as a power series locally.

---

# Harmonic Functions and Geometric Properties

## Laplace eqⁿ & Harmonic conjugates

If $f(z) = u(x,y) + iv(x,y)$ is analytic in a domain $D$:

1. Both $u$ & $v$ satisfy the 2D Laplace Equation:

$$\nabla^2 u = \frac{\partial^2 u}{\partial x^2} + \frac{\partial^2 u}{\partial y^2} = 0 \qquad \nabla^2 v = \frac{\partial^2 v}{\partial x^2} + \frac{\partial^2 v}{\partial y^2} = 0$$

* Thus, $u(x,y)$ and $v(x,y)$ are Harmonic functions, $v$ is called the harmonic conjugate of $u$.

2. **Mean Value Property:** The value of a harmonic funⁿ at any point equals the average of its values along any circle centered at that point.

3. **Max-Modulus Principle:** A non-constant analytic funⁿ cannot attain an absolute max for $|f(z)|$ in the interior of its domain (max occurs on the boundary).

---

## Orthogonal trajectories

From CR conⁿ, the gradients satisfy:

$$\nabla u \cdot \nabla v = \frac{\partial u}{\partial x} \frac{\partial v}{\partial x} + \frac{\partial u}{\partial y} \frac{\partial v}{\partial y} = 0$$

* **Geometric interpretation:** The curves of constant real part $u(x,y) = C_1$ and constant imaginary part $v(x,y) = C_2$ are mutually orthogonal at all points where $f'(z) \neq 0$.

---

## Quick Classification & Comparison

| $\text{fun}^n f(z)$ | Analytic / Non-Analytic | Reason |
| :--- | :--- | :--- |
| $z^n, e^z, \sin z, \cosh z$ | Entire (Analytic everywhere) | Satisfies CR everywhere with conⁿ P.D. |
| $\frac{P(z)}{Q(z)}$ | Analytic except at roots of $Q(z)$ | Differ. everywhere except $Q(z) = 0$. |
| $z^* = x - iy$ | Non-Analytic everywhere | $\frac{\partial u}{\partial x} = 1 \neq -1 = \frac{\partial v}{\partial y}$; explicit dependence on $z^*$. |
| $|z|^2 = x^2 + y^2$ | Differentiable only at $z=0$ (Non-analytic) | CR satisfied only at $(0,0)$. No neighborhood of analyticity. |
| $\text{Re}(z) = x$, $\text{Im}(z) = y$ | Non-analytic everywhere | Non-zero imaginary part missing; fails CR conⁿ. |
| $\ln z$ | Analytic on $\mathbb{C} \setminus (-\infty, 0]$ | Requires a branch cut to remain single valued. |


> ✍️ **Added by:** < Abhi balai >, <16/08/2026>


## Analytic Functions

* A function $f(z)$ call analytic function:
  * Continuous and satisfied Cauchy-Riemann equation
  * Called analytic function.
* Analyticity is **not isolated**.
* Analyticity similar to power series.
* Analytic functions are differentiable to all orders.

---

### Properties of Analytic Functions

* $f, g$ analytic $\implies f+g, f-g, fg$ are analytic at all points.
* $f/g$ is also analytic at all points.

#### For Division Method
* $f/g$ is analytic everywhere except when $g = 0$.

#### Composition of Functions
* If $g(z)$ is analytic at point $z$, $f(z)$ is analytic at $w = g(z)$
* Then $F(z) = f(g(z))$ is analytic at $z$.

#### Singularity in Analytic Function
* $f(g(z))$ that point are singular where either $f(z)$ is analytic or $g(z)$ is analytic.

---

### Sufficient Condition for Analytic

Satisfied C-R equations:

$$\left[ \frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \right] \quad \text{and} \quad \left[ \frac{\partial v}{\partial x} = -\frac{\partial u}{\partial y} \right]$$

---

## Example / Problem

**Ex:** $f(z) = z^2$. Find this function is analytic function.

**Solution:**

We know that: 

$$z = x + iy$$

$$f(z) = (x + iy)^2$$

$$f(z) = x^2 - y^2 + 2ixy$$

So,

$$\text{Real part } = u(x, y) = x^2 - y^2$$

$$\text{Img } = v(x, y) = 2xy$$

We know that for analytic function $f(z)$ is satisfied C-R equation.

**C-R Equation:**

$$\boxed{\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y}} \quad \text{and} \quad \boxed{\frac{\partial v}{\partial x} = -\frac{\partial u}{\partial y}}$$

Differentiating:

$$\frac{\partial u}{\partial x} = 2x \quad ; \quad \frac{\partial v}{\partial y} = 2x$$

$$\frac{\partial v}{\partial x} = 2y \quad ; \quad \frac{\partial u}{\partial y} = -2y$$

So,

$$\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \quad \text{and} \quad \frac{\partial v}{\partial x} = -\frac{\partial u}{\partial y}$$

This condition satisfy.

So, **$f(z) = z^2$ is analytic function.**


---

## Module 2: Integral Transforms

---

## Module 3: Differential Equations of Physics

---

## Module 4: Linear Algebra

---
