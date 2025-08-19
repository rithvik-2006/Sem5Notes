Here are the revision notes on all the definitions and propositions found in Chapter 2 of the provided text:

### Chapter 2: Vector Spaces

#### 2.1 Introduction to Vector Spaces

*   **Definition 2.1.1 (Vector Space)**:
    A **vector space V** over a **field F** is a set `V` equipped with two operations:
    *   **Vector addition (+)**: A function `+ : V × V → V` (mapping `(v, w)` to `v + w`).
    *   **Scalar multiplication (·)**: A function `· : F × V → V` (mapping `(ϑ, v)` to `ϑ · v`).
    These operations must satisfy the following **eight axioms** for all `u, v, w ∈ V` and `ϑ, ϱ ∈ F`:
    1.  **Commutativity of vector addition**: `u + v = v + u`.
    2.  **Associativity of vector addition**: `(u + v) + w = u + (v + w)`.
    3.  **Existence of an additive identity (zero vector)**: There exists an element `0 ∈ V` such that `v + 0 = v` for all `v ∈ V`. This zero vector is unique.
    4.  **Existence of an additive inverse**: For each `v ∈ V`, there exists `−v ∈ V` such that `v + (−v) = 0`. This inverse vector is unique.
    5.  **Distributivity of scalar multiplication over vector addition**: `ϑ · (u + v) = ϑ · u + ϑ · v`.
    6.  **Distributivity of scalar multiplication with respect to addition in F**: `(ϑ + ϱ) · u = ϑ · u + ϱ · u`.
    7.  **Scalar compatibility (associativity of scalar multiplication)**: `ϑ · (ϱ · u) = (ϑ · ϱ) · u`.
    8.  **Multiplicative identity**: `1 · u = u` for all `u ∈ V`, where `1` is the multiplicative identity in `F`.
    Elements of `V` are called **vectors**, and elements of `F` are called **scalars**.

*   **Proposition 2.1.3**:
    For any `v ∈ V` (a vector) and `ϑ ∈ F` (a scalar), the following hold:
    *   **(i)** `0 · v = 0` (scalar zero times any vector results in the zero vector) and `ϑ · 0 = 0` (any scalar times the zero vector results in the zero vector).
    *   **(ii)** If `ϑ · v = 0`, then either `ϑ = 0` (the scalar) or `v = 0` (the zero vector).
    *   **(iii)** `(−1) · v = −v` (multiplying a vector by scalar minus one gives its additive inverse).

*   **Definition 2.1.5 (Subspace)**:
    A **non-empty subset W** of a vector space `V` over `F` is called a **subspace** if `W` itself is a vector space under the operations of addition and scalar multiplication defined on `V`.
    Specifically, `W` must satisfy these conditions:
    1.  **Closure under vector addition**: If `u, v ∈ W`, then `u + v ∈ W`.
    2.  **Closure under scalar multiplication**: If `u ∈ W` and `ϑ ∈ F`, then `ϑ · u ∈ W`.
    *   **Remark**: It follows that the zero vector `0` must be in `W`, and for any `u ∈ W`, its additive inverse `−u` must also be in `W`.

*   **Definition 2.1.8 (Column Space)**:
    Given a matrix `A ∈ M_{m×n}(F)`, the **column space Col(A)** of `A` is a subspace of `M_{m×1}(F)`.
    It is defined as the set of all possible matrix products `A · B` where `B ∈ M_{n×1}(F)`: `Col(A) = {A · B : B ∈ M_{n×1}(F)}`.
    **Equivalently**, `C` is in `Col(A)` if and only if the system of linear equations `AX = C` has a solution.

*   **Definition 2.1.9 (Row Space)**:
    Given a matrix `A ∈ M_{m×n}(F)`, the **row space row(A)** of `A` is a subspace of `M_{1×n}(R)` (or `M_{1×n}(C)` if `F` is complex).
    It is defined as the set of all possible matrix products `B · A` where `B ∈ M_{1×m}(F)`: `Row(A) = {B · A : B ∈ M_{1×m}(F)}`.

