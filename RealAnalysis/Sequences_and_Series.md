
### Chapter 2: Sequences and Series

This chapter introduces the fundamental concepts of sequences and series, which are crucial for understanding limits in analysis.

#### 2.1 Sequences and Limits

*   **Sequence Definition**: A sequence (of real numbers) is formally defined as a function $x: \mathbb{N} \to \mathbb{R}$. The $n$th element is typically denoted by $x_n$, and the sequence itself by $\{x_n\}^\infty_{n=1}$.

*   **Bounded Sequences**: A sequence $\{x_n\}^\infty_{n=1}$ is **bounded** if its underlying set of values $\{x_n : n \in \mathbb{N}\}$ is bounded. This means there exists a $B \in \mathbb{R}$ such that $|x_n| \le B$ for all $n \in \mathbb{N}$.

*   **Convergence and Limit**:
    *   A sequence $\{x_n\}^\infty_{n=1}$ **converges to a number $x \in \mathbb{R}$** if for every $\epsilon > 0$, there exists an $M \in \mathbb{N}$ such that $|x_n - x| < \epsilon$ for all $n \ge M$.
    *   The number $x$ is called the **limit** of the sequence, written as $\lim_{n \to \infty} x_n = x$.
    *   A sequence that converges is **convergent**, otherwise it is **divergent**.
    *   **Uniqueness of Limit**: A convergent sequence has a **unique limit**. This is proven by assuming two limits, $x$ and $y$, and showing that for any $\epsilon > 0$, $|y - x| < \epsilon$, which implies $y=x$.
    *   **Boundedness of Convergent Sequences**: A convergent sequence is always **bounded**. However, the converse is not true; a bounded sequence is not necessarily convergent (e.g., $\{(-1)^n\}^\infty_{n=1}$).

*   **Monotone Sequences**:
    *   A sequence $\{x_n\}^\infty_{n=1}$ is **monotone increasing** if $x_n \le x_{n+1}$ for all $n \in \mathbb{N}$.
    *   A sequence $\{x_n\}^\infty_{n=1}$ is **monotone decreasing** if $x_n \ge x_{n+1}$ for all $n \in \mathbb{N}$.
    *   If a sequence is either monotone increasing or monotone decreasing, it is **monotone**.

*   **Monotone Convergence Theorem**: A monotone sequence $\{x_n\}^\infty_{n=1}$ is **bounded if and only if it is convergent**.
    *   If $\{x_n\}^\infty_{n=1}$ is monotone increasing and bounded, then $\lim_{n \to \infty} x_n = \sup\{x_n : n \in \mathbb{N}\}$.
    *   If $\{x_n\}^\infty_{n=1}$ is monotone decreasing and bounded, then $\lim_{n \to \infty} x_n = \inf\{x_n : n \in \mathbb{N}\}$.
    *   A monotone increasing sequence is always bounded below by its first term, and a monotone decreasing sequence is always bounded above by its first term.

*   **Tail of a Sequence**:
    *   The **$K$-tail** (or just the tail) of a sequence $\{x_n\}^\infty_{n=1}$ is the sequence starting at $K+1$, written as $\{x_{n+K}\}^\infty_{n=1}$ or $\{x_n\}^\infty_{n=K+1}$.
    *   The convergence and the limit of a sequence depend **only on its tail**. Specifically, a sequence converges if and only if its $K$-tail converges for *all* $K \in \mathbb{N}$, or if its $K$-tail converges for *some* $K \in \mathbb{N}$. If the limits exist, they are equal: $\lim_{n \to \infty} x_n = \lim_{n \to \infty} x_{n+K}$.

*   **Subsequences**:
    *   A **subsequence** of $\{x_n\}^\infty_{n=1}$ is a sequence $\{x_{n_i}\}^\infty_{i=1}$ where $\{n_i\}^\infty_{i=1}$ is a strictly increasing sequence of natural numbers ($n_i < n_{i+1}$).

    *   If a sequence converges to $p$, then **every subsequence also converges to $p$**. The converse is not necessarily true; existence of a convergent subsequence does not imply convergence of the sequence itself (e.g., $0, 1, 0, 1, \dots$).

#### 2.2 Facts about Limits of Sequences

*   **Squeeze Lemma**: If $\{a_n\}^\infty_{n=1}$, $\{b_n\}^\infty_{n=1}$, and $\{x_n\}^\infty_{n=1}$ are sequences such that $a_n \le x_n \le b_n$ for all $n \in \mathbb{N}$, and if $\lim_{n \to \infty} a_n = \lim_{n \to \infty} b_n = x$, then $\{x_n\}^\infty_{n=1}$ converges to $x$.

