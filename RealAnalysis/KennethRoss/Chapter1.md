Here are detailed revision notes for Chapter 1, "Introduction," drawing on the provided sources:

Chapter 1, titled "**Introduction**", sets the scene for the entire book by laying down the fundamental properties of the set of **real numbers (R)**, which serves as the underlying space for all the analysis discussed. These properties act as axioms, from which all other properties of real numbers can be derived. The chapter also briefly touches upon **set notation** in an appendix.

### §1 The Set N of Natural Numbers

*   **Definition of N**: The set of **natural numbers**, denoted by **N**, is defined as the set of all positive integers: **{1, 2, 3, ...}**.
*   **Successor**: Every positive integer *n* in **N** has a successor, *n + 1*.
*   **Peano Axioms (Peano Postulates)**: These five properties describe **N**:
    *   **N1**: **1** belongs to **N**.
    *   **N2**: If *n* belongs to **N**, then its successor *n + 1* belongs to **N**.
    *   **N3**: **1** is not the successor of any element in **N**.
    *   **N4**: If *n* and *m* in **N** have the same successor, then *n = m*.
    *   **N5**: A subset of **N** which contains **1**, and which contains *n + 1* whenever it contains *n*, must equal **N**.
        *   **N5** is considered the basis of **mathematical induction**.
*   **Principle of Mathematical Induction**: This principle asserts that a list of statements *P1, P2, P3, ...* are all true, provided two conditions are met:
    *   **(I1) P1 is true** (known as the **basis for induction**).
    *   **(I2) Pn+1 is true whenever Pn is true** (known as the **induction step**).
*   **Extended Principle of Mathematical Induction**: A list of propositions *Pm, Pm+1, ...* is true provided *Pm* is true, and *Pn+1* is true whenever *Pn* is true and *n ≥ m*.
*   **The Binomial Theorem**: For *a, b ∈ R* and a positive integer *n*, it asserts:
    *   **(a + b)n = (n 0) an + (n 1) an-1b + (n 2) an-2b2 + · · · + (n n-1) abn-1 + (n n) bn**.
    *   This can also be written as **an + nan-1b + (1/2)n(n-1)an-2b2 + · · · + nabn-1 + bn**.
    *   The binomial coefficients **(n k)** are defined as **n! / (k!(n-k)!)** for *k = 0, 1, ..., n*, with *n! = 1 · 2 · 3 · · · n* and *0! = 1*.

### §2 The Set Q of Rational Numbers

*   **Definition of Q**: The set of **rational numbers**, denoted by **Q**, consists of numbers that can be expressed as *m/n*, where *m, n ∈ Z* (integers) and *n ≠ 0*.
*   **Properties of Q**:
    *   **Q** includes all terminating decimals.
    *   **Q** is a "highly satisfactory algebraic system" where basic operations (addition, multiplication, subtraction, division) can be fully studied.
    *   However, **Q** is described as "inadequate in some ways," possessing "defects".
*   **Theorem 2.2: Rational Zeros Theorem**: Suppose *c0, c1, ..., cn* are integers and *r* is a rational number satisfying the polynomial equation *cnx n + cn-1x n-1 + · · · + c1x + c0 = 0*. If *r = p/d* where *p* and *d* are integers with no common factors, then *p* divides *c0* and *d* divides *cn*.
*   **Corollary 2.3**: For a polynomial equation *xn + cn-1x n-1 + · · · + c1x + c0 = 0* where *c0, c1, ..., cn-1* are integers and *c0 ≠ 0*, any rational solution must be an integer that divides *c0*.
    *   This corollary is useful for proving that certain numbers, like **√2**, are not rational.
*   **Examples of Non-rational Numbers**: The theorem and its corollary are used to demonstrate that numbers such as **√2, √3, √5, √7, √24, √31** are not rational numbers. Similarly, **3√2, 7√5, 4√13** are not rational.

### §3 The Set R of Real Numbers

