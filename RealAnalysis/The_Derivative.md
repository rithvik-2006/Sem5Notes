### Chapter 4 : The Derivative
### 4.1 The Derivative

*   **Definition of the Derivative**:
    *   Let $I$ be an interval and $f : I \to \mathbb{R}$ be a function. For a point $c \in I$, if the limit $L = \lim_{x \to c} \frac{f(x) - f(c)}{x - c}$ exists, then $f$ is said to be **differentiable at $c$**.
    *   This limit $L$ is called the **derivative of $f$ at $c$**, denoted as $f'(c)$.
    *   The expression $\frac{f(x) - f(c)}{x - c}$ is known as the **difference quotient**.
    *   If $f$ is differentiable at every point $c \in I$, then $f$ is simply called **differentiable**, and $f'$ becomes a function $f' : I \to \mathbb{R}$.
    *   **Graphical Interpretation**: The derivative $f'(c)$ represents the **slope of the tangent line** to the graph of $f$ at the point $(c, f(c))$. The difference quotient represents the slope of the secant line passing through $(c, f(c))$ and $(x, f(x))$.

*   **Examples of Derivatives**:
    *   For $f(x) = x^2$, $f'(c) = 2c$.
    *   For $f(x) = ax + b$, $f'(c) = a$.
    *   For $f(x) = \sqrt{x}$ (for $x > 0$), $f'(c) = \frac{1}{2\sqrt{c}}$.
    *   The function $f(x) = |x|$ is **not differentiable at the origin** ($x=0$) because the left-hand limit of the difference quotient is $-1$ and the right-hand limit is $1$.

*   **Differentiability Implies Continuity**:
    *   **Proposition 4.1.6**: If a function $f : I \to \mathbb{R}$ is differentiable at $c \in I$, then it is **continuous at $c$**.
    *   **Proof Idea**: $f(x) - f(c) = \left(\frac{f(x) - f(c)}{x - c}\right) (x - c)$. Taking the limit as $x \to c$, since both $\frac{f(x) - f(c)}{x - c}$ and $(x - c)$ converge (to $f'(c)$ and $0$ respectively), their product converges to $f'(c) \cdot 0 = 0$. This implies $\lim_{x \to c} f(x) = f(c)$.
    *   **Important Note**: The converse is not true; a continuous function is not necessarily differentiable (e.g., $f(x) = |x|$ at $x=0$).

*   **Rules of Differentiation**:
    *   **Linearity (Proposition 4.1.7)**: If $f$ and $g$ are differentiable at $c$, and $\alpha \in \mathbb{R}$:
        *   The function $h(x) = \alpha f(x)$ is differentiable at $c$ and $h'(c) = \alpha f'(c)$.
        *   The function $h(x) = f(x) + g(x)$ is differentiable at $c$ and $h'(c) = f'(c) + g'(c)$.
    *   **Product Rule (Proposition 4.1.8)**: If $f$ and $g$ are differentiable at $c$, and $h(x) = f(x)g(x)$, then $h$ is differentiable at $c$ and **$h'(c) = f(c)g'(c) + f'(c)g(c)$**.
    *   **Quotient Rule (Proposition 4.1.9)**: If $f$ and $g$ are differentiable at $c$ and $g(x) \neq 0$ for all $x \in I$, and $h(x) = \frac{f(x)}{g(x)}$, then $h$ is differentiable at $c$ and **$h'(c) = \frac{f'(c)g(c) - f(c)g'(c)}{(g(c))^2}$**.
    *   **Chain Rule (Proposition 4.1.10)**: If $g : I_1 \to I_2$ is differentiable at $c \in I_1$, and $f : I_2 \to \mathbb{R}$ is differentiable at $g(c)$, and $h(x) = (f \circ g)(x) = f(g(x))$, then $h$ is differentiable at $c$ and **$h'(c) = f'(g(c))g'(c)$**.

### 4.2 Mean Value Theorem

*   **Relative Minima and Maxima**:
    *   A function $f : S \to \mathbb{R}$ has a **relative maximum at $c \in S$** if there exists a $\delta > 0$ such that for all $x \in S$ where $|x - c| < \delta$, $f(x) \le f(c)$. (A similar definition applies for a relative minimum).
    *   **Lemma 4.2.2**: If $f : (a, b) \to \mathbb{R}$ is differentiable at $c \in (a, b)$, and $f$ has a relative minimum or a relative maximum at $c$, then **$f'(c) = 0$**.
    *   A point $c$ where $f'(c) = 0$ (or where $f'(c)$ does not exist, for non-differentiable functions) is called a **critical point**. This lemma is fundamental for finding extrema.

