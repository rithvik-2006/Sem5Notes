Certainly! Here are detailed revision notes on Chapter 1, "The Real and Complex Number Systems," from "Principles of Mathematical Analysis" by Walter Rudin, drawing on the provided sources. This chapter lays the foundational concepts necessary for the study of mathematical analysis.

### Chapter 1: The Real and Complex Number Systems

**Introduction**
The chapter begins by emphasizing that a satisfactory discussion of core analysis concepts like convergence, continuity, differentiation, and integration requires an accurately defined number concept. It assumes familiarity with rational numbers (numbers of the form m/n, where m and n are integers and n ≠ 0). However, the text points out that the rational number system has "gaps". For instance, despite the fact that there's always another rational number between any two given rationals (e.g., (r+s)/2 between r and s), certain numbers like the square root of 2 (√2) are not rational. This "gap" means that for any rational p, p² can be less than 2 or greater than 2, but never exactly 2. The purpose of the real number system is to "fill these gaps," which is why it plays a fundamental role in analysis.

**Ordered Sets**
To understand the structure of real and complex numbers, general concepts like "ordered set" and "field" are introduced.

*   **Definitions 1.3 & 1.4:**
    *   A **set** is any collection of elements.
    *   `x ∈ A` means `x` is a member (or element) of set `A`.
    *   `x ∉ A` means `x` is not a member of set `A`.
    *   The **empty set** is the set containing no elements.
    *   A set with at least one element is **nonempty**.
    *   `A` is a **subset** of `B` (`A ⊂ B` or `B ⊃ A`) if every element of `A` is an element of `B`.
    *   `A` is a **proper subset** of `B` if `A ⊂ B` and there is an element of `B` not in `A`.
    *   `A = B` if `A ⊂ B` and `B ⊂ A`.
    *   `Q` denotes the set of all rational numbers throughout Chapter 1.

*   **Definition 1.5:**
    *   An **order** on a set `S` is a relation, denoted by `<`, with two properties:
        1.  If `x ∈ S` and `y ∈ S`, then exactly one of `x < y`, `x = y`, or `y < x` is true.
        2.  If `x < y` and `y < z`, then `x < z` (transitivity).
    *   An ordered set is a set `S` on which an order is defined.

**Fields**
A field is an algebraic structure where addition and multiplication can be performed, and where these operations behave similarly to how they do for rational or real numbers.

*   **Definition 1.12:** A set `F` with two operations, addition (`+`) and multiplication (`·`), is a **field** if it satisfies the following axioms for all `x, y, z ∈ F`:
    *   **Addition Axioms (A):**
        *   (A1) `x + y = y + x` (commutative law)
        *   (A2) `(x + y) + z = x + (y + z)` (associative law)
        *   (A3) There exists an element `0 ∈ F` such that `x + 0 = x` for all `x` (additive identity).
        *   (A4) For every `x ∈ F`, there exists `-x ∈ F` such that `x + (-x) = 0` (additive inverse).
    *   **Multiplication Axioms (M):**
        *   (M1) `xy = yx` (commutative law)
        *   (M2) `(xy)z = x(yz)` (associative law)
        *   (M3) There exists an element `1 ∈ F` such that `x · 1 = x` and `1 ≠ 0` (multiplicative identity).
        *   (M4) For every `x ∈ F` such that `x ≠ 0`, there exists `1/x ∈ F` such that `x · (1/x) = 1` (multiplicative inverse).
    *   **Distributive Law (D):**
        *   (D) `x(y + z) = xy + xz`.

*   **Remarks 1.13:**
    *   The set of all rational numbers `Q` is a field with customary addition and multiplication.
    *   Studying field axioms is valuable because familiar properties of `Q` (and later `R` and `C`) are consequences of these axioms.