*   **Definition of R**: The set of **real numbers**, denoted by **R**, is the mathematical system on which the book's analysis is performed.
    *   **R** includes all rational numbers, all algebraic numbers, **π, e, and more**.
    *   **R** can be visualised as the **real number line**, where every real number corresponds to a point and every point corresponds to a real number, meaning **R** has no "gaps" (unlike **Q**).
    *   Real numbers also have **decimal expansions**.
*   **Algebraic Properties (Field Properties)**: **R** satisfies nine properties related to addition and multiplication (A1-A4, M1-M4, DL). A system with more than one element satisfying these is called a **field**.
    *   **A1** (Associative Law for addition): *(a + b) + c = a + (b + c)*
    *   **A2** (Commutative Law for addition): *a + b = b + a*
    *   **A3** (Additive Identity): There is a unique element *0* such that *a + 0 = a* for all *a*
    *   **A4** (Additive Inverse): For each *a*, there is a unique element *-a* such that *a + (-a) = 0*
    *   **M1** (Associative Law for multiplication): *(ab)c = a(bc)*
    *   **M2** (Commutative Law for multiplication): *ab = ba*
    *   **M3** (Multiplicative Identity): There is a unique element *1 ≠ 0* such that *a · 1 = a* for all *a*
    *   **M4** (Multiplicative Inverse): For each *a ≠ 0*, there is a unique element *a-1* such that *a · a-1 = 1*
    *   **DL** (Distributive Law): *a(b + c) = ab + ac* [34, source for definitions based on common mathematical knowledge - not explicitly defined in the provided snippets, but referenced as 'these nine properties'].
*   **Order Properties (O1-O5)**: **R** is an ordered field, meaning it has an ordering '≤' that satisfies these properties (not explicitly detailed in snippets, but referenced).
*   **Definition 3.3: Absolute Value**: For *a ∈ R*, **|a| = a if a ≥ 0** and **|a| = -a if a ≤ 0**.
    *   Intuitively, **|a|** represents the distance between **0** and **a**.
*   **Definition 3.4: Distance**: For numbers *a* and *b*, **dist(a, b) = |a - b|**. It represents the distance between *a* and *b*.
*   **Theorem 3.5: Properties of Absolute Value**:
    *   **(i) |a| ≥ 0** for all *a ∈ R*.
    *   **(ii) |ab| = |a| · |b|** for all *a, b ∈ R*.
    *   **(iii) |a + b| ≤ |a| + |b|** for all *a, b ∈ R* (known as the **Triangle Inequality**).
*   **Theorem 3.7: Triangle Inequality**: **|a + b| ≤ |a| + |b|** for all *a, b ∈ R*.
    *   A useful variant: **||a| - |b|| ≤ |a - b|**.
    *   Generalization: **|a1 + a2 + · · · + an| ≤ |a1| + |a2| + · · · + |an|**.
*   **Inequalities involving absolute value**:
    *   **|b| ≤ a if and only if -a ≤ b ≤ a**.
    *   **|b| < a if and only if -a < b < a**.
    *   **|a - b| < c if and only if b - c < a < b + c**.
    *   **|a - b| ≤ c if and only if b - c ≤ a ≤ b + c**.

### §4 The Completeness Axiom

*   **Significance**: This axiom is crucial as it guarantees **R has no "gaps"** and almost every significant result in the book relies on it.
*   **Definition 4.1**:
    *   **(a) Maximum (maxS)**: If a nonempty subset **S** of **R** contains a largest element *s0* (*s0 ∈ S* and *s ≤ s0* for all *s ∈ S*), then *s0* is the maximum of **S**.
    *   **(b) Minimum (minS)**: If **S** contains a smallest element, it is called the minimum of **S**.
*   **Definition 4.2: Bounded Sets**:
    *   **(a) Bounded Above**: A set **S** is bounded above if there exists *M ∈ R* such that *s ≤ M* for all *s ∈ S*. *M* is an **upper bound**.
    *   **(b) Bounded Below**: A set **S** is bounded below if there exists *m ∈ R* such that *s ≥ m* for all *s ∈ S*. *m* is a **lower bound**.
    *   **(c) Bounded Set**: A set **S** is bounded if it is both bounded above and bounded below.