*   **Rolle's Theorem (Theorem 4.2.3)**:
    *   Let $f : [a, b] \to \mathbb{R}$ be a **continuous function** differentiable on $(a, b)$ such that **$f(a) = f(b)$**. Then there exists a $c \in (a, b)$ such that **$f'(c) = 0$**.
    *   **Proof Idea**: Since $f$ is continuous on a closed interval, it attains an absolute maximum and minimum. If these occur at the endpoints, then $f$ must be constant, so $f'(x)=0$ everywhere. Otherwise, an extremum occurs in the interior $(a, b)$, where by Lemma 4.2.2, the derivative must be zero.
    *   **Key Condition**: Differentiability on the *open* interval $(a, b)$ is crucial (e.g., $f(x) = |x|$ on $[-1, 1]$ fails the theorem).

*   **Mean Value Theorem (Theorem 4.2.4)**:
    *   Let $f : [a, b] \to \mathbb{R}$ be a **continuous function** differentiable on $(a, b)$. Then there exists a point $c \in (a, b)$ such that **$f(b) - f(a) = f'(c)(b - a)$**.
    *   **Geometric Interpretation**: There is a point $c$ in the interval where the slope of the tangent line ($f'(c)$) is equal to the slope of the secant line connecting $(a, f(a))$ and $(b, f(b))$.
    *   **Proof Idea**: The proof involves constructing an auxiliary function $g(x) = f(x) - \frac{f(b) - f(a)}{b - a}(x - b)$ and applying Rolle's Theorem to $g(x)$.

*   **Cauchy's Mean Value Theorem (Theorem 4.2.5)**:
    *   Let $f : [a, b] \to \mathbb{R}$ and $\varphi : [a, b] \to \mathbb{R}$ be continuous functions differentiable on $(a, b)$. Then there exists a point $c \in (a, b)$ such that **$(f(b) - f(a))\varphi'(c) = f'(c)(\varphi(b) - \varphi(a))$**. (The MVT is a special case when $\varphi(x) = x$).

*   **Applications of the Mean Value Theorem**:
    *   **Constant Functions (Proposition 4.2.6)**: If $f : I \to \mathbb{R}$ is differentiable and $f'(x) = 0$ for all $x \in I$, then $f$ is **constant** on $I$.
    *   **Increasing/Decreasing Functions (Proposition 4.2.7)**: If $f : I \to \mathbb{R}$ is differentiable:
        *   $f$ is increasing if and only if $f'(x) \ge 0$ for all $x \in I$.
        *   $f$ is decreasing if and only if $f'(x) \le 0$ for all $x \in I$.
    *   **Strict Monotonicity (Proposition 4.2.8)**:
        *   If $f'(x) > 0$ for all $x \in I$, then $f$ is **strictly increasing**.
        *   If $f'(x) < 0$ for all $x \in I$, then $f$ is **strictly decreasing**. (The converse is not true; e.g., $f(x)=x^3$ is strictly increasing but $f'(0)=0$).
    *   **First Derivative Test (Proposition 4.2.9)**: Conditions on the sign of $f'(x)$ around $c$ to determine if $f$ has an absolute minimum or maximum at $c$.
    *   **Differentiability at Endpoints (Proposition 4.2.10)**: If $f$ is continuous on $[a, b)$ (or $(a, b]$), differentiable on $(a, b)$, and $\lim_{x \to a} f'(x) = L$ (or $\lim_{x \to b} f'(x) = L$), then $f$ is differentiable at $a$ (or $b$) and $f'(a) = L$ (or $f'(b) = L$).

*   **Darboux's Theorem (Theorem 4.2.11)**:
    *   Let $f : [a, b] \to \mathbb{R}$ be **differentiable**. Suppose $y \in \mathbb{R}$ is such that $f'(a) < y < f'(b)$ or $f'(a) > y > f'(b)$. Then there exists a $c \in (a, b)$ such that **$f'(c) = y$**.
    *   **Significance**: This means that derivatives satisfy the **intermediate value property**, even if the derivative function itself is not continuous.
    *   **Example**: The function $f(x) = (x \sin(1/x))^2$ for $x \neq 0$ and $f(0)=0$ is differentiable everywhere, but its derivative $f'(x)$ is **not continuous at $0$**.

*   **Continuously Differentiable Functions**: If $f : I \to \mathbb{R}$ is differentiable and its derivative $f'$ is continuous on $I$, then $f$ is said to be **continuously differentiable**. This is denoted as $f \in C^1(I)$.

### 4.3 Taylor's Theorem

*   **Higher-Order Derivatives**:
    *   The derivative of $f'$ is the **second derivative**, denoted $f''$ or $f^{(2)}$.
    *   The $n$th derivative is denoted $f^{(n)}$.
    *   A function is **$n$ times differentiable** if it possesses $n$ derivatives.

