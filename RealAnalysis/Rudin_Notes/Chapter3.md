Here are detailed revision notes on Chapter 3, "Numerical Sequences and Series," from Walter Rudin's "Principles of Mathematical Analysis". This chapter lays the fundamental groundwork for understanding convergence in the context of sequences and series, initially in general metric spaces, and then specializing to real and complex numbers.

### Chapter 3: Numerical Sequences and Series

This chapter primarily focuses on sequences and series of complex numbers, but the initial sections introduce basic facts about convergence in a more general setting, namely metric spaces, to highlight their fundamental nature.

---

#### 1. Convergent Sequences

**Definition 3.1: Convergent Sequence**
A sequence $\{p_n\}$ in a metric space $X$ is said to **converge** if there exists a point $p \in X$ such that for every $\epsilon > 0$, there is an integer $N$ where $n > N$ implies $d(p_n, p) < \epsilon$.
*   In this case, we say $\{p_n\}$ converges to $p$, or $p$ is the **limit** of $\{p_n\}$, written $p_n \to p$ or $\lim_{n \to \infty} p_n = p$.
*   If a sequence does not converge, it is said to **diverge**.
*   **Remark**: The definition of "convergent sequence" depends on the space $X$. For example, $\{1/n\}$ converges to 0 in $\mathbb{R}^1$ but not in the set of positive real numbers.
*   The **range** of a sequence $\{p_n\}$ is the set of all its terms $\{p_1, p_2, p_3, \dots\}$.
*   A sequence is **bounded** if its range is bounded.

**Theorem 3.2: Properties of Convergent Sequences**
Let $\{p_n\}$ be a sequence in a metric space $X$:
*   **(a)** $\{p_n\}$ converges to $p \in X$ if and only if every neighborhood of $p$ contains all but finitely many terms of $\{p_n\}$. This means that for any neighborhood $V$ of $p$, there exists an $N$ such that for all $n > N$, $p_n \in V$.
*   **(b)** If $p, p' \in X$ and $\{p_n\}$ converges to both $p$ and $p'$, then $p' = p$. This demonstrates the **uniqueness of the limit**.
*   **(c)** If $\{p_n\}$ converges, then $\{p_n\}$ is **bounded**.
*   **(d)** If $E \subset X$ and $p$ is a limit point of $E$, then there is a sequence $\{p_n\}$ in $E$ such that $p = \lim_{n \to \infty} p_n$.

**Theorem 3.3: Limits of Sequences of Complex Numbers**
If $\{a_n\}$ and $\{b_n\}$ are complex sequences such that $\lim a_n = A$ and $\lim b_n = B$, then:
*   **(a)** $\lim (a_n + b_n) = A + B$.
*   **(b)** $\lim (c a_n) = c A$ for any complex number $c$.
*   **(c)** $\lim (a_n b_n) = A B$.
*   **(d)** $\lim (1/a_n) = 1/A$ if $A \neq 0$.

**Theorem 3.4: Convergence in $\mathbb{R}^k$**
*   **(a)** A sequence $\{x_n\}$ in $\mathbb{R}^k$ (where $x_n = (\alpha_{1,n}, \dots, \alpha_{k,n})$) converges to $x = (\alpha_1, \dots, \alpha_k)$ if and only if $\lim_{n \to \infty} \alpha_{j,n} = \alpha_j$ for each $j = 1, \dots, k$.
*   **(b)** If $x_n, y_n \in \mathbb{R}^k$ and $\lim x_n = x, \lim y_n = y$, then $\lim (x_n \cdot y_n) = x \cdot y$. (This is a generalization of Theorem 3.3(c) for dot products in $\mathbb{R}^k$.)

---

#### 2. Subsequences

**Definition 3.5: Subsequence**
Given a sequence $\{p_n\}$, a **subsequence** is a sequence $\{p_{n_k}\}$ where $\{n_k\}$ is a strictly increasing sequence of positive integers ($n_1 < n_2 < n_3 < \dots$).
*   If $\{p_n\}$ converges, its limit is called a **subsequential limit** of $\{p_n\}$.
*   A sequence $\{p_n\}$ converges to $p$ if and only if every subsequence of $\{p_n\}$ converges to $p$.

