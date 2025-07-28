
### Chapter 6 : Sequences of Functions

*   Analysis largely revolves around taking limits. Up until Chapter 6, discussions focused on sequences of real numbers. However, a crucial concept in analysis is the **sequence of functions**, often used when solutions to differential equations are found as limits of approximate solutions.
*   When dealing with sequences of functions, there are multiple notions of limits.

### 6.1 Pointwise and Uniform Convergence

This section introduces two key ways sequences of functions can converge.

*   **Pointwise Convergence**
    *   A sequence of functions $\{f_n\}^\infty_{n=1}$ from $S \to \mathbb{R}$ **converges pointwise** to a function $f: S \to \mathbb{R}$ if for every $x \in S$, the sequence of real numbers $\{f_n(x)\}^\infty_{n=1}$ converges to $f(x)$.
    *   Pointwise limits are **unique**.
    *   **Example**: The sequence $f_n(x) = x^{2n}$ on $[-1, 1]$ converges pointwise to $f(x) = 0$ for $x \in (-1, 1)$, and $f(x) = 1$ for $x = -1$ or $x = 1$.
    *   **Reformulation**: Pointwise convergence means that for every $x \in S$ and every $\epsilon > 0$, there exists an $N \in \mathbb{N}$ such that $|f_n(x) - f(x)| < \epsilon$ for all $n \geq N$.

*   **Uniform Convergence**
    *   A sequence of functions $\{f_n\}^\infty_{n=1}$ from $S \to \mathbb{R}$ **converges uniformly** to $f: S \to \mathbb{R}$ if for every $\epsilon > 0$, there exists an $N \in \mathbb{N}$ such that for all $x \in S$, $|f_n(x) - f(x)| < \epsilon$ for all $n \geq N$.
    *   The key distinction from pointwise convergence is that the $N$ (or $\delta$) depends only on $\epsilon$, **not on the specific point $x$**. This means that for $n \geq N$, the graph of $f_n(x)$ is entirely contained within a strip of width $2\epsilon$ around the graph of $f(x)$.
    *   **Relationship to Pointwise Convergence**: If a sequence converges uniformly, it **must also converge pointwise**. However, the converse is **not true**. For instance, $f_n(x) = x^{2n}$ converges pointwise on $[-1, 1]$ but not uniformly.

*   **Convergence in Uniform Norm**
    *   For **bounded functions**, the **uniform norm** (or sup norm, infinity norm) is defined as $\|f\|_S \text{ = sup} \{|f(x)| : x \in S\}$.
    *   A sequence of bounded functions $f_n: S \to \mathbb{R}$ converges uniformly to $f: S \to \mathbb{R}$ if and only if $\text{lim}_{n \to \infty} \|f_n - f\|_S = 0$. This means that uniform convergence is equivalent to convergence in the uniform norm.
    *   **Cauchy Criterion for Uniform Convergence**: A sequence of bounded functions $\{f_n\}^\infty_{n=1}$ is **uniformly Cauchy** if for every $\epsilon > 0$, there exists an $N \in \mathbb{N}$ such that for all $n, k \geq N$, $\|f_n - f_k\|_S < \epsilon$. If a sequence of bounded functions is uniformly Cauchy, then it **converges uniformly**. This is an important property when working with complete metric spaces, as the space of continuous functions with the uniform norm is a complete metric space.

### 6.2 Interchange of Limits

A significant challenge in modern analysis involves swapping the order of two limiting operations, as this is **not always permissible**. For example, $\text{lim}_{n \to \infty} (\text{lim}_{k \to \infty} \frac{n}{n+k}) \neq \text{lim}_{k \to \infty} (\text{lim}_{n \to \infty} \frac{n}{n+k})$.

*   **Continuity of the Limit**
    *   If $\{f_n\}^\infty_{n=1}$ is a sequence of continuous functions, their pointwise limit is **not necessarily continuous**.
    *   **Theorem**: If $\{f_n\}^\infty_{n=1}$ is a sequence of continuous functions $f_n: S \to \mathbb{R}$ **converging uniformly** to $f: S \to \mathbb{R}$, then $f$ is **continuous**.

