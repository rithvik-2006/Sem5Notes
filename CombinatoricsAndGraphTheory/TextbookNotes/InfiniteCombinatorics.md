Here are detailed revision notes for Chapter 3, "Infinite Combinatorics and Graphs," drawing on the provided sources:

### Chapter 3: Infinite Combinatorics and Graphs

This chapter explores the peculiar nature of infinite sets, contrasting them with finite sets using ideas from graph theory and combinatorics. It delves into the axioms required for manipulating infinite sets and how combinatorial properties can distinguish between different sizes of infinite sets or illuminate the limitations of axiom systems.

---

#### 3.1 Pigeons and Trees

*   **Finite vs. Infinite Sets**:
    *   A primary distinction is illustrated with the **finite pigeonhole principle**: if there are more pigeons than finite pigeonholes, some pigeonhole must contain more than one pigeon.
    *   A set is **finite** if its elements can be matched with a bounded initial segment of natural numbers (N); otherwise, it's **infinite**. For example, {A, B, C, D} is finite because it can be matched with {0, 1, 2, 3}.
*   **Infinite Pigeonhole Principle (Theorem 3.1)**:
    *   If an **infinite** set of pigeons (P) is distributed among a **finite** number of pigeonholes (H), then **at least one pigeonhole must contain an infinite number of pigeons**.
    *   The proof involves a simple contradiction: if all pigeonholes contained only a finite number of pigeons, their union (the total pigeon set) would also be finite, contradicting the initial assumption.
*   **Trees in an Infinite Context**:
    *   A **tree** is a connected acyclic graph.
    *   **Root**: A designated starting vertex.
    *   **Levels**: Collections of vertices at a fixed distance from the root.
    *   **Immediate Successors**: A neighbour in the next higher level of the tree.
    *   **Path**: A sequence of vertices leading up and away from the root.
*   **König's Lemma (Theorem 3.2)**:
    *   This fundamental theorem states that an **infinite tree in which every level is finite must contain an infinite path**.
    *   The proof involves iteratively selecting a vertex at each level that has infinitely many successors, ensuring an infinite path can be constructed.
    *   **Historical Note**: Credited to Dénes König (1927), though sometimes referred to as König's Infinity Theorem.
*   **Applications/Connections (Exercises)**:
    *   Used to prove that if every finite subgraph of an infinite graph can be 2-colored, then the entire graph is 2-colorable.
    *   Applied in the proof of the Heine–Borel Theorem on compactness of the real interval.

---

#### 3.2 Ramsey Revisited

*   **Finite Ramsey Theory Recap**:
    *   In Chapter 1, it was proven that any 2-coloring of the edges of a complete graph with 6 vertices (K6) must contain a monochromatic K3 (three mutual acquaintances or three mutual strangers). This is denoted **R(3,3) = 6**.
    *   Similarly, **R(4,4) = 18**, meaning K18 is the smallest complete graph guaranteed to contain a monochromatic K4.
*   **Infinite Ramsey's Theorem (Theorem 3.3)**:
    *   For a complete **infinite graph** (with vertices V = {vi | i ∈ N}), **any 2-coloring of its edges will contain an infinite complete monochromatic subgraph**.
    *   The proof uses repeated application of the Infinite Pigeonhole Principle to construct such a subgraph. This theorem is used to prove results about finite graphs, imitating Ramsey himself.
*   **Arrow Notation**:
    *   **κ → (λ)n_c**: Means that every complete graph on κ vertices, where n-tuples (subsets of size n) are c-colored, contains a monochromatic complete subgraph with λ vertices.
    *   R(3,3) = 6 is written as **6 → (3)2_2** (kappa arrows lambda two c), signifying a graph of size 6, a monochromatic subgraph of size 3, 2-tuples (edges), and 2 colors.
    *   Theorem 3.3 is concisely written as **ω → (ω)2_2**, where ω denotes the size of N.
    *   The notation is especially useful for many colors or larger tuples.
*   **Generalised Ramsey's Theorem**:
    *   **Infinite Ramsey's Theorem (Theorem 3.5)**: For all natural numbers n and c, **ω → (ω)n_c** (any c-coloring of n-tuples of an infinite set produces an infinite monochromatic subset).
    *   **Finite Ramsey's Theorem (Theorem 3.6)**: For all natural numbers k, n, c, there exists a natural number m such that **m → (k)n_c** (a sufficiently large finite set guarantees a finite monochromatic subset for n-tuples and c colors). This is derivable from the infinite version.
