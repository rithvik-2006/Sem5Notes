Here are the definitions and theorems from the provided notes:

### Matrices and Systems of Linear Equations

*   **Definition 1.1.1 (Euclidean Real Space)**: Let R denote the set of real numbers. For any natural number n > 0, Rn = {(x1, x2, · · · , xn) : xi → R, i = 1, 2, · · ·n}. The elements are called n-tuples of real numbers. The space Rn is referred to as the Euclidean real space or real Euclidean space of dimension n.
*   **Definition 1.1.2 (Euclidean Complex Space)**: Let R denote the set of real numbers. For any natural number n > 0, Cn = {(x1, x2, · · · , xn) : xi → C, i = 1, 2, · · ·n}. The elements are called n-tuples of complex numbers.
*   **Definition 1.2.1 (Matrix)**: A **matrix** is a rectangular array of numbers, symbols, or expressions, arranged in rows and columns. It is denoted by a capital letter (e.g., A), and its elements by lowercase letters with two subscripts (e.g., aij), where the first subscript `i` denotes the row number and the second `j` denotes the column number. Each `aij` is the `i,j`-th entry of A.
*   **Definition 1.2.2 (Identity Matrix)**: The `n`×`n` matrix `I` with ones on the main diagonal and zeros elsewhere is called an **identity matrix**.
*   **Definition 1.2.4 (Transpose)**: For a matrix A → Mm→n(F), the **transpose of A**, denoted A↑ → Mn→m(F), is a matrix such that `[A↑]ij = [A]ji`.
*   **Definition 1.2.6 (Left Invertible matrix)**: A **matrix A → Mm→n(F) is left-invertible** if there exists a matrix L → Mn→m such that `LA = I`, where `I → Mn→n` is the identity matrix.
*   **Definition 1.2.7 (Right Invertible matrix)**: A **matrix A → Mm→n(F) is right-invertible** if there exists a matrix R → Mn→m such that `AR = I`, where `I → Mm→m` is the identity matrix.
*   **Definition 1.2.9 (Invertible Matrix)**: A **matrix A → Mn(F) is invertible** if there exists a matrix S → Mn(F) such that `AS = SA = I`, where `I → Mn(F)` is the identity matrix. `S` is denoted as `A↓1`.
*   **Proposition 1.2.11**: If a matrix A → Mm→n(F) is both left-invertible and right-invertible, then its left and right inverses are the same. Moreover, A is invertible, which implies `m = n`.
*   **Definition 1.2.14 (Determinant - Laplace Expansion)**: The **determinant of a square matrix** `A` is defined as `det(A) = ∑ni=1 (↗1)i+jaijMij(A)`, where `1 ↑ j ↑ n` is fixed arbitrarily, and `Mij(A)` (the `i,j`-th minor of A) is the determinant of the `(n↗1)`×`(n↗1)` submatrix obtained by removing the `i`-th row and `j`-th column.
*   **Definition 1.2.15 (Determinant - Leibniz Expansion)**: For a matrix `A → Mn→n`, **det(A)** = `∑ω↔Sn sgn(ϖ) ∏ni=1 ai,ω(i)`, where `Sn` is the set of all permutations of `{1, 2, . . . , n}` and `sgn(ϖ)` is the sign (parity) of the permutation `ϖ`.
*   **Theorem 1.2.16 (Properties of Determinant)**: Let A,B → Mn(F) and `R1, . . . Rn` be the rows of A. The **determinant satisfies the following properties**:
    *   (i) `det(I) = 1` for the identity matrix `I → Mn(F)`.
    *   (ii) `det(AB) = det(A) det(B)`.
    *   (iii) Swapping two rows changes the sign of the determinant: `det([R1 | · · · | Ri | · · · | Rj | · · · | Rn] ↑) = ↗1 det([R1 | · · · | Rj | · · · | Ri | · · · | Rn] ↑)`.
    *   (iv) Adding a scalar multiple of one row to another does not change the determinant: `det([R1 | · · · | Ri + ϑK | · · · | Rn] ↑) = det([R1 | · · · | Ri | · · · | Rn] ↑) + ϑ det([R1 | · · · | K | · · · | Rn] ↑)`.
