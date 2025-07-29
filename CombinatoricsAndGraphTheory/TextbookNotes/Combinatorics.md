Here are detailed revision notes for Chapter 2, "Combinatorics," drawing on the information provided in the sources:

Chapter 2 focuses primarily on **enumerative combinatorics**, which deals with counting arrangements of objects subject to various constraints. It also touches upon **existential combinatorics** (in Sections 2.4 and 2.10) and **constructive combinatorics** (in Sections 2.9 and 2.10). The chapter exclusively studies arrangements of **finite sets**.

### 2.1 Some Essential Problems
This introductory section lays the groundwork for counting strategies:
*   **Sum Rule**: If you have `m` mutually disjoint finite sets, S1, S2, ..., Sm, with cardinalities `n1, n2, ..., nm` respectively, the number of ways to select one object from *any* of these sets is the **sum `n1 + n2 + ... + nm`**.
*   **Product Rule**: If you make selections in sequence from `m` finite sets, S1, S2, ..., Sm, with cardinalities `n1, n2, ..., nm` respectively, the total number of ways to make these selections is the **product `n1 * n2 * ... * nm`**, provided the selections are **independent**. For example, the number of `m`-letter acronyms from the full alphabet is `26^m` by this rule.

### 2.2 Binomial Coefficients
This section explores fundamental identities and properties of binomial coefficients:
*   **Definition**: Binomial coefficients, denoted `(n k)`, appear in the **binomial theorem** `(x + y)^n = Σk (n k) x^k y^(n-k)`.
*   **Pascal's Triangle**: A tabular arrangement where `n` indexes rows and `k` indexes columns. Entries are computed using the **addition identity**: `(n k) = (n-1 k) + (n-1 k-1)`.
*   **Key Identities**:
    *   **Sum across `n`-th row**: `Σk (n k) = 2^n`. This also represents the number of different subsets of an `n`-element set.
    *   **Alternating sum across `n`-th row**: `Σk (-1)^k (n k) = 0` for `n ≥ 1`, and `1` for `n = 0`.
    *   **Symmetry**: `(n k) = (n n-k)`.
    *   **Parallel summation identity**: `Σ(k=0 to n) (m+k k) = (m+n+1 n)`.
    *   **Hexagon identity**: A specific relationship between six binomial coefficients arranged in a hexagonal shape in Pascal's triangle.

### 2.3 Multinomial Coefficients
This section generalises binomial coefficients and their application to multisets:
*   **Definition**: Multinomial coefficients, `(n k1, ..., km)`, arise from the **multinomial theorem**: `(x1 + ... + xm)^n = Σ(k1+...+km=n) (n k1, ..., km) x1^k1 ... xm^km`.
*   **Counting Arrangements in Multisets**: Used to count the number of ways to order a collection of `n` objects when some objects are identical (a multiset). For example, the number of rearrangements of "ALMA, ALABAMA" (ignoring case) is calculated using this concept.

### 2.4 The Pigeonhole Principle
A simple yet powerful combinatorial idea:
*   **Pigeonhole Principle (Basic)**: If more than `n` objects are distributed among `n` containers, then at least one container must contain **more than one object**.
*   **Generalized Pigeonhole Principle**: If more than `mn` objects are distributed among `n` containers, then at least one container must contain **at least `m + 1` objects**.
*   **Applications**:
    *   **Monotonic Subsequences**: A sequence of more than `mn` real numbers must contain either an increasing subsequence of length at least `m + 1`, or a strictly decreasing subsequence of length at least `n + 1`.
    *   **Dirichlet's Approximation Theorem**: For an irrational real number `α` and a positive integer `Q`, there exists a rational number `p/q` with `1 ≤ q ≤ Q` such that `|α - p/q| < 1 / (Q + 1)`.

