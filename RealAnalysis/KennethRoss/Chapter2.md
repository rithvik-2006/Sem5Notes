Here are detailed revision notes on Chapter 2, "Sequences," drawing on the provided sources:

### Chapter 2: Sequences

Chapter 2 delves into the fundamental concepts of sequences and their convergence, laying crucial groundwork for understanding analysis. It introduces key definitions, theorems, and techniques for proving convergence, often without prior knowledge of the limit.

---

#### **§7 Limits of Sequences**

This section defines what a sequence is and introduces the concept of its limit.

*   **Definition of a Sequence**: A sequence is defined as a function whose domain is a set of integers of the form `{n ∈ Z : n ≥ m}`, where `m` is usually 1 or 0.
    *   The value of the sequence at `n` is denoted `sn` (rather than `s(n)`).
    *   Sequences are often written as `(sn)∞n=m` or `(sn)` when the domain is understood.
    *   In this chapter, sequences have **real numbers** as their range values.
*   **Sequence vs. Set of Values**: It's crucial to distinguish between a sequence `(sn)` (which has an ordered infinite number of terms, even if values repeat) and its set of values `{sn}` (which is a set of numbers).
    *   *Example*: The sequence `(an)` where `an = (−1)^n` for `n ≥ 0` is `(1, −1, 1, −1, ...)`, which has infinitely many terms. Its set of values is `{−1, 1}`.
*   **Convergent Sequence / Limit**: A sequence `(sn)` **converges** to a real number `s` (called its **limit**, denoted `lim sn = s`) if for every `ε > 0`, there exists a number `N` such that `n > N` implies `|sn − s| < ε`.
    *   *Intuitive meaning*: The terms `sn` get arbitrarily close to `s` for sufficiently large `n`.
*   **Uniqueness of Limits**: If a sequence converges, its limit is unique. That is, if `lim sn = s` and `lim sn = t`, then `s = t`.

---

#### **§8 A Discussion about Proofs**

This section focuses on developing the ability to read and write rigorous mathematical proofs, particularly those involving the definition of a sequence's limit.

*   **Formal Proofs**: The section provides detailed examples of "formal proofs" to emphasize rigorous mathematical reasoning.
*   **Proof Strategy**: Often, one works backward from the desired conclusion to identify the conditions (e.g., how to choose `N` given `ε`), and then presents the formal proof with steps that are logically reversible.
    *   *Example*: To prove `lim (1/n^2) = 0`, for any `ε > 0`, one needs to find `N` such that `n > N` implies `|1/n^2 - 0| < ε`. This simplifies to `1/n^2 < ε`, or `n^2 > 1/ε`, so `n > 1/√ε`. Thus, one can choose `N = 1/√ε`.
*   **Key Implications for Convergent Sequences `(sn)` with `lim sn = s`**:
    *   If `sn ≥ a` for all but finitely many `n`, then `s ≥ a` [8.9(a) on 76].
    *   If `sn ≤ b` for all but finitely many `n`, then `s ≤ b` [8.9(b) on 76].
    *   If all but finitely many `sn` belong to `[a, b]`, then `s` belongs to `[a, b]` [8.9(c) on 76].
    *   If `s > a`, then there exists `N` such that `n > N` implies `sn > a` [8.10 on 76].

---

#### **§9 Limit Theorems for Sequences**

This section presents fundamental theorems for calculating limits of sequences, including operations on limits and the concept of infinite limits.

*   **Arithmetic of Limits**: If `(sn)` and `(tn)` are convergent sequences with `lim sn = s` and `lim tn = t`, then:
    *   `(sn + tn)` converges to `s + t` [Theorem 9.3(i) on 76].
    *   `(c * sn)` converges to `c * s` for any real number `c` [Theorem 9.3(ii) on 76].
    *   `(sn * tn)` converges to `s * t` [Theorem 9.4(i) on 76].
    *   `(sn / tn)` converges to `s / t`, provided `t ≠ 0` [Theorem 9.6 on 76].
*   **Specific Limits**:
    *   `lim (1/n^p) = 0` for any `p > 0` [Theorem 9.7(a) on 77].
    *   `lim a^n = 0` for any `a` with `|a| < 1` [Theorem 9.7(b) on 77].
    *   `lim n^(1/n) = 1` [Theorem 9.7(c) on 72, 77].
    *   `lim (1 + 1/n)^n` converges to `e`.
