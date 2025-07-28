
### Chapter 5 : The Riemann Integral

This chapter focuses on defining and understanding the Riemann integral, often informally thought of as the "area under the curve". It introduces rigorous definitions for integrals, their properties, the fundamental theorem of calculus, and then uses these tools to formally define important functions like the logarithm and exponential, and to tackle improper integrals.

#### 5.1 The Riemann Integral

The Riemann integral is defined using **Darboux integrals**, which are technically simpler.

*   **Partitions and Darboux Sums**:
    *   A **partition** $P$ of an interval $[a, b]$ is a finite set of ordered points $\{x_0, x_1, \dots, x_n\}$ such that $a = x_0 < x_1 < \dots < x_n = b$.
    *   For a bounded function $f : [a, b] \to \mathbb{R}$ and a partition $P$:
        *   $m_i = \inf \{f(x) : x_{i-1} \le x \le x_i \}$.
        *   $M_i = \sup \{f(x) : x_{i-1} \le x \le x_i \}$.
        *   The **lower Darboux sum** is $L(P, f) = \sum_{i=1}^n m_i \Delta x_i$, where $\Delta x_i = x_i - x_{i-1}$. This represents the area of shaded rectangles under the curve.
        *   The **upper Darboux sum** is $U(P, f) = \sum_{i=1}^n M_i \Delta x_i$. This represents the area of both shaded and unshaded rectangles above the curve.
    *   **Bounds**: For any partition $P$, if $m \le f(x) \le M$ for all $x \in [a, b]$, then $m(b-a) \le L(P, f) \le U(P, f) \le M(b-a)$.

*   **Darboux Integrals**:
    *   The **lower Darboux integral** is $\underline{\int_a^b} f(x) \, dx = \sup \{ L(P, f) : P \text{ a partition of } [a,b] \}$.
    *   The **upper Darboux integral** is $\overline{\int_a^b} f(x) \, dx = \inf \{ U(P, f) : P \text{ a partition of } [a,b] \}$.
    *   **Crucial Property**: For any bounded function $f$, the lower Darboux integral is always less than or equal to the upper Darboux integral.

*   **Riemann Integrability**:
    *   A bounded function $f : [a, b] \to \mathbb{R}$ is **Riemann integrable** if its lower and upper Darboux integrals are equal.
    *   If $f$ is Riemann integrable, its **Riemann integral** is defined as $\int_a^b f(x) \, dx = \underline{\int_a^b} f(x) \, dx = \overline{\int_a^b} f(x) \, dx$.
    *   The set of Riemann integrable functions on $[a, b]$ is denoted by $\text{R}([a, b])$.
    *   **Criterion for Integrability (Proposition 5.1.13)**: $f$ is Riemann integrable if and only if for every $\epsilon > 0$, there exists a partition $P$ such that $U(P, f) - L(P, f) < \epsilon$. This means the difference between the upper and lower sums can be made arbitrarily small.
    *   **Examples**:
        *   **Constant functions** are Riemann integrable: If $f(x) = c$, then $\int_a^b f = c(b-a)$.
        *   The **Dirichlet function** ($f(x)=1$ for $x \in \mathbb{Q}$, $f(x)=0$ for $x \notin \mathbb{Q}$) is **not Riemann integrable** because its lower integral is 0 and its upper integral is 1.
        *   A function with a **single jump discontinuity** can be Riemann integrable.
    *   **Integral Notation for $a \not< b$**:
        *   If $b < a$ and $f \in \text{R}([b, a])$, then $\int_a^b f \stackrel{\text{def}}{=} - \int_b^a f$.
        *   $\int_a^a f \stackrel{\text{def}}{=} 0$.

#### 5.2 Properties of the Integral

The Riemann integral possesses several intuitive properties that align with the notion of summation.

*   **Additivity of the Integral**:
    *   If $a < b < c$ and $f$ is bounded on $[a, c]$, then the Darboux integrals are additive: $\underline{\int_a^c} f = \underline{\int_a^b} f + \underline{\int_b^c} f$ and $\overline{\int_a^c} f = \overline{\int_a^b} f + \overline{\int_b^c} f$.
    *   **Proposition 5.2.2**: A function $f : [a, c] \to \mathbb{R}$ is Riemann integrable if and only if it is Riemann integrable on $[a, b]$ and $[b, c]$ (for $a < b < c$). If so, $\int_a^c f = \int_a^b f + \int_b^c f$.
    *   **Corollary 5.2.3**: If $f \in \text{R}([a, b])$ and $[c, d] \subset [a, b]$, then $f|_{[c,d]} \in \text{R}([c, d])$.

