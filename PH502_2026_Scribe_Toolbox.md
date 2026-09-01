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



> ✍️ **Added by:** souryadeep Lenka , <16/08/2026>



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



> ✍️ **Added by:** shravani , <16/08/2026>



# Basis of Analysis / calculus

### i) Neighborhood of $z_0$
A neighborhood of a point $z_0$ in the complex plane is the set of all points $z$ such that $|z - z_0| < \epsilon$, where $\epsilon$ is a small positive real number.

Thus a neighborhood of a point $z_0$ is the set of all points lying inside a circle $C$ (but not on the circle) of radius $\epsilon$ with centre at $z_0$.

---

### ii) Open set
A subset $S$ of a complex plane is said to be open set if it contains only the inner points (i.e. it contains none of its boundary points).

For ex:- $|z| < 1$ is an open set

A set $S$ is called a closed set.

---

### iii) Connected set
An open set is said to be connected if any two of its points can be joined by a finite number of line segments all of whose points belong to the set.

For ex:- The $|z| < 2$ is connected set.

---

# Limit of a Function

A function $w = f(z)$ is said to tend to limit $l$ as $z$ tends to $z_0$ if every $\epsilon > 0$, there exists a $\delta > 0$ such that:

$$|f(z) - l| < \epsilon \quad \text{for all } |z - z_0| < \delta$$

The above definition implies that the value of $f(z)$ can be made arbitrary close to $l$ for all $z$ in the neighbourhood of $z_0$ except perhaps at $z = z_0$.

We write this as:

$$\lim_{z \to z_0} f(z) = l$$

$$\lim_{z \to z_0} f(z) = a_0, \qquad \lim_{z \to z_0} g(z) = b_0 \quad \text{and further}$$

$$f(z) = u(x, y) + i v(x, y), \qquad z_0 = x_0 + i y_0 \quad \text{and} \quad a_0 = u_0 + i v_0$$

* **a)** $\lim_{z \to z_0} f(z) = a_0 \implies \lim_{(x, y) \to (x_0, y_0)} u(x, y) = u_0$ and $\lim_{(x, y) \to (x_0, y_0)} v(x, y) = v_0$
* **b)** $\lim_{z \to z_0} [f(z) + g(z)] = a_0 \pm b_0$
* **c)** $\lim_{z \to z_0} [f(z) \cdot g(z)] = a_0 \cdot b_0$
* **d)** $\lim_{z \to z_0} \left[ \frac{f(z)}{g(z)} \right] = \frac{a_0}{b_0} \quad \text{provided that } b_0 \neq 0$

---

# Continuity

A function $f(z)$ of complex variable $z$ is said to be continuous at a point $z_0$, if:

1. $f(z)$ is defined at $z = z_0$
2. $\lim_{z \to z_0} f(z)$ exists.
3. $\lim_{z \to z_0} f(z) = f(z_0)$

The sum, difference and product of continuous functions of a complex variable are continuous. Also the quotient of two continuous functions is continuous at points where the denominator function does not vanish.

A function $f(z)$ is said to be continuous in a domain $D$ if it is continuous at every point of $D$.

It can be easily seen that the functions:

$$f(z) = z, \quad f(z) = \text{Re}(z), \quad f(z) = \text{Im}(z), \quad f(z) = |\bar{z}|$$

are continuous in the entire complex plane.

The polynomial plane:

$$f(z) = C_0 z^n + C_1 z^{n-1} + C_2 z^{n-2} \dots + C_n$$

where $C_0, C_1, C_2 \dots C_n$ are complex constant, is continuous in the entire complex plane.

---

# Differentiation

A function $f(z)$ is said to be differentiable at a point $z = z_0$ if:

$$\lim_{z \to z_0} \frac{f(z) - f(z_0)}{z - z_0} \quad \text{exists}$$

This limit is then called the derivative of $f(z)$ at $z = z_0$ and is denoted by $f'(z_0)$.

Putting $z = z_0 + \delta z$, we have $\delta z = z - z_0$. Thus we may also write:

$$f'(z_0) = \lim_{\delta z \to 0} \frac{f(z_0 + \delta z) - f(z_0)}{\delta z}$$

---

### Example:-
Find the derivative of $f(z) = z^3$ at $z = z_0$.

**Solⁿ:-** Consider,

$$\begin{aligned}
\lim_{\delta z \to 0} \frac{f(z_0 + \delta z) - f(z_0)}{\delta z} &= \lim_{\delta z \to 0} \frac{(z_0 + \delta z)^3 - (z_0)^3}{\delta z} \\
&= \lim_{\delta z \to 0} \frac{3 z_0^2 \delta z + 3 z_0 (\delta z)^2 + (\delta z)^3}{\delta z} \\
&= \lim_{\delta z \to 0} \left( 3 z_0^2 + 3 z_0 \delta z + (\delta z)^2 \right) = 3 z_0^2
\end{aligned}$$

---

# Cauchy Riemann Condition

### Necessary condition:-
A necessary condition that $f(z) = u(x, y) + i v(x, y)$ be analytic in a domain $D$ is that of the first order derivative of $u$ and $v$ w.r.t $x$ and $y$ must exist and must satisfy the equations.

$f(z) = u(x, y) + i v(x, y)$ to be differentiable at point $z_0 = x_0 + i y_0$ if $f'(z_0)$ exists,

The CR eqⁿ:

$$\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \quad \text{and} \quad \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}$$

Or in subscript notation: $u_x = v_y$ and $u_y = -v_x$

If $f(z) = u(x, y) + i v(x, y)$ is differentiable at $z_0 = x_0 + i y_0$ then,

* The first order partial derivatives $u_x, u_y, v_x, v_y$ exist at $(x_0, y_0)$.
* Then satisfy $u_x = v_y$ and $u_y = -v_x$ at $(x_0, y_0)$.