*   **Definition 1.2.20 (Singular and Non-singular Matrix)**: A **matrix A → Mn(F) is singular if det(A) = 0**, and **non-singular if det(A) ↘= 0**.
*   **Definition 1.2.23 (Trace)**: For a matrix `A → Mn(F)`, the **trace of A**, denoted `trA`, is defined as the sum of its diagonal elements: `trA = ∑ni=1 (aii)`.
*   **Definition 1.3.1 (Homogeneous System of Equation)**: A **system of linear equations `AX = C` is homogeneous if all entries `ci` on the right-hand side are zero** (`C = 0`). Otherwise, it is an inhomogeneous equation.
*   **Theorem 1.3.3 (Cramer’s Rule)**: If A → Mn(F) is an invertible matrix, then the system of equations `AX = C` has a **unique solution**. The `k`-th entry of the solution vector `b` is given by `bk = (1/det(A)) det(Ak(C))`, where `Ak(C)` is the matrix formed by replacing the `k`-th column of `A` with the column vector `C`.
*   **Corollary 1.3.3.1 (Inverse Matrix Entry Formula)**: For an invertible matrix A → Mn(F), the `i,j`-th entry of the inverse matrix `A↓1` is given by `[A↓1]ij = (1/detA) det(Ak(Ej))`, where `Ej` is the `j`-th column of the identity matrix.
*   **Definition 1.3.5 (Elementary Row Operations)**: The **elementary row operations** on a matrix `A` are:
    1.  **Replacing the `i`-th row of `A` with the `j`-th row of `A`** (denoted `Ri ⇔ Rj`).
    2.  **Multiplying the `j`-th row of `A` by a non-zero scalar `ϑ`** (denoted `ϑRj`).
    3.  **Replacing the `j`-th row of `A` with `ϑ` times the `i`-th row plus the `j`-th row of `A`** (denoted `Rj ⇑ Rj + ϑRi`).
*   **Definition 1.3.6 (Elementary Matrix)**: An **elementary matrix is a matrix formed by performing a single elementary row operation on an identity matrix**.
*   **Proposition 1.3.8**: Any elementary row operation on an `m`×`n` matrix is equivalent to **pre-multiplying the matrix by the corresponding `m`×`m` elementary matrix**.
*   **Corollary 1.3.8.1**: Every **elementary matrix is invertible**.
*   **Proposition 1.3.11**: For a system of equations `AX = C`, if `B|D` is an augmented matrix obtained from `A|C` by elementary row operations, then the **solution sets are identical**: `{X : AX = C} = {X : BX = D}`.
*   **Definition 1.3.12 (Row Echelon Form (REF))**: A **matrix is in row echelon form (REF) if it satisfies**:
    *   (i) All non-zero rows are above any rows of all zeros.
    *   (ii) The leading entry (pivot) of each non-zero row is strictly to the right of the leading entry of the previous row.
    *   (iii) The leading entry in any non-zero row is 1 (sometimes optional).
*   **Theorem 1.3.13**: For any matrix A → Mm→n(F), there exist finitely many elementary matrices `E1, . . . , Ep` such that `E1 ↔ · · ·↔ Ep ↔ A` is in **REF**.
*   **Definition 1.3.14 (Reduced Row Echelon Form (RREF))**: A **matrix is in reduced row echelon form (RREF) if it satisfies**:
    1.  The matrix is in row echelon form.
    2.  Each leading (or pivot) 1 is the only non-zero entry in its column.
*   **Theorem 1.3.17**: For A → Mn(F), **A is non-singular (det(A) ↘= 0) if and only if A is invertible**.
*   **Corollary 1.3.17.1**: If A → Mn→n is either right or left invertible, then **A must be invertible**.
*   **Corollary 1.3.17.2**: For A → Mn→n(F), **A is invertible if and only if its RREF is the identity matrix I**. Consequently, `AX = 0` has a unique solution if and only if the RREF of A is I.
*   **Theorem 1.3.24**: If A → Mm→n(F) such that `m < n`, then the **homogeneous system `AX = 0` has at least one non-zero solution**. If the cardinality of the field `F` is infinite, it has infinitely many solutions.
*   **Corollary 1.3.24.1**: If A → Mm→n(R) or (C) with `m < n` has at least one solution to `AX = C`, then it has **infinitely many solutions**.
*   **Proposition 1.3.25**: If A → Mm→n(F) is both left-invertible and right-invertible, then its left and right inverses are identical, and **A is invertible (i.e., `m = n`)**.

### Vector Spaces