*   **Key Insight**: Infinite constructions and principles are powerful tools for proving both infinite and finite combinatorial results.

---

#### 3.3 ZFC (Zermelo-Fraenkel Set Theory with the Axiom of Choice)

*   **Foundation of Mathematics**: ZFC is the de facto axiomatic foundation for standard mathematical practice, capable of formalising nearly all theorems. It's crucial for discussing complex results about infinite sets.
*   **Language and Logical Axioms**:
    *   **Variables**: Represent sets (e.g., A, B, x, y3).
    *   **Symbols**: ∅ (empty set), P (power set), ∪ (union).
    *   **Atomic Formulas**: `x ∈ y` (x is an element of y) and `x = y` (x equals y). All objects in ZFC are sets.
    *   **Logical Connectives**: ¬ (not), ∧ (and), ∨ (or), → (if...then), ↔ (if and only if).
    *   **Quantifiers**: ∀x (for all sets x), ∃x (there is a set x).
    *   **Theorem 3.7**: Equal sets have the same elements (`x = y → ∀t(t ∈ x ↔ t ∈ y)`).
*   **Proper Axioms of ZF (Zermelo-Fraenkel without Choice)**:
    1.  **Extensionality**: Sets are equal if and only if they have the same elements.
    2.  **Empty Set**: The empty set (∅) exists.
    3.  **Pairing**: For any two sets x and y, the set {x, y} exists.
    4.  **Union**: For any set X, the union of all elements of X (∪X) exists.
    5.  **Power Set**: For any set X, the set of all subsets of X (P(X)) exists.
    6.  **Separation**: For any set X and any definable property ψ, the subset of X containing only elements satisfying ψ exists. This axiom implies there is **no universal set** (Theorem 3.12).
    7.  **Replacement**: The range of a function restricted to a set exists. This axiom implies **x ∉ x** (Theorem 3.13).
    8.  **Infinity**: A set exists that contains the empty set and is closed under the successor operation (x ↦ x ∪ {x}).
    9.  **Regularity (Foundation)**: Every non-empty set X contains an element y such that X and y are disjoint.
*   **Axiom of Choice (AC)**:
    *   **Version 1 (AC)**: If T is a set of nonempty sets, there is a set Y ⊂ ∪T that contains exactly one element from each set in T.
    *   **Version 2 (AC2)**: If T is a set of nonempty sets, there is a function f (a choice function) such that for every t ∈ T, f(t) ∈ t.
    *   **Theorem 3.14**: ZF proves that **AC holds if and only if AC2 holds**.
    *   **Independence**: AC can **neither be proved nor disproved in ZF** (Gödel, Cohen).

---

#### 3.4 The Return of der König

*   **Axiom of Choice and SDRs**:
    *   AC is a statement about **infinite systems of distinct representatives (SDR)**.
    *   **Theorem 3.15**: ZF proves that **AC is equivalent to the existence of an SDR for any family of disjoint nonempty sets**.
*   **Restricted Versions of AC**:
    *   **Axiom of Choice for Finite Sets (ACF)**: AC applied to a family of finite, nonempty, mutually disjoint sets.
    *   **Countable Axiom of Choice (CAC)**: AC applied to a countable family of nonempty, mutually disjoint sets.
    *   **Countable Axiom of Choice for Finite Sets (CACF)**: CAC with the added hypothesis that each set in the family is finite.
    *   Theorem 3.16 shows the existence of an SDR for countable families of finite sets.
*   **Equivalence of Core Principles (Theorem 3.17)**:
    *   ZF proves that the following are equivalent:
        1.  **König's Lemma** (infinite path in an infinite tree with finite levels).
        2.  **Theorem 3.16** (SDR for countable families of finite sets).
        3.  **CACF**.
    *   This highlights the foundational importance of these seemingly distinct concepts.
*   **Dedekind Finite Sets**:
    *   A set X is **Dedekind finite** if no proper subset of X can be matched with X.
    *   In ZFC, finite sets are precisely Dedekind finite sets.

---

#### 3.5 Ordinals, Cardinals, and Many Pigeons