The derivative is defined as:

$$f'(z_0) = \lim_{\Delta z \to 0} \frac{f(z_0 + \Delta z) - f(z_0)}{\Delta z}$$

Since $f'(z_0)$ exists, the limit must yield the same result regardless of the path along which $\Delta z = \Delta x + i \Delta y$.

* **Path 1 ($\Delta y = 0, \Delta z = \Delta x$):**

$$f'(z_0) = \lim_{\Delta x \to 0} \frac{u(x_0 + \Delta x, y_0) + i v(x_0 + \Delta x, y_0) - [u(x_0, y_0) + i v(x_0, y_0)]}{\Delta x}$$

* **Path 2 ($\Delta x = 0, \Delta z = i \Delta y$):**

$$f'(z_0) = \lim_{\Delta y \to 0} \frac{u(x_0, y_0 + \Delta y) + i v(x_0, y_0 + \Delta y) - [u(x_0, y_0) + i v(x_0, y_0)]}{i \Delta y}$$

Eqⁿ the real and imaginary parts from path 1 and path 2 gives:

$$\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \quad \text{and} \quad \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}$$

---

* The eqⁿ $\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y}$ and $\frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}$ are called **Cauchy-Riemann equations**.

$\Rightarrow$ Thus the Cauchy-Riemann eqⁿ (CR eqⁿ) are necessary conditions for a function $f(z) = u(x, y) + i v(x, y)$ to be analytic at a point. However these are not sufficient conditions for $f(z)$ to be analytic. Thus these can be used to locate points at which $f(z)$ is not analytic.

---

1. $f(z) \text{ analytic} \Rightarrow \frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \text{ and } \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}$
2. $\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \text{ and } \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x} \text{ need not imply } f(z) \text{ analytic}$
3. $\text{CR eq}^n \text{ are not satisfied at a point } z_0 \Rightarrow f'(z_0) \text{ does not exist and hence not analytic at } z_0$.
   * $\text{CR eq}^n \text{ not sufficient condition for } f(z) \text{ to be analytic.}$



> ✍️ **Added by:**  Dhani Sangwan , <16/08/2026>



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



> ✍️ **Added by:** Abhi balai , <16/08/2026>



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


> ✍️ **Added by:** Divyanshu Kumar, 2026-08-23

### Sequences, Series & Convergence Tests (Ratio and Root Tests)

**Statement:**

A sequence of numbers $z_1, z_2, z_3, \ldots$ converges to a limit $z_\infty$ if

$$\lim_{n\to\infty} z_n = z_\infty$$

i.e. for every $\varepsilon > 0$ there exists $N_0$ such that $|z_n - z_\infty| \le \varepsilon$ for all $n \ge N_0$.

A series with terms $x_k$ converges if the sequence of its partial sums

$$S_n = \sum_{k=1}^{n} x_k$$

converges. The series is **absolutely convergent** if

$$\sum_{k=1}^{\infty} |x_k|$$

converges.

Two standard tools for testing absolute convergence of a series $\sum_n a_n$ are:

**Ratio test** — the series is absolutely convergent if

$$\lim_{n\to\infty}\left|\frac{a_{n+1}}{a_n}\right| < 1$$

**Root test** — the series is absolutely convergent if

$$\limsup_{n\to\infty} |a_n|^{1/n} < 1$$


**Worked example:**

*Ratio test:* Test the series $\sum_{n=1}^{\infty} \dfrac{n}{2^n}$:

$$\lim_{n\to\infty}\left|\frac{a_{n+1}}{a_n}\right| = \lim_{n\to\infty} \frac{(n+1)/2^{n+1}}{n/2^n} = \lim_{n\to\infty} \frac{n+1}{2n} = \frac{1}{2}$$

Since $\frac{1}{2} < 1$, the series converges absolutely.

*Root test (where the ratio test fails):* Consider the oscillating sequence

$$a_n = \begin{cases} (1/2)^n & n \text{ odd} \\ (1/3)^n & n \text{ even} \end{cases}$$

The ratio $a_{n+1}/a_n$ jumps back and forth depending on parity and never settles to a single value, so $\lim_{n\to\infty} |a_{n+1}/a_n|$ does not exist — the **ratio test is inconclusive** here.

The root test still works fine, since

$$|a_n|^{1/n} = \begin{cases} 1/2 & n \text{ odd} \\ 1/3 & n \text{ even} \end{cases}$$

This oscillates between $1/2$ and $1/3$ forever, so its ordinary limit doesn't exist either — but its $\limsup$ does:

$$\limsup_{n\to\infty} |a_n|^{1/n} = \frac{1}{2} < 1$$

So $\sum a_n$ **converges absolutely** by the root test, even though the ratio test alone couldn't tell us that.

**Pitfalls / conditions to watch:**

Both tests are inconclusive when the relevant limit equals exactly $1$ — the series may converge or diverge depending on finer details.

The root test is strictly more general than the ratio test: whenever the ratio test applies, the root test agrees with it, but as the second example above shows, the root test can succeed even when the ratio of successive terms oscillates and never settles to a limit at all.

---


### Taylor Series Representation & Radius of Convergence

**Statement:** If $f(z)$ is analytic inside a region $R$ of the complex plane, then for any $z_0 \in R$ there exists a neighbourhood of $z_0$ in which $f(z)$ can be expanded in an absolutely convergent power series (a **Taylor series**) in non-negative powers of $(z-z_0)$:
$$f(z) = \sum_{n=0}^{\infty} a_n (z-z_0)^n$$
The series converges absolutely inside the **circle of convergence** $|z - z_0| = R$, where the **radius of convergence** is
$$R = \lim_{n\to\infty}\left|\frac{a_n}{a_{n+1}}\right| \quad \text{(equivalently, } R^{-1} = \limsup_{n\to\infty} |a_n|^{1/n}\text{)}$$
Once $f(z)$ and $z_0$ are fixed, the coefficients are uniquely determined by $a_n = \frac{1}{n!}\frac{d^n f}{dz^n}\Big|_{z=z_0}$ — analyticity of $f$ guarantees derivatives of all orders exist.