*   **Definition 2.1.10 (Null Space / Kernel)**:
    Given a matrix `A ∈ M_{m×n}(F)`, the **null space** or **kernel ker(A)** of `A` is a subspace of `M_{n×1}(F)`.
    It is defined as the set of all vectors `B ∈ M_{n×1}(F)` such that `AB = 0`: `ker(A) = {B ∈ M_{n×1}(F) : AB = 0}`.
    **Remark**: `ker(A)` is precisely the set of **solutions to the homogeneous system of linear equations AX = 0**.

#### 2.2 Basis and Dimension

*   **Definition 2.2.1 (Span)**:
    Let `V` be a vector space over `F`, and `S` be a subset of `V`.
    The **span of S**, denoted by `span(S)`, is the set of all possible **finite linear combinations** of vectors from `S`.
    `span(S) = { ∑_{i=1}^n ϑ_i v_i | n ∈ N, v_i ∈ S, ϑ_i ∈ F, i = 1, ..., n }`.
    *   **Convention**: `span(∅) = {0}` (the zero vector).
    *   **Property**: For any set `S ⊆ V`, `span(S)` is a **vector subspace of V** that contains `S`. Furthermore, `span(S)` is the **smallest subspace of V** containing `S`.

*   **Definition 2.2.10 (Minimal Spanning Set)**:
    A subset `S ⊆ V` is called a **minimal spanning set for V** if it satisfies two conditions:
    1.  `span(S) = V` (meaning `S` is a **spanning set** for `V`).
    2.  For any element `a ∈ S`, `span(S \ {a}) ≠ V` (meaning no vector can be removed from `S` without reducing its span).

*   **Proposition 2.2.12**:
    Let `V` be a vector space over `F`, and `S ⊆ V` be any subset. If `v ∈ V` such that `v ∈ span(S)`, then **`span(S ∪ {v}) = span(S)`**.
    This implies that adding a vector that is already a linear combination of existing vectors in a set does not change the span of that set.

*   **Definition 2.2.14 (Linear Independence)**:
    Let `V` be a vector space over `F`. A set `S ⊆ V` is said to be **linearly independent** if for any finite collection of distinct vectors `{v₁, v₂, ..., v_n} ⊆ S`, the equation `ϑ₁v₁ + ϑ₂v₂ + ... + ϑ_n v_n = 0` (where `ϑ_i ∈ F`) implies that **all scalars `ϑ_i` must be zero**: `ϑ₁ = ϑ₂ = ... = ϑ_n = 0`.
    Any set of vectors that is **not linearly independent** is called **linearly dependent**.
    *   **Equivalently**: A set `S` is linearly independent if and only if for any `v₁, ..., v_n ∈ S`, if `∑ ϑ_i v_i = ∑ ϱ_i v_i`, then `ϑ_i = ϱ_i` for all `i`.
    *   **Note**: If a set is linearly dependent, it means at least one vector in the set can be expressed as a linear combination of the others. A set containing the **zero vector** is always linearly dependent.

*   **Proposition 2.2.8**:
    Let `A` be an `m × n` matrix.
    *   **(i) Col(A) = M_{m×1}(F)** (the column space spans the entire `m`-dimensional column vector space) **if and only if A is right invertible**.
    *   **(ii) Row(A) = M_{1×m}(F)** (the row space spans the entire `m`-dimensional row vector space) **if and only if A is left invertible**.

*   **Corollary 2.2.8.1**:
    Let `A` be an `n × n` (square) matrix. Then, **`Row(A) = M_{1×n}(F)` and `Col(A) = M_{n×1}(F)` if and only if A is invertible**.

*   **Remark 2.2.9 (Equivalences for Invertible Matrices)**:
    For a square matrix `A ∈ M_n(F)`, the following statements are equivalent:
    *   `A` is **invertible**.
    *   `ker(A) = {0}` (the null space contains only the zero vector, meaning `AX = 0` has only the trivial solution).
    *   `Col(A) = M_{n×1}(F)` (the column space spans the entire `n`-dimensional column vector space).
    *   `det(A) ≠ 0` (A is **non-singular**).
    *   The **Reduced Row Echelon Form (RREF) of A is the identity matrix I**.
    *   The system of equations `AX = C` has a **unique solution** for any `C`.
    *   `A` is either **right or left invertible** (implies it is invertible).