*   **Limits and Inequalities**:
    *   If $\{x_n\}^\infty_{n=1}$ and $\{y_n\}^\infty_{n=1}$ are convergent sequences such that $x_n \le y_n$ for all $n \in \mathbb{N}$, then $\lim_{n \to \infty} x_n \le \lim_{n \to \infty} y_n$.
    *   If $x_n \ge 0$ for all $n$ and $\{x_n\}^\infty_{n=1}$ converges, then $\lim_{n \to \infty} x_n \ge 0$.
    *   If $a \le x_n \le b$ for all $n$ and $\{x_n\}^\infty_{n=1}$ converges, then $a \le \lim_{n \to \infty} x_n \le b$.
    *   **Crucial Note**: Strict inequalities ($x_n < y_n$) are **not necessarily preserved** by the limit operation; they may become non-strict ($\lim x_n \le \lim y_n$).

*   **Continuity of Algebraic Operations**: If $\{x_n\}^\infty_{n=1}$ and $\{y_n\}^\infty_{n=1}$ are convergent sequences, then:
    *   **Sum/Difference**: $\lim_{n \to \infty} (x_n \pm y_n) = \lim_{n \to \infty} x_n \pm \lim_{n \to \infty} y_n$.
    *   **Product**: $\lim_{n \to \infty} (x_n y_n) = (\lim_{n \to \infty} x_n) (\lim_{n \to \infty} y_n)$.
    *   **Quotient**: If $\lim_{n \to \infty} y_n \ne 0$ and $y_n \ne 0$ for all $n$, then $\lim_{n \to \infty} (x_n / y_n) = (\lim_{n \to \infty} x_n) / (\lim_{n \to \infty} y_n)$.

*   **Limits and Roots/Absolute Values**:
    *   If $\{x_n\}^\infty_{n=1}$ is a convergent sequence with $x_n \ge 0$ for all $n$, then $\lim_{n \to \infty} \sqrt{x_n} = \sqrt{\lim_{n \to \infty} x_n}$. This also applies to $k$th roots.
    *   If $\{x_n\}^\infty_{n=1}$ is a convergent sequence, then $\{|x_n|\}^\infty_{n=1}$ is convergent and $\lim_{n \to \infty} |x_n| = |\lim_{n \to \infty} x_n|$. The converse is not true.
*   **Recursively Defined Sequences**: The algebraic properties of limits are crucial for finding limits of sequences defined recursively, provided the sequence is shown to converge first (e.g., using the Monotone Convergence Theorem).

*   **Convergence Tests**:
    *   If there exists an $x \in \mathbb{R}$ and a convergent sequence $\{a_n\}^\infty_{n=1}$ with $\lim_{n \to \infty} a_n = 0$ such that $|x_n - x| \le a_n$ for all $n$, then $\{x_n\}^\infty_{n=1}$ converges to $x$.
    *   **Ratio Test for Sequences**: For a sequence $\{x_n\}^\infty_{n=1}$ with $x_n \ne 0$ and $L = \lim_{n \to \infty} \frac{|x_{n+1}|}{|x_n|}$:
        *   If $L < 1$, then $\lim_{n \to \infty} x_n = 0$.
        *   If $L > 1$, then $\{x_n\}^\infty_{n=1}$ is unbounded (and thus diverges).
        *   If $L = 1$, the test is inconclusive.

#### 2.3 Limit Superior, Limit Inferior, and Bolzano–Weierstrass

*   **Upper and Lower Limits for Bounded Sequences**: For a bounded sequence $\{x_n\}^\infty_{n=1}$:
    *   Define $a_n = \sup\{x_k : k \ge n\}$ and $b_n = \inf\{x_k : k \ge n\}$.
    *   **Limit Superior**: $\lim \sup_{n \to \infty} x_n = \lim_{n \to \infty} a_n$.
    *   **Limit Inferior**: $\lim \inf_{n \to \infty} x_n = \lim_{n \to \infty} b_n$.
    *   The sequence $\{a_n\}^\infty_{n=1}$ is bounded monotone decreasing, and $\{b_n\}^\infty_{n=1}$ is bounded monotone increasing. Therefore, $\lim \sup_{n \to \infty} x_n$ and $\lim \inf_{n \to \infty} x_n$ **always exist** for bounded sequences.
    *   Always, $\lim \inf_{n \to \infty} x_n \le \lim \sup_{n \to \infty} x_n$.