**Derivation / justification (condensed):** Absolute convergence of $\sum a_n(z-z_0)^n$ is tested via the ratio test: the series converges absolutely where
$$\lim_{n\to\infty}\left|\frac{a_{n+1}}{a_n}\right||z-z_0| < 1 \implies |z-z_0| < R.$$
For power series, absolute convergence implies uniform convergence on the disc, which is what licenses term-by-term differentiation and integration anywhere strictly inside the circle of convergence.

**Worked example:** The geometric series gives the "master" representation
$$\frac{1}{1-z} = \sum_{n=0}^{\infty} z^n, \qquad |z| < 1$$
(ratio test: $R = \lim |a_n/a_{n+1}| = 1$). The *same* function has infinitely many other valid power series representations, one for each choice of expansion centre $a$:
$$\frac{1}{1-z} = \frac{1}{1-a}\sum_{n=0}^{\infty}\left(\frac{z-a}{1-a}\right)^n, \qquad |z-a| < |1-a|$$
E.g. for $a = -\tfrac12, i, 2$ this gives three more series, each valid in its own disc. All of them agree pointwise wherever their domains overlap (e.g. all evaluate to $1$ at $z=0$, except the $a=2$ series, whose disc $|z-2|<1$ doesn't contain $z=0$ at all).

**Pitfalls / conditions to watch:** The radius of convergence is fixed the moment you fix the centre $a$ — different centres give different discs, but every one of these discs has its boundary passing through $z=1$, the actual singularity of $\frac{1}{1-z}$ (not a coincidence: singularities can't hide ). A series representation says nothing about the function outside its own disc, even if the function is perfectly well-defined there via another representation.

---

### Behaviour on the Circle of Convergence

**Statement:**

Inside the circle of convergence a power series converges absolutely and represents an analytic function; outside it, the series diverges. On the circle itself, behaviour is not determined by $R$ alone — the series may converge at some boundary points and diverge at others, or even oscillate without converging.

A general fact, stated here without proof: the analytic function represented inside the circle of convergence must have at least one singularity on that circle.

**Worked example:**

Even where a series oscillates on the boundary, its Cesàro mean — the average of successive partial sums — can still recover the function's value there.

Consider $\dfrac{1}{1-z} = \sum z^n$ at the point $z = -1$, which lies on $|z| = 1$. The partial sums alternate:

$$S_m = 1 \ (m \text{ odd}), \qquad S_m = 0 \ (m \text{ even})$$

The Cesàro mean is $\frac{1}{2}$, matching

$$\frac{1}{1-z}\bigg|_{z=-1} = \frac{1}{2}$$

exactly.


At $z = i$, also on $|z| = 1$, the series is

$$1 + i - 1 - i + 1 - i - 1 - i + \cdots$$

Its partial sums cycle through $1,\ 1+i,\ i,\ 0$ and repeat. The Cesàro mean of these four values again matches the function value:

$$\frac{1}{1-z}\bigg|_{z=i} = \frac{1+i}{2}$$

**Pitfalls / conditions to watch:**

Don't assume a series either converges everywhere on its circle or nowhere — both extremes, and everything in between, are possible. The series $\sum z^n/n^2$ converges absolutely at every point on $|z|=1$, while some **lacunary series** diverge at every point on their circle.

If a power series is singular everywhere on its circle of convergence, the function it represents cannot be analytically continued past that circle.

---

### Entire Functions and Their Order

**Statement:**

An **entire function** is analytic everywhere in the finite complex plane. Its power series, about any centre, has infinite radius of convergence, and its only possible singularity is at $z = \infty$.

Entire functions can be classified by their **order** $\rho$, describing asymptotic growth as $r \to \infty$, writing $z = re^{i\theta}$ or by using the power series representation:

$$\rho = \limsup_{r\to\infty} \frac{\log\log|f(z)|}{\log r} = \limsup_{n\to\infty}\frac{n\log n}{\log(1/|a_n|)}$$



**Worked example:**

For a degree-$N$ polynomial $f(z) = \sum_{n=0}^N b_n z^n$:

$$\rho = \limsup_{r\to\infty} \frac{\log[\log|b_N| + N\log r]}{\log r} = 0$$

For $f(z) = e^z$: since $\log\log(e^z) \approx \log r$,

$$\rho = \lim_{r\to\infty} \frac{\log r}{\log r} = 1$$

**Pitfalls / conditions to watch:**

All entire functions share the same location of singularity, $z = \infty$, but the order $\rho$ distinguishes how fast they blow up there. This is genuinely different information than simply "has infinite radius of convergence," which is common to all entire functions and doesn't by itself distinguish between them.

--- 


✍️ **Added by:** Sunil Bhadu, 2026-08-23
# Scribe Work: Cauchy's Integral Theorem

## Introduction and Properties

Let $F(z)$ be analytic in some region R. Then the line integral $\int F(z)dz$ is independent of the actual path provided the paths lie entirely in Region R.

* The value of the line integral depends only on the end points.
* The integral of $f(z)$ over a closed contour is zero.

Let C be an oriented, closed contour lying entirely in R, then:

$$
\oint f(z)dz=0
$$

It is evident that the contour C may be distorted like a rubber band (to any other contour like C') without changing the property, as long as it does not leave R.

These properties are responsible for much of the power of contour integration in evaluating definite integrals.

**Reference:** V. Balakrishna, Mathematical Physics (23.1)

---

## Proof: $\oint_{C}F(z)dz=0$

Let $z=x+iy$ and $dz=dx+idy$

We can write the integral as:

$$
\oint_{C}F(z)dz = \oint_{C}(udx-vdy) + i\oint_{C}(vdx+udy)
$$

We know that applying Green's Theorem:

$$
\oint(Pdx+Qdy) = \iint_{S}\left(\frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y}\right)dxdy
$$

Applying this to our equation:

$$
\oint f(z)dz = \iint_{\text{inside } C}\left(-\frac{\partial v}{\partial x}-\frac{\partial u}{\partial y}\right)dxdy + i\iint_{\text{inside } C}\left(\frac{\partial u}{\partial x}-\frac{\partial v}{\partial y}\right)dxdy
$$

By Cauchy-Riemann Conditions:

$$
\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y} \quad \text{and} \quad \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x}
$$

