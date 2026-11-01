> ✍️ **Added by:** Sagar Shakya, 2026-10-30
# Differential Equations

Differential equations are the simplest way to characterize the laws governing the physics of a variety of systems, so a good understanding of them is indispensable for any student of physics.

### Differentiation is linear

Derivatives of any order are linear operations:

$$
\frac{d^n}{dx^n}\bigl(a\varphi(x)+b\psi(x)\bigr)
= a\frac{d^n\varphi}{dx^n}+b\frac{d^n\psi}{dx^n}.
$$

Hence the general differential operator

$$
\boxed{
\mathcal{L} \equiv \sum_{\nu=0}^{n} p_\nu(x)
\left(\frac{d^\nu}{dx^\nu}\right)
}
$$

is also linear, i.e.

$$
\mathcal{L}[a\varphi+b\psi]
= a\mathcal{L}\varphi+b\mathcal{L}\psi
$$

(check!).

> **Remark (Theory):**
>
> The check is immediate: each term \(p_\nu(x)\,d^\nu/dx^\nu\) is a derivative (linear) followed by multiplication by a fixed function (also linear), and a sum of linear operators is linear.

### Linear and homogeneous ODEs

**Linear ODE:**

$$
\mathcal{L}\varphi(x)=F(x)
$$

**Homogeneous ODE:**

$$
\mathcal{L}\varphi(x)=0
\quad
(\varphi \text{ appears to the same power in every term})
$$

**Inhomogeneous ODE:**

$$
\mathcal{L}\varphi(x)=F(x)
=F(x)(\varphi(x))^0
$$

### Non-uniqueness and superposition

Solutions of linear ODEs are in general not unique (without additional *boundary conditions*). Any linear combination of two solutions is another solution: if

$$
\mathcal{L}\varphi=0
\qquad \text{and} \qquad
\mathcal{L}\psi=0,
$$

then

$$
\mathcal{L}[a\varphi+b\psi]=0.
$$

### Order and degree

The **order** of an ODE is the order of its highest derivative; the **degree** is the power of that highest derivative.

> **Remark (Theory):**
>
> Superposition holds only for homogeneous linear equations. For \(\mathcal{L}y=F\neq 0\), the sum of two solutions solves the equation with source \(2F\), not \(F\). Instead, the difference of two solutions of the inhomogeneous equation solves the homogeneous one, so the general solution is
>
> $$
> y=y_{\text{hom}}+y_{\text{part}}.
> $$

---

**Reading suggestion:** Arfken/Weber, Sections 7.1–7.3.

### Methods to solve different kinds of DEs


### Linear first-order ODEs

As a class of ODEs with a general solution method, consider

$$
\frac{dy}{dx}+p(x)\,y=q(x).
\tag{2A}
$$

If the equation is *exact*, i.e. it can be simplified to

$$
\frac{d}{dx}\varphi(y,x)=0,
$$

then \(\varphi(y,x)=\text{const}\) is the solution.

If not, introduce an **integrating factor** \(\alpha(x)\):

$$
\alpha(x)\frac{dy}{dx}+\alpha(x)p(x)\,y=\alpha(x)q(x).
$$

We want the left-hand side to be a perfect differential,

$$
\frac{d}{dx}\bigl[\alpha(x)y(x)\bigr].
$$

This requires

$$
\begin{aligned}
\frac{d}{dx}[\alpha y]
&=\alpha\frac{dy}{dx}+\alpha p\,y\\
\alpha\frac{dy}{dx}+\frac{d\alpha}{dx}y
&=\alpha\frac{dy}{dx}+\alpha p\,y
\end{aligned}
$$

which gives

$$
\frac{d\alpha}{dx}=\alpha(x)\,p(x),
$$

which is a separable equation. Therefore,

