# PH 502 Course Toolbox

A shared, running reference for Mathematical Methods of Physics, built up over the semester by the class itself. Each week, the rotating Scribing/Toolbox team adds entries under the relevant biweekly module document.

## How to use this repository

- **Find your module and week** and add your entry to the appropriate biweekly file (`week1-2.md`, `week3-4.md`, etc.), at the end of the existing entries.
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

## Course Modules & Biweekly Scribe Notes

### Module 0: Foundational Toolkit

*(self-study — add entries here if you find something from the mock quiz worth recording)*

---

### Module 1: Complex Analysis

#### [Week 1–2](week1-2.md)
Entries and topics covered during Weeks 1 and 2:
- **Complex Numbers in Polar Form & Foundations** (Lokesh Sati — 2026-08-16)
  - Complex Numbers in Polar (Exponential) Form
  - Euler's Formula & Basic Properties
  - De Moivre's Theorem
  - Equations of Curves in Complex Plane (circles, rays, Apollonius circles)
  - Powers and Roots of Complex Numbers
- **Elementary Complex Functions** (Souryadeep Lenka — 16/08/2026)
  - Elementary Complex Functions: Real and imaginary parts decomposition
  - Exponential, Trigonometric, and Hyperbolic Functions
  - Multivalued Functions (Logarithmic, Inverse Trigonometric & Hyperbolic)
- **Basis of Analysis & Differential Calculus** (Shravani — 16/08/2026)
  - Neighborhood of $z_0$, Open sets, Connected sets
  - Limit of a Function
  - Continuity
  - Differentiation
  - Cauchy-Riemann Condition (derivation along orthogonal paths)
- **Complex Differentiability, Analyticity & Harmonic Functions** (Dhani Sangwan — 16/08/2026)
  - Definition of Derivative & Cauchy-Riemann Conditions (Cartesian, Polar, Wirtinger)
  - Necessary vs. Sufficient Conditions for Differentiability
  - Analyticity, Entire Functions, and Liouville's Theorem
  - Harmonic Functions, Laplace Equation, and Orthogonal Trajectories
  - Classification Table of Analytic vs. Non-Analytic Functions
- **Analytic Functions Properties & Verification** (Abhi Balai — 16/08/2026)
  - Properties of Analytic Functions (arithmetic operations, composition, singularities)
  - Sufficient Conditions for Analyticity
  - Worked Verification for $f(z) = z^2$
- **Sequences, Series & Convergence Tests** (Divyanshu Kumar — 2026-08-23)
  - Sequences, Series & Convergence Tests (Ratio and Root Tests)
  - Taylor Series Representation & Radius of Convergence
  - Behaviour on the Circle of Convergence (Cesàro mean)
  - Entire Functions and Their Order $\rho$
- **Cauchy's Integral Theorem** (Sunil Bhadu — 2026-08-23)
  - Introduction and Properties (path independence, rubber band distortion)
  - Proof using Green's Theorem and Cauchy-Riemann Conditions
  - Limitations, Conditions, and Example Evaluation
- **Deformation of Cauchy's Theorem & Cauchy's Integral Formula** (Naveen Kumar Deegwal — 2026-08-23)
  - Deformation of Cauchy's Theorem across annular contours
  - Cauchy's Integral Formula
- **Higher-Order Derivatives, Taylor & Laurent Expansion Theorems** (Mansi Chaudhary — 2026-08-23)
  - Higher-Order Derivatives & Cauchy's Inequality
  - Taylor Series Expansion Theorem (via Cauchy's Integral Formula)
  - Laurent Expansion Theorem for Annular Regions

---

#### [Week 3–4](week3-4.md)
Entries and topics covered during Weeks 3 and 4:
- **Singularities, Poles & Residues** (Nikhil Chaudhary — 31/08/2026)
  - Definition and Classification of Isolated Singularities
  - Removable Singularities
  - Simple Poles and Laurent Series Singular Part
  - Residue Formula and $g(a)/h'(a)$ Shortcut
  - Extension: Higher-Order (Multiple) Poles
- **Essential Singularities & Laurent Series Convergence** (Drishya Verma — 01/09/2026)
  - Essential Singularity
  - Laurent Series Region of Validity (annular region from first principles)
  - Singularity at Infinity Setup
- **Contour Integration, Residue Calculus & Special Integrals** (Jaskirat — 12/09/2026)
  - Cauchy's Residue Theorem
  - Real Trigonometric Integrals over $[0, 2\pi]$ (unit-circle substitution)
  - Integrals of Decaying Rational Functions over $(-\infty, \infty)$
  - Integrals with Complex Exponentials (Jordan's Lemma)
  - Indented Contours and the Cauchy Principal Value (CPV) with Fractional Residue Lemma
  - Residue at Infinity
  - Multivalued Functions, Branch Points, and Branch Cuts

---

### Module 2: Integral Transforms

*(self-study / upcoming entries)*

---

### Module 3: Differential Equations of Physics

*(self-study / upcoming entries)*

---

### Module 4: Linear Algebra

*(self-study / upcoming entries)*

---

## Sample Entry

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