Substituting these conditions makes the integral zero, hence proved:

$$
\oint f(z)dz = 0
$$

---

## Limitations and Conditions

These theorems are only well valid when the function is non-singular, meaning defined at all points on surface and inside C.

* $\oint f(z)dz=0$ works when $F(z)$ is entirely analytic (smooth, safe) everywhere inside the loop.

**The Problem of Singularities:** So the problem arises that when a function is not analytic, then it blows up or down inside the contour. In this condition, $\oint f(z)dz=0$ can not be applied.

This problem is solved by Cauchy's extended theorem or the principle of contour deformation.

---

## Example Evaluation

**Question:** Evaluate the contour integral $\oint_{C}z^{2}dz$, where C is the unit circle defined by $|z| = 1$ traversed in the counter-clockwise direction.

**Solution:**

$F(z)=z^{2}$

We know that $z^{2}$ is polynomial. So it is analytic everywhere in complex plane, particularly on and inside C. It does not have any singularities.

By applying Cauchy Integral Theorem:

$$
\oint_{C}F(z)dz=0
$$

Therefore,

$$
\oint_{C}z^{2}dz=0
$$

So we come to this conclusion because $F(z)$ satisfies all conditions of Cauchy Integral theorem like:
* Analyticity
* Non-singularity

---

✍️ **Added by:** Naveen Kumar Deegwal, 2026-08-23

### Deformation of Cauchy's Theorem

**Statement:** If $C$ and $\Gamma$ are closed contours with $\Gamma$ lying entirely inside $C$, and $f(z)$ is analytic throughout the annular region between $C$ and $\Gamma$ (not necessarily inside $\Gamma$ itself), then

$$\oint_C f(z)\.dz = \oint_\Gamma f(z)\.dz$$

both integrals taken with the same (anticlockwise) orientation.

**Derivation / justification (condensed):** Cut two thin bridges connecting $C$ to $\Gamma$, splitting the annular region between them into two simply-connected pieces, call them $C_A$ and $C_B$. Each piece consists of part of the outer curve $C$, a bridge across to $\Gamma$, part of $\Gamma$, and the bridge back. The crucial observation is that each bridge is shared by both pieces but walked in **opposite directions** by $C_A$ and $C_B$ — one traverses it going one way, the other traverses the same segment going the opposite way. So when the two contour integrals are added, every bridge contribution cancels exactly, and what remains is one full pass around $C$ combined with one full pass around $\Gamma$ in the reverse direction:

$$\oint_{C_A} f\.dz + \oint_{C_B} f\.dz = \oint_C f\.dz - \oint_\Gamma f\.dz$$

But $f$ is analytic inside each of $C_A$ and $C_B$ individually, since that enclosed region is just a piece of the annulus where $f$ is already assumed analytic. So by Cauchy's theorem, each integral on the left vanishes:

$$\oint_{C_A} f\.dz + \oint_{C_B} f\.dz = 0 \implies \oint_C f\.dz = \oint_\Gamma f\.dz$$

**Worked example:** Let $f(z) = 1/z$, which is analytic everywhere except at $z=0$. Take $C$ to be $|z|=2$ and $\Gamma$ to be $|z|=1$, both anticlockwise — the annulus between them avoids the singularity at $z=0$, so deformation applies:

$$\oint_{|z|=2} \frac{dz}{z} = \oint_{|z|=1} \frac{dz}{z} = 2\pi i$$

Both integrals give the same value $2\pi i$, even though $C$ and $\Gamma$ are different curves — exactly as the theorem predicts, since $1/z$ is analytic throughout the annulus $1 < |z| < 2$.

**Pitfalls / conditions to watch:** $f$ only needs to be analytic in the region *between* $C$ and $\Gamma$ — it can misbehave (have singularities) anywhere inside $\Gamma$, and the theorem still holds. This is what makes it powerful: it lets you replace a complicated contour $C$ with a simple one $\Gamma$ (like a small circle) as long as nothing singular lies between them. Both contours must have matching orientation for the formula as stated; reversing one flips its sign.

---

### Cauchy's Integral Formula

**Statement:** If $f(z)$ is analytic inside and on a positively oriented (anticlockwise) closed contour $\Gamma$, and $z_0$ is any point strictly enclosed inside $\Gamma$, then

$$\oint_\Gamma \frac{f(z)}{z-z_0}\.dz = 2\pi i\. f(z_0)$$

**Derivation / justification (condensed):** By the deformation theorem above, since $f(z)/(z-z_0)$ is analytic everywhere in $\Gamma$'s interior except at $z_0$, the integral over $\Gamma$ equals the integral over a small circle $\gamma$ of radius $\delta$ centered at $z_0$. Write

$$\oint_\gamma \frac{f(z)}{z-z_0}\.dz = \oint_\gamma \frac{f(z)-f(z_0)}{z-z_0}\.dz + f(z_0)\oint_\gamma \frac{dz}{z-z_0}$$

