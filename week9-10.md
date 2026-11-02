> Added by Samyak Gawai Date: 02/11/2026
# Second-Order Linear ODEs, Frobenius Method, & Sturm-Liouville Theory

## Page 20

$$= P(x)(y_{1}^{\prime}w_{23} - y_{2}^{\prime}w_{13} + y_{3}^{\prime}w_{12})$$

$$= P(x)\det\begin{pmatrix} y_{1} & y_{2} & y_{3} \\ y_{1}^{\prime} & y_{2}^{\prime} & y_{3}^{\prime} \\ y_{1}^{\prime} & y_{2}^{\prime} & y_{3}^{\prime} \end{pmatrix} = 0 \quad \text{(2 rows same)}$$

$$\Rightarrow W = 0$$

$$\therefore \{y_{1}, y_{2}, y_{3}\} \text{ are linearly dependent.}$$

**A Linear Second-Order Homogeneous ODE has at most 2 linearly independent solutions.**

### Second Solution:
Let 

$$y^{\prime\prime} + P(x)y^{\prime} + Q(x)y = 0 \quad \text{--- (20A)}$$

Let $y_{1}, y_{2}$ be two linearly independent solutions:

$$W = y_{1}y_{2}^{\prime} - y_{2}y_{1}^{\prime}$$

From earlier:

$$W^{\prime} = -P(x)W \quad \text{--- (20B)}$$

**Remark:** If $P(x) = 0 \implies W^{\prime} = 0 \Rightarrow W = y_{1}y_{2}^{\prime} - y_{1}^{\prime}y_{2} = \text{const}$

From earlier, 
$$W^{\prime} = -P(x)W \quad \text{--- (20B)}$$

**Remark:** If $P(x) = 0 \implies W^{\prime} = 0 \Rightarrow W = y_{1}y_{2}^{\prime} - y_{1}^{\prime}y_{2} = \text{const}$

---

## Page 21

In general from Eq. (20B)

$$\frac{dW}{W} = -P \, dx \implies W(x) = \exp\left[-\int^{x} P(x^{\prime}) dx^{\prime}\right]$$

**Note:** If $P(x)$ remains finite in the domain, $W(x) \neq 0$ unless $W(a) = 0$

Wronskian $>0$ or never $0$. But if $P(x)$ is not finite, we have to be careful to ensure $W(x) \neq 0$

Now:
$$W(x) = y_{1}y_{2}^{\prime} - y_{1}^{\prime}y_{2} = y_{1}^{2}\frac{d}{dx}\left(\frac{y_{2}}{y_{1}}\right) \quad \text{--- (21B)}]$$

Combining (21A) & (21B):
$$\frac{d}{dx}\left(\frac{y_{2}}{y_{1}}\right) = \frac{W(a)\exp\left[-\int_{a}^{x} P(x_{1}) dx_{1}\right]}{y_{1}^{2}}[cite: 1]$$

Integrating:
$$\int_{b}^{x} d\left(\frac{y_{2}}{y_{1}}\right)$$

$$y_{2}(x) = y_{1}(x) W(a) \int_{b}^{x} \frac{\exp\left[-\int_{a}^{x_{2}} P(x_{1}) dx_{1}\right] dx_{2}}{[y_{1}(x_{2})]^{2}} \quad \text{--- (21C)}$$

Here $a, b$ are arbitrary constants. A term $\propto y_{1}(x)$ can be neglected as it is simply a constant multiplying $y_{1}(x)$[cite: 1].

We can always choose $a$ such that $W(a) = 1$.

---



We can also make Eq. (21C) an indefinite integral[cite: 1]. Choice of $a,b$ will only add constants or terms proportional to $y_{1}(x)$:

$$y_{2}(x) = y_{1}(x) \int^{x} \frac{\exp\left[-\int^{x_{2}} P(x_{1}) dx_{1}\right] dx_{2}}{[y_{1}(x_{2})]^{2}} \quad \text{--- (22A)}$$

If $P(x) = 0$:
$$y_{2}(x) = y_{1}(x) \int^{x} \frac{dx_{2}}{[y_{1}(x_{2})]^{2}} \quad \text{--- (22B)}$$

### Example: Simple Harmonic Oscillator (SHO)
$$\frac{d^{2}y}{dx^{2}} + y = 0$$

Using Eq. (22B) with $y_{1}(x) = \sin x$:

$$y_{2}(x) = \sin x \int^{x} \frac{dx_{2}}{\sin^{2}x_{2}} = \sin x \int^{x} \csc^{2}x_{2} \, dx_{2} = \sin x (-\cot x) = -\cos x$$

### Second Solution of a Series Expansion
The method of Eq. (22A) can be directly applied when one series solution is available.

---



Further insight into Fuchs' theorem is obtained if we expand $P(x)$ & $Q(x)$ as a power series as well

*(Regular singularity at $x=0$, which is the minimum criterion for Frobenius)*

First expand $xP(x)$ & $x^{2}Q(x)$ as power series:

$$xP(x) = \sum_{i=0}^{\infty} p_{i} x^{i} \implies P(x) = \sum_{i=-1}^{\infty} p_{i} x^{i}$$

$$x^{2}Q(x) = \sum_{j=0}^{\infty} q_{j-2} x^{j} \implies Q(x) = \sum_{j=-2}^{\infty} q_{j} x^{j}$$

Develop a few terms of a power series solution for $y_{1}(x)$ & then use Eq. (22A) to get $y_{2}(x)$ by term-by-term integration.

**Step 1:**
$$y^{\prime\prime} + (p_{-1}x^{-1} + p_{0} + p_{1}x + \dots)y^{\prime} + (q_{-2}x^{-2} + q_{-1}x^{-1} + \dots)y = 0$$

**Step 2:**
Substitute $y(x) = \sum_{\lambda=0}^{\infty} a_{\lambda} x^{s+\lambda}$

$$\sum_{\lambda=0}^{\infty}(s+\lambda)(s+\lambda-1)a_{\lambda}x^{s+\lambda-2} + \sum_{i=-1}^{\infty}p_{i}x^{i}\sum_{\lambda=0}^{\infty}(s+\lambda)a_{\lambda}x^{\lambda+s-1} + \sum_{j=-2}^{\infty}q_{j}x^{j}\sum_{\lambda=0}^{\infty}a_{\lambda}x^{s+\lambda} = 0$$

The coefficient of lowest power ($\lambda=0$) yields the indicial equation:

$$s(s-1) + p_{-1}s + q_{-2} = 0$$

$$s^{2} + (p_{-1}-1)s + q_{-2} = 0 \quad \text{--- (23B)}[cite: 1]$$

Let the two roots of the indicial equation be $s_{1}, s_{2}$[cite: 1].

---

## Page 24

Let $s_{1} - s_{2} = n$ (an integer)[cite: 1]. First root gives:

$$y_{1}(x) = x^{s_{1}}\sum_{j=0}^{\infty}a_{j}x^{j} \implies y_{1}(x) = x^{s_{1}}(a_{0} + a_{1}x + a_{2}x^{2} + \dots)[cite: 1]$$

Now plug into Eq. (22A)[cite: 1]:

$$y_{2}(x) = y_{1}(x)\int^{x}\frac{\exp\left[-\int^{x_{2}}P(x_{1})dx_{1}\right]dx_{2}}{[y_{1}(x_{2})]^{2}}[cite: 1]$$

Expand integrand[cite: 1]:

$$P(x) = \frac{p_{-1}}{x} + p_{0} + p_{1}x + \dots[cite: 1]$$

$$\int^{x_{2}} P(x_{1}) dx_{1} = p_{-1}\ln x_{2} + p_{0}x_{2} + \frac{p_{1}x_{2}^{2}}{2} + \dots[cite: 1]$$

$$\exp\left[-\int^{x_{2}}P(x_{1})dx_{1}\right] = x_{2}^{-p_{-1}}\exp\left[-p_{0}x_{2} - \frac{p_{1}x_{2}^{2}}{2} - \dots\right] = x_{2}^{-p_{-1}}(1 - p_{0}x_{2} + \dots)[cite: 1]$$

Now expand $[y_{1}(x_{2})]^{-2}$[cite: 1]:

$$[y_{1}(x_{2})]^{-2} = x_{2}^{-2s_{1}}a_{0}^{-2}\left(1 + \frac{a_{1}}{a_{0}}x_{2} + \dots\right)^{-2} = x_{2}^{-2s_{1}}a_{0}^{-2}\left(1 - 2\frac{a_{1}}{a_{0}}x_{2} + \dots\right)[cite: 1]$$

Combining terms in the integrand[cite: 1]:

$$\frac{\exp\left[-\int^{x_{2}}P(x_{1})dx_{1}\right]}{[y_{1}(x_{2})]^{2}} = x_{2}^{-p_{-1}-2s_{1}}(c_{0} + c_{1}x_{2} + c_{2}x_{2}^{2} + \dots)[cite: 1]$$

---

## Page 25

From (23B): $s_{1} + s_{2} = 1 - p_{-1} \implies -p_{-1} - 2s_{1} = s_{2} - s_{1} - 1 = -n - 1$[cite: 1]

$$y_{2}(x) = y_{1}(x)\int_{1}^{x}[c_{0}x_{2}^{-n-1} + c_{1}x_{2}^{-n} + c_{2}x_{2}^{-n+1} + \dots + c_{n}x_{2}^{-1} + \dots] dx_{2}[cite: 1]$$

This leads to a coefficient $c_{n}$ multiplying a $\ln(x)$ term[cite: 1]!

$$\implies y_{2}(x) = c_{n}y_{1}(x)\ln|x| + x^{s_{2}}(\text{power series})[cite: 1]$$

In summary, given the first solution $y_1(x)$ from root $s_{1}$, the second solution for $s_{2} = s_{1} - n$ takes the form[cite: 1]:

$$y_{2}(x) = y_{1}(x)\ln|x| + \sum_{j=-n}^{\infty} d_{j}x^{j+s_{1}} \quad \text{--- (25A)}[cite: 1]$$

### Example: Bessel Function with $n=0$
$$P(x) = x^{-1}, \quad Q(x) = 1[cite: 1]$$

$$p_{-1} = 1, \quad q_{0} = 1[cite: 1]$$

Indicial equation: $s^{2} = 0 \implies s = 0$[cite: 1]

From the first solution[cite: 1]:
$$y_{1}(x) = J_{0}(x) = 1 - \frac{x^{2}}{4} + \frac{x^{4}}{64} - O(x^{6})[cite: 1]$$

---

## Page 26

$$y_{2}(x) = J_{0}(x)\int^{x}\frac{\exp\left[-\int^{x_{2}}x_{1}^{-1}dx_{1}\right]dx_{2}}{\left[1 - \frac{x_{2}^{2}}{4} + \frac{x_{2}^{4}}{64} - \dots\right]^{2}}[cite: 1]$$

$$y_{2}(x) = J_{0}(x)\{\ln x + \frac{x^{2}}{4} + \frac{5x^{4}}{128} + \dots\}$$

This second solution is essentially (up to additive constants) the Neumann function $Y_{0}(x)$:

$$Y_{0}(x) = \frac{2}{\pi}[\ln x - \ln 2 + \gamma] J_{0}(x) + \frac{2}{\pi}\{\frac{x^{2}}{4} - \frac{3x^{4}}{128} + \dots\}$$

*($\gamma$ = Euler-Mascheroni constant)*

---

## Page 27

## Inhomogeneous Linear ODEs

Consider:
$$y^{\prime\prime} + P(x)y^{\prime} + Q(x)y = F(x) \quad \text{--- (27A)}[cite: 1]$$

### Variation of Parameters
Assume a solution of the form:
$$y(x) = u_{1}(x)y_{1}(x) + u_{2}(x)y_{2}(x)[cite: 1]$$

where $y_{1}, y_{2}$ are solutions of the homogeneous equation[cite: 1].

$$y^{\prime}(x) = u_{1}y_{1}^{\prime} + u_{2}y_{2}^{\prime} + (y_{1}u_{1}^{\prime} + y_{2}u_{2}^{\prime})[cite: 1]$$

We choose $u_{1}, u_{2}$ such that[cite: 1]:
$$y_{1}u_{1}^{\prime} + y_{2}u_{2}^{\prime} = 0 \quad \text{--- (27B)}[cite: 1]$$

$$\implies y^{\prime}(x) = u_{1}y_{1}^{\prime} + u_{2}y_{2}^{\prime}[cite: 1]$$

Differentiating again[cite: 1]:
$$y^{\prime\prime} = u_{1}y_{1}^{\prime\prime} + u_{2}y_{2}^{\prime\prime} + u_{1}^{\prime}y_{1}^{\prime} + u_{2}^{\prime}y_{2}^{\prime} \quad \text{--- (27C)}[cite: 1]$$

Substituting into (27A) and using homogeneous conditions $y_{1,2}^{\prime\prime} + P(x)y_{1,2}^{\prime} + Q(x)y_{1,2} = 0$[cite: 1]:
$$\implies u_{1}^{\prime}y_{1}^{\prime} + u_{2}^{\prime}y_{2}^{\prime} = F(x) \quad \text{--- (27D)}[cite: 1]$$