**Theorem 3.6: Existence of Convergent Subsequences**
*   **(a)** If $\{p_n\}$ is a sequence in a compact metric space $X$, then some subsequence of $\{p_n\}$ converges to a point of $X$. (If the range of $\{p_n\}$ is finite, a constant subsequence exists. If infinite, Theorem 2.37 guarantees a limit point, and a subsequence can be constructed to converge to it.).
*   **(b)** Every bounded sequence in $\mathbb{R}^k$ contains a convergent subsequence. This follows from (a) because Theorem 2.41 implies that every bounded subset of $\mathbb{R}^k$ lies in a compact subset of $\mathbb{R}^k$.

**Theorem 3.7: Set of Subsequential Limits**
The subsequential limits of a sequence $\{p_n\}$ in a metric space $X$ form a **closed subset** of $X$.

---

#### 3. Cauchy Sequences

**Definition 3.8: Cauchy Sequence**
A sequence $\{p_n\}$ in a metric space $X$ is a **Cauchy sequence** if for every $\epsilon > 0$, there is an integer $N$ such that $d(p_n, p_m) < \epsilon$ if $n > N$ and $m > N$.

**Definition 3.9: Diameter of a Set**
Let $E$ be a subset of a metric space $X$. The **diameter** of $E$, denoted $\text{diam}(E)$, is the supremum of the set of all real numbers $d(p,q)$ for $p, q \in E$.
*   A sequence $\{p_n\}$ is a Cauchy sequence if and only if $\lim_{N \to \infty} \text{diam}(E_N) = 0$, where $E_N = \{p_N, p_{N+1}, p_{N+2}, \dots\}$.

**Theorem 3.10: Properties related to Diameter**
*   **(a)** If $\overline{E}$ is the closure of a set $E$ in a metric space $X$, then $\text{diam}(\overline{E}) = \text{diam}(E)$.
*   **(b)** If $\{K_n\}$ is a sequence of compact sets in $X$ such that $K_n \supset K_{n+1}$ for all $n$, and $\lim_{n \to \infty} \text{diam}(K_n) = 0$, then $\bigcap_{n=1}^\infty K_n$ consists of exactly one point. (This is a refinement of Theorem 2.36 Corollary, which only states non-emptiness).

**Theorem 3.11: Convergence and Cauchy Sequences (Cauchy Criterion)**
*   **(a)** In any metric space $X$, every convergent sequence is a Cauchy sequence.
*   **(b)** If $X$ is a compact metric space and if $\{p_n\}$ is a Cauchy sequence in $X$, then $\{p_n\}$ converges to some point of $X$.
*   **(c)** In $\mathbb{R}^k$, every Cauchy sequence converges.
    *   **Note**: The difference between convergence and Cauchy definition is that the limit is explicitly known in the former. Theorem 3.11(b) and (c) are crucial because they allow determining convergence without knowing the limit. This fact in $\mathbb{R}^k$ is often called the **Cauchy criterion for convergence**. The proof for (c) relies on (b) by showing that a Cauchy sequence in $\mathbb{R}^k$ is bounded, and thus its closure is compact (Theorem 2.41).

**Definition 3.12: Complete Metric Space**
A metric space in which every Cauchy sequence converges is said to be **complete**.
*   Thus, all compact metric spaces and all Euclidean spaces are complete.
*   Every closed subset $E$ of a complete metric space $X$ is also complete.

**Theorem 3.14: Monotonic Sequences**
If $\{s_n\}$ is a monotonic sequence of real numbers, then $\{s_n\}$ converges if and only if it is bounded.

---

#### 4. Upper and Lower Limits

**Definition 3.15: Limits to $\pm\infty$**
For a sequence of real numbers $\{s_n\}$:
*   We write $s_n \to +\infty$ if for every real $M$, there is an integer $N$ such that $n > N$ implies $s_n > M$.
*   Similarly, $s_n \to -\infty$ if for every real $M$, there is an integer $N$ such that $n > N$ implies $s_n < M$.

**Definition 3.16: Upper and Lower Limits**
Let $\{s_n\}$ be a sequence of real numbers. Let $E$ be the set of numbers $x$ (in the extended real number system, $\mathbb{R} \cup \{+\infty, -\infty\}$) such that $s_{n_k} \to x$ for some subsequence $\{s_{n_k}\}$.
*   The **upper limit** of $\{s_n\}$ is defined as $s^* = \sup E$, denoted $\limsup_{n \to \infty} s_n = s^*$.
*   The **lower limit** of $\{s_n\}$ is defined as $s_* = \inf E$, denoted $\liminf_{n \to \infty} s_n = s_*$.