The function $\phi(z) = \dfrac{f(z)-f(z_0)}{z-z_0}$ extends continuously to $z_0$ (its limit there is $f'(z_0)$), so it's analytic throughout the disc, making the first integral zero by Cauchy's theorem. Since this holds for arbitrarily small $\delta$, and the bound $\left|\oint_\gamma \phi\,dz\right| \le 2\pi\delta \max_\gamma|\phi(z)|$ shrinks to zero as $\delta \to 0$, only the second term survives:

$$\oint_\gamma \frac{f(z)}{z-z_0}\.dz = f(z_0)\oint_\gamma \frac{dz}{z-z_0} = f(z_0)\cdot 2\pi i$$

**Worked example:** Evaluate $\displaystyle\oint_{|z|=2} \frac{e^z}{z-1}\.dz$. Here $f(z) = e^z$ is entire (analytic everywhere), and $z_0 = 1$ lies strictly inside $|z|=2$. Directly applying the formula:

$$\oint_{|z|=2} \frac{e^z}{z-1}\.dz = 2\pi i\, f(1) = 2\pi i\. e$$

**Pitfalls / conditions to watch:** $z_0$ must lie *strictly inside* $\Gamma$ — if $z_0$ is outside, $f(z)/(z-z_0)$ is analytic everywhere inside $\Gamma$ and the integral is simply $0$ by Cauchy's theorem, not $2\pi i f(z_0)$. $f$ itself must be analytic on and inside all of $\Gamma$ (only the extra factor $1/(z-z_0)$ is allowed to be singular, and only at $z_0$). This formula is also the starting point for expressing derivatives of $f$ as contour integrals, since differentiating both sides with respect to $z_0$ under the integral sign gives $f^{(n)}(z_0)$ in terms of $\oint f(z)/(z-z_0)^{n+1}\.dz$.



---

> ✍️ **Added by:** Mansi Chaudhary, 2026-08-23

### Higher-Order Derivatives & Cauchy's Inequality

**Statement:** If $f(z)$ is analytic at a point $z$, its derivatives to all orders exist and are given by

$$\frac{d^n}{dz^n} f(z) = \frac{n!}{2\pi i} \oint_C \frac{f(\xi)}{(\xi-z)^{n+1}}\,d\xi$$

where $C$ is any contour around $z$ such that $f$ is analytic inside and on $C$.

**Cauchy's Inequality:** Let $C_R$ be the circle $|z-z_0|=R$, with $f$ analytic on and inside $C_R$, and let $M_R = \max|f(z)|$ on $C_R$. Then

$$|f^{(n)}(z_0)| \le \frac{n!\, M_R}{R^n}$$

**Derivation / justification (condensed):** The higher-derivative formula follows by differentiating Cauchy's Integral Formula under the integral sign with respect to $z$, repeated $n$ times: since $z$ is strictly inside $C$ and $\xi$ ranges over $C$, we always have $\xi - z \neq 0$, so every derivative of $1/(\xi-z)$ with respect to $z$ exists on $C$.

Cauchy's inequality follows by bounding the same integral (for $z_0$ the centre, $C = C_R$): the integrand has magnitude at most $M_R/R^{n+1}$ everywhere on $C_R$, and the contour has length $2\pi R$, so

$$|f^{(n)}(z_0)| = \left|\frac{n!}{2\pi i}\oint_{C_R} \frac{f(\xi)}{(\xi-z_0)^{n+1}}\,d\xi\right| \le \frac{n!}{2\pi}\cdot 2\pi R \cdot \frac{M_R}{R^{n+1}} = \frac{n!\,M_R}{R^n}$$

**Worked example:** Suppose $f(z)$ is analytic on and inside $|z|=2$, and $|f(z)| \le 5$ everywhere on that circle (so $M_R = 5$, $R=2$). Cauchy's inequality bounds the second derivative at the centre:

$$|f''(0)| \le \frac{2!\cdot 5}{2^2} = \frac{10}{4} = 2.5$$

This bound holds no matter what $f$ actually is, as long as it satisfies the stated analyticity and boundary bound.

**Pitfalls / conditions to watch:** $M_R$ must be the maximum of $|f|$ specifically on the boundary circle $C_R$, not somewhere in the interior. The inequality only gives an upper bound on $|f^{(n)}(z_0)|$, never an exact value. $f$ must be analytic on the *entire* closed disc $|z-z_0|\le R$, not just at $z_0$ — a single singularity anywhere in that disc invalidates the bound.

---

### Taylor Series Expansion Theorem (via Cauchy's Integral Formula)

**Statement:** If $f(z)$ is analytic in a region $A$ and $z_0 \in A$, then

$$f(z) = \sum_{n=0}^{\infty} a_n (z-z_0)^n, \qquad a_n = \frac{f^{(n)}(z_0)}{n!} = \frac{1}{2\pi i}\oint_C \frac{f(\xi)}{(\xi-z_0)^{n+1}}\,d\xi$$

with $C$ any curve contained in $A$ encircling $z_0$. The series converges for all $z$ inside the circle of convergence centred at $z_0$, whose radius $R$ equals the distance from $z_0$ to the **nearest singularity** of $f(z)$.

**Derivation / justification (condensed):** Starting from Cauchy's Integral Formula $f(z) = \frac{1}{2\pi i}\oint_\Gamma \frac{f(\xi)}{\xi - z}\,d\xi$ (valid for $z$ inside $\Gamma$), rewrite the kernel as a geometric series:

$$\frac{1}{\xi - z} = \frac{1}{(\xi-z_0) - (z-z_0)} = \frac{1}{\xi - z_0}\sum_{n=0}^{\infty}\left(\frac{z-z_0}{\xi-z_0}\right)^n$$

which converges (by the ratio test) whenever $|z-z_0| < |\xi - z_0|$ — i.e. whenever $z$ lies strictly inside the circle traced by $\xi$. Substituting back and interchanging the sum and the integral (justified since the series converges uniformly on $\Gamma$) gives the Taylor series with the coefficients above. Since $\Gamma$ can be deformed to any contour $C$ inside $A$ without crossing a singularity (by the deformation theorem), the radius of convergence extends exactly up to the nearest point where $f$ stops being analytic.

**Worked example:** Taylor expand $f(z) = \dfrac{1}{(z^2+4)(z-5)}$ about $z=-3$, and find the radius of convergence. The singularities of $f$ are at $z=5$ and $z=\pm 2i$. Their distances from the centre $z_0=-3$ are:

$$|5-(-3)| = 8, \qquad |{\pm 2i}-(-3)| = |{-3\mp 2i}| = \sqrt{3^2+2^2} = \sqrt{13}$$

The nearest singularity is at $z=\pm 2i$, distance $\sqrt{13}$, so the radius of convergence is $R=\sqrt{13}$ — determined purely by geometry, without computing a single coefficient. The first coefficient is $a_0 = f(-3) = \dfrac{1}{13\cdot(-8)} = -\dfrac{1}{104}$.

**Pitfalls / conditions to watch:** The radius of convergence is fixed entirely by the distance to the *nearest* singularity — you don't need to locate every singularity, only the closest one. If $f$ is entire (no singularities at all), $R=\infty$ automatically. This is the same theorem introduced earlier from first principles; this entry shows the actual derivation via Cauchy's Integral Formula, which also explains *why* the radius equals that particular distance.

---

### Laurent Expansion Theorem

**Statement:** Let $f(z)$ be analytic in the annular region $R$ between two concentric circles $\Gamma_1$ (radius $r_1$) and $\Gamma_2$ (radius $r_2$), both centred at $z_0$. Then for $z \in R$, $f(z)$ can be expanded in a **Laurent series** with both positive and negative powers:

$$f(z) = \underbrace{\sum_{n=0}^{\infty} a_n(z-z_0)^n}_{\text{principal part}} + \underbrace{\sum_{n=1}^{\infty} b_n(z-z_0)^{-n}}_{\text{singular part}}$$

with

$$a_n = \frac{1}{2\pi i}\oint_C \frac{f(\xi)}{(\xi-z_0)^{n+1}}\,d\xi, \qquad b_n = \frac{1}{2\pi i}\oint_C f(\xi)(\xi-z_0)^{n-1}\,d\xi$$

where $C$ is any curve lying in the annulus $r_1 < |z-z_0| < r_2$. The positive-power part converges for $|z-z_0|<r_2$, the negative-power part converges for $|z-z_0|>r_1$, and together they converge to $f(z)$ throughout the annulus.

**Derivation / justification (condensed):** This is the natural extension of Cauchy's Integral Formula to a non-simply-connected (annular) region: build a contour from the outer circle $\Gamma_2$, a bridge inward, the inner circle $\Gamma_1$ traversed in reverse, and the bridge back — the bridges cancel exactly as in the deformation theorem, leaving Cauchy's formula evaluated on $\Gamma_2 - \Gamma_1$. On $\Gamma_2$ (outer), $|z-z_0| < |\xi - z_0|$, so the kernel expands exactly as in the Taylor case, giving the positive-power part. On $\Gamma_1$ (inner), $|z-z_0| > |\xi-z_0|$, so the kernel instead expands as a geometric series in $(\xi-z_0)/(z-z_0)$, producing the negative-power part.

Notably, nothing is assumed about $f$'s behaviour at $z=z_0$ itself. If $f$ happens to be analytic everywhere inside $\Gamma_1$ too, then $b_n = 0$ for all $n$ (by Cauchy's theorem applied to the $b_n$ integral), and the Laurent series collapses back to an ordinary Taylor series.