---

## Page 28

Equations (27B) & (27D) form an algebraic system for $u_{1}^{\prime}, u_{2}^{\prime}$ with determinant equal to the Wronskian $W \neq 0$[cite: 1]:

$$\begin{pmatrix} y_{1} & y_{2} \\ y_{1}^{\prime} & y_{2}^{\prime} \end{pmatrix} \begin{pmatrix} u_{1}^{\prime} \\ u_{2}^{\prime} \end{pmatrix} = \begin{pmatrix} 0 \\ F(x) \end{pmatrix}[cite: 1]$$

Integrating $u_{1}^{\prime}, u_{2}^{\prime}$ yields $u_{1}(x), u_{2}(x)$[cite: 1].

### Example:
$$(1-x)y^{\prime\prime} + xy^{\prime} - y = (1-x)^{2}[cite: 1]$$

Homogeneous solutions: $y_{1}(x) = x, \quad y_{2}(x) = e^{x}$[cite: 1]

(27B) gives: $x u_{1}^{\prime} + e^{x} u_{2}^{\prime} = 0$[cite: 1]

(27D) gives: $u_{1}^{\prime} + e^{x} u_{2}^{\prime} = F(x) = (1-x)$ *(written in standard form)*[cite: 1]

Solving:
$$u_{1}^{\prime} = 1 \implies u_{1}(x) = x[cite: 1]$$
$$u_{2}^{\prime} = -xe^{-x} \implies u_{2}(x) = (x+1)e^{-x}[cite: 1]$$

Particular Solution:
$$y_{p}(x) = u_{1}y_{1} + u_{2}y_{2} = x^{2} + x + 1[cite: 1]$$

General Solution[cite: 1]:
$$y(x) = C_{1}x + C_{2}e^{x} + x^{2} + 1[cite: 1]$$

---

## Page 29

## Sturm-Liouville Theory

A typical physics problem governed by an ODE involves:
- **Boundary Conditions (BCs)** that solutions must satisfy[cite: 1]
- **Parameters** adjusted to ensure BCs are satisfied[cite: 1]

### Example: Vibrating String
$$\frac{d^{2}\psi}{dx^{2}} + k^{2}\psi = 0[cite: 1]$$

Boundary Conditions: $\psi(0) = \psi(l) = 0$[cite: 1].

---

## Page 30


## Page 30

This problem defines a function space whose members are:
$$V = \{ \psi(x) \mid 0 \le x \le l, \, \psi(x) \text{ differentiable and } \psi(0)=\psi(l)=0 \}$$

ODE becomes the eigenvalue equation:
$$\mathcal{L}\psi = k^{2}\psi \quad \text{--- (30A)}$$

$$\mathcal{L} = -\frac{d^{2}}{dx^{2}} \quad \text{--- (30B)}$$

One way to solve eigenvalue equations is to convert into a matrix eigenvalue problem by choosing appropriate basis; this is the linear algebra approach. Instead, here we will use our ability to solve ODEs which is much easier as it is adapted to the ODE. Let us do that with Eq. (30A):

$$\frac{d^{2}\psi}{dx^{2}} + k^{2}\psi(x) = 0$$

$$\psi(x) = A\sin(kx) + B\cos(kx) \quad \text{general solution}$$

Boundary Conditions (BCs):
$$\psi(x=0) = 0 \implies B = 0$$

$$\psi(l) = 0 \implies A\sin(kl) = 0 \implies A = 0 \text{ (trivial solution) or } kl = n\pi$$

$$\implies k = \frac{n\pi}{l}$$

$$\psi(x) = \psi_{n}(x) = A\sin\left(\frac{n\pi x}{l}\right), \quad k^{2} = \frac{n^{2}\pi^{2}}{l^{2}}, \quad n = 1, 2, \dots$$

*($n=0$ only flips sign of $A$, producing a solution that is not linearly independent from the original. So we take $n > 0$)*

## Page 31

### Inner Product & Normalization
Inner product on $V$:
$$\langle f | g \rangle = \int_{0}^{l} f^{*}(x)g(x) \, dx[cite: 1]$$

Demanding normalization $\langle \psi_{n} | \psi_{n} \rangle = 1$[cite: 1]:
$$\psi_{n}(x) = \sqrt{\frac{2}{l}}\sin\left(\frac{n\pi x}{l}\right)[cite: 1]$$

