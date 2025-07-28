Here are detailed revision notes for Chapter 1: "Real Numbers," covering sections 1.1 to 1.5, drawing from the provided sources.

### Chapter 1: Real Numbers

This chapter lays the rigorous groundwork for real analysis by deeply exploring the **properties of the real number system**. Understanding these properties is crucial as they form the "basis for all that follows" in the course.

#### 1.1 Basic Properties

This section introduces the foundational algebraic and order properties that define the real numbers.
*   **Main Objects**: The primary objects of study in analysis are the **real numbers (ℝ)**.
*   **Key Properties of ℝ**: The real numbers are characterised by three essential properties:
    1.  It is an **ordered set**.
    2.  It possesses the **least-upper-bound property** (completeness).
    3.  It is a **field** compatible with its order.

*   **Ordered Sets**:
    *   **Definition**: An ordered set *S* is a set with a relation '<' satisfying two axioms:
        *   **(Trichotomy)** For any *x, y* in *S*, exactly one of *x < y*, *x = y*, or *y < x* holds.
        *   **(Transitivity)** If *x < y* and *y < z*, then *x < z*.
    *   **Notation**: *x ≤ y* means *x < y* or *x = y*. Similarly for '>' and '≥'.
    *   **Examples**: The set of **rational numbers (ℚ)**, **natural numbers (ℕ)**, and **integers (ℤ)** are ordered sets. Other examples include countries ordered by landmass or words by lexicographic ordering.
*   **Bounded Sets, Supremum, and Infimum**:
    *   **Bounded Above**: A set *E ⊂ S* is bounded above if there exists an element *b ∈ S* (an **upper bound**) such that *x ≤ b* for all *x ∈ E*.
    *   **Bounded Below**: A set *E ⊂ S* is bounded below if there exists an element *b ∈ S* (a **lower bound**) such that *x ≥ b* for all *x ∈ E*.
    *   **Bounded**: A set is bounded if it is both bounded above and bounded below.
    *   **Least Upper Bound (Supremum)**: If an upper bound *b₀* of *E* is less than or equal to all other upper bounds of *E*, *b₀* is the **supremum** (sup *E*) of *E*. If it exists, the supremum is **unique**.
    *   **Greatest Lower Bound (Infimum)**: Similarly, if a lower bound *b₀* of *E* is greater than or equal to all other lower bounds of *E*, *b₀* is the **infimum** (inf *E*) of *E*. If it exists, the infimum is **unique**.
*   **The Least-Upper-Bound Property (Completeness Property)**:
    *   This property states that **every nonempty subset of ℝ that is bounded above has a supremum in ℝ**.
    *   The set of rational numbers ℚ **does not have this property**; for example, the set {*x ∈ ℚ : x² < 2*} is bounded above in ℚ (e.g., by 2), but its supremum, √2, is not in ℚ. This illustrates a fundamental difference between ℚ and ℝ.
*   **Fields**:
    *   **Definition**: A set *F* is a **field** if it has two operations, addition (+) and multiplication (·), satisfying specific axioms (A1-A5 for addition, M1-M5 for multiplication, and the distributive law D). These axioms define the basic arithmetic properties like commutativity, associativity, existence of identity elements (0 and 1), and inverses (additive and multiplicative).
    *   **Examples**: The set of rational numbers **ℚ is a field**. The set of integers **ℤ is not a field** because it lacks multiplicative inverses (e.g., 2 has no inverse in ℤ).
*   **Ordered Fields**:
    *   **Definition**: An ordered field is a field that is also an ordered set, where the order relation is compatible with the field operations:
        *   *x < y* implies *x + z < y + z* for all *x, y, z* in *F*.
        *   *x > 0* and *y > 0* implies *xy > 0* for all *x, y* in *F*.
    *   **Properties**: Various inequalities can be proven from these axioms, such as *x² > 0* for any non-zero *x*, and *1 > 0*.
    *   **Complex Numbers (ℂ)**: The complex numbers are a field, but they **cannot be made into an ordered field** because *i² = -1*, which would contradict the property that squares of non-zero numbers must be positive in an ordered field (*-1 < 0* must hold).

#### 1.2 The Set of Real Numbers