*   **Infinite Limits**:
    *   **Definition**: A sequence `(sn)` **diverges to +∞** (`lim sn = +∞`) if for every `M > 0`, there exists `N` such that `n > N` implies `sn > M` [Definition 9.8 on 78].
    *   Similarly, `(sn)` **diverges to −∞** (`lim sn = −∞`) if for every `M < 0`, there exists `N` such that `n > N` implies `sn < M` [Definition 9.8 on 78].
    *   *Examples*: `lim n^2 = +∞`, `lim (−n) = −∞`, `lim 2^n = +∞`.
    *   **Caution**: Not all unbounded sequences diverge to `+∞` or `−∞` (e.g., `sn = (−1)^n n` is unbounded but does not have `+∞` or `−∞` as a limit).
*   **Theorems for Infinite Limits**: Similar arithmetic theorems exist for sequences involving `+∞` or `−∞` (e.g., if `lim sn = +∞` and `lim tn = L` finite, `lim (sn + tn) = +∞`) [Exercise 9.11 on 81].

---

#### **§10 Monotone Sequences and Cauchy Sequences**

This section introduces two powerful theorems that allow determining sequence convergence without knowing the limit in advance.

*   **Monotone Sequences**:
    *   **Definition 10.1**: An increasing sequence satisfies `sn+1 ≥ sn` for all `n`. A decreasing sequence satisfies `sn+1 ≤ sn` for all `n`. A sequence is **monotone** if it is either increasing or decreasing.
    *   **Theorem 10.2 (Monotone Convergence Theorem)**: **All bounded monotone sequences converge**.
        *   This theorem is a **vital ingredient** and relies on the **Completeness Axiom 4.4** of the real numbers.
*   **Decimal Expansions**: Every nonnegative decimal expansion `K.d1d2d3...` is shorthand for the limit of a **bounded increasing sequence**. By Theorem 10.2, this sequence converges to a real number.
    *   *Example*: `3.333...` represents `lim (3 + 3/10 + 3/10^2 + ... + 3/10^n) = 10/3`.
    *   *Important Note*: Different decimal expansions can represent the same real number (e.g., `0.999... = 1.000...`).
*   **lim sup’s and lim inf’s (Limit Superior and Limit Inferior)**:
    *   **Definition 10.6**: For a sequence `(sn)` in `R`:
        *   `lim sup sn = lim N→∞ sup{sn : n > N}`.
        *   `lim inf sn = lim N→∞ inf{sn : n > N}`.
    *   **Conventions for unbounded sequences**: If `(sn)` is not bounded above, `lim sup sn = +∞`. If not bounded below, `lim inf sn = −∞`.
    *   **Convergence Criterion**: A sequence `(sn)` converges if and only if `lim inf sn = lim sup sn`. If they are equal, their common value is the limit of the sequence.
*   **Cauchy Sequences**:
    *   **Definition 10.8**: A sequence `(sn)` is a **Cauchy sequence** if for every `ε > 0`, there exists a number `N` such that `m, n > N` implies `|sn − sm| < ε`.
    *   **Properties**:
        *   **Convergent sequences are Cauchy sequences** [Lemma 10.9 on 90].
        *   **Cauchy sequences are bounded** [Lemma 10.10 on 91].
    *   **Theorem 10.11 (Cauchy Convergence Criterion)**: A sequence is a **convergent sequence if and only if it is a Cauchy sequence**.
        *   This theorem is of **great theoretical importance** because it allows verifying convergence by checking a property of the terms themselves, without knowing the limit.
        *   The proof of this theorem relies implicitly on the **Completeness Axiom 4.4** (via Theorem 10.7 and Theorem 10.2).

---

#### **§11 Subsequences**

This section introduces subsequences and the fundamental Bolzano-Weierstrass Theorem.

*   **Definition 11.1**: A **subsequence** `(tk)k∈N` of a sequence `(sn)n∈N` is formed by selecting terms `sn_k` such that the indices `nk` form a strictly increasing sequence of positive integers: `n1 < n2 < n3 < ...`.
    *   A subsequence is essentially an ordered selection of an infinite subset of the original sequence's terms.
*   **Theorem 11.2 (Subsequential Convergence)**: A real number `t` is the limit of some subsequence of `(sn)` if and only if the set `{n ∈ N : |sn − t| < ε}` is infinite for all `ε > 0`.
*   **Theorem 11.4 (Monotonic Subsequence Theorem)**: **Every sequence has a monotonic subsequence**.
*   **Theorem 11.5 (Bolzano-Weierstrass Theorem)**: **Every bounded sequence has a convergent subsequence**.
    *   **Proof**: A direct consequence of Theorem 11.4 (existence of a monotonic subsequence) and Theorem 10.2 (convergence of a bounded monotonic sequence).
    *   **Significance**: This theorem is **very important** and generalises to other mathematical settings (like `R^k`) where monotonicity may not be defined.
