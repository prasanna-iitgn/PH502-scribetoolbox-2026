# Linear Vector Spaces, Dirac Notation, and Matrix Algebras

## Table of Contents

* 1\. Fundamentals of Linear Vector Spaces and Dirac Notation

* 2\. Dual Spaces, Inner Products, Basis Sets, and Dimensionality

* 3\. Orthonormal Basis Sets, Gram-Schmidt Procedure, and Vector Inequalities

* 4\. Pauli Matrices, Matrix Exponentials, 3D Rotations, and Secular Equations

### 1. Fundamentals of Linear Vector Spaces and Dirac Notation

A Linear Vector Space (LVS) $V$ over a field $\mathbb{F}$ ($\mathbb{R}$ or $\mathbb{C}$) is a set of elements (vectors) closed under vector addition and scalar multiplication.

#### Vector Addition Axioms

Vector addition defines a mapping $V \times V \to V$ satisfying:

* **Commutativity:** $\vert{}\phi\rangle + \vert{}\chi\rangle = \vert{}\chi\rangle + \vert{}\phi\rangle$

* **Associativity:** $\vert{}\phi\rangle + (\vert{}\psi\rangle + \vert{}\chi\rangle) = (\vert{}\phi\rangle + \vert{}\psi\rangle) + \vert{}\chi\rangle$

* **Existence of a Unique Null Vector** $\vert{}\Omega\rangle = 0$**:** $\vert{}\phi\rangle + \vert{}\Omega\rangle = \vert{}\phi\rangle$

* **Existence of a Unique Additive Inverse** $-\vert{}\phi\rangle$**:** $\vert{}\phi\rangle + (-\vert{}\phi\rangle) = \vert{}\Omega\rangle$

#### Scalar Multiplication Axioms

Scalar multiplication defines a mapping $\mathbb{F} \times V \to V$ for scalars $a, b \in \mathbb{F}$ satisfying:

* **Closure:** $a\vert{}\psi\rangle \in V$

* **Scalar Associativity:** $a(b\vert{}\psi\rangle) = (ab)\vert{}\psi\rangle$

* **Distributivity:** $(a+b)\vert{}\psi\rangle = a\vert{}\psi\rangle + b\vert{}\psi\rangle$ and $a(\vert{}\psi\rangle + \vert{}\phi\rangle) = a\vert{}\psi\rangle + a\vert{}\phi\rangle$

* **Scalar Identity and Zero:** $1\vert{}\psi\rangle = \vert{}\psi\rangle$ and $0\vert{}\psi\rangle = \vert{}\Omega\rangle = 0$

#### Dirac Notation & Examples

* **Dirac Notation:** Introduced by Paul Dirac for quantum mechanics, representing abstract vectors as "ket" vectors $\vert{}\psi\rangle$.

* **Concrete Examples of LVS:**

  * **Euclidean Space (**$\mathbb{R}^3$**):** Represented by column vectors $\vert{}\mathbf{v}\rangle = \begin{pmatrix} x \\ y \\ z \end{pmatrix}$.

  * **Differential Equation Solutions:** The set of solutions to $\frac{d^2y}{dt^2} = -\omega^2 y$ forms a 2D LVS spanned by linearly independent basis functions $y_1(t) = e^{i\omega t}$ and $y_2(t) = e^{-i\omega t}$ (or $\cos(\omega t)$ and $\sin(\omega t)$).

  * **Tuple Spaces:** Ordered real or complex $n$-tuples ($\mathbb{R}^n, \mathbb{C}^n$).

  * **Matrix Spaces:** Set of all $n \times n$ square matrices under elementwise addition.

  * **Discrete/Binary Field Spaces:** Spaces defined over binary fields $\{0, 1\}$ with rules $1+0=1$, $1+1=0$, $0 \times 1 = 0$, and $1 \times 1 = 1$.

> ✍️ **Added by:** Saptam, 2026-11-08

### 2. Dual Spaces, Inner Products, Basis Sets, and Dimensionality

The concept of dual spaces allows associating scalars with vectors, generalizing metric concepts like vector lengths and dot products.

#### Dual Space ($\tilde{V}$)

The collection of all linear functionals $S_\phi[\cdot]$ mapping vectors to scalars forms a dual vector space $\tilde{V}$. Elements of $\tilde{V}$ are denoted as "bra" vectors $\langle\phi\vert{}$.

* **Dual functional properties:** $S_{\phi+\chi}[\cdot] = S_\phi[\cdot] + S_\chi[\cdot]$ and $S_{a\phi}[\cdot] = a^* S_\phi[\cdot]$