*   **Proposition 1.14 (Consequences of Addition Axioms):**
    *   (a) If `x + y = x + z`, then `y = z` (cancellation law).
    *   (b) If `x + y = x`, then `y = 0` (uniqueness of additive identity).
    *   (c) If `x + y = 0`, then `y = -x` (uniqueness of additive inverse).
    *   (d) `-(-x) = x`.
    *   **Proof Sketch:** (a) Add `-x` to both sides and use associativity and identity axioms. (b) Take `z = 0` in (a). (c) Take `z = -x` in (a). (d) Use (c) with `-x` in place of `x`.

*   **Proposition 1.15 (Consequences of Multiplication Axioms):** Similar statements for multiplication hold. (Proof omitted as similar to 1.14).

*   **Proposition 1.16 (Consequences of Field Axioms):**
    *   (a) `0x = 0`.
    *   (b) If `x ≠ 0` and `y ≠ 0`, then `xy ≠ 0`.
    *   (c) `(-x)y = -(xy) = x(-y)`.
    *   (d) `(-x)(-y) = xy`.
    *   **Proof Sketch:** (a) `0x + 0x = (0+0)x = 0x`. By 1.14(b), `0x = 0`.

*   **Definition 1.17:** An **ordered field** is a field `F` which is also an ordered set (satisfying Definition 1.5) and has the following properties for all `x, y, z ∈ F`:
    *   (i) If `x > 0` and `y > 0`, then `x + y > 0`.
    *   (ii) If `x > 0` and `y > 0`, then `xy > 0`.

*   **Proposition 1.18 (Properties of Ordered Fields):**
    *   (a) If `x > 0`, then `-x < 0`, and vice versa.
    *   (b) If `x > y`, then `x + z > y + z`.
    *   (c) If `x > 0` and `y < z`, then `xy < xz`.
    *   (d) If `x < 0` and `y < z`, then `xy > xz`.
    *   (e) If `x ≠ 0`, then `x² > 0`.
    *   (f) `1 > 0`.
    *   (g) If `0 < x < y`, then `0 < 1/y < 1/x`.
    *   **Proof Sketch:** (a) Add `x` or `-x` to inequalities. (b) `z-y > 0`, so `x(z-y) > 0`. (e) If `x > 0`, `x² > 0` by (ii). If `x < 0`, `-x > 0`, so `(-x)² > 0`, and `x² = (-x)²`. (f) `1 = 1²`, so `1 > 0` by (e). (g) Multiply by `(1/x)(1/y)`.

**The Real Field**
This section introduces the real number system `R` as an ordered field with a crucial additional property.

*   **Definition 1.8:** An ordered set `S` has the **least-upper-bound property** if every non-empty subset of `S` that is bounded above has a supremum (least upper bound) in `S`.

*   **Theorem 1.19 (Existence of Real Field):** There exists an ordered field `R` which has the least-upper-bound property. Moreover, `R` contains `Q` as a subfield. The members of `R` are called **real numbers**.
    *   **Proof:** The proof is long and tedious and is presented in the Appendix to Chapter 1, where `R` is actually constructed from `Q`. This construction, known as Dedekind's construction, starts with rational numbers and builds the real numbers by defining them as "cuts".

*   **Theorem 1.20 (Archimedean Property & Density of Rationals):**
    *   (a) If `x ∈ R`, `y ∈ R`, and `x > 0`, then there is a positive integer `n` such that `nx > y` (Archimedean property).
    *   (b) If `x ∈ R`, `y ∈ R`, and `x < y`, then there exists a rational `p ∈ Q` such that `x < p < y` (Density of Rationals).
    *   **Proof Sketch:** (a) Assume `nx ≤ y` for all `n`. Then `y` is an upper bound of the set `{nx}`. By the least-upper-bound property, this set has a supremum, say `α`. Then `α - x` is not an upper bound, so `α - x < mx` for some `m`. This implies `α < (m+1)x`, contradicting `α` being the supremum. (b) Apply (a) to `1` and `y-x` to find an `n` such that `n(y-x) > 1`. Then find an integer `m` such that `m-1 ≤ nx < m`. This leads to `x < m/n < y`, where `p = m/n` is rational.