*   **Definition 11.6 (Subsequential Limit)**: A **subsequential limit** is any real number or symbol `+∞` or `−∞` that is the limit of some subsequence of `(sn)`.
    *   If a sequence has a limit `s`, then all its subsequences also have `s` as a limit.
    *   *Examples*: The sequence `sin(nπ/3)` has subsequential limits `{-√3/2, 0, √3/2}`. An enumeration of rational numbers `(rn)` has `R ∪ {−∞, +∞}` as its set of subsequential limits.
*   **Theorem 11.7**: For any sequence `(sn)`, there exists a monotonic subsequence whose limit is `lim sup sn`, and another monotonic subsequence whose limit is `lim inf sn`.
*   **Theorem 11.8**: For any sequence `(sn)`, the set `S` of all its subsequential limits is **closed**, and `lim sup sn = sup S` and `lim inf sn = inf S`.

---

#### **§12 lim sup’s and lim inf’s**

This section further explores the properties and utility of `lim sup` and `lim inf`.

*   **Relationship with Subsequential Limits**: This section reinforces the definitions of `lim sup sn` and `lim inf sn` as the supremum and infimum, respectively, of the set of subsequential limits `S`.
*   **Theorem 12.1 (Multiplication by a Convergent Sequence)**: If `(sn)` converges to a positive real number `s` and `(tn)` is any sequence, then `lim sup (sn tn) = s · lim sup tn` (with standard conventions for `±∞`).
*   **Theorem 12.2 (Ratio Test Lemma)**: For any sequence `(sn)` of nonzero real numbers, the following inequalities hold:
    `lim inf |sn+1/sn| ≤ lim inf |sn|^(1/n) ≤ lim sup |sn|^(1/n) ≤ lim sup |sn+1/sn|`.
    *   This theorem is crucial for proving the **Ratio Test and Root Test for series** in §14.

---

#### **§13 * Some Topological Concepts in Metric Spaces (Enrichment Section)**

This section provides a brief introduction to metric spaces, generalizing concepts previously discussed for the real numbers `R`.

*   **Metric Space**: A set `S` equipped with a **metric** `d` (a distance function) satisfying properties like non-negativity, symmetry, `d(x,y)=0` iff `x=y`, and the triangle inequality [Definition 13.1 on 116].
*   **`R^k` (k-dimensional Euclidean space)**: An important example of a metric space, with the standard Euclidean metric.
*   **Convergence and Cauchy Sequences in `R^k`**: A sequence `(x(n))` in `R^k` converges (or is a Cauchy sequence) if and only if each of its coordinate sequences `(x(n)j)` converges (or is a Cauchy sequence) in `R` [Lemma 13.3 on 117].
*   **Completeness of `R^k`**: The space `R^k` is a **complete metric space**, meaning every Cauchy sequence in `R^k` converges to a point in `R^k` [Theorem 13.4 on 118].
*   **Open and Closed Sets**:
    *   An element `s0` is **interior** to a set `E` if there is an open ball around `s0` contained in `E` [Definition 13.6 on 119].
    *   A set `E` is **open** if every point in `E` is interior to `E` [Definition 13.6 on 119].
    *   A set `E` is **closed** if its complement `S \ E` is an open set [Definition 13.8 on 121].
    *   **Closure**: The closure `E−` of a set `E` is the intersection of all closed sets containing `E`. A set `E` is closed if and only if `E = E−` [Proposition 13.9(a) on 122].
*   **Compact Sets**:
    *   An **open cover** of a set `E` is a collection of open sets whose union contains `E`.
    *   A set `E` is **compact** if every open cover of `E` has a **finite subcover**.
    *   **Heine-Borel Theorem 13.12**: A subset `E` of `R^k` is compact if and only if it is **closed and bounded**.
    *   Every `k-cell` (a `k`-dimensional box) in `R^k` is compact [Proposition 13.13 on 127].

---

#### **§14 Series**

This section builds upon the theory of sequences to define and analyze infinite series.

*   **Definition of a Series**: An **infinite series** `∑∞n=m an` is defined as the limit of its sequence of **partial sums** `(sn)`, where `sn = ∑nk=m ak`. If the sequence of partial sums converges to a real number, the series converges; otherwise, it diverges.
*   **Absolute Convergence**: A series `∑ an` is said to **converge absolutely** if the series of absolute values `∑ |an|` converges.
    *   **Corollary 14.7**: Absolutely convergent series are convergent.
