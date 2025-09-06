# Cheat Sheet — Real & Complex Number Systems (Rudin, Ch.1)

## 1. Ordered Sets

- **Order relation** `<` on set S:
  1. For $x, y \in S$, exactly one of: $x < y$, $x = y$, $y < x$.
  2. **Transitivity**: $x < y$, $y < z \Rightarrow x < z$.
- **Supremum (sup)**: least upper bound.
- **Infimum (inf)**: greatest lower bound.
- **LUB property**: every non-empty, bounded-above subset has a supremum.

## 2. Fields

A **field F** = set with $+$ and $\cdot$ satisfying:

- **Addition axioms (A)**: (A1) Commutative, (A2) Associative, (A3) Additive identity $0$, (A4) Additive inverse.
- **Multiplication axioms (M)**: (M1) Commutative, (M2) Associative, (M3) Multiplicative identity $1 \neq 0$, (M4) Multiplicative inverse (for $x \neq 0$).
- **Distributive law (D)**: $x(y + z) = xy + xz$.
- **Examples**: $\mathbb{Q}, \mathbb{R}, \mathbb{C}$.

## 3. Ordered Fields

A **field F with an order** `<` such that:

1. $x > 0, y > 0 \Rightarrow x + y > 0$.
2. $x > 0, y > 0 \Rightarrow xy > 0$.

**Properties:**
- If $x \neq 0$, then $x^2 > 0$.
- $1 > 0$.
- **Archimedean property**: $\forall x > 0, y \in \mathbb{R}$, $\exists n \in \mathbb{N}$ s.t. $nx > y$.
- **Density**: $\forall x < y \in \mathbb{R}$, $\exists p \in \mathbb{Q}$ s.t. $x < p < y$.

## 4. The Real Numbers ℝ

- $\mathbb{R}$ = unique ordered field with **LUB property**.
- Contains $\mathbb{Q}$ as subfield.
- **nth root theorem**: $\forall x > 0 \in \mathbb{R}$, $\exists!$ $y \in \mathbb{R}$ s.t. $y^n = x$.

## 5. Extended Real Numbers

- $\mathbb{R} \cup \{+\infty, -\infty\}$.
- **Order**: $-\infty < x < +\infty$ $\forall x \in \mathbb{R}$.
- **Not a field**.

## 6. Complex Numbers ℂ

- Defined as pairs $(a, b)$, written $a + bi$.
- $i^2 = -1$.
- **Conjugate**: $z = a + bi \Rightarrow \bar{z} = a - bi$.
- **Absolute value**: $|z| = \sqrt{z\bar{z}} = \sqrt{a^2 + b^2}$.

**Properties:**
- $|zw| = |z||w|$.
- $|\text{Re } z| \leq |z|$.
- **Triangle inequality**: $|z + w| \leq |z| + |w|$.
- **Schwarz inequality**: $\left|\sum a_j \bar{b_j}\right|^2 \leq \left(\sum |a_j|^2\right)\left(\sum |b_j|^2\right)$.

## 7. Euclidean Space ℝᵏ

- **Elements**: $x = (x_1, \ldots, x_k)$.
- **Inner product**: $x \cdot y = \sum x_i y_i$.
- **Norm**: $|x| = \sqrt{x \cdot x}$.

**Properties:**
- **Schwarz inequality**: $|x \cdot y| \leq |x||y|$.
- **Triangle inequality**: $|x + y| \leq |x| + |y|$.

## 8. Construction of ℝ (Dedekind Cuts)

A **cut** $\alpha \subset \mathbb{Q}$ satisfies:

1. $\alpha \neq \emptyset, \alpha \neq \mathbb{Q}$.
2. **Downward closed**: $p \in \alpha, q < p \Rightarrow q \in \alpha$.
3. **No largest element**.

- **Define order**: $\alpha < \beta \Leftrightarrow \alpha \subset \beta$.
- **Define addition, multiplication** of cuts → get ordered field with LUB property.
- **Embed rationals**: $r^* = \{q \in \mathbb{Q} | q < r\}$.

## 🔑 Quick Symbols

- $\mathbb{Q}$ = rationals
- $\mathbb{R}$ = reals
- $\mathbb{C}$ = complex
- $\mathbb{N}$ = naturals
- $\mathbb{Z}$ = integers
- $\sup A$ = least upper bound of $A$
- $\inf A$ = greatest lower bound of $A$
- $\bar{z}$ = conjugate
- $|z|$ = modulus
- $x \cdot y$ = dot product
- $|x|$ = norm

---

👉 This gives you a **bird's eye view** with **notation and properties** for instant recall before exam.
# Rudin Chapter 2 — Basic Topology (Cheat Sheet)

## 1. Sets and Countability

### Functions and Mappings
- **Function (map)**: $f: A \to B$, with each $x \in A$ maps to unique $f(x) \in B$.
  - **Domain** = $A$, **Range** = $\{f(x): x \in A\}$.
  - **1–1 (Injective)**: $f(x_1) = f(x_2) \Rightarrow x_1 = x_2$.
  - **Onto (Surjective)**: Range = $B$.