*   **Cardinality**: A way to measure the "size" of sets.
    *   **X ≺ Y**: There's a one-to-one function from X into Y, but no one-to-one function from X onto Y (X is strictly smaller than Y).
    *   **X ∼ Y**: There's a one-to-one function from X onto Y (X and Y have the same cardinality, they can be matched).
    *   **Cantor's Theorem**: **N ≺ P(N) ≺ P(P(N))**... (the power set of a set is always strictly larger than the set itself).
    *   **Cantor–Bernstein Theorem (Theorem 3.20)**: If there exists a one-to-one function from A into B (A  B) and a one-to-one function from B into A (B  A), then **there exists a one-to-one function from A onto B (A ∼ B)**. This is a very useful shortcut for proving sets have the same size.
    *   **Countable Sets**: **N × N ∼ N** (Corollary 3.22), implying the set of rational numbers (Q) and the set of all finite sequences of natural numbers (Seq) are also countable (∼ N).
    *   **Uncountable Sets**: **R (real numbers) is uncountable** (|R| ≻ N) because P(N) ∼ R (Corollary 3.23).
*   **Ordinals**: A way to order sets.
    *   **Linear Ordering**: A relation ≤ satisfying reflexivity, antisymmetry, transitivity, and trichotomy.
    *   **Well-ordered Set**: A linearly ordered set where every non-empty subset has a least element.
    *   **Theorem 3.24**: A linearly ordered set is well-ordered **if and only if it contains no infinite descending sequences**.
    *   **Transitive Set**: A set X is transitive if every element of an element of X is also an element of X (if y ∈ X and x ∈ y, then x ∈ X).
    *   **Ordinal Definition**: A **transitive set that is well-ordered by the ∈ (element-of) relation**. Finite ordinals correspond to natural numbers (0 = ∅, 1 = {∅}, 2 = {∅, {∅}}, etc.).
    *   **Theorem 3.25**: Properties of ordinals: union of ordinals is an ordinal, α ∪ {α} is an ordinal, any two ordinals are comparable by ∈ (α ∈ β or α = β or β ∈ α).
    *   **Theorem 3.26**: Every well-ordered set is **order isomorphic to a unique ordinal**. Ordinals act as canonical well-orderings.
    *   **Well-Ordering Principle (Theorem 3.27)**: **Every set can be well-ordered** (this relies on the Axiom of Choice).
    *   **Corollary 3.28**: For every set X, there is a **unique least ordinal α such that X ∼ α** (α is the cardinality of X).
*   **Cardinals**: Special ordinals used for size.
    *   **Aleph Numbers (ℵ)**: The infinite cardinal numbers (e.g., ℵ0 for the cardinality of N).
    *   **Theorem 3.29**: **|X| = |Y| if and only if X ∼ Y**.
*   **Ultimate Pigeonhole Principle**:
    *   **Theorem 3.30**: For every **infinite cardinal κ, |κ × κ| = κ**. This is a crucial result for infinite cardinal arithmetic and is proved by defining a well-ordering on κ × κ.
    *   **Corollary 3.31 (Ultimate Pigeonhole Principle)**: **κ is a regular cardinal if and only if putting κ pigeons into λ < κ pigeonholes implies some pigeonhole must contain κ pigeons**.
        *   **Regular Cardinal**: A cardinal κ where the cofinality of κ is κ itself (roughly, it cannot be expressed as a union of fewer than κ smaller sets).
        *   **Singular Cardinal**: A cardinal that is not regular (e.g., ℵω, which is the limit of ℵ0, ℵ1, ℵ2, ... but its cofinality is ω, not ℵω).
    *   **Corollary 3.32**: For each ordinal α, the cardinal **ℵα+1 is regular**. So, ℵ0, ℵ1, ℵ2, ... are all regular.
    *   **Corollary 3.33**: If κ is an infinite cardinal and |Xα| ≤ κ for each α < κ, then **|∪α<κ Xα| ≤ κ**. In particular, a countable or finite union of at most countable sets is at most countable.

---

#### 3.6 Incompleteness and Cardinals

*   **Gödel's Incompleteness Theorems**:
    *   **First Incompleteness Theorem**: If PA (formal Peano Arithmetic) is ω-consistent, then there is a formula G such that PA can neither prove G nor ¬G.
    *   **Second Incompleteness Theorem**: If PA is consistent, it cannot prove its own consistency (ConPA).
    *   **Applicability**: These theorems apply to any formal theory with sufficient arithmetic capability to encode statements and check proofs, including **ZFC**. Thus, **ZFC cannot prove its own consistency** (ConZFC), nor can it prove or disprove certain other statements.