*   **Definition 4.3: Supremum and Infimum**:
    *   **(a) Supremum (supS)**: If **S** is bounded above, its **supremum** is the **least upper bound** of **S** (the smallest of all upper bounds).
    *   **(b) Infimum (infS)**: If **S** is bounded below, its **infimum** is the **greatest lower bound** of **S** (the largest of all lower bounds).
    *   **Properties**:
        *   If **S** has a maximum, then **maxS = supS**.
        *   If **S** has a minimum, then **minS = infS**.
        *   If **S** is bounded above, *M = supS* if and only if *s ≤ M* for all *s ∈ S*, and whenever *M1 < M*, there exists *s1 ∈ S* such that *s1 > M1*.
*   **Axiom 4.4: The Completeness Axiom**: Every nonempty subset of **R** that is bounded above has a supremum in **R**.
    *   This axiom is implicitly used in showing *lim inf sn* and *lim sup sn* are meaningful.
*   **Corollary 4.5**: Every nonempty subset of **R** that is bounded below has an infimum in **R**. Specifically, **inf S = -sup(-S)**.
*   **Theorem 4.6: Archimedean Property**: If *a > 0* and *b > 0*, then for some positive integer *n*, **na > b**.
    *   This implies: if *a > 0*, then **1/n < a** for some *n ∈ N*; and if *b > 0*, then **b < n** for some *n ∈ N*.
*   **Theorem 4.7: Denseness of Q** (referenced in Exercise 4.11): Between any two distinct real numbers *a* and *b*, there exists a rational number *r* such that *a < r < b*.

### §5 The Symbols +∞ and −∞

*   **Purpose**: These symbols (**+∞** and **−∞**, often just **∞**) are extremely useful but **are not real numbers**.
*   **Extension of Ordering**: They are adjoined to **R** to form **R ∪ {−∞, +∞}**, with the agreement that **−∞ ≤ a ≤ +∞** for all *a* in **R ∪ {−∞, +∞}**.
    *   This extended set is **not provided with any algebraic structure**.
*   **Extension of Interval Notation**: Used to define unbounded intervals:
    *   **[a, ∞) = {x ∈ R : a ≤ x}**
    *   **(a, ∞) = {x ∈ R : a < x}**
    *   **(-∞, b] = {x ∈ R : x ≤ b}**
    *   **(-∞, b) = {x ∈ R : x < b}**
    *   **(-∞, ∞)** is used for **R**.
*   **Extension of Supremum/Infimum Definitions**:
    *   **supS = +∞ if S is not bounded above**.
    *   **infS = −∞ if S is not bounded below**.
    *   **For any nonempty subset S of R, supS and infS always make sense**.
    *   **inf S ≤ sup S** always holds for any nonempty subset of **R**.

### §6 A Development of R (Enrichment Section)

*   **Motivation**: Real numbers can be described as the supremum of a set of rationals: **a = sup{r ∈ Q : r < a}**.
*   **Dedekind Cuts**: Subsets **α** of **Q** satisfying three properties are called **Dedekind cuts**:
    *   **(i) α ≠ Q and α is not empty**.
    *   **(ii) If r ∈ α, s ∈ Q and s < r, then s ∈ α**.
    *   **(iii) α contains no largest rational**.
*   **Definition of R using Dedekind Cuts**: In this development, the set **R** of real numbers is defined as the space of all Dedekind cuts.
    *   Rational numbers are identified with specific Dedekind cuts: **s\* = {r ∈ Q : r < s}**.
*   **Order Structure**: For Dedekind cuts **α** and **β**, **α ≤ β** signifies **α ⊆ β**.
*   **Addition**: For Dedekind cuts **α** and **β**, **α + β = {r1 + r2 : r1 ∈ α and r2 ∈ β}**.
*   **Completeness**: The ordered field **R** constructed from **Q** in this manner is **complete**, meaning the completeness property (Axiom 4.4) can be *proved* as a theorem rather than taken as an axiom.
*   **Alternative Developments**: **R** can also be developed from Cauchy sequences in **Q** or based on Peano's axioms.