*   **Theorem 1.21 (Existence of nth Roots):** For every real `x > 0` and every integer `n > 0`, there is one and only one real `y` such that `yⁿ = x`. This `y` is written as `√ⁿx` or `x¹/ⁿ`.
    *   **Proof Sketch:** The uniqueness is clear (`y₁ < y₂` implies `y₁ⁿ < y₂ⁿ`). For existence, let `E` be the set of all positive real numbers `t` such that `tⁿ < x`. `E` is non-empty (e.g., `x/(1+x) ∈ E`) and bounded above (e.g., `1+x` is an upper bound). By Theorem 1.19, `y = sup E` exists. The proof then shows `yⁿ` cannot be less than `x` (by constructing `y+h ∈ E` for some `h>0`) and cannot be greater than `x` (by constructing `y-h ∉ E` for some `h>0`), thus `yⁿ = x` must hold.

**The Extended Real Number System**
This system expands the real numbers by including infinities.

*   **Definition:** The extended real number system consists of the real numbers `R` and two symbols, `+∞` and `-∞`. The original order in `R` is preserved, and `-∞ < x < +∞` for every `x ∈ R`.
*   **Property:** In this system, `+∞` is an upper bound of every subset, and every nonempty subset has a least upper bound. Similarly for lower bounds.
*   **Note:** The extended real number system **does not form a field**. Certain conventions are made for arithmetic with `±∞`.

**The Complex Field**
Complex numbers are introduced as ordered pairs of real numbers.

*   **Definition 1.24:** A **complex number** `z` is an ordered pair `(a, b)` of real numbers. Rules for addition and multiplication are defined:
    *   `(a, b) + (c, d) = (a+c, b+d)`.
    *   `(a, b) · (c, d) = (ac-bd, ad+bc)`.
*   **Theorem 1.25:** The set of complex numbers, with these operations, forms a field. (Proof shows verification of all field axioms).
*   **Theorem 1.26:** For any real numbers `a` and `b`, `(a, 0) + (b, 0) = (a+b, 0)` and `(a, 0)(b, 0) = (ab, 0)`. This shows complex numbers of the form `(a, 0)` have the same arithmetic properties as real numbers, allowing identification of `(a, 0)` with `a`, making the real field a subfield of the complex field.
*   **Definition 1.27:** `i = (0, 1)`.
*   **Theorem 1.28:** `i² = -1`. (Proof: `i² = (0, 1)(0, 1) = (-1, 0) = -1`).
*   **Theorem 1.29:** If `a` and `b` are real, then `(a, b) = a + bi`. (Proof: `a + bi = (a, 0) + (b, 0)(0, 1) = (a, 0) + (0, b) = (a, b)`).
*   **Definition 1.30:** If `z = a + bi`, its **conjugate** is `z̄ = a - bi`. `a` is the **real part** (`Re(z)`) and `b` is the **imaginary part** (`Im(z)`).
*   **Theorem 1.31 (Properties of Conjugates):**
    *   (a) `z + w = z̄ + w̄`.
    *   (b) `zw = z̄w̄`.
    *   (c) `z + z̄ = 2Re(z)`.
    *   (d) `z - z̄ = 2i Im(z)`.
    *   (e) `z z̄` is real and positive (except when `z = 0`).
    *   **Proof Sketch:** (a), (b), (c) trivial. (d) If `z = a + bi`, `zz̄ = a² + b²`.