### Set Equivalence and Cardinality
- **Equivalence of sets**: $A \sim B$ ⟺ ∃ bijection $f: A \to B$.
- **Cardinality**:
  - $J_n = \{1, \ldots, n\}$, $J = \{1, 2, 3, \ldots\}$.
  - **Finite** ⟺ $A \sim J_n$.
  - **Infinite** ⟺ not finite.
  - **Countable** ⟺ $A \sim J$.
  - **At most countable** ⟺ finite or countable.
  - **Uncountable** ⟺ neither.
- **Sequence**: function $f: J \to A$, usually written $\{x_n\}$.

### Set Operations
- **Union/Intersection**:
  - $\bigcup_{\alpha \in A} E_\alpha = \{x : \exists \alpha, x \in E_\alpha\}$.
  - $\bigcap_{\alpha \in A} E_\alpha = \{x : \forall \alpha, x \in E_\alpha\}$.
  - **Disjoint**: $A \cap B = \emptyset$.

### Key Theorems
- **2.8**: Infinite subset of countable set ⟹ countable.
- **2.12**: Countable union of countable sets ⟹ countable.
- **2.13**: $n$-tuples from countable set ⟹ countable. ⟹ $\mathbb{Q}$ is countable.
- **2.14**: $\{0,1\}^{\mathbb{N}}$ (all binary sequences) uncountable ⟹ $\mathbb{R}$ uncountable.

## 2. Metric Spaces

### Basic Definitions
- **Metric space** $(X, d)$ where $d: X \times X \to \mathbb{R}$ satisfies:
  1. $d(p,q) \geq 0$; $d(p,q) = 0$ ⟺ $p = q$.
  2. **Symmetry**: $d(p,q) = d(q,p)$.
  3. **Triangle inequality**: $d(p,q) \leq d(p,r) + d(r,q)$.

### Topological Concepts
- **Neighborhood**: $N_r(p) = \{q : d(p,q) < r\}$.
- **Limit point**: $p$ is limit of $E$ if every $N_r(p)$ has some $q \in E, q \neq p$.
- **Isolated point**: $p \in E$ not a limit point.
- **Closed set**: contains all its limit points.
- **Open set**: every point is interior.
- **Interior point**: ∃ $N_r(p) \subset E$.
- **Perfect**: closed + no isolated points.
- **Bounded**: ∃ $M, q$ with $d(p,q) < M$ ∀ $p \in E$.
- **Dense**: closure = whole space.
- **Closure**: $\bar{E} = E \cup E'$ (all points + limit points).

### Key Theorems
- **2.19**: Every neighborhood is open.
- **2.20**: Limit point ⟹ every neighborhood has ∞ many points of $E$.
- **2.22 (De Morgan)**: $(\bigcup E_\alpha)^c = \bigcap E_\alpha^c$, $(\bigcap E_\alpha)^c = \bigcup E_\alpha^c$.
- **2.23**: $E$ open ⟺ $E^c$ closed.
- **2.24**:
  - Union of opens = open.
  - Intersection of closeds = closed.
  - Finite intersection of opens = open.
  - Finite union of closeds = closed.
- **2.26 (Closure properties)**:
  - $\bar{E}$ is closed, smallest closed superset of $E$.
  - $E$ closed ⟺ $E = \bar{E}$.
- **2.28**: If $E \subset \mathbb{R}$ bounded above, $\sup E = \gamma \in \bar{E}$. If closed, $\gamma \in E$.
- **2.30**: **Relative openness**: $E \subset Y$ open in $Y$ ⟺ $E = Y \cap G$ for some open $G \subset X$.

## 3. Compact Sets

### Definition
- **Open cover**: $\{G_\alpha\}$ with $E \subset \bigcup G_\alpha$.
- **Compact**: Every open cover has finite subcover.

### Key Theorems
- **2.33**: Compactness is relative — $K \subset Y \subset X$. $K$ compact in $Y$ ⟺ $K$ compact in $X$.

## Quick Mnemonics ✅

- **Countable ⟹ listable** ($\mathbb{N}, \mathbb{Z}, \mathbb{Q}$).
- **Uncountable ⟹ diagonal** ($\mathbb{R}$).
- **Open ⟹ neighborhood inside**.
- **Closed ⟹ contains limits**.
- **Compact ⟹ every cover has a finite subcover**.

# Chapter 3 Cheat Sheet

## 1. The Basics: Sequences

- **Sequence:** An ordered list of numbers: $p_1, p_2, p_3, \ldots$
- **Convergence ($p_n \to p$ or $\lim_{n\to\infty} p_n = p$):**
  - **Simple Idea:** The terms $p_n$ get and stay arbitrarily close to a specific point $p$.
  - **Formal:** For every $\epsilon > 0$, there is an integer $N$ such that $d(p_n, p) < \epsilon$ for all $n > N$.
- **Key Facts:**
  - A convergent sequence has only **one limit**.
  - Every convergent sequence is **bounded**.
  - In $\mathbb{R}^k$, a sequence converges **if and only if** each of its component sequences converges.

