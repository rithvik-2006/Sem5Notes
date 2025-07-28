
### Chapter 7 : Metric Spaces


*   The concept of a metric space serves as a **powerful tool in analysis** to unify notions of limits, particularly when dealing with sequences of points in higher dimensions (e.g., 3-dimensional space), continuous functions of several variables, or even functions on more complex spaces like the surface of the Earth. It extends beyond the real number line, providing an abstract setting for studying limits.

### 7.1 Metric spaces

*   **Definition**: A **metric space** is a pair $(X, d)$, where $X$ is a set and $d: X \times X \to \mathbb{R}$ is a function called the **metric** or **distance function**, satisfying the following properties for all $x, y, z \in X$:
    *   **(i) Nonnegativity**: $d(x, y) \geq 0$.
    *   **(ii) Identity of indiscernibles**: $d(x, y) = 0$ if and only if $x = y$.
    *   **(iii) Symmetry**: $d(x, y) = d(y, x)$.
    *   **(iv) Triangle inequality**: $d(x, z) \leq d(x, y) + d(y, z)$.

*   **Examples of Metric Spaces**:
    *   **Real numbers ($\mathbb{R}$)**: With the standard metric $d(x, y) = |x - y|$. This is the default metric for $\mathbb{R}$ unless specified otherwise.
    *   **Real numbers with a nonstandard metric**: For example, $d(x, y) = \frac{|x - y|}{|x - y| + 1}$. This metric always results in $d(x, y) < 1$.
    *   **n-dimensional Euclidean space ($\mathbb{R}^n$)**: With the standard metric $d(x, y) = \sqrt{\sum_{k=1}^n (x_k - y_k)^2}$. This relies on the **Cauchy–Schwarz inequality**.
    *   **Complex numbers ($\mathbb{C}$)**: Can be viewed as $\mathbb{R}^2$ with the metric $d(z_1, z_2) = |z_1 - z_2| = \sqrt{(x_1 - x_2)^2 + (y_1 - y_2)^2}$.
    *   **Discrete metric**: For any set $X$, $d(x, y) = 1$ if $x \neq y$ and $d(x, x) = 0$.
    *   **Space of continuous functions ($C([a, b], \mathbb{R})$)**: The set of continuous real-valued functions on $[a, b]$ with the metric $d(f, g) = \sup_{x \in [a, b]} |f(x) - g(x)|$. This is also known as the **uniform norm** or **sup norm**. This space is crucial for advanced analysis, including Picard's theorem.