*   **Definition 1.32:** The **absolute value** of `z` is `|z| = (zz̄)¹/²`.
*   **Theorem 1.33 (Properties of Absolute Value):**
    *   (a) `|z| > 0` unless `z = 0`, `|0| = 0`.
    *   (b) `|z| = |z̄|`.
    *   (c) `|zw| = |z||w|`.
    *   (d) `|Re z| ≤ |z|`.
    *   (e) `|z+w| ≤ |z|+|w|` (Triangle Inequality).
    *   **Proof Sketch:** (c) `|zw|² = (ac-bd)² + (ad+bc)² = (a²+b²)(c²+d²) = |z|²|w|²`. (d) `a² ≤ a²+b²` implies `|a| ≤ √(a²+b²)`. (e) `|z+w|² = (z+w)(z̄+w̄) = zz̄ + zw̄ + z̄w + ww̄ = |z|² + 2Re(zw̄) + |w|²`. Since `Re(zw̄) ≤ |zw̄| = |z||w|`, the inequality follows.

*   **Theorem 1.35 (Schwarz Inequality):** For complex numbers `a₁, ..., aₙ` and `b₁, ..., bₙ`:
    `|∑(j=1 to n) aⱼb̄ⱼ|² ≤ (∑(j=1 to n) |aⱼ|²)(∑(j=1 to n) |bⱼ|²)`.
    *   **Proof Sketch:** Let `A = ∑|aⱼ|²`, `B = ∑|bⱼ|²`, `C = ∑aⱼb̄ⱼ`. If `B=0`, trivial. Assume `B>0`. Consider `∑|Baⱼ - Cbⱼ|² = B(AB - |C|²)`. Since `∑|Baⱼ - Cbⱼ|² ≥ 0`, it implies `AB - |C|² ≥ 0`, hence `|C|² ≤ AB`.

**Euclidean Spaces**
Euclidean spaces generalize the concept of a line or a plane to higher dimensions.

*   **Definition 1.36:** For each positive integer `k`, **Euclidean k-space** `Rᵏ` is the set of all ordered `k`-tuples `x = (x₁, ..., xᵏ)` where `xᵢ ∈ R`.
    *   **Vector Addition:** `x + y = (x₁ + y₁, ..., xᵏ + yᵏ)`.
    *   **Scalar Multiplication:** `cx = (cx₁, ..., cxᵏ)`.
    *   **Inner Product (dot product):** `x · y = ∑(i=1 to k) xᵢyᵢ`.
    *   **Norm (length):** `|x| = (x · x)¹/² = (∑(i=1 to k) xᵢ²)¹/²`.

