Chapter 2 of "Abstract Algebra" by I.N. Herstein, Third Edition, introduces the fundamental concept of **Groups**. This chapter lays the groundwork for understanding algebraic structures with a single operation and explores their core properties, special types, and important theorems.

Here's a detailed breakdown for revision:

### 1. Definitions and Examples of Groups

*   **Definition of a Group**: A non-empty set G is a **group** if it has a defined operation `*` satisfying four axioms:
    *   **(a) Closure**: For any elements `a`, `b` in G, `a * b` is also in G.
    *   **(b) Associativity**: For any `a`, `b`, `c` in G, `a * (b * c) = (a * b) * c`.
    *   **(c) Existence of a Unit (Identity) Element**: There exists a special element `e` in G such that `a * e = e * a = a` for all `a` in G. `e` is called the identity or unit element.
    *   **(d) Existence of Inverses**: For every `a` in G, there exists an element `b` in G (denoted `a⁻¹`) such that `a * b = b * a = e`. `b` is called the inverse of `a`.
*   **Motivation**: These axioms were patterned after the properties observed in the set of 1-1 mappings of a set S onto itself, **A(S)**, under composition.
*   **Notation**: The operation `*` is often called the "product" and written as `ab` instead of `a * b`.
*   **Examples of Groups**:
    *   The set of **integers (ℤ)** under **ordinary addition (+)** is a group. The identity is 0, and the inverse of `a` is `-a`.
    *   The set of **rational numbers (ℚ)** under **ordinary addition (+)** is a group.
    *   The set of **non-zero rational numbers (ℚ')** under **ordinary multiplication (×)** is a group.
    *   The set of **positive real numbers (ℝ⁺)** under **ordinary multiplication (×)** is a group.
    *   The set of **nth roots of unity (E_n)**, which are complex numbers `θ^j` where `θ = cos(2π/n) + i sin(2π/n)`, forms a group under multiplication.
    *   **A(S)**, the set of 1-1 mappings of S onto itself, is a group under composition. If S has `n` elements, it's called the **symmetric group of degree n (S_n)**.
    *   Groups of 2x2 matrices with real entries `(a b)`.
    *   **Dihedral groups (D_n)**, which represent symmetries of regular n-gons. `D_n` has order `2n`.
    *   The group of rotations of a circle about its center.
*   **Finite Group**: A group G is finite if it has a finite number of elements. The number of elements is called the **order of the group (denoted |G|)**. `E_n` is a finite group of order `n`.
*   **Abelian Group**: A group G is **abelian (or commutative)** if `a * b = b * a` for all `a, b` in G. Named after Niels Henrik Abel. Most numerical examples (like ℤ under +) are abelian. `S_n` for `n ≥ 3` is nonabelian.
*   **Non-Examples of Groups**:
    *   Integers under multiplication fail because 0 has no inverse, and other elements (like 3) don't have integer inverses.
    *   Non-zero real numbers under `a * b = a²b` fail associativity and identity existence.
    *   Positive integers under multiplication fail due to lack of inverses (e.g., 3 has no inverse in positive integers).
*   **Shorthand Notation**: For `a` in a group G, `aⁿ` denotes `a * a * ... * a` (n times). `a⁻ⁿ = (a⁻¹)ⁿ` for positive `n`, and `a⁰ = e`.

### 2. Some Simple Remarks

*   **Uniqueness of Identity Element**: A group has only one identity element.
*   **Uniqueness of Inverse Element**: Every element in a group has a unique inverse.
*   **Inverse of an Inverse**: For any `a` in G, `(a⁻¹)⁻¹ = a`.
*   **Inverse of a Product**: For `a, b` in G, `(ab)⁻¹ = b⁻¹a⁻¹`.
*   **Cancellation Laws**:
    *   If `ab = ac`, then `b = c` (left cancellation).
    *   If `ba = ca`, then `b = c` (right cancellation).
    *   Note: `ab = ca` does not generally imply `b = c` in nonabelian groups.

### 3. Subgroups

*   **Definition of a Subgroup**: A non-empty subset `H` of a group `G` is a **subgroup** of `G` if `H` itself forms a group under the same operation as `G`.
*   **Trivial Subgroups**: Every group `G` has `G` itself and `{e}` (the subgroup containing only the identity element) as trivial subgroups.
*   **Subgroup Test (Lemma 2.3.1)**: A non-empty subset `A` of `G` is a subgroup if and only if:
    *   `A` is closed under the operation of `G` (i.e., `ab ∈ A` for `a, b ∈ A`).
    *   For every `a ∈ A`, its inverse `a⁻¹` is also in `A`.
*   **Subgroup Test for Finite Subsets (Lemma 2.3.2)**: If `G` is a group and `H` is a non-empty *finite* subset of `G` closed under the product in `G`, then `H` is a subgroup of `G`.
*   **Examples of Subgroups**:
    *   The set of **even integers** is a subgroup of **ℤ** under addition. More generally, the set of all **multiples of `m` (H_m)** in **ℤ** forms a subgroup.
    *   For `A(S)`, the set `H(a) = {f ∈ A(S) | f(a) = a}` (permutations fixing `a`) is a subgroup.
    *   Subgroups of matrix groups.
    *   **Cyclic Subgroup**: For any `a ∈ G`, the set of all integer powers of `a`, denoted **(a) = {a^i | i ∈ ℤ}**, is a subgroup of `G`. This is the **cyclic subgroup generated by `a`**.
    *   **Centralizer**: For any `a ∈ G`, the set **C(a) = {g ∈ G | ga = ag}** (elements that commute with `a`) is a subgroup of `G`.
    *   **Center of a Group**: **Z(G) = {z ∈ G | zx = xz for all x ∈ G}** (elements that commute with *all* elements in G) is a subgroup of `G`. `Z(G)` is the intersection of all centralizers `C(x)`.
    *   **Conjugate Subgroup**: For a subgroup `H` and element `a ∈ G`, **a⁻¹Ha = {a⁻¹ha | h ∈ H}** is a subgroup of `G`.

### 4. Lagrange's Theorem

*   **Equivalence Relation**: A relation `~` on a set `S` is an equivalence relation if it satisfies:
    *   **(a) Reflexivity**: `a ~ a`
    *   **(b) Symmetry**: `a ~ b` implies `b ~ a`
    *   **(c) Transitivity**: `a ~ b` and `b ~ c` implies `a ~ c`
*   **Examples of Equivalence Relations**:
    *   **Congruence modulo n**: `a ≡ b mod n` if `n | (a - b)`. This is highly important in number theory.
    *   In a group `G` with subgroup `H`, `a ~ b` if `ab⁻¹ ∈ H`.
    *   **Conjugacy**: `a ~ b` if `b = x⁻¹ax` for some `x ∈ G`.
*   **Equivalence Class**: For an equivalence relation `~`, the class of `a`, `[a] = {b ∈ S | b ~ a}`.
    *   For `a ~ b` if `ab⁻¹ ∈ H`, `[b] = Hb = {hb | h ∈ H}`, called a **right coset of H in G**.
    *   For conjugacy, `[a] = {x⁻¹ax | x ∈ G}`, called the **conjugacy class of `a` (cl(a))**. If G is abelian, `cl(a) = {a}`.
*   **Partitioning Theorem (Theorem 2.4.1)**: An equivalence relation partitions a set `S` into disjoint equivalence classes (`S = ∪[a]`, and `[a] ≠ [b]` implies `[a] ∩ [b] = ∅`).
*   **Lagrange's Theorem (Theorem 2.4.2)**: If `G` is a finite group and `H` is a subgroup of `G`, then the **order of `H` divides the order of `G`**. The proof involves showing that all right cosets of `H` have the same number of elements as `H` itself, and `G` is a disjoint union of these cosets.
*   **Consequences of Lagrange's Theorem**:
    *   **Theorem 2.4.3**: A group `G` of prime order `p` is **cyclic**.
    *   **Order of an Element**: For `a ∈ G`, the **order of `a` (o(a))** is the least positive integer `m` such that `a^m = e`. The cyclic subgroup `(a)` has order `o(a)`.
    *   **Theorem 2.4.4**: If `G` is finite and `a ∈ G`, then `o(a)` divides `|G|`.
    *   **Theorem 2.4.5**: If `G` is a finite group of order `n`, then `aⁿ = e` for all `a ∈ G`.
*   **Integers Modulo n (ℤ_n)**:
    *   `ℤ_n = {,, ..., [n-1]}` forms a **cyclic group under addition** `[a] + [b] = [a+b]`. The identity is ``, inverse of `[a]` is `[-a]`. `ℤ_n` is generated by ``.
    *   Multiplication `[a][b] = [ab]` is also defined in `ℤ_n`, making it a commutative ring.
    *   **Euler's Phi-function (φ(n))**: Counts positive integers less than `n` and relatively prime to `n`.
    *   **Group of Invertible Elements Modulo n (U_n)**: `U_n = {[a] ∈ ℤ_n | (a, n) = 1}` forms a group under multiplication. Its order is `φ(n)`.
    *   **Theorem 2.4.8 (Euler's Theorem)**: If `a` is an integer relatively prime to `n`, then `a^φ(n) ≡ 1 mod n`.
    *   **Fermat's Little Theorem (Corollary to Euler's Theorem)**: If `p` is a prime, `a^(p-1) ≡ 1 mod p` for `p <binary data, 1 bytes><binary data, 1 bytes><binary data, 1 bytes> a`.
*   **Converse of Lagrange's Theorem**: The converse is generally *not* true; a group of order `n` need not have a subgroup for every divisor `m` of `n`.

### 5. Homomorphisms and Normal Subgroups

*   **Homomorphism (for Groups)**: A mapping `φ: G → G'` between two groups `G` and `G'` is a **homomorphism** if `φ(ab) = φ(a)φ(b)` for all `a, b ∈ G`. It *preserves the operation*.
*   **Properties of Homomorphisms (Lemma 2.5.2)**:
    *   `φ(e) = e'` (identity maps to identity).
    *   `φ(a⁻¹) = φ(a)⁻¹` (inverse maps to inverse).
*   **Image of a Homomorphism (φ(G))**: `φ(G) = {φ(a) | a ∈ G}` is a **subgroup** of `G'`.
*   **Kernel of a Homomorphism (Ker φ)**: `Ker φ = {a ∈ G | φ(a) = e'}` (elements mapping to the identity of `G'`). It measures how far a homomorphism is from being 1-1.
    *   **Theorem 2.5.5**: `Ker φ` is a **subgroup** of `G`, and for any `a ∈ G`, `a⁻¹(Ker φ)a ⊆ Ker φ`.
    *   **Corollary**: `φ` is a **monomorphism** (1-1) if and only if `Ker φ = {e}`.
*   **Normal Subgroup (Definition)**: A subgroup `N` of `G` is a **normal subgroup** of `G` if `a⁻¹Na ⊆ N` for every `a ∈ G` (denoted `N ◁ G`).
    *   `Ker φ` is always a normal subgroup.
    *   **Theorem 2.5.6**: `N ◁ G` if and only if every left coset of `N` in `G` is a right coset of `N` in `G` (i.e., `aN = Na` for all `a ∈ G`).
    *   Note: `a⁻¹Na = N` does *not* mean `a⁻¹na = n` for every `n ∈ N`, but that the *set* of such conjugates is `N`.
*   **Examples of Normal Subgroups**:
    *   In an **abelian group**, every subgroup is normal.
    *   The **center Z(G)** is always a normal subgroup of `G`.
    *   `A_n` (alternating group) is a normal subgroup of `S_n`.
    *   Some groups, like the **quaternion group** (a Hamiltonian group), have all subgroups normal but are nonabelian.
*   **Monomorphism**: A homomorphism that is 1-1 (injective).
*   **Isomorphism**: A homomorphism that is both 1-1 and onto (bijective). If `φ: G → G'` is an isomorphism, `G` and `G'` are **isomorphic (G ≅ G')**. Isomorphic groups have the "same structure".
*   **Automorphism**: An isomorphism from a group `G` to itself.
    *   **Inner Automorphism**: `σ_a(x) = a⁻¹xa` is an automorphism of `G` induced by `a`.
*   **Cayley's Theorem (Theorem 2.5.1)**: Every group `G` is isomorphic to some subgroup of `A(S)` for an appropriate set `S` (specifically, `S = G`). For finite groups, this means any finite group can be represented as a group of permutations.

### 6. Factor Groups

*   **Motivation**: If `N` is a normal subgroup, can we define a group operation on the set of cosets `G/N`? Yes, if and only if `N` is normal.
*   **Construction of G/N**:
    *   `G/N = {[a] | a ∈ G} = {Na | a ∈ G}` (the set of all right cosets of `N` in `G`).
    *   **Product Definition**: `[a][b] = [ab]` (or `(Na)(Nb) = Nab`). This product is **well-defined** if `N` is normal.
    *   **Theorem 2.6.1**: If `N ◁ G`, then `G/N` is a group under this product.
*   **Natural Homomorphism (Theorem 2.6.2)**: The map `ψ: G → G/N` defined by `ψ(a) = [a]` is a homomorphism of `G` onto `G/N` with **kernel `N`**. This connects normal subgroups directly to kernels of homomorphisms.
*   **Order of Factor Group (Theorem 2.6.3)**: If `G` is a finite group and `N ◁ G`, then `|G/N| = |G|/|N|` (also denoted as `i_G(N)`, the index of `N` in `G`).
*   **Cauchy's Theorem (for Abelian Groups - Theorem 2.6.4)**: If `G` is a finite abelian group and `p` is a prime that divides `|G|`, then `G` has an element of order `p`. (Proof uses induction and factor groups, showing how information can be "pulled back" from `G/N` to `G`).
*   **Interpretation**: Forming `G/N` means "identifying" elements of `G` that are "equal up to `N`". Examples include `ℤ/nℤ ≅ ℤ_n` and `ℝ/ℤ` being analogous to a circle.

### 7. The Homomorphism Theorems

These theorems formalize relationships between groups, their homomorphic images, and their subgroups/normal subgroups.

*   **First Homomorphism Theorem (Theorem 2.7.1)**: Let `φ: G → G'` be a homomorphism of `G` onto `G'` with kernel `K`. Then **`G' ≅ G/K`**. The isomorphism is `ψ: G/K → G'` defined by `ψ(Ka) = φ(a)`.
*   **Correspondence Theorem (Theorem 2.7.2)**: Let `φ: G → G'` be a homomorphism of `G` onto `G'` with kernel `K`. There is a **one-to-one correspondence** between subgroups of `G'` and subgroups of `G` that contain `K`. This correspondence preserves normality.
*   **Second Homomorphism Theorem (Theorem 2.7.3)**: Let `H` be a subgroup of `G` and `N` a normal subgroup of `G`. Then `HN = {hn | h ∈ H, n ∈ N}` is a subgroup of `G`, `N ◁ HN`, and **`(HN)/N ≅ H/(H ∩ N)`**.
*   **Third Homomorphism Theorem (Theorem 2.7.4)**: If `φ: G → G'` is a homomorphism of `G` onto `G'` with kernel `K`, and `N' ◁ G'`, let `N = {a ∈ G | φ(a) ∈ N'}`. Then **`G/N ≅ G'/N'`**. Equivalently, **`(G/K)/(N/K) ≅ G/N`**.

### 8. Cauchy's Theorem (General Case)

*   **Orbits of Permutations**: If `f ∈ A(S)`, the **orbit of `s` under `f`** is `O(s) = {f^i(s) | all integers i}`. `S` is a disjoint union of orbits.
*   **Lemma 2.8.1**: If `f ∈ A(S)` has prime order `p`, then the orbit of any element `s ∈ S` under `f` has either `1` or `p` elements.
*   **Cauchy's Theorem (Theorem 2.8.2, McKay's Proof)**: If `p` is a prime and `p` divides the order of `G` (any finite group), then **`G` contains an element of order `p`**.
    *   Proof uses the set `S` of `p`-tuples `(a₁, ..., a_p)` where `a₁...a_p = e` and shows `|S| = |G|^(p-1)`. A permutation `f` defined by cyclically shifting elements `f(a₁, ..., a_p) = (a_p, a₁, ..., a_p-1)` is applied. Orbits under `f` have size 1 or `p`. Elements in orbits of size 1 are those with `a₁=a₂=...=a_p`. Since `|S|` is divisible by `p`, and `|S| = (number of orbits of size 1) + (p * number of orbits of size p)`, the number of orbits of size 1 must be divisible by `p`. Since `(e, ..., e)` is one such element, there must be at least `p-1` other such elements `(x, ..., x)` where `x^p=e` and `x≠e`.
*   **Consequences of Cauchy's Theorem**:
    *   **Lemma 2.8.3**: If `G` has order `pq` (`p, q` primes, `p > q`), and `a ∈ G` has order `p`, then `(a)` is a **normal subgroup** of `G`.
    *   **Lemma 2.8.4**: If `a ∈ G` has order `m` and `b ∈ G` has order `n`, where `m` and `n` are relatively prime and `ab = ba`, then `c = ab` has order `mn`.
    *   **Theorem 2.8.5**: Let `G` be a group of order `pq`, where `p, q` are primes and `p > q`. If `q` does *not* divide `(p-1)`, then `G` must be **cyclic**. (Proven using the previous lemmas and Fermat's Theorem).

### 9. Direct Products

*   **External Direct Product**: Given groups `G₁, G₂, ..., G_n`, their **(external) direct product** `G₁ × G₂ × ... × G_n` is the set of all ordered `n`-tuples `(a₁, a₂, ..., a_n)` where `a_i ∈ G_i`, with component-wise multiplication `(a₁, b₁)(a₂, b₂) = (a₁a₂, b₁b₂)`.
    *   The identity element is `(e₁, e₂, ..., e_n)`.
    *   The subsets `G_j' = {(e₁, ..., e_(j-1), a_j, e_(j+1), ..., e_n)}` are subgroups isomorphic to `G_j` and are **normal** in the direct product `G`.
*   **Internal Direct Product**: A group `G` is the **(internal) direct product** of its normal subgroups `N₁, N₂, ..., N_n` if every `a ∈ G` has a **unique representation** in the form `a = a₁a₂...a_n` where each `a_i ∈ N_i`.
*   **Lemma 2.9.2**: If `M, N` are normal subgroups of `G` such that `M ∩ N = {e}`, then any `m ∈ M` commutes with any `n ∈ N` (i.e., `mn = nm`).
*   **Lemma 2.9.3**: If `G` is an internal direct product of normal subgroups `N₁, ..., N_n`, then `N_i ∩ N_j = {e}` for `i ≠ j`.
*   **Theorem 2.9.4**: The mapping `ψ((a₁, a₂, ..., a_n)) = a₁a₂...a_n` is an isomorphism from `G₁ × G₂ × ... × G_n` (external direct product) onto `G` if and only if `G` is the internal direct product of `N₁, N₂, ..., N_n` (where `N_i` are normal subgroups of `G` isomorphic to `G_i`).
*   **Corollary**: `G` is the internal direct product of `N₁` and `N₂` if and only if `G = N₁N₂` and `N₁ ∩ N₂ = {e}`.

### 10. Finite Abelian Groups (Optional)

*   **Fundamental Theorem on Finite Abelian Groups (Theorem 2.10.3)**: Any finite abelian group is the **direct product of cyclic groups**.
    *   The proof involves reducing the problem to p-groups (groups of order `p^n`) and then showing that a p-group is a direct product of cyclic groups using elements of maximal order.
    *   **Lemma 2.10.1**: If `G` is an abelian group of order `mn` where `m` and `n` are relatively prime, and `M = {x ∈ G | x^m = e}`, `N = {x ∈ G | x^n = e}`, then `G = M × N`.
    *   **Corollary**: Any finite abelian group `G` can be expressed as `G = P × T`, where `P` is a p-Sylow subgroup (elements whose order is a power of `p`) and `T` is a subgroup whose order is relatively prime to `p`.
    *   **Theorem 2.10.2**: Let `G` be an abelian group of order `p^n`, `p` a prime, and let `a ∈ G` have maximal order. Then `G = (a) × Q`, where `(a)` is the cyclic subgroup generated by `a`.
*   **Invariants of Abelian Groups**: The orders of the cyclic factors `p^(n_i)` in the decomposition `G = A₁ × A₂ × ... × A_k` (where `|A_i| = p^(n_i)` and `n₁ ≥ n₂ ≥ ... ≥ n_k`) are unique and are called the **invariants of `G`**.
*   **Classification**: Two abelian groups of order `p^n` are isomorphic if and only if they have the same invariants. The number of non-isomorphic abelian groups of order `p^n` equals the number of partitions of `n`. For general order `n = p₁^(a₁) ... p_k^(a_k)`, the number of non-isomorphic abelian groups is `f(a₁)f(a₂) ... f(a_k)`, where `f(m)` is the number of partitions of `m`.

### 11. Conjugacy and Sylow's Theorem (Optional)

*   **Conjugacy Class (cl(a))**: For `a ∈ G`, `cl(a) = {x⁻¹ax | x ∈ G}`. It's an equivalence class under the conjugacy relation.
*   **Centralizer (C(a))**: The set of elements that commute with `a`. `C(a)` is a subgroup of `G`.
*   **Number of Conjugates (Theorem 2.11.2)**: The number of distinct conjugates of `a` in `G` (i.e., `|cl(a)|`) is equal to the **index of `C(a)` in `G` (`[G:C(a)] = |G|/|C(a)|`)**.
*   **Class Equation (Theorem 2.11.3)**: If `G` is a finite group, then `|G| = Σ [G:C(a_i)] = Σ |G|/|C(a_i)|`, where the sum runs over one `a_i` from each distinct conjugacy class.
*   **Theorem 2.11.4**: If `G` is a group of order `pⁿ` (`p` is prime), then the **center of `G` (Z(G)) is not trivial** (`Z(G) ≠ {e}`). (Proof uses the class equation).
*   **Theorem 2.11.5**: If `G` is a group of order `p²` (`p` is prime), then `G` is **abelian**. (Proof uses Theorem 2.11.4).
*   **Theorem 2.11.6**: If `G` is a group of order `pⁿ` (`p` is prime), then `G` contains a **normal subgroup of order `p^(n-1)`**. (Proof uses induction and Theorem 2.11.4 with factor groups).
*   **Sylow's Theorem (Theorem 2.11.7 - First Part)**: Suppose `|G| = pⁿm`, where `p` is a prime and `p` does not divide `m`. Then `G` has a **subgroup of order `pⁿ`** (called a **p-Sylow subgroup**).
    *   Proof uses induction on `|G|` and the class equation, along with Cauchy's Theorem and the Correspondence Theorem.
*   **Other Parts of Sylow's Theorem (Mentioned)**:
    *   Any two p-Sylow subgroups of `G` are **conjugate**.
    *   The number of p-Sylow subgroups of `G` is of the form `1 + kp` for some integer `k ≥ 0`, and this number **divides `|G|`**.

This comprehensive overview covers the core concepts and theorems introduced in Chapter 2, providing a solid foundation for revision.