*   **Subsequences and Limit Superior/Inferior**:
    *   If $\{x_n\}^\infty_{n=1}$ is a bounded sequence, there exists a subsequence $\{x_{n_k}\}^\infty_{k=1}$ such that $\lim_{k \to \infty} x_{n_k} = \lim \sup_{n \to \infty} x_n$.
    *   Similarly, there exists a subsequence $\{x_{m_k}\}^\infty_{k=1}$ such that $\lim_{k \to \infty} x_{m_k} = \lim \inf_{n \to \infty} x_n$.
    *   For any convergent subsequence $\{x_{n_k}\}^\infty_{k=1}$, we have $\lim \inf_{n \to \infty} x_n \le \lim_{k \to \infty} x_{n_k} \le \lim \sup_{n \to \infty} x_n$.

*   **Convergence Criterion**: A bounded sequence $\{x_n\}^\infty_{n=1}$ converges if and only if $\lim \inf_{n \to \infty} x_n = \lim \sup_{n \to \infty} x_n$. If it converges, then $\lim_{n \to \infty} x_n = \lim \inf_{n \to \infty} x_n = \lim \sup_{n \to \infty} x_n$.

*   **Bolzano–Weierstrass Theorem**: Suppose a sequence $\{x_n\}^\infty_{n=1}$ of real numbers is **bounded**. Then there exists a **convergent subsequence**. This is a crucial result in analysis.

*   **Infinite Limits**:
    *   A sequence $\{x_n\}^\infty_{n=1}$ **diverges to infinity** ($\lim_{n \to \infty} x_n = \infty$) if for every $K \in \mathbb{R}$, there exists an $M \in \mathbb{N}$ such that for all $n \ge M$, $x_n > K$.
    *   Similarly, it **diverges to minus infinity** ($\lim_{n \to \infty} x_n = -\infty$).
    *   For a monotone unbounded sequence, the limit can be $\infty$ (if increasing) or $-\infty$ (if decreasing).
    *   $\lim \sup$ and $\lim \inf$ can also be defined for unbounded sequences, allowing values of $\infty$ or $-\infty$.

#### 2.4 Cauchy Sequences

*   **Definition**: A sequence $\{x_n\}^\infty_{n=1}$ is a **Cauchy sequence** if for every $\epsilon > 0$, there exists an $M \in \mathbb{N}$ such that for all $n \ge M$ and all $k \ge M$, we have $|x_n - x_k| < \epsilon$. Informally, the terms of the sequence eventually become arbitrarily close to each other.
*   **Boundedness of Cauchy Sequences**: If a sequence is Cauchy, then it is **bounded**.

*   **Cauchy Convergence Theorem**: A sequence of real numbers is **Cauchy if and only if it converges**.
    *   This theorem highlights the **completeness property of the real numbers**.
    *   The "if" part is relatively straightforward, extending from the definition of convergence.
    *   The "only if" part uses the fact that a Cauchy sequence is bounded, allowing the use of the existence of lim inf and lim sup for bounded sequences, and then showing they must be equal, thus implying convergence.

*   **Important Distinction**: The condition $|x_{n+1} - x_n| \to 0$ as $n \to \infty$ is **not sufficient** for a sequence to be Cauchy (and thus convergent). A prime example is the harmonic series partial sums, where consecutive terms get arbitrarily close, but the sequence diverges.

#### 2.5 Series

*   **Definition**: Given a sequence $\{x_n\}^\infty_{n=1}$, a **series** is the formal object $\sum^\infty_{n=1} x_n$.
    *   A series **converges** if its sequence of **partial sums** $\{s_k\}^\infty_{k=1}$ converges, where $s_k = \sum^k_{n=1} x_n$.
    *   If the sequence of partial sums diverges, the series is **divergent**.

*   **Geometric Series**: For $-1 < r < 1$, the geometric series $\sum^\infty_{n=0} r^n$ converges, and $\sum^\infty_{n=0} r^n = \frac{1}{1-r}$.
*   **Tail of a Series**: The convergence of a series $\sum^\infty_{n=1} x_n$ is equivalent to the convergence of its $M$-tail $\sum^\infty_{n=M} x_n$ for any $M \in \mathbb{N}$.

*   **Cauchy Series**: A series $\sum^\infty_{n=1} x_n$ is a **Cauchy series** if its sequence of partial sums is a Cauchy sequence. Since a sequence of real numbers converges if and only if it is Cauchy, a series converges if and only if it is Cauchy.
*   **Necessary Condition for Convergence**: If a series $\sum^\infty_{n=1} x_n$ converges, then the sequence of its terms $\{x_n\}^\infty_{n=1}$ must converge to **zero** ($\lim_{n \to \infty} x_n = 0$).

    *   **Crucial Note**: The converse is **not true**. The terms of a series can converge to zero, but the series itself can diverge.
    *   **Harmonic Series**: The series $\sum^\infty_{n=1} \frac{1}{n}$ (harmonic series) is a classic example where $\lim_{n \to \infty} \frac{1}{n} = 0$, but the series **diverges**.