*   **Weakly Inaccessible Cardinals**:
    *   Definition: An **uncountable regular limit cardinal**.
    *   **L (Constructible Universe)**: A special inner model of ZFC, defined by levels Lα for ordinals α.
    *   **Theorem 3.34**: If κ is weakly inaccessible, then **Lκ is a model of ZFC** (all ZFC axioms hold when quantifiers are restricted to Lκ).
    *   **Theorem 3.35**: Assuming ZFC is consistent, **ZFC cannot prove the existence of a weakly inaccessible cardinal**. This is a direct consequence of Gödel's Second Incompleteness Theorem applied to Lκ.
*   **Large Cardinals**: Cardinals whose existence cannot be proven in ZFC.
    *   **Hierarchy of Large Cardinals** (from "smaller" to "larger"):
        *   **Weakly Inaccessible (W)**: Uncountable regular limit cardinal.
        *   **Strong Limit**: For every λ < κ, |P(λ)| < κ.
        *   **Strongly Inaccessible (I)**: Uncountable regular strong limit cardinal. (GCH implies weakly inaccessible = strongly inaccessible).
        *   **Weakly Compact (C)**: Uncountable and κ → (κ)2_2 (if you 2-color edges of Kκ, there's a monochromatic Kκ).
        *   **n-Subtle (Sn)**: Defined by properties involving sequences of n-tuples and closed and unbounded (club) sets.
        *   **Ramsey (R)**: κ → (κ)<ω (monochromatic for all finite n-tuples simultaneously).
        *   **Measurable (M)**: Involves the existence of a special measure on the power set of the cardinal.
    *   **Known Hierarchy**: **W ≤ I < C < S1 < S2 < · · · < Sn < · · · < R < M**.

---

#### 3.7 Weakly Compact Cardinals

*   **Definition**: An uncountable cardinal κ is **weakly compact if κ → (κ)2_2**.
*   **Theorem 3.36**: **|R| → (ℵ1)2_2** and consequently, **ℵ1 → (ℵ1)2_2**. This means the real numbers (R) and ℵ1 are **not weakly compact**, demonstrating that not all uncountable cardinals possess this property. The proof involves constructing a specific 2-coloring of edges based on the ordering of elements.
*   **Theorem 3.37**: Extends the non-weak compactness to all successor cardinals: **|P(ℵα)| → (ℵα+1)2_2**.
*   **Theorem 3.38**: If κ is weakly compact, then **κ is strongly inaccessible**. This shows that weakly compact cardinals are "large".
*   **Tree Property**:
    *   A cardinal κ has the **tree property** if whenever T is a tree with κ many nodes and every level of T has size less than κ, then T must have a path of size κ.
    *   **König's Lemma (Theorem 3.2)** states that **ℵ0 has the tree property**.
    *   **Theorem 3.39**: **κ is weakly compact if and only if κ is strongly inaccessible and has the tree property**.
    *   **Counterexample for ℵ1**: ZFC proves that **ℵ1 does not have the tree property**; there exists an **ℵ1-Aronszajn tree** (a tree with ℵ1 nodes, levels of size < ℵ1, but no path of size ℵ1).

---

#### 3.8 Infinite Marriage Problems

*   **Generalising Hall's Theorem**: This section extends the stable marriage problem and matching concepts to infinite sets.
*   **Espousable Society**: A society (M, W) (men, women) where every man can be married to a unique woman, satisfying specific conditions for subsets of men and their preferred women.
*   **Marshall Hall Jr.'s Theorem (Theorem 3.41)**:
    *   If (M, W) is a society with a **countable set of men** (|M| ≤ ℵ0) and **each man's preference list is finite** (|W(m)| < ℵ0), then the society is **espousable if and only if for every subset S of men, |S| ≤ |W(S)|** (where W(S) is the union of women preferred by men in S).
    *   This theorem is equivalent to **König's Lemma** and **CACF** (Countable Axiom of Choice for Finite Sets) in ZF.
*   **Beyond Finite Preference Lists (Countable Men)**:
    *   **Theorem 3.42 (Damerell and Milner)**: For a society with a **countable set of men** (but potentially infinite preference lists), it's espousable if and only if a complex "margin function" (μω1) is non-negative for all subsets of women. The proof involves transfinite induction.
    *   **Theorem 3.43**: Unifies several equivalent conditions for espousability of societies with countable men, including c-admissibility, q-admissibility, and μ-admissibility.
*   **Uncountably Many Men**:
    *   **Theorem 3.44 (Aharoni, Nash-Williams, Shelah)**: For a society (M, W) (with potentially uncountable M and infinite preference lists), it is **espousable if and only if there is no κ-obstruction for every cardinal κ that is either finite or regular**.
        *   A **κ-obstruction** is a specific subgraph structure.
        *   This provides a "forbidden subgraph" characterisation for infinite marriage problems.
        *   It involves concepts like **club (closed and unbounded) sets** and **stationary sets** in cardinals.
*   **Espousable Cardinals**:
    *   Definition: A cardinal κ is **espousable** if every society (M, W) with |M| = κ, where |W(m)| < κ for all m, and |S| ≤ |W(S)| for all S ⊂ M with |S| < κ, is espousable.
    *   **ℵ0 is espousable**, but **ℵ1 is not**.
    *   **Theorem 3.45**: If κ is an uncountable espousable cardinal, then **κ is a limit cardinal** (e.g., ℵ2 is not espousable).
    *   **Theorem 3.46**: If κ is an uncountable espousable cardinal, then **κ is regular** (e.g., ℵω is not espousable).
    *   **Conclusion**: Uncountable espousable cardinals must be **uncountable regular limit cardinals, i.e., weakly inaccessible cardinals**.
    *   **Theorem 3.47**: **Every weakly compact cardinal is espousable**. This places espousable cardinals high in the large cardinal hierarchy.
*   **Perfect Matchings (Symmetrically Espousable)**:
    *   A society is **symmetrically espousable** if it has an espousal that maps men *onto* women, implying a **perfect matching** between the two sets. This requires both sets to have the same cardinality.

---

#### 3.9 Finite Combinatorics with Infinite Consequences

*   This section demonstrates how seemingly abstract infinite mathematical tools can be used to prove subtle facts about finite combinatorial objects.
*   **Example**: Proving the uncomputability of a certain graph-theoretic property (existence of a Hamiltonian path in a computable graph) by encoding the halting problem (a non-computable set) within it and using Ramsey's Theorem.

---

#### 3.10 k-critical Linear Orderings

*   **Linear Orderings**: A set with an antisymmetric, transitive, and trichotomous relation. "No endpoints" means no maximum or minimum element.
*   **Regressive Function**: For an increasing k-tuple x1 < ... < xk, f(x1, ..., xk) < x1.
*   **k-critical Linear Ordering**: A linear ordering where for every regressive function f: [X]k → X, there exists a sequence b1 < ... < bk+1 such that f(b1, ..., bk) = f(b2, ..., bk+1).
*   **Connection to Large Cardinals (Friedman's Theorems)**:
    *   **Theorem 3.49**: **ZFC proves that κ is the least cardinality of a (k+1)-critical linear ordering if and only if κ is the least k-subtle cardinal**.
    *   **Theorem 3.50**: **ZFC proves that there is a k-critical linear ordering for every non-zero k ∈ ω if and only if there is a k-subtle cardinal for every non-zero k ∈ ω**.
*   These theorems provide an elegant, more "combinatorial" characterization of k-subtle cardinals without directly referring to (n, κ)-sequences or club sets.

---

#### 3.11 Points of Departure

*   **Computability**: Explores graph theory problems where the existence of a solution is tied to computability, like the set of indices of computable graphs with Hamiltonian paths being Σ1_1-complete (Theorem 3.54).
*   **Reverse Mathematics**: A program to determine the minimal axiomatic strength required to prove mathematical theorems.
    *   Example: RCA0 (a weak base system) can prove that "every 2-regular graph with no odd cycles is bipartite" is equivalent to "Weak König's Lemma" (every infinite tree with binary labels has an infinite path) (Theorem 3.53).
*   **Analytical Hierarchy**: Classifies subsets of natural numbers based on the complexity of the formulas defining them using set quantifiers. Σ1_1-complete sets embody all information of other Σ1_1-definable sets.
*   **Further Study**: Mentions other Ramsey-style theorems (Van der Waerden, Hindman, Milliken, Galvin–Prikry, Erdős–Rado) and named trees (Aronszajn, Suslin, Kurepa) for advanced exploration.