**Theorem 3.17: Properties of Upper Limit**
Let $\{s_n\}$ be a sequence of real numbers. Let $E$ and $s^*$ be as in Definition 3.16. Then $s^*$ has the following two properties:
*   **(a)** $s^* \in E$. This means $s^*$ is itself a subsequential limit (or $\pm\infty$ is reached).
*   **(b)** If $x > s^*$, there is an integer $N$ such that $n > N$ implies $s_n < x$. (No terms are eventually greater than $s^*$).
*   Moreover, $s^*$ is the only number with properties (a) and (b). An analogous result holds for $s_*$.

**Examples 3.18:**
*   (a) A sequence containing all rationals has $\limsup = +\infty$ and $\liminf = -\infty$.
*   (b) For $s_n = (-1)^n / (1 + 1/n)$, $\limsup s_n = 1$ and $\liminf s_n = -1$.
*   (c) For a real-valued sequence $\{s_n\}$, $\lim s_n = s$ if and only if $\limsup s_n = \liminf s_n = s$.

**Theorem 3.19: Inequality for Limits**
If $s_n \le t_n$ for $n > N$ (for some fixed $N$), then $\liminf s_n \le \liminf t_n$ and $\limsup s_n \le \limsup t_n$.

---

#### 5. Some Special Sequences

**Theorem 3.20: Common Limits**
*   **(a)** If $p > 0$, then $\lim_{n \to \infty} (1/n^p) = 0$.
*   **(b)** If $p > 0$, then $\lim_{n \to \infty} p^{1/n} = 1$.
*   **(c)** $\lim_{n \to \infty} n^{1/n} = 1$.
*   **(d)** If $p > 0$ and $\alpha$ is real, then $\lim_{n \to \infty} (n^\alpha / (1+p)^n) = 0$.
*   **(e)** $\lim_{n \to \infty} x^n = 0$ if $|x| < 1$.

---

#### 6. Series

**Definition 3.21: Infinite Series**
Given a sequence $\{a_n\}$, the sum $a_p + a_{p+1} + \dots + a_q$ is denoted $\sum_{n=p}^q a_n$. With $\{a_n\}$, we associate the sequence of **partial sums** $\{s_n\}$, where $s_n = \sum_{k=1}^n a_k$.
*   The symbolic expression $a_1 + a_2 + a_3 + \dots$ (or $\sum a_n$) is called an **infinite series**.
*   If $\{s_n\}$ converges to $s$, we say the series **converges**, and write $\sum_{n=1}^\infty a_n = s$. Otherwise, it **diverges**.
*   The concepts of sequences and series are interchangeable: a series generates a sequence of partial sums, and any sequence can be seen as the sequence of partial sums of some series.

**Theorem 3.22: Cauchy Criterion for Series**
$\sum a_n$ converges if and only if for every $\epsilon > 0$, there is an integer $N$ such that $|\sum_{k=n}^m a_k| < \epsilon$ if $m \ge n \ge N$.

**Theorem 3.23: Necessary Condition for Convergence**
If $\sum a_n$ converges, then $\lim_{n \to \infty} a_n = 0$.
*   **Important Note**: The condition $a_n \to 0$ is *not sufficient* for convergence. For instance, the harmonic series $\sum (1/n)$ diverges.

**Theorem 3.24: Series of Nonnegative Terms**
A series of nonnegative terms converges if and only if its partial sums form a bounded sequence.

**Theorem 3.25: Comparison Test**
*   **(a)** If $|a_n| \le c_n$ for $n > N_0$ (fixed integer), and if $\sum c_n$ converges, then $\sum a_n$ converges.
*   **(b)** If $a_n \ge d_n > 0$ for $n > N_0$, and if $\sum d_n$ diverges, then $\sum a_n$ diverges. (Note: (b) applies only to series of nonnegative terms $a_n$).

**Theorem 3.26: Geometric Series**
$\sum_{n=0}^\infty x^n$ converges if $|x| < 1$ and diverges if $|x| \ge 1$. If it converges, its sum is $1/(1-x)$.