This section formally introduces the real numbers and their crucial properties.
*   **Existence and Uniqueness**: The **real number system ℝ** is defined as the **unique ordered field with the least-upper-bound property** that contains ℚ. This theorem is stated without proof in this textbook, simplifying the construction of ℝ.
*   **Proving Equality in Analysis**: A common strategy in analysis to prove *x = 0* (or any equality) is to **prove two inequalities**: *x ≤ 0* and *x ≥ 0*. To show *x ≤ 0*, one typically proves that *x < 𝜖* for all *𝜖 > 0*. This "estimate and inequality" approach is central to analysis.
*   **Existence of √2**: The least-upper-bound property guarantees the existence of numbers not in ℚ. For example, there exists a **unique positive real number *r* such that *r² = 2***, denoted as √2. This is proven by considering the set {*x ∈ ℝ : x² < 2*}, showing it is bounded and nonempty, and then demonstrating that its supremum satisfies *r² = 2*. √2 is an **irrational number** (√2 ∉ ℚ). The set of **irrational numbers (ℝ \ ℚ) is nonempty**.
*   **Archimedean Property**:
    *   **Statement**: For any *x, y ∈ ℝ* with *x > 0*, there exists a natural number *n ∈ ℕ* such that **nx > y**.
    *   **Interpretation**: This implies that **ℕ is not bounded above in ℝ**.
*   **Density of Rational Numbers (ℚ is dense in ℝ)**:
    *   **Statement**: For any two real numbers *x, y* such that *x < y*, there exists a **rational number *r ∈ ℚ* such that *x < r < y***. This means that between any two distinct real numbers, there is always a rational number.
    *   The proof relies on the Archimedean property to find a suitable *n* such that *1/n* is smaller than the interval length *y-x*, then finding an integer *m* to place *m/n* within (*x, y*).
*   **Using Supremum and Infimum with Operations**:
    *   For a nonempty set *A ⊂ ℝ* and *x ∈ ℝ*:
        *   **sup(*x* + *A*) = *x* + sup *A***.
        *   **inf(*x* + *A*) = *x* + inf *A***.
    *   For *x > 0*: **sup(*x*A) = *x*(sup *A*)** and **inf(*x*A) = *x*(inf *A*)**.
    *   For *x < 0*: **sup(*x*A) = *x*(inf *A*)** and **inf(*x*A) = *x*(sup *A*)**. **Multiplying by a negative number swaps supremum and infimum**.
    *   If *A, B ⊂ ℝ* are nonempty such that *x ≤ y* for all *x ∈ A, y ∈ B*, then **sup *A* ≤ inf *B***.
    *   **Approximation Property of Supremum**: If *S ⊂ ℝ* is nonempty and bounded above, for every *𝜖 > 0*, there exists an *x ∈ S* such that **(sup *S*) - *𝜖* < *x* ≤ sup *S***.
*   **Extended Real Numbers (ℝ*)**:
    *   To allow for suprema and infima of empty or unbounded sets, **∞** and **-∞** are introduced.
    *   **Definitions**: sup ∅ = -∞, sup *A* = ∞ (if *A* is not bounded above), inf ∅ = ∞, inf *A* = -∞ (if *A* is not bounded below).
    *   **ℝ*** = ℝ ∪ {-∞, ∞} forms an **ordered set** where -∞ < *x* < ∞ for all *x ∈ ℝ*.
    *   **Important Note**: ℝ* is **not a field**, and arithmetic with ∞ and -∞ is restricted to avoid inconsistencies (e.g., ∞ - ∞ is undefined).
*   **Maxima and Minima**:
    *   When the supremum or infimum of a set *A* actually **belongs to *A***, they are called the **maximum (max *A*)** or **minimum (min *A*)**, respectively. This notation is commonly used for finite sets.

#### 1.3 Absolute Value and Bounded Functions

This section introduces the crucial concept of absolute value and its application to functions.
*   **Absolute Value**:
    *   **Definition**: For *x ∈ ℝ*, **|x|** is defined as *x* if *x ≥ 0*, and *-x* if *x < 0*. It represents the "size" of a real number.
    *   **Properties**: Key properties include:
        *   |x| ≥ 0, and |x| = 0 if and only if *x = 0*.
        *   |-x| = |x|.
        *   |xy| = |x||y|.
        *   |x|² = x².
        *   |x| ≤ *y* if and only if -*y* ≤ *x* ≤ *y*.
        *   -*|x|* ≤ *x* ≤ *|x|*.
    *   **Triangle Inequality**: **|x + y| ≤ |x| + |y|**.
    *   **Reverse Triangle Inequality**: **||x| - |y|| ≤ |x - y|**.