*   **Linearity of Series**: If $\sum^\infty_{n=1} x_n$ and $\sum^\infty_{n=1} y_n$ are convergent series and $\alpha \in \mathbb{R}$, then:
    *   $\sum^\infty_{n=1} (\alpha x_n) = \alpha \sum^\infty_{n=1} x_n$.
    *   $\sum^\infty_{n=1} (x_n + y_n) = \sum^\infty_{n=1} x_n + \sum^\infty_{n=1} y_n$.

*   **Series with Nonnegative Terms**: If $x_n \ge 0$ for all $n$, then $\sum^\infty_{n=1} x_n$ converges if and only if its sequence of partial sums is **bounded above**.

*   **Absolute Convergence**: A series $\sum^\infty_{n=1} x_n$ **converges absolutely** if $\sum^\infty_{n=1} |x_n|$ converges. If a series converges absolutely, then it also converges (conditionally or absolutely).

*   **Comparison Test**: Let $\sum^\infty_{n=1} x_n$ and $\sum^\infty_{n=1} y_n$ be series with nonnegative terms ($0 \le x_n \le y_n$ for all $n$).
    *   If $\sum^\infty_{n=1} y_n$ converges, then $\sum^\infty_{n=1} x_n$ also converges.
    *   If $\sum^\infty_{n=1} x_n$ diverges, then $\sum^\infty_{n=1} y_n$ also diverges.
*   **p-Series Test**: The series $\sum^\infty_{n=1} \frac{1}{n^p}$ **converges if and only if $p > 1$**.

*   **Ratio Test for Series**: For a series $\sum^\infty_{n=1} x_n$ with $x_n \ne 0$ and $L = \lim_{n \to \infty} \frac{|x_{n+1}|}{|x_n|}$:
    *   If $L < 1$, then $\sum^\infty_{n=1} x_n$ **converges absolutely**.
    *   If $L > 1$, then $\sum^\infty_{n=1} x_n$ **diverges**.
    *   If $L = 1$, the test is inconclusive.

#### 2.6 More on Series

*   **Root Test**: For a series $\sum^\infty_{n=1} x_n$ and $L = \lim \sup_{n \to \infty} |x_n|^{1/n}$:
    *   If $L < 1$, then $\sum^\infty_{n=1} x_n$ **converges absolutely**.
    *   If $L > 1$, then $\sum^\infty_{n=1} x_n$ **diverges**.
    *   If $L = 1$, the test is inconclusive.
*   **Alternating Series Test**: If $\{x_n\}^\infty_{n=1}$ is a **monotone decreasing sequence of positive real numbers** such that $\lim_{n \to \infty} x_n = 0$, then the alternating series $\sum^\infty_{n=1} (-1)^n x_n$ **converges**. This test gives a large supply of conditionally convergent series.

*   **Rearrangements**:
    *   **Absolutely Convergent Series**: If a series converges absolutely, then any **rearrangement** of the series (summing the same terms in a different order) will **converge to the same sum**.

    *   **Conditionally Convergent Series**: For conditionally convergent series, rearrangements can lead to **different sums**, or even make the series diverge.
*   **Mertens’ Theorem (Cauchy Product of Series)**: If $\sum^\infty_{n=0} a_n$ and $\sum^\infty_{n=0} b_n$ are two convergent series, and **at least one of them converges absolutely**, then their Cauchy product $\sum^\infty_{n=0} c_n$ (where $c_n = \sum^n_{i=0} a_i b_{n-i}$) converges to $(\sum^\infty_{n=0} a_n) (\sum^\infty_{n=0} b_n)$.

*   **Power Series**: A **power series** is a series of the form $\sum^\infty_{n=0} c_n (x-a)^n$.
    *   **Radius of Convergence ($\rho$)**: For any power series, there exists a unique $\rho \in [0, \infty]$ (the radius of convergence) such that:
        *   The series converges absolutely on the interval $(a-\rho, a+\rho)$.
        *   The series diverges when $x < a-\rho$ or $x > a+\rho$.
        *   At the endpoints $x = a \pm \rho$, the series may converge or diverge.
    *   The radius of convergence $\rho$ can be computed from $R = \lim \sup_{n \to \infty} |c_n|^{1/n}$ as $\rho = 1/R$ (with special definitions for $R=0$ and $R=\infty$).

    *   **Uniform Convergence of Power Series**: A power series converges **uniformly** on any closed interval $[a-r, a+r]$ whenever $0 < r < \rho$. This implies that the limit function of a power series is **continuous** within its interval of convergence.
    *   **Term-by-Term Integration and Differentiation**: Within its radius of convergence, a power series can be integrated and differentiated term by term, and the resulting series have the **same radius of convergence**.