*   **Definition 2.1.1 (Vector Space)**: A **vector space V over a field F** is a set with two operations: **vector addition** (`+ : V ↔ V ⇓ V`) and **scalar multiplication** (`· : F↔ V ⇓ V`), satisfying eight axioms:
    *   (i) Commutativity of addition: `u+ v = v + u`.
    *   (ii) Associativity of addition: `(u+ v) + w = u+ (v + w)`.
    *   (iii) Existence of a zero vector: There exists `0 → V` such that `v + 0 = v`.
    *   (iv) Existence of additive inverses: For each `v → V`, there exists `↗v → V` such that `v + (↗v) = 0`.
    *   (v) Distributivity of scalar multiplication over vector addition: `ϑ · (u+ v) = ϑ · u+ ϑ · v`.
    *   (vi) Distributivity of scalar multiplication over field addition: `(ϑ+ϱ)·u = ϑ·u+ϱ ·u`.
    *   (vii) Scalar compatibility: `ϑ · (ϱ · u) = (ϑ · ϱ) · u`.
    *   (viii) Identity element for scalar multiplication: `1 · u = u`.
*   **Proposition 2.1.3**: For all `v → V` and `ϑ → F` in a vector space `V`:
    *   (i) `0 · v = ϑ · 0 = 0`.
    *   (ii) `ϑ · v = 0` if and only if `ϑ = 0` or `v = 0`.
    *   (iii) `(↗1) · v = ↗v`.
*   **Definition 2.1.5 (Subspace)**: A **non-empty subset W of a vector space V over F is a subspace** if `W` itself is a vector space under the operations of `V`. Specifically, `W` must be closed under vector addition (`u, v → W ⇐ u+ v → W`) and scalar multiplication (`u → W, ϑ → F ⇐ ϑ · u → W`).
*   **Definition 2.1.8 (Column Space)**: For a matrix A → Mm→n(F), the **column space `col(A)` is a subspace of `Mm→1(F)`** defined as `Col(A) = {A↔ B : B → Mn→1(F)}`.
*   **Definition 2.1.9 (Row Space)**: For a matrix A → Mm→n(F), the **row space `row(A)` is a subspace of `M1→n(R)`** defined as `Row(A) = {B ↔ A : B → M1→n(F)}`.
*   **Definition 2.1.10 (Null Space/Kernel)**: For a matrix A → Mm→n(F), the **null space or kernel `ker(A)` is a subspace of `Mn→1(F)`** defined as `ker(A) = {B → Mn→1(F) : AB = 0}`.
*   **Definition 2.2.1 (Span)**: Let V be a vector space over F and S ≃ V. The **span of S, denoted `span(S)`, is the set of all finite linear combinations of vectors in S**: `span(S) = { ∑ni=1 ϑivi | n → N, vi → V , ϑi → F, i = 1, . . . n }`.
*   **Proposition 2.2.8**: For an `m`×`n` matrix A:
    *   (i) **Col(A) = Mn→1(F) if and only if A is right invertible**.
    *   (ii) **Row(A) = M1→m(F) if and only if A is left invertible**.
*   **Corollary 2.2.8.1**: For an `n`×`n` matrix A, **Row(A) = M1→n(F) and Col(A) = Mn→1(F) if and only if A is invertible**.
*   **Proposition 2.2.10**: Let V be a vector space over F and S ≃ V. If `v → V` such that **`v → span(S)` then `span(S ′ {v}) = span(S)`**.
*   **Definition 2.2.12 (Linear Independence)**: A **set S ≃ V is linearly independent if for any finite subset `{v1, v2, . . . , vn} ≃ S`, the equation `ϑ1v1 + ϑ2v2 + · · ·+ ϑnvn = 0` implies that all scalars `ϑ1 = ϑ2 = · · · = ϑn = 0`**.
*   **Proposition 2.2.19**: For A → Mn→n(F), **`det(A) ↘= 0` if and only if the columns of A are linearly independent**.
*   **Proposition 2.2.20**: For A → Mm→n(F), the **following statements are equivalent**:
    *   (i) Columns of A are linearly independent.
    *   (ii) The system `AX = 0` has a unique solution.
*   **Corollary 2.2.20.1**: For A → Mm→n(F), if **`n > m` then the columns of A are linearly dependent**.
*   **Definition 2.2.21 (Minimal Spanning Set)**: A subset S ≃ V is a **minimal spanning set for V if `span(S) = V` and for any `a → S`, `span(S \ {a}) ↘= V`**.
*   **Definition 2.2.22 (Maximal Linearly Independent Set)**: A **linearly independent subset S ≃ V is a maximal independent subset if for any `0 ↘= w → V`, the set `S ′ {w}` is linearly dependent**.
*   **Theorem 2.2.23**: Let V be a vector space over F and `B = {b1, . . . , bn} ≃ V`. The **following statements are equivalent**:
    *   (i) For every `v → V`, there exist unique scalars `ϑ1, . . . ,ϑn` such that `v = ∑ni=1 ϑibi`.
    *   (ii) `B` is a minimal spanning set for `V`.
    *   (iii) `B` is a maximal linearly independent subset of `V`.