**Worked example:** Find the first few terms of the Laurent expansion of

$$f(z) = \frac{5z-3}{z(z+2)(z-1)}$$

valid in the annulus $1 < |z| < 2$. Using partial fractions and expanding $\frac{1}{z-1}$ and $\frac{1}{z+2}$ each as a series valid in this annulus (one in positive powers of $z$, one in negative powers, since $|z|>1$ and $|z|<2$ respectively), the expansion works out to

$$f(z) = \left(-\frac{13}{12} + \frac{13}{24}z - \frac{13}{48}z^2 + \cdots\right) + \left(\frac{13}{6z} - \frac{2}{3z^2} + \cdots\right)$$

the first bracket being the principal (positive-power) part and the second the singular (negative-power) part.

**Pitfalls / conditions to watch:** The *same* function has different Laurent expansions in different annuli around the same centre — just as with multiple Taylor representations, always double check which annulus you're expanding in before writing down the series (compare $1<|z|<2$ versus $1<|z-1|<3$ for this same $f(z)$, which give different series). The number of non-zero terms in the singular part will later turn out to characterize the type of singularity at $z=z_0$.





> ✍️ **Added by:** Nikhil Chaudhary , <31/08/2026>

# Singularities, Poles & Residues


## Introduction

In complex analysis, a function is generally well behaved at points where it is analytic. However, at some points the function may fail to be defined or may fail to remain analytic. Such points are called **singularities**. Understanding singularities is important because their local behaviour determines whether a point is removable, a pole, or a more severe type of singularity, and it also leads naturally to the concept of residues.

Singularities are studied by examining the behaviour of a function in a neighbourhood of the point. In particular, the Laurent expansion provides a convenient way to identify the type of singularity and to extract the residue when a pole is present.

## Definition of a Singularity

Let $f(z)$ be a complex function that is analytic in a punctured neighbourhood of $z=a$, i.e. for

$$0<|z-a|<R$$