*   **Bounded Functions**:
    *   A function *f: D → ℝ* is **bounded** if its range *f(D)* is a bounded set.
    *   The supremum and infimum of a function *f* over its domain *D* are denoted **supₓ∈D *f(x)*** (or sup *f(D)*) and **infₓ∈D *f(x)*** (or inf *f(D)*).
    *   **Property**: If *f: D → ℝ* and *g: D → ℝ* are bounded functions such that *f(x) ≤ g(x)* for all *x ∈ D*, then **supₓ∈D *f(x)* ≤ supₓ∈D *g(x)*** and **infₓ∈D *f(x)* ≤ infₓ∈D *g(x)***.

#### 1.4 Intervals and the Size of ℝ

This section formally defines intervals and discusses the "size" of the real number set.
*   **Intervals**: For *a, b ∈ ℝ* with *a < b*:
    *   **Closed interval**: **[*a, b*]** = {*x ∈ ℝ : a ≤ x ≤ b*}.
    *   **Open interval**: **(*a, b*)** = {*x ∈ ℝ : a < x < b*}.
    *   **Half-open intervals**: **(*a, b*]** and **[*a, b*)**.
    *   **Unbounded intervals**: **[*a, ∞*)**, **(*a, ∞*)**, **(-∞, *b*]**, **(-∞, *b*)**, and **(-∞, ∞) = ℝ**.
*   **Characterisation of Intervals**: A set *I ⊂ ℝ* is an interval if and only if it contains at least two points and for any *a, c ∈ I* and *b ∈ ℝ* such that *a < b < c*, it implies *b ∈ I*.
*   **Cardinality of Intervals**: All intervals in ℝ (with at least two points) have the **same "size" (cardinality)**.
*   **Uncountability of ℝ**:
    *   The set of real numbers **ℝ is uncountable**. This means it cannot be put into a one-to-one correspondence with the natural numbers ℕ.
    *   This is a significant contrast to the **rational numbers ℚ, which are countable**.
    *   **Cantor's Diagonalization Argument**: This method is used to prove the uncountability of ℝ. The core idea is to assume that ℝ (or a subset like (0,1]) is countable and can be listed as a sequence {*x₁*, *x₂*, ...}. A new real number *y* is then constructed such that its *n*-th digit differs from the *n*-th digit of *xₙ* for every *n*, ensuring *y* is not in the list. This leads to a contradiction, proving ℝ is uncountable.
    *   The cardinality of ℝ is the same as the cardinality of the power set of ℕ (P(ℕ)), although this is stated without proof in this section.

#### 1.5 Decimal Representation of the Reals

This section connects real numbers to their familiar decimal representations.
*   **Finite Decimal Representation**: Integers and some rational numbers can be represented with a finite number of decimal digits (e.g., 2, 0.5).
*   **Infinite Decimal Representation**: For all real numbers (especially irrationals like √2 and rationals like 1/3), an **infinite sequence of decimal digits** is required.
*   **Definition**: For *x ∈ (0, 1]*, its decimal representation *0.d₁d₂d₃...* defines *x* as the **supremum of its finite truncations**: *x* = supₙ∈ℕ (d₁/10 + d₂/10² + ... + dₙ/10ⁿ).
*   **Properties of Decimal Representations**:
    *   Every infinite sequence of digits *0.d₁d₂d₃...* represents a **unique real number *x ∈***.
    *   For every *x ∈ (0, 1]*, there exists at least one infinite sequence of digits representing *x*. There is a **unique representation** that satisfies *Dₙ < x ≤ Dₙ + 1/10ⁿ* for all *n* (where *Dₙ* is the *n*-digit truncation).
*   **Non-Unique Representations**: Some rational numbers have **two distinct decimal representations** (e.g., 0.5 = 0.4999...).
*   **Rational Numbers and Repeating Decimals**:
    *   A real number *x ∈ (0, 1]* is a **rational number if and only if its decimal digits eventually start repeating**. This means there exist positive integers *N* and *P* such that for all *n ≥ N*, *dₙ = dₙ+P*.
    *   This implies that **irrational numbers have non-repeating, non-terminating decimal representations**.
*   **Cantor Diagonalization Example (using decimals)**: The proof of uncountability can be illustrated using decimal representations. By constructing a number whose *n*-th decimal digit differs from the *n*-th decimal digit of the *n*-th number in a supposed countable list of all real numbers, one creates a number that cannot be in the list, thus proving the list cannot contain all real numbers.