*   **Geometric Series**: A series `∑ ar^n` converges to `a/(1-r)` if `|r| < 1`. If `a ≠ 0` and `|r| ≥ 1`, the series diverges [Example 1 on 135, 136].
*   **p-Series**: The series `∑ 1/n^p` converges if and only if `p > 1` [Example 2 on 136].
*   **Cauchy Criterion for Series 14.4**: A series converges if and only if it satisfies the Cauchy criterion: for every `ε > 0`, there exists `N` such that `n ≥ m > N` implies `|∑nk=m ak| < ε`.
*   **Necessary Condition for Convergence**: If a series `∑ an` converges, then `lim an = 0` [Corollary 14.5 on 137].
    *   **Caution**: The converse is **false** (e.g., the harmonic series `∑ 1/n` diverges, even though `lim (1/n) = 0`).
*   **Tests for Convergence**:
    *   **Comparison Test 14.6**: If `0 ≤ an ≤ bn` for all `n` (or `n > N0`), then if `∑ bn` converges, `∑ an` converges. If `∑ an` diverges, `∑ bn` diverges.
    *   **Ratio Test 14.8**: For a series `∑ an` of nonzero terms:
        *   Converges absolutely if `lim sup |an+1/an| < 1`.
        *   Diverges if `lim inf |an+1/an| > 1`.
        *   Otherwise (if `lim inf |an+1/an| ≤ 1 ≤ lim sup |an+1/an|`), the test gives no information.
        *   The proof uses Theorem 12.2.
    *   **Root Test 14.9**: For a series `∑ an`:
        *   Converges absolutely if `lim sup |an|^(1/n) < 1`.
        *   Diverges if `lim sup |an|^(1/n) > 1`.
        *   Otherwise (if `lim sup |an|^(1/n) = 1`), the test gives no information.

---

#### **§15 Alternating Series and Integral Tests**

This section introduces additional tests useful for determining the convergence of series, particularly for alternating series and those related to improper integrals.

*   **Integral Test (Discussion 15.2)**: For a continuous, non-negative, and decreasing function `f` on `[1, ∞)`, the series `∑∞n=1 f(n)` converges if and only if the improper integral `∫∞1 f(x) dx` converges.
    *   *Example*: The divergence of `∑ 1/n` can be shown by comparing it to `∫ 1/x dx = +∞`.
*   **Theorem 15.1 (p-Series Revisited)**: The series `∑ 1/n^p` converges if and only if `p > 1`. This is proven using the integral test.
*   **Theorem 15.3 (Alternating Series Theorem)**: Let `(an)` be a decreasing sequence of positive numbers such that `lim an = 0`. Then the alternating series `∑∞n=1 (−1)^(n+1) an` converges.
    *   **Error Estimate**: For such a series, the error in approximating the sum `s` by the `N`-th partial sum `sN` is `|s − sN| ≤ aN+1`.

---

#### **§16 * Decimal Expansions of Real Numbers (Enrichment Section)**

This section explores the representation of real numbers through decimal expansions, including their uniqueness and connection to rational and irrational numbers.

*   **Representation of Real Numbers**: Every nonnegative decimal expansion `K.d1d2d3...` represents a real number as the limit of a bounded increasing sequence of real numbers [Discussion 10.3 on 85, 153].
*   **Theorem 16.2**: Every nonnegative real number `x` has at least one decimal expansion.
*   **Uniqueness of Decimal Expansions**:
    *   A real number `x` has **exactly one decimal expansion**, OR
    *   It has **two decimal expansions**: one ending in a sequence of all `0`s and the other ending in a sequence of all `9`s (e.g., `1.000...` and `0.999...`) [Theorem 16.3 on 155].
*   **Rational Numbers and Repeating Decimals**:
    *   **Theorem 16.5**: A real number `x` is **rational if and only if its decimal expansion is repeating**. If `x` has two decimal expansions, they are both repeating.
    *   This implies that non-repeating decimal expansions represent irrational numbers [Example 4 on 159].
*   **Irrationality Proofs**:
    *   **Proof that `e` is irrational**: Based on showing that `(b+1)! * e` cannot be an integer if `e = a/b` [Example 6(a) on 160, 161].
    *   **Proof that `π^2` is irrational (and thus `π` is irrational)**: Uses a sequence of integrals and contradiction by showing an integer must lie in `(0, 1)` [Example 6(b) on 161, 163]. This proof is a simplification of Niven's famous proof.

---