for some $R>0$. If $f$ is **not analytic at $z=a$**, then $z=a$ is called an **isolated singularity** of $f$.

In simple terms, a singularity is a point where the function ceases to be analytic, even though it is analytic at all nearby points except possibly the point itself.

For an isolated singularity, there are three standard possibilities:

1. **Removable singularity:** $f(z)$ approaches a finite limit as $z\to a$, so the function can be redefined at $a$ to make it analytic.
2. **Pole:** $|f(z)|\to\infty$ as $z\to a$. A pole may be simple or of higher order.
3. **Essential singularity:** the singularity is neither removable nor a pole; the behaviour near $a$ is more complicated.

The sections below begin with the removable case and then develop poles and residues.

## 1. Removable Singularities

Before talking about genuine singularities, it's worth being precise about the ones that aren't
singularities at all. Take

$$f(z) = \frac{\sin z}{z}.$$

Strictly, $f$ is undefined at $z=0$ — the formula gives $0/0$ there, and it *looks* singular
because the denominator vanishes. But

$$\lim_{z\to 0} f(z) = 1,$$

so nothing pathological is actually happening near the origin; redefining $f(0)=1$ makes the
function analytic there too. This is a **removable singularity**, and the standing convention for
the rest of the section (and the rest of the course) is that wherever one turns up, it's assumed
to already have been dealt with this way — otherwise "singular at $z=a$" would technically include
a lot of perfectly well-behaved points.

## 2. Simple Poles

The first genuinely interesting kind of singularity is the **simple pole**. $f(z)$ has a simple
pole at $z=a$ if, in a sufficiently small neighbourhood of $a$, it can be written

$$f(z) = \underbrace{\frac{C_{-1}}{z-a}}_{\text{singular part}} \;+\; \underbrace{\sum_{n=0}^{\infty} C_n (z-a)^n}_{\text{regular part}}$$

The regular part is an ordinary convergent power series — analytic straight through $z=a$; it may
terminate after finitely many terms, or be absent entirely. The singular part is what actually
blows up as $z \to a$. The coefficient $C_{-1}$ (finite, in general complex) is the **residue** of
$f$ at $z=a$ — the notation reminds you it's the coefficient of $(z-a)^{-1}$.

At a simple pole, by definition, the singular part is *literally* just the one term
$C_{-1}/(z-a)$ — but that doesn't mean $C_{-1}$ is always sitting there in plain sight. Example 2
below is the case where it takes a bit of work to expose it.

### Example 1 — $f(z) = \sin(z)/z^2$

From the Maclaurin series of $\sin z$:

$$\frac{\sin z}{z^2} = \underbrace{\frac 1z}_{\text{singular part}} + \underbrace{\left(-\frac{z}{3!}+\frac{z^3}{5!}-\cdots\right)}_{\text{regular part}}$$

Simple pole at $z=0$, residue $=1$. No other finite singularities anywhere in the plane.

### Example 2 — $\mathrm{cosec}{cosec}(z)$

Here the pole location is clear ($\sin z$ has simple zeros at $z=n\pi,\ n\in\mathbb Z$, so
$\mathrm{cosec}(z)=1/\sin(z)$ should have simple poles there) but the residue takes real
work to extract. Taylor-expand $\sin z$ about $z=n\pi$:

$$\sin z = (-1)^n(z-n\pi)\left[1-\frac16(z-n\pi)^2+\frac{1}{120}(z-n\pi)^4-\cdots\right]$$

Inverting the bracket via the binomial series gives

$$\mathrm{cosec}{cosec} z = \underbrace{\frac{(-1)^n}{z-n\pi}}_{\text{singular part}} + \underbrace{\frac{(-1)^n}{6}\left[(z-n\pi)+\frac{7}{60}(z-n\pi)^3+\cdots\right]}_{\text{regular part}}$$

So $\mathrm{cosec}{cosec}(z)$ has a simple pole at every $z=n\pi$, with residue $(-1)^n$ — the sign
alternates from one pole to the next along the real axis. Worth keeping in mind: the residue of a
function need not be a single fixed number; it can (and here does) depend on *which* pole you're
evaluating at.

## 3. The Residue Formula

Doing a full Laurent expansion every time, as Example 2 required, is slow. In general, if $f$ has
a simple pole at $z=a$, the residue can be pulled out directly as a limit:

$$
\mathrm{Res}_{z=a} f(z) = C_{-1}
= \lim_{z\to a}\left[(z-a)f(z)\right]
$$

**Why it works:** multiplying by $(z-a)$ kills the $1/(z-a)$ blow-up, leaving $C_{-1}$ plus a power
series in $(z-a)$. Every term of that series vanishes as $z\to a$, so only $C_{-1}$ survives.