*   **Linearity of the Integral (Proposition 5.2.4)**:
    *   If $f, g \in \text{R}([a, b])$ and $\alpha \in \mathbb{R}$:
        *   $\alpha f \in \text{R}([a, b])$ and $\int_a^b \alpha f(x) \, dx = \alpha \int_a^b f(x) \, dx$.
        *   $f + g \in \text{R}([a, b])$ and $\int_a^b (f(x) + g(x)) \, dx = \int_a^b f(x) \, dx + \int_a^b g(x) \, dx$.

*   **Monotonicity of the Integral (Proposition 5.2.6)**:
    *   If $f, g : [a, b] \to \mathbb{R}$ are bounded and $f(x) \le g(x)$ for all $x \in [a, b]$, then $\underline{\int_a^b} f \le \underline{\int_a^b} g$ and $\overline{\int_a^b} f \le \overline{\int_a^b} g$.
    *   If $f, g \in \text{R}([a, b])$, then $\int_a^b f \le \int_a^b g$.

*   **Integrability of Continuous and Monotone Functions**:
    *   **Lemma 5.2.7**: If $f : [a, b] \to \mathbb{R}$ is a **continuous function**, then $f \in \text{R}([a, b])$. This is because continuous functions on closed, bounded intervals are uniformly continuous, which allows for making the difference between upper and lower sums arbitrarily small.
    *   **Theorem 5.2.9**: A bounded function $f : [a, b] \to \mathbb{R}$ with **finitely many discontinuities** is Riemann integrable.
    *   **Proposition 5.2.10**: If $f \in \text{R}([a, b])$ and $g : [a, b] \to \mathbb{R}$ is such that $f(x) = g(x)$ for all $x \in [a, b] \setminus S$ where $S$ is a finite set, then $g \in \text{R}([a, b])$ and $\int_a^b g = \int_a^b f$. This means changing values at a finite number of points does not change the integral.
    *   **Proposition 5.2.11**: A **monotone function** (increasing or decreasing) on $[a, b]$ is Riemann integrable.

#### 5.3 Fundamental Theorem of Calculus

The fundamental theorem of calculus establishes a crucial link between differentiation and integration, allowing for the calculation of integrals and the definition of antiderivatives.

*   **First Form (Theorem 5.3.1)**:
    *   Let $F : [a, b] \to \mathbb{R}$ be a continuous function, differentiable on $(a, b)$.
    *   Let $f \in \text{R}([a, b])$ such that $F'(x) = f(x)$ for all $x \in (a, b)$.
    *   Then $\int_a^b f(x) \, dx = F(b) - F(a)$.
    *   This form is used to compute integrals when an antiderivative is known. For example, $\int_0^1 x^2 \, dx = \frac{1^3}{3} - \frac{0^3}{3} = \frac{1}{3}$.

*   **Second Form (Theorem 5.3.3)**:
    *   Let $f : [a, b] \to \mathbb{R}$ be a Riemann integrable function.
    *   Define $F(x) = \int_a^x f(t) \, dt$.
    *   Then $F$ is continuous on $[a, b]$.
    *   Furthermore, if $f$ is continuous at a point $c \in [a, b]$, then $F$ is differentiable at $c$ and $F'(c) = f(c)$.
    *   If $f$ is continuous on $[a, b]$, then $F$ is differentiable on all of $[a, b]$ and $F'(x) = f(x)$ for all $x \in [a, b]$.
    *   The base point of integration can be any $d \in [a,b]$ for defining $F(x) = \int_d^x f(t) \, dt$.

*   **Change of Variables (Theorem 5.3.5)**:
    *   Also known as $u$-substitution.
    *   Let $g : [a, b] \to \mathbb{R}$ be a continuously differentiable function.
    *   Let $f : [c, d] \to \mathbb{R}$ be a continuous function, and suppose $g([a, b]) \subset [c, d]$.
    *   Then $\int_a^b f(g(x))g'(x) \, dx = \int_{g(a)}^{g(b)} f(s) \, ds$.

#### 5.4 The Logarithm and the Exponential

This section provides a rigorous definition of the natural logarithm and exponential functions using the integral and inverse function concepts.

*   **The Logarithm**:
    *   **Proposition 5.4.1**: There exists a **unique function** $L : (0, \infty) \to \mathbb{R}$ satisfying:
        *   $L(1) = 0$.
        *   $L$ is differentiable and $L'(x) = 1/x$.
        *   $L$ is strictly increasing, bijective, with $\lim_{x \to 0^+} L(x) = -\infty$ and $\lim_{x \to \infty} L(x) = \infty$.
        *   $L(xy) = L(x) + L(y)$ for all $x, y \in (0, \infty)$.
        *   $L(x^q) = qL(x)$ for rational $q$ and $x > 0$.
    *   **Definition**: This unique function is defined as $L(x) = \int_1^x \frac{1}{t} \, dt$ and is called the **natural logarithm**, denoted $\ln(x)$ (or $\log(x)$ by mathematicians).