* **Self-Duality:** $\tilde{\tilde{V}} \equiv V$. In 3D Euclidean space, ket vectors are $3 \times 1$ columns while bra vectors are represented as $1 \times 3$ row vectors $\langle\psi\vert{} = (d \ e \ f)$.

#### Inner Product & Norm

A bilinear rule $\langle\phi\vert{}\psi\rangle$ pairing a bra and a ket to produce a scalar:

* **Linearity in Ket:** $\langle\phi\vert{} ( \vert{}\psi\rangle + \vert{}\chi\rangle ) = \langle\phi\vert{}\psi\rangle + \langle\phi\vert{}\chi\rangle$ and $\langle\phi\vert{} a\psi\rangle = a\langle\phi\vert{}\psi\rangle$

* **Anti-linearity in Bra:** $\langle a\phi\vert{}\psi\rangle = a^*\langle\phi\vert{}\psi\rangle$

* **Conjugate Symmetry:** $\langle\phi\vert{}\psi\rangle = \langle\psi\vert{}\phi\rangle^*$

* **Norm of a Vector:** Defines magnitude in an inner-product space:
  
$$
\vert{}\vert{}\psi\vert{}\vert{} = \sqrt{\langle\psi\vert{}\psi\rangle}
$$

#### Basis Sets & Dimensionality

* **Linear Independence:** A set $\{\vert{}\psi_k\rangle\}$ is linearly independent if $\sum_k a_k \vert{}\psi_k\rangle = 0 \implies a_k = 0$ for all $k$.

* **Spanning Property:** A set spans $V$ if any $\vert{}\gamma\rangle \in V$ can be expanded as $\vert{}\gamma\rangle = \sum_k b_k \vert{}\psi_k\rangle$.

* **Dimensionality** $n$**:** The number of basis vectors in an LVS is unique. Every $n$-dimensional inner-product LVS is isomorphic to $\mathbb{R}^n$ or $\mathbb{C}^n$.

* **Infinite-Dimensional Spaces:** Spaces with no finite basis, such as the space of all polynomials of a complex variable $z$.

> ✍️ **Added by:** Arpita, 2026-11-09

### 3. Orthonormal Basis Sets, Gram-Schmidt Procedure, and Vector Inequalities

Orthonormal bases provide standardized coordinate frames where vector expansions simplify into component projections.

#### Orthonormality & Completeness

* **Orthonormality Condition:** $\langle\phi_j\vert{}\phi_k\rangle = \delta_{jk}$ (Kronecker delta).

* **Completeness Relation (Resolution of Identity):**
  
$$
\sum_j \vert{}\phi_j\rangle\langle\phi_j\vert{} = I
$$

* **Operator Action:** The outer product ket-bra $\vert{}\phi\rangle\langle\psi\vert{}$ acts on a ket $\vert{}\gamma\rangle$ via $(\vert{}\phi\rangle\langle\psi\vert{})\vert{}\gamma\rangle = \vert{}\phi\rangle(\langle\psi\vert{}\gamma\rangle)$ to yield a new ket.

* **Component Expansion:** For $\vert{}\psi\rangle = \sum_k c_k \vert{}\phi_k\rangle$, the expansion coefficients are projections $c_k = \langle\phi_k\vert{}\psi\rangle$.

#### Gram-Schmidt Orthonormalization

Constructs an orthonormal basis $\{\vert{}\phi_k\rangle\}$ from an arbitrary linearly independent set $\{\vert{}\psi_k\rangle\}$:

1. **Normalize the first vector:**
   
$$
\vert{}\phi_1\rangle = \frac{\vert{}\psi_1\rangle}{\sqrt{\langle\psi_1\vert{}\psi_1\rangle}}
$$

2. **Iteratively subtract projections along prior orthonormal directions and normalize:**
   
$$
\vert{}\phi_k\rangle = \frac{\vert{}\psi_k\rangle - \sum_{j=1}^{k-1}\langle\phi_j\vert{}\psi_k\rangle\vert{}\phi_j\rangle}{\left[\langle\psi_k\vert{}\psi_k\rangle - \sum_{j=1}^{k-1}\vert{}\langle\phi_j\vert{}\psi_k\rangle\vert{}^2\right]^{1/2}}
$$

#### Change of Basis & Inequalities