## 2. Subsequences

- **Subsequence ($p_{n_k}$):** A sequence formed by taking some of the terms of $p_n$ in order (e.g., $p_2, p_5, p_9, \ldots$).
- **Key Facts:**
  - If $p_n \to p$, **every** subsequence also $\to p$.
  - **Bolzano-Weierstrass Theorem:** Every **bounded** sequence in $\mathbb{R}^k$ has a **convergent subsequence**.

## 3. Cauchy Sequences & Completeness

- **Cauchy Sequence:** A sequence where the terms get closer to **each other**.
  - **Formal:** For every $\epsilon > 0$, there is an integer $N$ such that $d(p_n, p_m) < \epsilon$ for all $n, m > N$.
- **Key Facts:**
  - **Every convergent sequence is Cauchy.**
  - **In $\mathbb{R}^k$ (and any complete space), every Cauchy sequence is convergent.**
- **Complete Metric Space:** A space where **Cauchy $\Rightarrow$ Convergent**. (e.g., $\mathbb{R}^k$ is complete).

## 4. Upper & Lower Limits (for real sequences)

- **Idea:** The "largest" and "smallest" limits a subsequence can have.
- **Notation:**
  - $\limsup_{n\to\infty} s_n = s^*$ (Upper limit, the supremum of all subsequential limits)
  - $\liminf_{n\to\infty} s_n = s_*$ (Lower limit, the infimum of all subsequential limits)
- **Key Fact:** $\lim_{n\to\infty} s_n$ exists **if and only if** $\limsup s_n = \liminf s_n$.

## 5. Special Sequences (Memorize These Limits)

1. $\lim_{n\to\infty} \frac{1}{n^p} = 0$ for $p > 0$
2. $\lim_{n\to\infty} p^{1/n} = 1$ for $p > 0$
3. $\lim_{n\to\infty} n^{1/n} = 1$
4. $\lim_{n\to\infty} \frac{n^\alpha}{(1+p)^n} = 0$ for $p > 0, \alpha \in \mathbb{R}$
5. $\lim_{n\to\infty} x^n = 0$ if $|x| < 1$

## 6. The Basics: Series ($\sum a_n$)

- **Series:** An infinite sum $a_1 + a_2 + a_3 + \ldots$
- **Convergence:** A series converges if its sequence of **partial sums** $s_n = a_1 + \ldots + a_n$ converges.
- **The Nth Term Test:** If $\sum a_n$ converges, then $\lim_{n\to\infty} a_n = 0$.
  - **WARNING:** The converse is **false**! ($a_n \to 0$ does **not** guarantee $\sum a_n$ converges).

## 7. Tests for Convergence (Positive-Term Series)

- **Comparison Test:**
  - If $|a_n| \leq c_n$ and $\sum c_n$ converges $\Rightarrow$ $\sum a_n$ converges.
  - If $a_n \geq d_n \geq 0$ and $\sum d_n$ diverges $\Rightarrow$ $\sum a_n$ diverges.
- **Ratio Test:** Let $L = \limsup \left|\frac{a_{n+1}}{a_n}\right|$
  - If $L < 1$: **Converges**
  - If $L > 1$: **Diverges**
  - If $L = 1$: **No info**
- **Root Test:** Let $\alpha = \limsup |a_n|^{1/n}$
  - If $\alpha < 1$: **Converges**
  - If $\alpha > 1$: **Diverges**
  - If $\alpha = 1$: **No info**
- **Integral Test / p-Series:** $\sum \frac{1}{n^p}$ converges **if and only if $p > 1$**.

## 8. Absolute vs. Conditional Convergence

- **Absolute Convergence:** $\sum |a_n|$ converges.
  - **Key Fact:** Absolute convergence $\Rightarrow$ convergence.
- **Conditional Convergence:** $\sum a_n$ converges but $\sum |a_n|$ diverges (e.g., the alternating harmonic series).
  - **Riemann's Theorem:** A conditionally convergent series can be **rearranged** to converge to any real number or even diverge.

## 9. Power Series ($\sum c_n z^n$)

- **Radius of Convergence (R):** Determined by $\alpha = \limsup |c_n|^{1/n}$, then $R = 1/\alpha$.
- **Behavior:**
  - **Converges absolutely** if $|z| < R$.
  - **Diverges** if $|z| > R$.
  - Behavior **on the circle** $|z| = R$ must be checked separately.

## 10. Useful Tests for "Tricky" Series

- **Alternating Series Test (Leibniz's Test):** If $c_n$ is...
  1. **Alternating** in sign,
  2. **Monotonically decreasing** ($|c_{n+1}| \leq |c_n|$),
  3. and $\lim c_n = 0$,
  
  then $\sum c_n$ **converges**.

- **Dirichlet's Test:** If the partial sums of $\sum a_n$ are **bounded** and $b_n$ is a **monotone** sequence converging to **0**, then $\sum a_n b_n$ **converges**. (The Alternating Series Test is a special case of this).