*   **Subspaces**: If $(X, d)$ is a metric space and $Y \subset X$, then the restriction of $d$ to $Y \times Y$ is a metric on $Y$. $(Y, d')$ is called a subspace of $(X, d)$.

*   **Bounded Sets and Spaces**:
    *   A subset $S \subset X$ is **bounded** if there exists a point $p \in X$ and a $B \in \mathbb{R}$ such that $d(p, x) \leq B$ for all $x \in S$.
    *   The **diameter** of a nonempty set $S$ is $\text{diam}(S) = \sup \{d(x, y) : x, y \in S\}$. A nonempty set is bounded if and only if its diameter is finite.
    *   For example, $\mathbb{R}$ with the standard metric is not bounded, but $\mathbb{R}$ with the discrete metric is bounded.

### 7.2 Open and closed sets

*   **Balls**:
    *   **Open ball**: $B(x, \delta) = \{y \in X : d(x, y) < \delta\}$.
    *   **Closed ball**: $C(x, \delta) = \{y \in X : d(x, y) \leq \delta\}$.
    *   In $\mathbb{R}$ with the standard metric, $B(x, \delta) = (x - \delta, x + \delta)$ and $C(x, \delta) = [x - \delta, x + \delta]$.

*   **Definitions**:
    *   A subset $V \subset X$ is **open** if for every $x \in V$, there exists a $\delta > 0$ such that $B(x, \delta) \subset V$.
    *   A subset $E \subset X$ is **closed** if its complement $E^c = X \setminus E$ is open.
    *   An open neighborhood of $x$ is an open set $V$ containing $x$.

*   **Properties of Open Sets**:
    *   The empty set $\emptyset$ and the space $X$ itself are open.
    *   A **finite intersection** of open sets is open.
    *   An **arbitrary union** of open sets is open.
    *   **Important Note**: An arbitrary intersection of open sets is *not* necessarily open (e.g., $\bigcap_{n=1}^\infty (-1/n, 1/n) = \{0\}$, which is not open in $\mathbb{R}$).

*   **Properties of Closed Sets**:
    *   The empty set $\emptyset$ and the space $X$ itself are closed.
    *   An **arbitrary intersection** of closed sets is closed.
    *   A **finite union** of closed sets is closed.
    *   **Open balls are open sets** and **closed balls are closed sets**.

*   **Subspace Topology**: A set $U \subset Y$ (where $Y \subset X$) is open in the subspace metric space $(Y, d|_{Y \times Y})$ if and only if there exists an open set $V \subset X$ such that $V \cap Y = U$.

*   **Connected Sets**:
    *   A nonempty metric space $(X, d)$ is **connected** if its only subsets that are both open and closed (clopen subsets) are $\emptyset$ and $X$ itself.
    *   In $\mathbb{R}$, a nonempty set $S \subset \mathbb{R}$ is connected if and only if $S$ is an **interval or a single point**.

*   **Closure and Boundary**:
    *   The **closure of $A$** (denoted $\bar{A}$) is the intersection of all closed sets that contain $A$.
        *   $\bar{A}$ is closed, and $A \subset \bar{A}$.
        *   If $A$ is closed, then $A = \bar{A}$.
        *   $x \in \bar{A}$ if and only if for every $\delta > 0$, $B(x, \delta) \cap A \neq \emptyset$. This means $x$ can be "approached" from within $A$.
    *   The **interior of $A$** (denoted $A^\circ$) is the set of points $x \in A$ for which there exists a $\delta > 0$ such that $B(x, \delta) \subset A$. $A^\circ$ is open.
    *   The **boundary of $A$** (denoted $\partial A$) is $\bar{A} \setminus A^\circ$. $\partial A$ is closed.
        *   $x \in \partial A$ if and only if every ball $B(x, \delta)$ contains points from both $A$ and its complement $A^c$.

### 7.3 Sequences and convergence

*   **Definition of a Sequence**: A sequence in a metric space $(X, d)$ is a function $x: \mathbb{N} \to X$, denoted $\{x_n\}_{n=1}^\infty$.
    *   A sequence is **bounded** if its range $\{x_n : n \in \mathbb{N}\}$ is a bounded set in the metric space.
    *   A **subsequence** $\{x_{n_k}\}_{k=1}^\infty$ is formed by taking elements from the original sequence in strictly increasing order of indices.

*   **Convergence**: A sequence $\{x_n\}_{n=1}^\infty$ **converges** to a point $p \in X$ if for every $\epsilon > 0$, there exists an $M \in \mathbb{N}$ such that $d(x_n, p) < \epsilon$ for all $n \geq M$.
    *   **Limits are unique**.
    *   A convergent sequence is always **bounded**.
    *   A sequence converges if and only if **every subsequence converges to the same limit**.

*   **Convergence in Specific Spaces**:
    *   In $C([a, b], \mathbb{R})$, convergence in the metric space sense is **identical to uniform convergence**.
    *   In $\mathbb{R}^n$, a sequence $\{x_m\}_{m=1}^\infty$ (where $x_m = (x_{m,1}, \dots, x_{m,n})$) converges to $p = (p_1, \dots, p_n)$ if and only if **each component sequence $\{x_{m,k}\}_{m=1}^\infty$ converges to $p_k$** for $k=1, \dots, n$.

*   **Convergence and Topology**:
    *   A sequence $\{x_n\}_{n=1}^\infty$ converges to $p$ if and only if for every **open neighborhood $U$ of $p$**, there exists an $M \in \mathbb{N}$ such that for all $n \geq M$, $x_n \in U$.
    *   If a sequence in a **closed set $E$** converges to some $p \in X$, then **$p$ must also be in $E$**.
    *   A point $p \in X$ is in the **closure of $A$** ($\bar{A}$) if and only if there exists a **sequence of elements in $A$ that converges to $p$**.

### 7.4 Completeness and compactness

*   **Cauchy Sequences**:
    *   A sequence $\{x_n\}_{n=1}^\infty$ in $(X, d)$ is a **Cauchy sequence** if for every $\epsilon > 0$, there exists an $M \in \mathbb{N}$ such that for all $n \geq M$ and $k \geq M$, $d(x_n, x_k) < \epsilon$.
    *   **Every convergent sequence is Cauchy**.

*   **Complete Metric Space**: A metric space $(X, d)$ is **complete** (or **Cauchy-complete**) if every Cauchy sequence in $X$ converges to a point $p \in X$.
    *   **$\mathbb{R}^n$ with the standard metric is a complete metric space**.
    *   The space of continuous functions **$C([a, b], \mathbb{R})$ with the uniform norm is a complete metric space**.
    *   A **closed subset of a complete metric space is complete** with the subspace metric.

*   **Compactness**:
    *   A set $K \subset X$ is **compact** if for every collection of open sets (an **open cover**) $\{U_\lambda\}_{\lambda \in I}$ such that $K \subset \bigcup_{\lambda \in I} U_\lambda$, there exists a **finite subset** of indices $\{\lambda_1, \dots, \lambda_m\} \subset I$ such that $K \subset \bigcup_{j=1}^m U_{\lambda_j}$ (i.e., every open cover has a **finite subcover**).
    *   If $K \subset X$ is compact, then $K$ is **closed and bounded**.
    *   The **Lebesgue covering lemma** states that for a sequentially compact set $K$ and an open cover, there exists a $\delta > 0$ (Lebesgue number) such that for every $x \in K$, $B(x, \delta)$ is contained in at least one set of the cover.
    *   A set $K \subset X$ is **compact if and only if every sequence in $K$ has a subsequence converging to a point in $K$** (this is called **sequentially compact**).
    *   If $K \subset X$ is compact and $E \subset K$ is a closed set, then **$E$ is compact**.
    *   **Heine–Borel Theorem**: A subset $K \subset \mathbb{R}^n$ is **compact if and only if it is closed and bounded**. This theorem is specific to $\mathbb{R}^n$ and does not hold for general metric spaces (e.g., $C([a,b],\mathbb{R})$).

### 7.5 Continuous functions

*   **Definition**: A function $f: X \to Y$ between metric spaces $(X, d_X)$ and $(Y, d_Y)$ is **continuous at $c \in X$** if for every $\epsilon > 0$, there is a $\delta > 0$ such that whenever $x \in X$ and $d_X(x, c) < \delta$, then $d_Y(f(x), f(c)) < \epsilon$.
    *   $f$ is continuous at $c$ if and only if for every sequence $\{x_n\}_{n=1}^\infty$ in $X$ converging to $c$, the sequence $\{f(x_n)\}_{n=1}^\infty$ converges to $f(c)$.

*   **Properties related to Continuity**:
    *   Polynomials in $\mathbb{R}^n$ are continuous.
    *   If $K \subset X$ is a **compact set** and $f: X \to Y$ is continuous, then the image $f(K)$ is a **compact set**.
    *   If $(X, d)$ is a nonempty compact metric space and $f: X \to \mathbb{R}$ is continuous, then $f$ is **bounded and achieves an absolute minimum and an absolute maximum** on $X$.
    *   A function $f: X \to Y$ is **continuous if and only if for every open $U \subset Y$, the preimage $f^{-1}(U)$ is open in $X$**. This implies that zero sets of continuous functions (e.g., polynomials) are closed.

*   **Uniform Continuity**:
    *   A function $f: X \to Y$ is **uniformly continuous** if for every $\epsilon > 0$, there is a $\delta > 0$ such that whenever $p, q \in X$ and $d_X(p, q) < \delta$, then $d_Y(f(p), f(q)) < \epsilon$. The $\delta$ depends only on $\epsilon$, not on specific points.
    *   If $f: X \to Y$ is continuous and **$X$ is compact**, then $f$ is **uniformly continuous**.
    *   **Lipschitz continuous functions** ($d_Y(f(p), f(q)) \leq K d_X(p, q)$ for some $K$) are uniformly continuous.

*   **Limits of Functions in Metric Spaces**:
    *   A point $p \in X$ is a **cluster point** of $S \subset X$ if for every $\epsilon > 0$, $B(p, \epsilon) \cap S \setminus \{p\}$ is not empty.
    *   The limit of a function $f(x)$ as $x$ goes to a cluster point $p$ can be defined similarly to real analysis, and the limit, if it exists, is unique.
    *   As in $\mathbb{R}$, continuous limits are equivalent to sequential limits in metric spaces.

### 7.6 Fixed point theorem and Picard’s theorem again

*   **Fixed Point Theorem (Contraction Mapping Principle / Banach Fixed Point Theorem)**:
    *   A map $\varphi: X \to Y$ is a **contraction** if it is a $k$-Lipschitz map for some $k < 1$ (i.e., $d_Y(\varphi(p), \varphi(q)) \leq k d_X(p, q)$ for all $p, q \in X$).
    *   A point $x \in X$ is a **fixed point** if $\varphi(x) = x$.
    *   **Theorem**: Let $(X, d)$ be a **nonempty complete metric space** and $\varphi: X \to X$ a **contraction**. Then $\varphi$ has a **unique fixed point**.
    *   The proof involves constructing a sequence of iterates $x_{n+1} = \varphi(x_n)$ and showing it is a Cauchy sequence, which then converges to the fixed point due to completeness.

*   **Picard's Theorem (Existence and Uniqueness of ODE Solutions)**:
    *   This theorem, a **pièce de résistance** of the course, guarantees the **existence and uniqueness of solutions to ordinary differential equations (ODEs)** of the form $y'(x) = F(x, y(x))$ with initial condition $y(x_0) = y_0$.
    *   It is a powerful application that combines many concepts in analysis.
    *   **Key Idea**: The ODE is reformulated as an integral equation: $y(x) = y_0 + \int_{x_0}^x F(t, y(t)) dt$.
    *   This integral equation is then viewed as a **fixed point problem** in the space of continuous functions $C([a, b], \mathbb{R})$.
    *   **Conditions**: The function $F(x, y)$ must be:
        1.  **Continuous** on a suitable rectangle $I \times J$.
        2.  **Lipschitz continuous in the second variable** (y), meaning there exists $L \in \mathbb{R}$ such that $|F(x, y) - F(x, z)| \leq L|y - z|$.
    *   **Proof Strategy**:
        1.  The space of continuous functions $C([a, b], \mathbb{R})$ with the uniform norm is a **complete metric space**.
        2.  A restricted subset of $C([a, b], \mathbb{R})$ (functions whose graphs stay within the defined region) forms a closed (and thus complete) subspace.
        3.  An operator $T(f)(x) = y_0 + \int_{x_0}^x F(t, f(t)) dt$ is defined. It is shown that $T$ maps this closed subspace to itself.
        4.  Crucially, for a sufficiently small interval around $x_0$ (determined by $h$), the operator $T$ is shown to be a **contraction mapping**.
        5.  By the **Contraction Mapping Principle**, there exists a **unique fixed point** $f$, which is the unique solution to the ODE.

    *   **Picard Iterates**: The proof involves generating a sequence of approximate solutions $f_k(x) = y_0 + \int_{x_0}^x F(t, f_{k-1}(t)) dt$, which converge uniformly to the true solution.
    *   Picard's theorem can also be proven without metric spaces (as introduced in Section 6.3), but the metric space approach using the fixed point theorem simplifies the proof considerably.