**Theorem 3.27: Cauchy's Condensation Test**
Suppose $a_1 \ge a_2 \ge a_3 \ge \dots \ge 0$. Then the series $\sum_{n=1}^\infty a_n$ converges if and only if the series $\sum_{k=0}^\infty 2^k a_{2^k} = a_1 + 2a_2 + 4a_4 + 8a_8 + \dots$ converges.

**Theorem 3.28: P-Series Test**
The series $\sum_{n=1}^\infty (1/n^p)$ converges if $p > 1$ and diverges if $p \le 1$.

**Theorem 3.29:**
If $p > 1$, the series $\sum_{n=2}^\infty (1/(n (\log n)^p))$ converges; if $p \le 1$, the series diverges.
*   This procedure can be continued, generating more finely differentiated convergence criteria (e.g., $\sum 1/(n \log n \log \log n)$ diverges, while $\sum 1/(n \log n (\log \log n)^p)$ converges for $p>1$).

---

#### 7. The Number $e$

**Definition 3.30: Definition of $e$**
$e = \sum_{n=0}^\infty (1/n!)$. (Here $n! = 1 \cdot 2 \cdot \dots \cdot n$ for $n \ge 1$, and $0! = 1$). The series converges rapidly.

**Theorem 3.30:**
$e$ is irrational.

---

#### 8. The Root and Ratio Tests

These are primarily tests for absolute convergence.

**Theorem 3.33: Root Test**
For the series $\sum a_n$, let $\alpha = \limsup_{n \to \infty} |a_n|^{1/n}$:
*   **(a)** If $\alpha < 1$, $\sum a_n$ converges.
*   **(b)** If $\alpha > 1$, $\sum a_n$ diverges.
*   **(c)** If $\alpha = 1$, the test gives no information (e.g., $\sum 1/n$ diverges, $\sum 1/n^2$ converges, both have $\alpha=1$).

**Theorem 3.34: Ratio Test**
For the series $\sum a_n$:
*   **(a)** If $\limsup_{n \to \infty} |a_{n+1}/a_n| < 1$, $\sum a_n$ converges.
*   **(b)** If $|a_{n+1}/a_n| \ge 1$ for $n > n_0$ (fixed integer), $\sum a_n$ diverges.
*   **Remark 3.35**: The root test is always "stronger" than or equal to the ratio test in terms of giving convergence information, meaning $\liminf |a_{n+1}/a_n| \le \liminf |a_n|^{1/n} \le \limsup |a_n|^{1/n} \le \limsup |a_{n+1}/a_n|$.

---

#### 9. Power Series

**Theorem 3.39:**
Given the power series $\sum c_n z^n$, let $\alpha = \limsup_{n \to \infty} |c_n|^{1/n}$ and $R = 1/\alpha$ (with $R = +\infty$ if $\alpha = 0$, $R = 0$ if $\alpha = +\infty$). Then $\sum c_n z^n$ converges if $|z| < R$ and diverges if $|z| > R$.
*   $R$ is called the **radius of convergence**. The series converges absolutely in the interior of its interval of convergence.

**Examples 3.40:**
*   (a) $\sum n^n z^n$ has $R=0$.
*   (b) $\sum z^n/n!$ has $R=+\infty$.
*   (c) $\sum z^n$ has $R=1$. Diverges if $|z|=1$.
*   (d) $\sum z^n/n$ has $R=1$. Diverges if $z=1$, converges for other $z$ with $|z|=1$ (Theorem 3.44).
*   (e) $\sum z^n/n^2$ has $R=1$. Converges for all $z$ with $|z|=1$.

---

#### 10. Summation by Parts

**Theorem 3.41: Partial Summation Formula**
Given two sequences $\{a_n\}$, $\{b_n\}$, let $A_n = \sum_{k=p}^n a_k$ for $n \ge p$, and $A_{p-1} = 0$. Then, if $0 < p \le q$:
$\sum_{n=p}^q a_n b_n = \sum_{n=p}^{q-1} A_n (b_n - b_{n+1}) + A_q b_q - A_{p-1} b_p$.
*   This formula is useful when $\{b_n\}$ is monotonic.

**Theorem 3.42: Dirichlet's Test (for convergence of $\sum a_n b_n$)**
Suppose:
*   (a) The partial sums of $\sum a_n$ form a bounded sequence.
*   (b) $b_n \to 0$ as $n \to \infty$.
*   (c) $b_1 \ge b_2 \ge b_3 \ge \dots$ (monotonic non-increasing).
Then $\sum a_n b_n$ converges.