Solutions give real eigenvalues and orthogonal eigenfunctions[cite: 1]:
$$\langle \psi_{n} | \psi_{m} \rangle = \delta_{nm}[cite: 1]$$

---

## Page 32–33

## Hermitian Differential Operators

Consider the general second-order operator:
$$\mathcal{L} = p_{0}(x)\frac{d^{2}}{dx^{2}} + p_{1}(x)\frac{d}{dx} + p_{2}(x) \quad \text{--- (32A)}[cite: 1]$$

Generalized inner product with weight function $w(x)$ on $[a,b]$[cite: 1]:
$$\langle v | u \rangle = \int_{a}^{b} v^{*}(x) u(x) w(x) \, dx \quad \text{--- (33A)}[cite: 1]$$

An operator $\mathcal{L}$ is **Hermitian** (self-adjoint) if[cite: 1]:
$$\langle v | \mathcal{L}u \rangle = \langle \mathcal{L}v | u \rangle \quad \text{--- (33B)}[cite: 1]$$

---

## Page 34–36

### Boundary Conditions for Hermiticity
Integrating by parts twice yields[cite: 1]:
$$\int_{a}^{b} v^{*} \mathcal{L} u \, dx = [p_{0}(v^{*}u^{\prime} - (v^{*})^{\prime}u)]_{a}^{b} + \int_{a}^{b} (\mathcal{L}v)^{*} u \, dx \quad \text{--- (36)}[cite: 1]$$

For Hermiticity, boundary terms must vanish, requiring one of the following conditions[cite: 1]:
1. **Dirichlet Condition:** $u(a)=v(a)=u(b)=v(b)=0$[cite: 1]
2. **Neumann Condition:** $u^{\prime}(a)=v^{\prime}(a)=u^{\prime}(b)=v^{\prime}(b)=0$[cite: 1]
3. **Periodic Condition:** $v^{*}(b)u^{\prime}(b)-(v^{\prime}(b))^{*}u(b) = v^{*}(a)u^{\prime}(a)-(v^{\prime}(a))^{*}u(a)$[cite: 1]
4. **Vanishing Coefficients:** $p_{0}(a) = p_{0}(b) = 0$[cite: 1]

Condition for self-adjointness with standard weight $w(x)=1$[cite: 1]:
$$\frac{dp_{0}}{dx} = p_{1}(x)[cite: 1]$$

---

## Page 38–40

### Making Non-Self-Adjoint ODEs Self-Adjoint
If $p_{0}^{\prime}(x) \neq p_{1}(x)$, multiply the ODE by weight factor $w(x)$[cite: 1]:

$$w(x) = \exp\left[ \int^{x} \frac{p_{1}(x_{1}) - p_{0}^{\prime}(x_{1})}{p_{0}(x_{1})} dx_{1} \right] \quad \text{--- (39)}[cite: 1]$$

---

## Page 41

### Example: Laguerre Functions
$$\mathcal{L} = x\frac{d^{2}}{dx^{2}} + (1-x)\frac{d}{dx} \quad \text{on } [0, \infty)[cite: 1]$$

Here $p_{0}(x) = x$, $p_{1}(x) = 1-x$[cite: 1]. The required weight function is[cite: 1]:
$$w(x) = e^{-x}[cite: 1]$$

Inner product under which Laguerre polynomials are orthogonal[cite: 1]:
$$\langle v | u \rangle = \int_{0}^{\infty} v^{*}(x)u(x)e^{-x} \, dx[cite: 1]$$

---

## Page 42

### Example: Hermite Equation
$$\mathcal{L}y = -y^{\prime\prime} + 2xy^{\prime} = \lambda y \quad \text{on } (-\infty, \infty)[cite: 1]$$

Weight factor[cite: 1]:
$$w(x) = e^{-x^{2}}[cite: 1]$$

Scalar product[cite: 1]:
$$\langle f | g \rangle = \int_{-\infty}^{\infty} f^{*}(x)g(x)e^{-x^{2}} \, dx[cite: 1]$$

Recurrence relation for coefficients[cite: 1]:
$$a_{j+2} = \frac{2j - \lambda}{(j+1)(j+2)} a_{j}[cite: 1]$$

To ensure finite norm $\langle y | y \rangle < \infty$, the series must terminate into a polynomial, which requires quantized eigenvalues $\lambda = 2j$