*   **The Exponential**:
    *   **Proposition 5.4.2**: There exists a **unique function** $E : \mathbb{R} \to (0, \infty)$ satisfying:
        *   $E(0) = 1$.
        *   $E$ is differentiable and $E'(x) = E(x)$.
        *   $E$ is strictly increasing, bijective, with $\lim_{x \to -\infty} E(x) = 0$ and $\lim_{x \to \infty} E(x) = \infty$.
        *   $E(x+y) = E(x)E(y)$ for all $x, y \in \mathbb{R}$.
        *   $E(qx) = (E(x))^q$ for rational $q$ and $x \in \mathbb{R}$.
    *   **Definition**: This unique function is called the **exponential function**, denoted $\exp(x)$. The number $e = E(1)$ is called **Euler's number**, the base of the natural logarithm.
    *   **General Powers (Corollary 5.4.3)**: For $x > 0$ and $y \in \mathbb{R}$, $x^y$ is defined as $\exp(y \ln(x))$, giving the familiar properties $(x^y)^z = x^{yz}$ and $\ln(x^y) = y \ln(x)$.

#### 5.5 Improper Integrals

Improper integrals extend the concept of the Riemann integral to cases involving unbounded intervals or unbounded functions.

*   **Definition**:
    *   For a function $f : [a, b) \to \mathbb{R}$ Riemann integrable on $[a, c]$ for all $c < b$ (where $b$ can be finite or infinite), the improper integral is defined as $\int_a^b f = \lim_{c \to b^-} \int_a^c f$.
    *   Similarly for $f : (a, b] \to \mathbb{R}$ or $\int_{-\infty}^b f$.
    *   If the limit exists, the integral **converges**; otherwise, it **diverges**.

*   **p-test for Integrals (Proposition 5.5.2)**:
    *   $\int_1^\infty \frac{1}{x^p} \, dx$ converges to $\frac{1}{p-1}$ if $\mathbf{p > 1}$ and diverges if $0 < p \le 1$.
    *   $\int_0^1 \frac{1}{x^p} \, dx$ converges to $\frac{1}{1-p}$ if $\mathbf{0 < p < 1}$ and diverges if $p \ge 1$.

*   **Properties of Improper Integrals**:
    *   **Tails (Proposition 5.5.3)**: For $f : [a, \infty) \to \mathbb{R}$ Riemann integrable on $[a, b]$ for all $b > a$, $\int_b^\infty f$ converges if and only if $\int_a^\infty f$ converges. In that case, $\int_a^\infty f = \int_a^b f + \int_b^\infty f$.
    *   **Nonnegative Functions (Proposition 5.5.4)**: If $f : [a, \infty) \to \mathbb{R}$ is nonnegative and Riemann integrable on $[a, b]$ for all $b > a$, then $\int_a^\infty f$ converges if and only if the function $G(x) = \int_a^x f$ is bounded on $[a, \infty)$. This implies that for nonnegative functions, divergence means divergence to infinity.
    *   **Comparison Test (Proposition 5.5.5)**: If $f, g : [a, \infty) \to \mathbb{R}$ are Riemann integrable on $[a, b]$ for all $b > a$, and $|f(x)| \le g(x)$ for all $x \ge a$:
        *   If $\int_a^\infty g$ converges, then $\int_a^\infty f$ converges, and $\int_a^\infty f \le \int_a^\infty g$.
        *   If $\int_a^\infty f$ diverges, then $\int_a^\infty g$ diverges.
    *   **Double Limits**: For $\int_a^b f$ where both $a$ and $b$ are improper (e.g., $(-\infty, \infty)$ or $(a, b)$ for unbounded function), it's defined as $\lim_{c \to a^+} \lim_{d \to b^-} \int_c^d f$.
    *   **Order of Limits (Proposition 5.5.10)**: For $f : \mathbb{R} \to \mathbb{R}$ integrable on every bounded interval, the order of limits can be switched if they exist, and the integral can be split into two parts: $\int_{-\infty}^\infty f = \int_{-\infty}^0 f + \int_0^\infty f$.

*   **Integral Test for Series (Proposition 5.5.13)**:
    *   Suppose $f : [k, \infty) \to \mathbb{R}$ is a **decreasing nonnegative function** for some integer $k$.
    *   Then the series $\sum_{n=k}^\infty f(n)$ converges if and only if the improper integral $\int_k^\infty f$ converges.
    *   In this case, $\int_k^\infty f \le \sum_{n=k}^\infty f(n) \le f(k) + \int_k^\infty f$. This allows for estimation of series sums.