*   **Theorem 1.37 (Properties of Inner Product and Norm):** For `x, y, z ∈ Rᵏ`:
    *   (a) `|x| ≥ 0`.
    *   (b) `|x| = 0` if and only if `x = 0`.
    *   (c) `|cx| = |c||x|`.
    *   (d) `|x · y| ≤ |x||y|` (Schwarz inequality for `Rᵏ`).
    *   (e) `|x+y| ≤ |x|+|y|` (Triangle inequality for `Rᵏ`).
    *   (f) `|x-z| ≤ |x-y|+|y-z|`.
    *   **Proof Sketch:** (a), (b), (c) obvious. (d) Follows directly from Theorem 1.35 by setting `aᵢ = xᵢ` and `bᵢ = yᵢ` (real case). (e) `|x+y|² = (x+y)·(x+y) = x·x + 2x·y + y·y = |x|² + 2x·y + |y|²`. Using (d), `2x·y ≤ 2|x||y|`, so `|x+y|² ≤ |x|² + 2|x||y| + |y|² = (|x|+|y|)². Taking square roots gives (e). (f) Replace `x` by `x-y` and `y` by `y-z` in (e).

*   **Remarks 1.38:**
    *   `R¹` (set of all real numbers) is called the **line** or **real line**.
    *   `R²` is called the **plane** or **complex plane**.
    *   In `R¹` and `R²`, the norm is just the absolute value of the corresponding real or complex number.

**Appendix: Construction of R from Q (Dedekind Cuts)**
This appendix provides the constructive proof for Theorem 1.19, demonstrating the existence of the real number system.

*   **Step 1: Definition of Cuts:**
    *   The members of `R` are defined as certain subsets of `Q`, called **cuts**.
    *   A cut `α` is a set `α ⊂ Q` with three properties:
        *   (I) `α` is not empty, and `α ≠ Q` (i.e., `α` is a proper non-empty subset of `Q`).
        *   (II) If `p ∈ α`, `q ∈ Q`, and `q < p`, then `q ∈ α` (i.e., `α` is "closed downwards").
        *   (III) If `p ∈ α`, then `p < r` for some `r ∈ α` (i.e., `α` has no largest member).
    *   (II) implies: If `p ∈ α` and `q ∉ α`, then `p < q`. If `r ∉ α` and `r < s`, then `s ∉ α`.

*   **Step 2: Order on Cuts:**
    *   For two cuts `α` and `β`, `α < β` is defined to mean that `α` is a proper subset of `β`.
    *   This relation satisfies the properties of an order (Definition 1.5): transitivity (`α < β` and `β < γ` implies `α < γ`) and trichotomy (exactly one of `α < β`, `α = β`, or `β < α` holds).
    *   Thus, `R` (the set of all cuts) becomes an ordered set.

*   **Step 3: Least-Upper-Bound Property:**
    *   To prove `R` has the least-upper-bound property, let `A` be a non-empty subset of `R` that is bounded above.
    *   Let `γ` be the union of all cuts `α` in `A` (`γ = ∪{α | α ∈ A}`). It is shown that `γ` is also a cut and `γ = sup A`.

*   **Step 4: Addition of Cuts:**
    *   For `α ∈ R` and `β ∈ R`, `α + β` is defined as the set of all sums `r + s`, where `r ∈ α` and `s ∈ β`.
    *   `0*` is defined as the set of all negative rational numbers; `0*` is shown to be a cut.
    *   The axioms for addition (A1-A5) are verified for `R`, with `0*` playing the role of `0`.

*   **Step 5: Order and Addition:**
    *   It is shown that if `α, β, γ ∈ R` and `β < γ`, then `α + β < α + γ`. This follows from the definition of addition and the cancellation law (Proposition 1.14).
    *   Also, `α > 0*` if and only if `-α < 0*`.

*   **Step 6: Multiplication of Cuts (for positive cuts):**
    *   For `α ∈ R⁺` (cuts `α > 0*`) and `β ∈ R⁺`, `αβ` is defined as the set of all `p ∈ Q` such that `p < rs` for some choice of `r ∈ α, s ∈ β, r > 0, s > 0`.
    *   `1*` is defined as the set of all rational numbers `q < 1`.
    *   The multiplication axioms (M) and distributive law (D) are shown to hold in `R⁺` with `1*` as the multiplicative identity.

*   **Step 7: Multiplication of Cuts (general case):**
    *   Multiplication is extended to all cuts `α, β ∈ R` by defining `α0* = 0*α = 0*`, and using rules like `(-α)(-β) = αβ`, `(-α)β = -[(-α)β]`, and `α(-β) = -[α(-β)]`.
    *   With these definitions, `R` is proven to be an **ordered field with the least-upper-bound property**.

*   **Step 8: Isomorphism of Q and Q*:**
    *   For each rational number `r`, a corresponding cut `r*` is defined as the set of all `p ∈ Q` such that `p < r`.
    *   It is proven that these "rational cuts" satisfy:
        *   (a) `r* + s* = (r+s)*`.
        *   (b) `r*s* = (rs)*`.
        *   (c) `r* < s*` if and only if `r < s`.
    *   This means the ordered field `Q` is isomorphic to the ordered field `Q*` (the set of rational cuts).

*   **Step 9: Q as a Subfield of R:**
    *   The isomorphism allows `Q` to be **regarded as a subfield of R**.
    *   The uniqueness of such ordered fields with the least-upper-bound property (up to isomorphism) is noted, implying `R` is completely characterized by these properties.
    *   Other constructions of `R` from `Q` exist, such as using equivalence classes of Cauchy sequences of rational numbers (Cantor's construction).