* **Basis Transformations:** Coefficients transform between bases $\{\vert{}\phi_k\rangle\}$ and $\{\vert{}\chi_j\rangle\}$ via $c_k = \sum_j d_j \langle\phi_k\vert{}\chi_j\rangle$.

* **Parseval's Identity:** Inner products and norms are basis-independent: $\langle\psi_A\vert{}\psi_B\rangle = \sum_k c_k^* C_k = \sum_j d_j^* D_j$.

* **Cauchy-Schwarz Inequality:**
  

$$
\vert{}\langle\phi\vert{}\psi\rangle\vert{} \le \vert{}\vert{}\phi\vert{}\vert{}\,\vert{}\vert{}\psi\vert{}\vert{}
$$

  
  *(Equality holds if and only if* $\vert{}\phi\rangle$ *and* $\vert{}\psi\rangle$ *are linearly dependent)*

* **Triangle Inequality:**
  

$$
\vert{}\vert{}\phi + \psi\vert{}\vert{} \le \vert{}\vert{}\phi\vert{}\vert{} + \vert{}\vert{}\psi\vert{}\vert{}
$$

> ✍️ **Added by:** Lokesh, 2026-11-09

### 4. Pauli Matrices, Matrix Exponentials, 3D Rotations, and Secular Equations

Matrices can be viewed either as elements of an $n^2$-dimensional LVS or as linear operators acting on an $n$-dimensional LVS.

#### Pauli Matrix Basis ($2 \times 2$ Matrices)

Any general matrix
$
M = \begin{pmatrix} a & b \\ c & d \end{pmatrix}
$
 can be expanded in the basis $\{I, \sigma_1, \sigma_2, \sigma_3\}$ as $M = \alpha_0 I + \vec{\alpha}\cdot\vec{\sigma}$:

$$
I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}, \quad \sigma_1 = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \quad \sigma_2 = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}, \quad \sigma_3 = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}
$$

* **Algebraic Identities:** Hermiticity ($\sigma_i^\dagger = \sigma_i$), $\sigma_i^2 = I$, eigenvalues $\pm 1$.

* **Product Rule:** $\sigma_k \sigma_l = \delta_{kl}I + i\epsilon_{klm}\sigma_m$.

* **Commutator:** $[\sigma_k, \sigma_l] = 2i\epsilon_{klm}\sigma_m$ and **Anti-commutator:** $\{\sigma_k, \sigma_l\} = 2\delta_{kl}I$.

* **Angular Momentum Algebra:** Generates $J_k = \frac{\sigma_k}{2}$ satisfying $[J_k, J_l] = i\epsilon_{klm}J_m$.

#### Matrix Exponentials & 3D Rotations

* **Matrix Exponential:** Defined via power series $e^M \equiv \sum_{n=0}^{\infty} \frac{M^n}{n!}$.

* **Closed Form for Pauli Vectors:**
  

$$
e^{i\vec{a}\cdot\vec{\sigma}} = I\cos a + i\frac{\vec{a}\cdot\vec{\sigma}}{a}\sin a
$$

* **General** $2 \times 2$ **Matrix Exponential:** $e^M = e^{\alpha_0}\left(I\cosh\alpha + \frac{\vec{\alpha}\cdot\vec{\sigma}}{\alpha}\sinh\alpha\right)$.

* **Translation Operators:** $e^{a \frac{d}{dx}} f(x) = f(x+a)$ acts as a spatial translation operator.

* **3D Rotations:** Rotations $R(\vec{n}, \psi)$ around unit axis $\vec{n}$ by angle $\psi$ are exponentiated generators:
  

$$
R(\vec{n}, \psi) = e^{i\vec{J}\cdot\vec{n}\psi}
$$

* **Rodrigues' Rotation Formula:** Explicit vector transformation under rotation:
  

$$
\vec{r}' = \cos\psi\,\vec{r} + (1-\cos\psi)(\vec{r}\cdot\vec{n})\vec{n} + \sin\psi(\vec{r}\times\vec{n})
$$

#### Eigenvalue Spectrum & Secular Equation

* **Characteristic Polynomial:** Calculated via $P_M(\lambda) = \det(\lambda I - M) = \lambda^n + c_1 \lambda^{n-1} + \dots + c_n = 0$.

* **Similarity Invariance:** Eigenvalues remain invariant under similarity transformations $M \mapsto S M S^{-1}$. Coefficients relate to trace invariants ($c_1 = -\text{Tr}(M)$ and $c_n = (-1)^n \det(M)$

> ✍️ **Added by:** Ritika, 2026-11-10