Simple poles very often arise in the form $f(z) = g(z)/h(z)$, with $g,h$ analytic at $z=a$,
$g(a)\ne 0$, and $h$ having a *simple* zero at $a$ (i.e. $h(a)=0$, $h'(a)\ne 0$). In that case
(52A) reduces to

$$\mathrm{Res}_{z=a} f(z) = \mathrm{Res}_{z=a}\frac{g(z)}{h(z)} = \frac{g(a)}{h'(a)}$$

This is the version actually used most in practice — it reproduces both examples above almost
instantly:

| Function | $g(z)$ | $h(z)$ | $h'(z)$ | Residue |
|---|---|---|---|---|
| $\sin z / z^2$ at $z=0$ | (direct limit, see below) | — | — | $1$ |
| $\mathrm{cosec}{cosec} z$ at $z=n\pi$ | $1$ | $\sin z$ | $\cos z$ | $\dfrac{1}{\cos(n\pi)} = (-1)^n$ |

For $\sin z/z^2$, applying (52A) directly: $\displaystyle\lim_{z\to0} z\cdot\frac{\sin z}{z^2} = \lim_{z\to0}\frac{\sin z}{z} = 1$ — same answer as the series computation, no expansion needed.

**Caution:** the $g(a)/h'(a)$ shortcut needs $h'(a)\ne 0$ *specifically*. If $h'(a)=0$ too, the
zero of $h$ isn't simple, $f$ has a higher-order pole, and this formula doesn't apply as-is (see
§4). Also check $g(a)\ne 0$ separately — if $g$ vanishes there too, part or all of the pole can
cancel against the zero of $g$, changing the order of the singularity.

## 4. Extension: Higher-Order (Multiple) Poles

$f(z)$ has a **pole of order $m$** at $z=a$ if, near $a$,

$$f(z) = \frac{C_{-m}}{(z-a)^m} + \frac{C_{-(m-1)}}{(z-a)^{m-1}} + \cdots + \frac{C_{-1}}{z-a} + \sum_{n\ge0} C_n(z-a)^n$$

The residue (still $C_{-1}$, the coefficient of the $(z-a)^{-1}$ term specifically — not any of
the other negative-power coefficients) generalises to

$$\mathrm{Res}_{z=a} f(z) = \frac{1}{(m-1)!}\lim_{z\to a}\frac{d^{m-1}}{dz^{m-1}}\Big[(z-a)^m f(z)\Big]$$

which is exactly same again when $m=1$ (the derivative and the factorial both drop out).

## References

1. Lecture notes, *PH502 — Complex Analysis, Module 1*, Section 5: "Singularities — Poles & Residues," pp. 60–64.
2. A. K. Kapoor, *Complex Variables: Principles and Problem Sessions



> ✍️ **Added by:** Drishya Verma, <01/09/2026>

### 1.1 Essential Singularity 

Extending the definition of a pole: the singular part of $f(z)$ may involve an **unbounded** number of negative powers of $(z-a)$.

$f(z)$ has an **isolated essential singularity** at $z=a$ if, in a neighbourhood of $z=a$, it can be written as

$$f(z) = \underbrace{\sum_{n=1}^{\infty} \frac{c_{-n}}{(z-a)^n}}_{\text{singular part}} + \underbrace{\sum_{n=0}^{\infty} c_n (z-a)^n}_{\text{regular part}} \qquad (54A)$$

As with a pole, $c_{-1}$ is still called the **residue** of $f(z)$ at the singularity.

**Worked example:** $f(z) = e^{1/z} = \displaystyle\sum_{n=1}^{\infty} \frac{1}{n!\,z^n} + 1$, valid for all $z \neq 0$. The series on the right converges absolutely, $f(z)$ has an essential singularity at $z=0$, residue $=1$, and the regular part is just the constant $1$.

### 1.2 Laurent Series 

Representations of complex functions with **both** positive and negative powers of $(z-a)$ (as in the equations for poles and essential singularities above) are called **Laurent series**.

General form:

$$f(z) = \sum_{n=1}^{N} \frac{c_{-n}}{(z-a)^n} + \sum_{n=0}^{\infty} c_n (z-a)^n \qquad $$

- For a **pole**, $N$ is finite (order of the pole).
- For an **essential singularity**, $N \to \infty$.

**Region of validity — worked out from first principles:**

1. *Regular part* is an ordinary (positive-power) convergent power series ⇒ converges inside a circle of radius $r_1$ centred at $z=a$. If the regular part is a polynomial ($c_{n>M}=0$) or, more generally, an entire function, then $r_1 = \infty$.
2. *Singular part*: substitute $w = \dfrac{1}{z-a}$, so $\displaystyle\sum_{n=1}^{N}\frac{c_{-n}}{(z-a)^n} = \sum_{n=1}^N c_{-n}w^n$ — an ordinary power series **in $w$**, convergent inside $|w| < r_2$ for some $r_2$ (infinite if the singular part is a polynomial/entire function of $w$). `
3. Translating $|w|<r_2$ back to the $z$-plane: $\left|\dfrac{1}{z-a}\right| < r_2 \iff |z-a| > \dfrac{1}{r_2}$.
4. **Only if** $\dfrac{1}{r_2} < r_1$ (i.e. $r_1 r_2 > 1$) does an **annular region** exist:

$$\frac{1}{r_2} < |z-a| < r_1$$

Inside this annulus both the regular and singular parts converge absolutely — **this annulus is the region of convergence of the Laurent series.**

**Edge cases:**
- If $r_2 \to \infty$ (i.e. $1/r_2 = 0$), the series converges on a **punctured disk** of radius $r_1$ centred at $z=a$ (with $z=a$ itself excluded).
- In some cases the outer radius $r_1 = \infty$ too, so the annulus extends to infinity.

**Revisit the $e^{1/z}$ example:** $e^{1/z} = \sum_{n=1}^{\infty}\frac{1}{n!}\frac{1}{z^n} + 1$ converges for all $|z|>0$, with $r_1 = \infty$ and $1/r_2 = 0$. Hence the Laurent series is convergent for **all $z\neq 0$** (including as $z\to\infty$). 

**Conclusion:** A Laurent series is, in general, convergent in some annular region whose inner radius may shrink to $0$ and whose outer radius may extend to $\infty$.

### 1.3 Singularity at Infinity — setup only

To classify the behaviour of $f(z)$ at $z=\infty$ in the extended complex plane:

1. Change variable $w = 1/z$ (this maps $z=\infty \to w=0$).
2. Examine the singularity of $\phi(w) \equiv f(1/w)$ **at $w=0$**.
3. The nature of that singularity determines the nature of the singularity of $f(z)$ at $z=\infty$.

## References

1. Lecture notes


---
---

## Module 2: Integral Transforms

---

## Module 3: Differential Equations of Physics

---

## Module 4: Linear Algebra

---