**Theorem 3.43: Alternating Series Test (Leibnitz's Test)**
Suppose:
*   (a) $|c_1| \ge |c_2| \ge |c_3| \ge \dots$ (monotonically decreasing magnitude).
*   (b) $c_{2m-1} > 0, c_{2m} < 0$ (alternating signs).
*   (c) $\lim_{n \to \infty} c_n = 0$.
Then $\sum c_n$ converges.

**Theorem 3.44: Convergence of Power Series on Unit Circle**
Suppose the radius of convergence of $\sum c_n z^n$ is $1$, and suppose $c_0 \ge c_1 \ge c_2 \ge \dots$ and $\lim_{n \to \infty} c_n = 0$. Then $\sum c_n z^n$ converges at every point on the circle $|z|=1$, except possibly at $z=1$.

---

#### 11. Absolute Convergence

**Definition:**
The series $\sum a_n$ is said to **converge absolutely** if the series $\sum |a_n|$ converges.

**Theorem 3.45:**
If $\sum a_n$ converges absolutely, then $\sum a_n$ converges.

**Remarks 3.46:**
*   For series of positive terms, absolute convergence is the same as convergence.
*   If $\sum a_n$ converges but $\sum |a_n|$ diverges, $\sum a_n$ converges **non-absolutely** (e.g., $\sum (-1)^n/n$).
*   Comparison, root, and ratio tests are primarily tests for absolute convergence.

---

#### 12. Addition and Multiplication of Series

**Theorem 3.47:**
If $\sum a_n = A$ and $\sum b_n = B$, then $\sum (a_n + b_n) = A + B$ and $\sum (c a_n) = cA$ for any complex constant $c$.

**Definition 3.48: Cauchy Product**
Given $\sum a_n$ and $\sum b_n$, their **product** (or Cauchy product) is $\sum c_n$, where $c_n = \sum_{k=0}^n a_k b_{n-k}$. This definition arises from multiplying power series.

**Example 3.49:**
The Cauchy product of two convergent series may actually diverge. An example is provided with $\sum (-1)^n / \sqrt{n+1}$ multiplied by itself.

**Theorem 3.50:**
Suppose $\sum a_n$ converges absolutely, $\sum a_n = A$, $\sum b_n = B$, and $c_n = \sum_{k=0}^n a_k b_{n-k}$. Then $\sum c_n = AB$.
*   This means the product of two convergent series converges to the right value if at least one of the two series converges absolutely.

---

#### 13. Rearrangements

**Definition 3.52: Rearrangement**
A **rearrangement** of $\sum a_n$ is a series $\sum a'_{n}$, where $\{k_n\}$ is a sequence in which every positive integer appears exactly once (a 1-1 function from $\mathbb{J}$ to $\mathbb{J}$), and $a'_n = a_{k_n}$.

**Example 3.53:**
The alternating harmonic series $1 - 1/2 + 1/3 - 1/4 + \dots$ converges, but its rearrangement $1 + 1/3 - 1/2 + 1/5 + 1/7 - 1/4 + \dots$ (two positive terms followed by one negative) converges to a different sum. This illustrates Riemann's theorem.

**Theorem 3.54: Riemann's Rearrangement Theorem**
Let $\sum a_n$ be a series of real numbers which converges, but not absolutely. Suppose $-\infty \le \alpha \le \beta \le +\infty$. Then there exists a rearrangement $\sum a'_n$ with partial sums $s'_n$ such that $\liminf s'_n = \alpha$ and $\limsup s'_n = \beta$.
*   This means that by rearranging a non-absolutely convergent series, its sum can be made to converge to any value between its upper and lower limits of the partial sums (inclusive), or even diverge to $\pm\infty$. The proof relies on the divergence of both the series of positive terms and the series of negative terms.

**Theorem 3.55:**
If $\sum a_n$ is a series of complex numbers which converges absolutely, then every rearrangement of $\sum a_n$ converges, and they all converge to the same sum.
*   This highlights a key property: absolute convergence ensures that the sum of a series is invariant under rearrangement.

---

This comprehensive overview covers the core definitions, theorems, and important examples within Chapter 3, providing a strong foundation for revision.