### 2.5 The Principle of Inclusion and Exclusion
This principle helps count elements with specific properties by systematically adding and subtracting counts:
*   **Formula**: `N0 = N - Σ N(ai) + Σ N(ai aj) - Σ N(ai aj ak) + ...`. `N0` is the number of objects with none of the properties, `N` is the total number of objects, and `N(ai...)` denotes the number of objects satisfying specified properties.
*   **Applications**:
    *   **Euler `ϕ` Function**: Calculates the number of positive integers `m ≤ n` that are relatively prime to `n`. The formula is `ϕ(n) = n * Π(p|n) (1 - 1/p)`, where `p` are prime factors of `n`.
    *   **Counting Prime Numbers**: Can be used to count primes up to `n` by excluding multiples of primes up to `√n`.
    *   **Chromatic Polynomials**: `cG(x)` measures the number of ways to properly colour the vertices of a graph `G` using at most `x` colours. The principle helps by defining `ai` as "edge `ei` connects two vertices with the same colour".

### 2.6 Generating Functions
A powerful method for solving combinatorial problems by encoding sequences as coefficients of polynomials:
*   **Basic Idea**: The expression `(x^0 + x^1)` can model picking an item (x^1) or not picking it (x^0). Multiplying such expressions for multiple items generates a polynomial where the coefficient of `x^k` is the number of ways to select `k` items.
*   **Double Decks**: For selecting `m` items from `n` different types, where each item can be selected at most twice, the generating function is `(1 + x + x^2)^n`.
*   **Counting with Repetition**: For selecting `m` objects from `n` different types with an inexhaustible supply of each (unlimited repetition), the generating function is `(1 - x)^(-n)`.
*   **Fibonacci Numbers**: The sequence `Fk` (where `F0=0, F1=1, Fk=Fk-1+Fk-2` for `k≥2`) can be analysed using its generating function `G(x) = x / (1 - x - x^2)`. A **closed form for `Fk`** can be determined from this rational function.
*   **Useful Generating Functions**: `1/(1-x) = Σ x^k`, `x/(1-x)^2 = Σ kx^k`, and `-ln(1-x) = Σ x^k/k`.

### 2.7 Pólya’s Theory of Counting
This theory provides a general method for counting combinations when symmetries are present:
*   **Permutation Groups**:
    *   **Permutation**: A bijection `π` on a set {1, ..., n}.
    *   **Symmetric Group (Sn)**: The set of all bijections on {1, ..., n} forms a group under composition.
    *   **Cycle Notation**: A way to represent permutations.
    *   **Transposition**: A permutation that swaps two elements.
    *   **Even/Odd Permutations**: A permutation can be represented as a product of transpositions; an even permutation uses an even number, an odd permutation uses an odd number.
    *   **Subgroups**: `Sn` contains important subgroups like the **Cyclic Group (Cn)** (rotations), **Dihedral Group (Dn)** (rotations and reflections), and the **Alternating Group (An)** (even permutations).
*   **Burnside’s Lemma**: Counts the number of **nonequivalent colorings** in the presence of symmetry. It states that the number of equivalence classes is the **average number of colorings fixed by each permutation in the group `G`**.
*   **Cycle Index**: A polynomial `PG(x1, ..., xn)` used to simplify calculations in Burnside's Lemma.
    *   **Pattern Inventory**: `FG(y1, ..., ym) = PG(Σy_i, Σy_i^2, ..., Σy_i^n)` is a polynomial where coefficients indicate the number of nonequivalent colorings with specific counts of each colour.
    *   **de Bruijn’s Enumeration Formula**: **Generalizes Pólya’s method** to account for symmetries in *both* the objects (`G`) and the colours (`H`).

### 2.8 More Numbers
This section introduces several important combinatorial sequences related to occupancy problems and permutations:
*   **Occupancy Problems**: Involve distributing objects into distinguishable or indistinguishable bins (groups/piles).
*   **Partitions (pn,k)**: The number of ways to write an integer `n` as a sum of `k` positive integers, where order does not matter.
    *   **Young Diagrams (Ferrers Diagrams)**: Visual representations of partitions as arrays of boxes or dots.
    *   **Conjugate Partition (`λ'`)**: Obtained by counting columns in the Young diagram of `λ`.
    *   **Pentagonal Number Theorem (Theorem 2.14)**: Relates the generating function for partitions to pentagonal numbers, stating `p(n) - p(n-1) - p(n-2) + p(n-5) + p(n-7) - ... = 0` (for `n ≥ 1`, `p(0)=1`).