*   **Definition 2.2.24 (Basis)**: A **set B ≃ V is a basis of V if it is linearly independent and `span(B) = V`**.
*   **Theorem 2.2.25 (Existence of Basis)**: Every vector space `V` over `F` **contains a basis**.
*   **Lemma 2.2.28**: Let V be a vector space over F. If `{b1, . . . , bn}` is a spanning set for V, then **any set of vectors in V with cardinality greater than `n` is linearly dependent**.
*   **Theorem 2.2.30 (Dimension Theorem)**: If `V` is a vector space over `F` and `B1, B2` are two bases of `V` with finite cardinality, then **`card(B1) = card(B2)`**.
*   **Definition 2.2.31 (Dimension of Vector Space)**: For a vector space `V` over `F` with a finite basis `B`, the **dimension of V, denoted `dim(V)`, is the cardinality of `B`**.
*   **Proposition 2.2.33**: For a finite-dimensional vector space `V`:
    *   (i) If `W △ V` is a subspace, then **`dim(W ) ↑ dim(V )`**.
    *   (ii) If **`dim(V) = n`, then any set of `n` linearly independent vectors forms a basis for `V`**.
*   **Theorem 2.2.34 (Extension to Basis)**: For an `n`-dimensional vector space `V` over `F`, any **linearly independent set `{f1, . . . , fr}` is contained within a basis of `V`**.

### Inner Product and Normed Linear Spaces

*   **Definition 2.3.1 (Complex Inner Product)**: For a vector space `V` over `C`, an **inner product `¬·, ·∅ : V ↔ V ⇓ C` satisfies**:
    *   (i) Conjugate symmetry: `¬u, v∅ = ¬v, u∅`.
    *   (ii) Linearity in the first argument: `¬ϑu+ v, w∅ = ϑ¬u, w∅+ ¬v, w∅`.
    *   (iii) Positive-definiteness: `¬v, v∅ ↓ 0`, and `¬v, v∅ = 0` if and only if `v = 0`.
*   **Definition 2.3.2 (Real Inner Product)**: For a vector space `V` over `R`, an **inner product `¬·, ·∅ : V ↔ V ⇓ R` satisfies**:
    *   (i) Symmetry: `¬u, v∅ = ¬v, u∅`.
    *   (ii) Linearity in the first argument: `¬ϑu+ v, w∅ = ϑ¬u, w∅+ ¬v, w∅`.
    *   (iii) Positive-definiteness: `¬v, v∅ ↓ 0`, and `¬v, v∅ = 0` if and only if `v = 0`.
*   **Definition 2.3.3 (Inner Product Space)**: A **vector space over `C` (or `R`) equipped with a complex (respectively real) inner product is called an Inner Product Space**.
*   **Definition 2.3.7 (Orthogonal Vectors)**: In an inner product space `V`, **two vectors `v, w → V` are orthogonal if `¬v, w∅ = 0`**.
*   **Definition 2.3.10 (Orthogonal and Orthonormal Basis)**: For an `n`-dimensional inner product space `V` over `C`, a spanning set `B = {b1, . . . , bn} ≃ V` is:
    *   An **orthogonal basis if `¬bi, bj∅ = 0` for `i ↘= j`**.
    *   An **orthonormal basis if `¬bi, bj∅ = 0` for `i ↘= j` and `¬bi, bi∅ = 1`**.
*   **Definition 2.3.11 (Unitary and Orthogonal Matrix)**:
    *   A **matrix U → Mn(C) is unitary if `U⇓U = UU⇓ = I`**.
    *   A **matrix O → Mn(R) is orthogonal if `O↑O = OO↑ = I`**.
*   **Definition 2.3.16 (Norm)**: For a vector space `V` over `F`, a **norm on V is a function `ℜ · ℜ : V ⇓ R+` such that**:
    *   (i) Positive-definiteness: `ℜvℜ ↭ 0` for all `v → V`, and `ℜvℜ = 0` if and only if `v = 0`.
    *   (ii) Scalar homogeneity: `ℜϑvℜ = |ϑ| · ℜvℜ` for `ϑ → F, v → V`.
    *   (iii) Triangle inequality: `ℜv + wℜ ↫ ℜvℜ+ ℜwℜ` for `v, w → V`.