*   **Taylor Polynomial (Definition 4.3.1)**:
    *   For an $n$ times differentiable function $f$ defined near $x_0$, the **$n$th order Taylor polynomial for $f$ at $x_0$** is:
        $P_{x_0}^n(x) = \sum_{k=0}^n \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k = f(x_0) + f'(x_0)(x - x_0) + \frac{f''(x_0)}{2}(x - x_0)^2 + \cdots + \frac{f^{(n)}(x_0)}{n!}(x - x_0)^n$.

*   **Taylor's Theorem (Theorem 4.3.2)**:
    *   Suppose $f : [a, b] \to \mathbb{R}$ has $n$ continuous derivatives on $[a, b]$ and $f^{(n+1)}$ exists on $(a, b)$. Given distinct points $x_0$ and $x$ in $[a, b]$, there exists a point $c$ between $x_0$ and $x$ such that:
        $f(x) = P_{x_0}^n(x) + \frac{f^{(n+1)}(c)}{(n+1)!}(x - x_0)^{n+1}$.
    *   The term $R_{x_0}^n(x) = \frac{f^{(n+1)}(c)}{(n+1)!}(x - x_0)^{n+1}$ is called the **remainder term** (specifically, the Lagrange form of the remainder).
    *   **Relationship to MVT**: The Mean Value Theorem is **Taylor's Theorem for $n=0$**.

*   **Taylor Series**:
    *   If $f$ is **infinitely differentiable**, the **Taylor series** for $f$ at $x_0$ is defined as $\sum_{k=0}^\infty \frac{f^{(k)}(x_0)}{k!}(x - x_0)^k$.
    *   **Analytic Functions**: Functions whose Taylor series at every point $x_0$ converges to $f$ in some open interval containing $x_0$ are called **analytic functions**.

*   **Second Derivative Test (Proposition 4.3.3)**:
    *   Suppose $f : (a, b) \to \mathbb{R}$ is **twice continuously differentiable**, $x_0 \in (a, b)$, $f'(x_0) = 0$ and $f''(x_0) > 0$. Then $f$ has a **strict relative minimum at $x_0$**. (A similar result holds for a strict relative maximum if $f''(x_0) < 0$).

### 4.4 Inverse Function Theorem

*   **Differentiation of Inverse Functions (Lemma 4.4.1)**:
    *   Let $I, J \subset \mathbb{R}$ be intervals. If $f : I \to J$ is **strictly monotone** (hence one-to-one), **onto** ($f(I) = J$), **differentiable at $x_0 \in I$**, and **$f'(x_0) \neq 0$**, then its inverse $f^{-1}$ is differentiable at $y_0 = f(x_0)$ and **$(f^{-1})'(y_0) = \frac{1}{f'(f^{-1}(y_0))} = \frac{1}{f'(x_0)}$**.
    *   If $f$ is continuously differentiable and $f'$ is never zero, then $f^{-1}$ is continuously differentiable.

*   **Inverse Function Theorem (Theorem 4.4.2)**:
    *   Let $f : (a, b) \to \mathbb{R}$ be a **continuously differentiable function**, and $x_0 \in (a, b)$ be a point where **$f'(x_0) \neq 0$**.
    *   Then there exists an open interval $I \subset (a, b)$ with $x_0 \in I$, such that the restriction $f|_I$ is **injective (one-to-one)**.
    *   The inverse function $g : J \to I$ (where $J = f(I)$ is an interval) is **continuously differentiable**, and its derivative is given by **$g'(y) = \frac{1}{f'(g(y))}$** for all $y \in J$.
    *   **Proof Idea**: The continuity of $f'$ and $f'(x_0) \neq 0$ implies there is an interval $I$ around $x_0$ where $f'$ maintains its sign, making $f$ strictly monotone and hence injective on $I$. Then Lemma 4.4.1 is applied.

*   **Application: Existence and Differentiability of $n$th Roots (Corollary 4.4.3)**:
    *   For $n \in \mathbb{N}$ and $x \ge 0$, there exists a **unique positive number $y$** (denoted $x^{1/n}$) such that $y^n = x$.
    *   Furthermore, the function $g(x) = x^{1/n}$ is continuously differentiable on $(0, \infty)$ and its derivative is **$g'(x) = \frac{1}{nx^{(n-1)/n}} = \frac{1}{n}x^{(1-n)/n}$**.
    *   **Key**: This is a direct application of the Inverse Function Theorem to $f(y) = y^n$.

*   **Limitations/Examples**:
    *   The theorem guarantees an *open interval* $I$ where the inverse exists and is differentiable; this interval might be smaller than the original domain (e.g., $f(x)=x^2$ on $\mathbb{R}$, its inverse $f^{-1}(x)=\sqrt{x}$ is only defined for $x \ge 0$).
    *   If $f'(x_0) = 0$, the inverse may not be differentiable at $f(x_0)$ (e.g., for $f(x)=x^3$, $f'(0)=0$, and $f^{-1}(y)=y^{1/3}$ is not differentiable at $y=0$).