$$
\int\frac{d\alpha}{\alpha}
=\int^x p(x')\,dx'
$$

and hence

$$
\boxed{
\alpha(x)=\exp\left[\int^x p(x')\,dx'\right]
}
$$

The original equation becomes

$$
\frac{d}{dx}[\alpha(x)y(x)]=\alpha(x)q(x),
$$

so

$$
\boxed{
y(x)=\frac{1}{\alpha(x)}
\left[
\int^x\alpha(x')q(x')\,dx'+C
\right]
\equiv y_2(x)+y_1(x)
}
$$

where

$$
\begin{aligned}
y_1(x)&=\frac{C}{\alpha(x)}
&&\text{solves the homogeneous equation }
\frac{dy}{dx}+p(x)y=0,\\[8pt]
y_2(x)&=\frac{1}{\alpha(x)}
\int^x\alpha(x')q(x')\,dx'
&&\text{particular solution / particular integral.}
\end{aligned}
$$

Thus the solution of equation (2A) is unique up to a constant \(C\) multiplying the homogeneous part.

#### The homogeneous first-order ODE has only one linearly independent solution

Consider

$$
y'(x)+p(x)y(x)=0.
$$

*Proof.* Let \(y_1(x),y_2(x)\) be two solutions. Then

$$
\frac{y_1'}{y_1}
=-p(x)
=\frac{y_2'}{y_2}
$$

which gives

$$
\ln y_1=\ln y_2+C
$$

and hence

$$
y_1=c\,y_2.
$$

Therefore, \(y_1,y_2\) are not linearly independent. \(\square\)

---

### ODEs with constant coefficients

As a warm-up to series solutions, consider the special case of an \(n\)th-order ODE with constant coefficients:

$$
\frac{d^n y}{dx^n}
+a_{n-1}\frac{d^{n-1}y}{dx^{n-1}}
+\dots
+a_1\frac{dy}{dx}
+a_0y=0.
\tag{4B}
$$

Try the solution form

$$
y(x)=e^{\alpha x}.
$$

This leads to

$$
\alpha^n+a_{n-1}\alpha^{n-1}
+\dots+a_1\alpha+a_0=0.
\tag{4A}
$$

If the algebraic equation (4A) has \(n\) non-repeating roots, then

$$
e^{\alpha_1x},\dots,e^{\alpha_nx}
$$

are \(n\) linearly independent solutions of equation (4B).

> **Remark (Theory):**
>
> Each substitution works because
>
> $$
> \frac{d^k}{dx^k}e^{\alpha x}
> =\alpha^k e^{\alpha x},
> $$
>
> so the ODE collapses to
>
> $$
> e^{\alpha x}\times
> \text{(polynomial in }\alpha\text{)}=0,
> $$
>
> and \(e^{\alpha x}\neq 0\).
>
> If a root \(\alpha\) is repeated \(m\) times, the additional independent solutions are
>
> $$
> xe^{\alpha x},\dots,x^{m-1}e^{\alpha x}.
> $$


> ✍️ **Added by:** Priya Yadav, Vivek Kumar Meena, 2026-10-30
## Second Order Homogeneous Linear ODEs

The general form of a second order linear ODE (SOLO, homogeneous case; the inhomogeneous case is commented on at the end) is

$$
\boxed{
y''(x)+P(x)\,y'(x)+Q(x)\,y(x)=0
}
\tag{5A}
$$

### Singular points of the SOLO

As a precursor to the series solution method, we classify ODEs using singularities. We will see that the nature of the singularities is intimately connected to the feasibility of finding series solutions. Given the SOLO (5A):

**Definition: Ordinary and singular points**

1. A point \(x_0\) such that \(P(x_0)\) and \(Q(x_0)\) are finite is an **ordinary point** of the ODE.
2. A point \(x_0\) such that \(P(x)\) or \(Q(x)\) diverges as \(x\to x_0\) is a **singular point** of the ODE.

**Definition: Regular and irregular singular points**

A singular point \(x_0\) is a **regular singular point** if, although \(P(x)\) or \(Q(x)\) diverges at \(x_0\), both

$$
(x-x_0)P(x)
\quad\text{and}\quad
(x-x_0)^2Q(x)
$$

remain finite as \(x\to x_0\).

It is an **irregular** ("essential") **singularity** if \(P(x)\) diverges faster than \(\dfrac{1}{x-x_0}\), or \(Q(x)\) diverges faster than \(\dfrac{1}{(x-x_0)^2}\), i.e.

$$
\boxed{
\lim_{x\to x_0}(x-x_0)P(x)=\infty
\quad\text{or}\quad
\lim_{x\to x_0}(x-x_0)^2Q(x)=\infty
}
$$

### Behaviour at infinity

The above definitions hold for every finite \(x_0\). To understand the behaviour as \(x\to\infty\), set

$$
z=\frac{1}{x}
$$

and consider \(W(z)=y(1/z)\). Given that \(y(x)\) satisfies (5A), \(W(z)\) satisfies

$$
\frac{d^2W}{dz^2}
+\underbrace{\frac{2z-P(z^{-1})}{z^2}}_{\tilde P(z)}
\frac{dW}{dz}
+\underbrace{\frac{Q(z^{-1})}{z^4}}_{\tilde Q(z)}
W(z)=0.
$$

We examine the behaviour of \(\tilde P(z),\tilde Q(z)\) at \(z=0\).

> **Remark (Theory: derivation)**
>
> With \(y(x)=W(1/x)\), one finds
>
> $$
> y'=-z^2W'
> $$
>
> and
>
> $$
> y''=z^4W''+2z^3W'.
> $$
>
> Substituting into \(y''+Py'+Qy=0\) and dividing by \(z^4\) gives the equation above.

**Example: Bessel's equation**

$$
x^2y''+xy'+(x^2-n^2)y=0
$$

where

$$
P(x)=\frac{1}{x},
\qquad
Q(x)=1-\frac{n^2}{x^2}.
$$

\(x=0\) is a singular point. It is a *regular* singular point because

$$
\lim_{x\to0}xP(x)=1,
\qquad
\lim_{x\to0}x^2Q(x)=-n^2.
$$

At infinity,

$$
\tilde P(z)=\frac{2z-z}{z^2}=\frac{1}{z},
$$

$$
\tilde Q(z)=\frac{1-n^2z^2}{z^4}.
$$

And

$$
\lim_{z\to0}z^2\tilde Q(z)=\infty.
$$

Hence \(z=0\) (i.e. \(x\to\infty\)) is an *irregular* singularity.

### Frobenius Method

Consider the homogeneous SOLO

$$
\frac{d^2y}{dx^2}+P(x)\frac{dy}{dx}+Q(x)y=0.
\tag{7A}
$$

We would like to solve (7A) by expressing \(y(x)\) as a power series in \(x\). One motivation is that \(y(x)\) often represents some physical function that we expect to be real analytic. We describe the method with a power series about \(x=0\) (general \(x=x_0\) is remarked on later).

### General form (Frobenius series)

$$
\boxed{
y(x)=x^s\sum_{j=0}^{\infty}a_jx^j
}
\qquad \text{with } a_0\neq0.
\tag{7B}
$$

The smallest power \(s\) and the coefficients \(a_j\) are to be determined by plugging (7B) into (7A).

### Steps

By uniqueness of power series, the coefficient of each power of \(x\) must vanish separately.

1. **Step 1:** Examine the coefficient of the *smallest* power of \(x\). This gives the **indicial equation** for \(s\).
2. **Step 2:** Consider the *second lowest* power of \(x\). This fixes (or constrains) \(a_1\).
3. **Step 3:** Consider the general term and demand that it vanishes. This gives a **recursion relation** for \(a_{j+2}\) (or \(a_{j+1}\)) in terms of earlier coefficients.

> **Remark (Theory: indicial equation in general)**
>
> If \(x=0\) is a regular singular point, write
>
> $$
> p_{-1}=\lim_{x\to0}xP(x),
> \qquad
> q_{-2}=\lim_{x\to0}x^2Q(x).
> $$
>
> The lowest power of \(x\) in (7A) gives
>
> $$
> \boxed{
> s(s-1)+p_{-1}s+q_{-2}=0.
> }
> $$

**Example: Simple harmonic oscillator**

$$
\frac{d^2y}{dx^2}+\omega^2y=0
\quad\Rightarrow\quad
P(x)=0,\quad Q(x)=\omega^2,
$$

so \(x=0\) is an ordinary point. Substituting (7B):

$$
\sum_{j=0}^{\infty}a_j(s+j)(s+j-1)x^{s+j-2}
+\omega^2\sum_{j=0}^{\infty}a_jx^{s+j}=0.
\tag{8A}
$$

**Step 1 (coefficient of \(x^{s-2}\)):**

$$
a_0s(s-1)=0
$$

with \(a_0\neq0\), the *indicial equation*, so

$$
\boxed{s=0\quad\text{or}\quad s=1.}
$$

**Step 2 (coefficient of \(x^{s-1}\)):**

$$
a_1(s+1)s=0.
$$

This is automatically satisfied for \(s=0\); if \(s=1\), then \(a_1=0\).

**Step 3 (coefficient of \(x^{s+j}\), \(j\geq0\)):**

$$
a_{j+2}(s+j+2)(s+j+1)+\omega^2a_j=0,
$$

so

$$
\boxed{
a_{j+2}=-a_j\frac{\omega^2}{(s+j+2)(s+j+1)}
}
\qquad \text{(recursion relation)}
\tag{8D}
$$

Once \(a_j\) is known, \(a_{j+2},a_{j+4},\dots\) are fixed.

**Case \(s=0\).**

\(a_1\) is arbitrary; take \(a_1=0\) (the odd series is anyway the \(s=1\) solution). Then

$$
a_3=a_5=a_7=\dots=0,
$$

and

$$
a_{j+2}=-a_j\frac{\omega^2}{(j+1)(j+2)}
$$

which gives

$$
a_2=-\frac{a_0\omega^2}{2!},
\qquad
a_4=+\frac{a_0\omega^4}{4!},
\qquad \dots
$$

In general,

$$
\boxed{
a_{2n}=\frac{(-1)^n\omega^{2n}}{(2n)!}a_0.
}
$$

Therefore,

$$
\begin{aligned}
y(x)\big|_{s=0}
&=a_0\left[
1-\frac{(\omega x)^2}{2!}
+\frac{(\omega x)^4}{4!}
-\frac{(\omega x)^6}{6!}
+\dots
\right]\\
&=\boxed{a_0\cos\omega x}.
\end{aligned}
$$

**Case \(s=1\).**

Here

$$
a_{j+2}=-a_j\frac{\omega^2}{(j+2)(j+3)},
$$

so

$$
a_{2n}=\frac{(-1)^n\omega^{2n}}{(2n+1)!}a_0
$$

and

$$
\begin{aligned}
y(x)\big|_{s=1}
&=a_0x\left[
1-\frac{(\omega x)^2}{3!}
+\frac{(\omega x)^4}{5!}
-\dots
\right]\\
&=\frac{a_0}{\omega}\left[
\omega x-\frac{(\omega x)^3}{3!}+\dots
\right]\\
&=\boxed{\frac{a_0}{\omega}\sin\omega x}.
\end{aligned}
$$

Hence the general solution is

$$
\boxed{
y(x)=c_1\cos\omega x+c_2\sin\omega x.
}
$$

### Remarks

1. The series solution should be substituted back into (7A) to ensure that errors in the calculation are detected.

2. A series solution may not always converge: sometimes the series satisfies the ODE formally but does not converge (the Legendre equation is an example, as we will see later).

3. We can also expand about \(x_0\neq0\):

   $$
   y(x)=\sum_{j=0}^{\infty}a_j(x-x_0)^{j+s}.
   $$

   Choosing \(x_0\) to be an ordinary point (not singular) is safe to ensure the existence of a series solution. Even in this case, we can expect divergence of the solution when

   $$
   |x-x_0|=|z_1-x_0|,
   $$

   where \(z_1\) is the nearest singular point to \(x_0\).

---

**Example: Bessel's equation**

The oscillator example was simple and gave two linearly independent solutions directly. Consider the more non-trivial case

$$
\boxed{
x^2y''+xy'+(x^2-n^2)y=0.
}
\tag{10A}
$$

Again take

$$
y(x)=\sum_{j=0}^{\infty}a_jx^{s+j}
$$

and substitute:

$$
\begin{aligned}
&\sum_j a_j(s+j)(s+j-1)x^{s+j}\\
&+\sum_j a_j(s+j)x^{s+j}\\
&+\sum_j a_jx^{s+j+2}\\
&-\sum_j a_jn^2x^{s+j}=0.
\end{aligned}
$$

**Lowest power \(x^s\):**

$$
a_0\bigl[s(s-1)+s-n^2\bigr]=0
$$

$$
s^2-n^2=0
$$

Hence,

$$
\boxed{s=+n,\quad s=-n.}
\tag{11A}
$$

**Second lowest power \(x^{s+1}\):**

$$
a_1\bigl[(s+1)s+(s+1)-n^2\bigr]=0
$$

or

$$
a_1\bigl[(s+1)^2-n^2\bigr]=0.
$$

For \(s=\pm n\), \((s+1)^2-n^2=(n\pm1)^2-n^2\neq0\) in general, therefore

$$
\boxed{a_1=0.}
\tag{11B}
$$

**General term \(x^{s+j}\):**

$$
\begin{aligned}
&a_j(s+j)(s+j-1)+a_j(s+j)\\
&\qquad+a_{j-2}-a_jn^2=0
\end{aligned}
$$

which gives

$$
a_j\bigl[n^2-(s+j)^2\bigr]=a_{j-2}.
$$

That is,

$$
\boxed{
a_{j+2}=\frac{-a_j}{(s+j+2)^2-n^2}.
}
\tag{12A}
$$

Since \(a_1=0\), all odd coefficients vanish:

$$
a_1=a_3=\dots=0.
$$

**Case \(s=+n\).**

Then

$$
a_{j+2}=\frac{-a_j}{(j+2)(j+2+2n)},
$$

which gives

$$
a_2=\frac{-a_0\,n!}{2^2\,1!\,(n+1)!},
$$

$$
a_4=\frac{a_0\,n!}{2^4\,2!\,(n+2)!},
\qquad \dots
$$

In general,

$$
\boxed{
a_{2p}=\frac{(-1)^p\,a_0\,n!}{2^{2p}\,p!\,(n+p)!}.
}
$$

Therefore,

$$
y(x)=a_0\,2^n\,n!
\sum_{j=0}^{\infty}
\frac{(-1)^j}{j!\,(n+j)!}
\left(\frac{x}{2}\right)^{n+2j}.
$$

Taking

$$
a_0=\frac{1}{2^nn!}
$$

gives

$$
\boxed{
y(x)=J_n(x)
}
\qquad
\text{(Bessel function of the first kind).}
$$

**Case \(s=-n\).**

From (12A),

$$
\begin{aligned}
a_{j+2}
&=\frac{-a_j}{(j+2-n)^2-n^2}\\
&=\frac{-a_j}{(j+2)(j+2-2n)}.
\end{aligned}
$$

When \(j+2=2n\), \(a_{j+2}\) blows up. So the series solution fails for \(s=-n\), and *only one solution is obtained for Bessel's equation* (for integer \(n\)).

> **Remark (Theory)**
>
> The two roots differ by \(2n\). If \(2n\) is not an integer, the \(s=-n\) series also works and gives \(J_{-n}(x)\). The breakdown above is the integer-difference case, treated by Fuchs' theorem below.

> ✍️ **Added by:** Jigyasa Rana, 2026-10-31
## Fuchs' Theorem

### When does a series solution work? (Heuristic analysis)

- SHO equation, \(x=0\): an ordinary (non-singular) point \(\Rightarrow\) 2 linearly independent solutions.
- Bessel equation, \(x=0\): a regular singular point \(\Rightarrow\) only 1 solution from the series.

So, seemingly, singular points have some influence. Consider

$$
y''-\frac{6}{x^2}y=0
\tag{13A}
$$

$$
y''-\frac{6}{x^3}y=0
\tag{13B}
$$

$$
y''+\frac{1}{x}y'-\frac{b^2}{x^2}y=0
\tag{13C}
$$

$$
y''+\frac{1}{x^2}y'-\frac{b^2}{x^2}y=0
\tag{13D}
$$

**Equation (13A).**

The indicial equation is

$$
s(s-1)-6=0,
$$

i.e.

$$
s^2-s-6=0,
$$

so \(s=3\) or \(s=-2\).

The equation is homogeneous in \(x\) (each term scales as \(x^{-2}\)), so there is no recurrence relation, and \(y=x^s\) gives the two solutions

$$
\boxed{
y=x^3,\qquad y=x^{-2}.
}
$$

Note that one of them diverges at \(x=0\). Here \(x=0\) is a regular singular point.

**Equation (13B).**

It differs from (13A) by one power of \(x\) (\(x=0\) is an irregular singularity). The lowest-power condition gives

$$
-6a_0=0,
$$

but \(a_0\neq0\). Therefore there is **no series solution**.

**Equation (13C).**

Here \(x=0\) is a regular singularity. The indicial equation is

$$
s^2-b^2=0,
$$

giving

$$
s=\pm b.
$$

By homogeneity, the two solutions are

$$
\boxed{
y=x^b,\qquad y=x^{-b}.
}
\tag{14A}
$$

**Equation (13D).**

This only increases the power in the \(y'\) coefficient from \(-1\) to \(-2\) (irregular singularity at \(x=0\)). The indicial equation gives \(s=0\) and the recurrence relation is

$$
\boxed{
a_{j+1}=a_j\frac{b^2-j(j-1)}{j+1}.
}
$$

Then

$$
\begin{aligned}
\lim_{j\to\infty}\left|\frac{a_{j+1}}{a_j}\right|
&=\lim_{j\to\infty}\frac{j(j-1)}{j+1}\\
&\to\infty.
\end{aligned}
$$

So the power series solution blows up (it has zero radius of convergence), unless \(b\) is chosen such that

$$
b^2=j_{\max}(j_{\max}-1),
$$

in which case the series terminates.

---

### Statement of the theorem

**Theorem (Fuchs)**

A Frobenius series expansion about an ordinary point or a regular singular point of a SOLO leads to at least one solution of the ODE.

Proving Fuchs' theorem rigorously is somewhat cumbersome (a note is provided on Google Classroom). The key idea is to ask when the series solution converges; unsurprisingly this depends on the behaviour of \(xP(x)\) and \(x^2Q(x)\), especially their Taylor expansions in the region of convergence.

### Cases

When expanding about a regular singular or ordinary point (with indicial roots \(s_1\geq s_2\)):

1. If the solutions of the indicial equation **differ by a non-integer**, Frobenius produces **two independent solutions**.

2. If the solutions of the indicial equation are **separated by an integer** (including 0), only **one solution is guaranteed**: the *larger* of the two roots definitely gives a solution.

Bessel's equation with integer \(n\) is the second case: \(s=\pm n\) differ by \(2n\), and only the \(s=+n\) root gave a solution.

> **Remark (Theory)**
>
> In the second case the second solution generally contains a logarithm,
>
> $$
> y_2=y_1\ln x+\dots
> $$
>
> (derived in the next subsection, beyond page 20).
>
> Also, a Frobenius series about \(x_0\) converges at least up to the nearest other singular point of the ODE in the complex plane.

> ✍️ **Added by:** Anushree Srivastava, 2026-11-01

## How to find other solution when Frobenius finds only one

We now develop a method to find the other solution by exploiting some general properties of SOLOs. To this end, we briefly introduce the linear algebra of functions.

### Concept of Wronskian

#### Linear algebra of functions

1. A function \(f(x)\) that is square-integrable, i.e.

   $$
   \int_{-\infty}^{\infty}dx\,|f(x)|^2<\infty,
   $$

   is a vector in an infinite-dimensional vector space, with column-vector representation

   $$
   f(x)\leftrightarrow
   \bigl(
   \dots,f(-x_N),f(-x_{N-1}),\dots,
   f(0),f(x_1),\dots,f(x_N),\dots
   \bigr)^T.
   $$

2. The **inner product** of two functions:

   $$
   (f(x),g(x))=\langle f|g\rangle
   =\int dx\,f^*(x)\,g(x).
   $$

3. Two functions \(\varphi_1(x),\varphi_2(x)\) are **orthogonal** if

   $$
   \langle\varphi_1|\varphi_2\rangle=0.
   $$

4. A set of functions \(\{\varphi_1(x),\dots,\varphi_n(x)\}\) is **linearly independent** if

   $$
   \sum_\lambda k_\lambda\varphi_\lambda(x)=0
   $$

   has only one solution,

   $$
   k_1=k_2=\dots=k_n=0.
   $$

   If not, the set is linearly dependent.

5. If the set is mutually orthogonal \(\Rightarrow\) linearly independent.

   *Proof.* Consider

   $$
   \Psi(x)=\sum_\lambda k_\lambda\varphi_\lambda
   $$

   (with the \(\varphi_\lambda\) mutually orthogonal and non-zero). Then

   $$
   \begin{aligned}
   \langle\Psi|\Psi\rangle
   &=\sum_\lambda |k_\lambda|^2
   \langle\varphi_\lambda|\varphi_\lambda\rangle\\
   &=0 \quad \text{if }\Psi(x)=0.
   \end{aligned}
   $$

   Therefore,

   $$
   \boxed{k_\lambda=0\qquad\forall\lambda.}
   $$

   \(\square\)

#### The Wronskian

Now consider a set of solutions \(\{\varphi_1,\dots,\varphi_n\}\) of an ODE. If the set is linearly dependent, there exist \(k_\lambda\), not all zero, with

$$
\sum_{\lambda=1}^n k_\lambda\varphi_\lambda(x)=0
$$

for all \(x\). Differentiating repeatedly:

$$
\begin{aligned}
&\sum_\lambda k_\lambda\varphi_\lambda(x)=0,\\
&\sum_\lambda k_\lambda\varphi_\lambda'(x)=0,\\
&\qquad\vdots\\
&\sum_\lambda k_\lambda\varphi_\lambda^{(n-1)}(x)=0.
\end{aligned}
$$

These are homogeneous linear equations for the variables \(k_\lambda\), valid for all \(x\). A non-trivial solution \(k_\lambda\) (i.e. not all \(k_\lambda=0\), as required for linear dependence) exists only if

$$
\boxed{
W(x)=
\det
\begin{pmatrix}
\varphi_1&\varphi_2&\cdots&\varphi_n\\
\varphi_1'&\varphi_2'&\cdots&\varphi_n'\\
\vdots&&&\vdots\\
\varphi_1^{(n-1)}&\varphi_2^{(n-1)}&\cdots&\varphi_n^{(n-1)}
\end{pmatrix}
=0
}
\qquad\text{(Wronskian)}
$$

Therefore:

- If the Wronskian \(W\neq0\) \(\Rightarrow\) linear independence.
- If \(W=0\) for all \(x\in[a,b]\), then \(\{\varphi_\lambda(x)\}\) is linearly dependent over \([a,b]\).

> **Remark (Theory)**
>
> The statement "\(W\equiv0\Rightarrow\) dependent" holds for *solutions of the same linear ODE*, which is the case used here. For arbitrary functions, \(W\equiv0\) does not by itself imply dependence (e.g. \(x^2\) and \(x|x|\) have \(W\equiv0\) but are independent on \(\mathbb R\)).

**Example**

**1) SHO solutions**

\(\varphi_1=\sin\omega x\), \(\varphi_2=\cos\omega x\):

$$
\begin{aligned}
W&=
\det
\begin{pmatrix}
\sin\omega x&\cos\omega x\\
\omega\cos\omega x&-\omega\sin\omega x
\end{pmatrix}\\
&=-\omega\sin^2\omega x-\omega\cos^2\omega x\\
&=-\omega\neq0\qquad\forall x.
\end{aligned}
$$

So \(\varphi_1,\varphi_2\) are linearly independent.

**2)**

\(\dfrac{d^2\varphi}{dx^2}=\varphi(x)\) has solutions

$$
\varphi_1=e^x,\qquad \varphi_2=e^{-x}.
$$

Their Wronskian is

$$
\begin{aligned}
W&=
\det
\begin{pmatrix}
e^x&e^{-x}\\
e^x&-e^{-x}
\end{pmatrix}\\
&=-1-1=-2\neq0.
\end{aligned}
$$

So \(\{e^x,e^{-x}\}\) is linearly independent.

But consider the set \(\{e^x,e^{-x},\cosh x\}\):

$$
W=
\det
\begin{pmatrix}
e^x&e^{-x}&\cosh x\\
e^x&-e^{-x}&\sinh x\\
e^x&e^{-x}&\cosh x
\end{pmatrix}
=0
\qquad\forall x.
$$

(The first and third rows are identical.)

So the set is linearly dependent, as

$$
\cosh x-\frac{e^x+e^{-x}}{2}=0.
$$

#### A second order equation has only two linearly independent solutions

Let \(\{y_1,y_2,y_3\}\) be three solutions of

$$
y''+P(x)y'+Q(x)y=0.
$$

The Wronskian of a pair \(\{y_j,y_k\}\) is

$$
W_{jk}=y_jy_k'-y_j'y_k,
$$

and note that

$$
W_{jk}'=y_jy_k''-y_j''y_k.
$$

From the ODE, for \(j\) and \(k\):

$$
\frac{y_j''}{y_j}
+P\frac{y_j'}{y_j}
=-Q(x)
=\frac{y_k''}{y_k}
+P\frac{y_k'}{y_k}.
$$

Multiplying by \(y_jy_k\) and rearranging,

$$
\begin{aligned}
&(y_j''y_k-y_k''y_j)
+P(x)(y_j'y_k-y_k'y_j)=0\\
&\Rightarrow -W_{jk}'-P(x)W_{jk}=0.
\end{aligned}
$$

Therefore,

$$
\boxed{
W_{jk}'=-P(x)\,W_{jk}.
}
\tag{19A}
$$

Now consider the full Wronskian of \(\{y_1,y_2,y_3\}\). Expanding along the second row,

$$
\begin{aligned}
W&=
\det
\begin{pmatrix}
y_1&y_2&y_3\\
y_1'&y_2'&y_3'\\
y_1''&y_2''&y_3''
\end{pmatrix}\\
&=-y_1'W_{23}'+y_2'W_{13}'-y_3'W_{12}'.
\end{aligned}
$$

Using (19A),

$$
W=P(x)\bigl(
y_1'W_{23}-y_2'W_{13}+y_3'W_{12}
\bigr).
$$

This can be written as

$$
W=P(x)
\det
\begin{pmatrix}
y_1&y_2&y_3\\
y_1'&y_2'&y_3'\\
y_1'&y_2'&y_3'
\end{pmatrix}
=0
$$

(two identical rows).

So \(W=0\) and \(\{y_1,y_2,y_3\}\) are linearly dependent. Hence,

$$
\boxed{
\text{A linear second order homogeneous ODE has at most 2 linearly independent solutions.}
}
$$