*   **Stirling Cycle Numbers (`[n k]`)**: The number of ways to seat `n` knights at `k` identical round tables, with no table empty. They allow expressing **rising factorial powers** as linear combinations of ordinary powers.
*   **Stirling Set Numbers (`{n k}`)**: The number of ways to partition a set of `n` distinguishable objects into `k` non-empty, indistinguishable subsets. They are related to **falling factorial powers**.
*   **Bell Numbers (`bn`)**: The total number of ways to partition a set of `n` distinguishable objects into any number of non-empty, indistinguishable subsets. `bn = Σk {n k}`. They have a recurrence relation `bn = Σ(k=0 to n-1) (n-1 k) bk` and an **exponential generating function `E(x) = e^(e^x - 1)`**.
*   **Eulerian Numbers (`<n k>`)**: Count permutations of `{1, ..., n}` with exactly `k` ascents.

### 2.9 Stable Marriage
This section delves into a constructive combinatorial problem involving pairing preferences:
*   **Stable Matching**: An arrangement of `n` marriages between `n` men and `n` women such that no unmatched man and woman prefer each other to their assigned spouses.
*   **Gale–Shapley Algorithm**: A specific algorithm that **always guarantees a stable matching** by having one set (e.g., men) propose to the other (women) based on their preference lists.
*   **Variations**:
    *   **Incomplete Preference Lists**: Some partners may be unacceptable. The algorithm can be amended to handle this, often by introducing a **fictitious "ogre" or "ogress"**. A complete stable matching exists if and only if the augmented system has a stable matching where the ogre is paired with the ogress.
    *   **Weakly Ordered Preferences**: Allows individuals to be indifferent between certain partners. A stable matching for weakly ordered preferences can be found by refining them to strongly ordered lists and applying the Gale-Shapley algorithm.
    *   **Unequal Numbers of Participants**: If there are `k` men and `n` women (or vice-versa), a stable matching exists, and every member of the *smaller* set will be paired.
*   **Perfect Matchings**: A matching that saturates every vertex of a graph.
    *   **Corollary 1.57**: If a bipartite graph is `k`-regular, it contains a perfect matching.
    *   **Theorem 1.58**: A graph of order `2n` with minimum degree `δ(G) ≥ n` has a perfect matching.
    *   **Tutte’s Theorem**: Provides a general characterisation of graphs with perfect matchings based on the number of odd components created by removing a subset of vertices.
    *   **Petersen’s Theorem**: Mentions a special class of 3-regular graphs that have perfect matchings, noting that not all 3-regular graphs do.

### 2.10 Combinatorial Geometry
This area studies combinatorial problems related to arrangements of points in space and geometric figures:
*   **Sylvester's Problem**: Asks if a line that passes through **exactly two** of the points (an "ordinary line") must exist, given `n ≥ 3` non-collinear points in the plane.
    *   **Dijkstra's Algorithm**: Provides a constructive proof for Sylvester's problem by showing a method to find such a line.
    *   **Result**: An ordinary line must **always exist** for any finite set of non-collinear points.
*   **Convex Polygons (Erdős-Szekeres Problem)**: Investigates the minimal number of points in the plane (in general position) required to guarantee a subcollection of `n` points forming a **convex `n`-gon**.
    *   **Generalized Ramsey Numbers (`Rk(m, n)`)**: Defined as the smallest integer `N` such that any 2-coloring of the `k`-subsets of `[N]` contains either a red `m`-subset or a blue `n`-subset.
    *   **Ramsey's Theorem (Theorem 2.28)**: States that these generalized Ramsey numbers **always exist** and provides an upper bound formula. This theorem has broader implications than the classical Ramsey numbers introduced in Chapter 1.
    *   **Connection to Convex Polygons (Theorem 2.30)**: Shows that `ES(n) ≤ R4(5, n)`, implying that a sufficiently large collection of points in general position must contain a convex `n`-gon. The value `ES(n)` represents the minimum number of points required.
    *   **Known Bounds**: `ES(n) ≤ (2n-4 n-2) + 1` (Erdős and Szekeres) and `ES(n) ≤ (2n-5 n-2) + 1` for `n ≥ 5` (Tóth and Valtr).
    *   **Conjecture**: Erdős and Szekeres conjectured `ES(n) = 2^(n-2) + 1` for `n ≥ 3`. This remains an **open problem**.

This comprehensive overview should serve as a solid foundation for revising Chapter 2.