*   **Integral of the Limit**
    *   If $\{f_n\}^\infty_{n=1}$ converges pointwise, the integral of the limit function is **not necessarily equal to the limit of the integrals**.
    *   **Theorem**: Let $\{f_n\}^\infty_{n=1}$ be a sequence of **Riemann integrable functions** $f_n: [a, b] \to \mathbb{R}$ **converging uniformly** to $f: [a, b] \to \mathbb{R}$. Then $f$ is **Riemann integrable**, and $\int^b_a f = \text{lim}_{n \to \infty} \int^b_a f_n$.

*   **Derivative of the Limit**
    *   Even if functions converge uniformly, the derivative of the limit is **not necessarily the limit of the derivatives**.
    *   **Theorem**: Let $I$ be a bounded interval and let $f_n: I \to \mathbb{R}$ be **continuously differentiable functions**. If $\{f'_n\}^\infty_{n=1}$ converges uniformly to $g: I \to \mathbb{R}$, and $\{f_n(c)\}^\infty_{n=1}$ is a convergent sequence for some $c \in I$, then $\{f_n\}^\infty_{n=1}$ **converges uniformly** to a continuously differentiable function $f: I \to \mathbb{R}$, and **$f' = g$**.

*   **Convergence of Power Series**
    *   A power series $\sum^\infty_{n=0} c_n(x-a)^n$ with a radius of convergence $\rho > 0$ **converges uniformly** in any closed interval $[a-r, a+r]$ where $0 < r < \rho$.
    *   Consequently, the sum of a power series is a **continuous function** within its interval of convergence.
    *   Power series can be **integrated term by term** within their radius of convergence. The integrated series also has a radius of convergence of at least $\rho$.
    *   Power series can be **differentiated term by term** within their radius of convergence. The differentiated series also has the same radius of convergence $\rho$. This implies that any power series defines an **infinitely differentiable function**.

### 6.3 Picard's Theorem

Picard's theorem is a fundamental result in analysis that guarantees the **existence and uniqueness of solutions to ordinary differential equations** (ODEs) under certain conditions.

*   **Problem Statement**: The theorem addresses ODEs of the form $y'(x) = F(x, y(x))$ with an initial condition $y(x_0) = y_0$.
*   **Conditions**:
    *   Let $I$ and $J$ be closed bounded intervals, and $(x_0, y_0)$ be an interior point of $I \times J$.
    *   The function $F: I \times J \to \mathbb{R}$ must be **continuous**.
    *   $F$ must be **Lipschitz continuous in the second variable** (i.e., $y$), meaning there exists an $L \in \mathbb{R}$ such that $|F(x, y) - F(x, z)| \leq L|y - z|$ for all $y, z \in J, x \in I$.
*   **Conclusion**: Under these conditions, there exists an $h > 0$ such that $[x_0 - h, x_0 + h] \subset I$ and a **unique differentiable function** $f: [x_0 - h, x_0 + h] \to J \subset \mathbb{R}$ that satisfies the ODE and the initial condition.
*   **Picard Iterates**: The proof of Picard's theorem involves constructing a sequence of functions, known as **Picard iterates**. Starting with an initial guess $f_0(x) = y_0$, subsequent iterates are defined by $f_k(x) = y_0 + \int^x_{x_0} F(t, f_{k-1}(t)) dt$.
*   **Proof Technique**: The proof demonstrates that this sequence of Picard iterates **converges uniformly** to the solution function $f$ on a suitable interval $[x_0 - h, x_0 + h]$. This convergence relies heavily on the concepts of **uniform convergence** and the **completeness** of the space of continuous functions (specifically, $C([a, b], \mathbb{R})$ with the uniform norm). The Picard theorem is presented as a sophisticated application of many concepts learned in analysis.
*   **Alternative Proof (Metric Spaces)**: Picard's theorem can also be elegantly proven using the **fixed point theorem for contraction mappings** in the context of metric spaces. This approach often simplifies the proof by leveraging the properties of complete metric spaces.