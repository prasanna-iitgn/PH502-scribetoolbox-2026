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

*(next entry goes here)*

---

## Module 2: Integral Transforms

---

## Module 3: Differential Equations of Physics

---

## Module 4: Linear Algebra

---
