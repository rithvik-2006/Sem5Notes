Here is a comprehensive list of all definitions, theorems, corollaries, and propositions from the notes, organised by section:

### **1.1 Systems of linear equations**

*   **Definition 1.1.1 (Euclidean complex Space)**: Let R denote the set of real numbers. For any natural number n > 0, **Rⁿ** is defined as the set of all n-tuples of real numbers (x₁, x₂, ..., xₙ) where each xᵢ belongs to R. These elements are called n-tuples of real numbers. The space Rⁿ is referred to as the **Euclidean real space** or **real Euclidean space of dimension n**.
*   **Definition 1.1.2 (Euclidean complex Space)**: Let R denote the set of real numbers. For any natural number n > 0, **Cⁿ** is defined as the set of all n-tuples of complex numbers (x₁, x₂, ..., xₙ) where each xᵢ belongs to C. These elements are called n-tuples of complex numbers.

### **1.2 Matrices**

*   **Definition 1.2.1 (Matrix)**: A **matrix** is a rectangular array of numbers, symbols, or expressions, arranged in rows and columns. Its elements, denoted aᵢⱼ, indicate their position, with the first subscript (i) for the row number and the second (j) for the column number. The collection of all m×n matrices with entries in a field F is denoted by M_m×n(F).
*   **Definition 1.2.2 (Identity Matrix)**: The **identity matrix** is an n×n matrix with 1s on the main diagonal and 0s elsewhere. It satisfies **I · A = A · I = A** for any n×n matrix A.
*   **Definition 1.2.4 (Transpose)**: For a matrix A ∈ M_m×n(F), its **transpose** Aᵀ ∈ M_n×m(F) is obtained by swapping rows and columns, such that **[Aᵀ]ᵢⱼ = [A]ⱼᵢ**.
*   **Definition 1.2.6 (Left Invertible matrix)**: A matrix A ∈ M_m×n(F) is **left-invertible** if there exists a matrix L ∈ M_n×m such that **LA = I**, where I is the n×n identity matrix.
*   **Definition 1.2.7 (Right Invertible matrix)**: A matrix A ∈ M_m×n(F) is **right-invertible** if there exists a matrix R ∈ M_n×m such that **AR = I**, where I is the m×m identity matrix.
*   **Definition 1.2.9 (Invertible Matrix)**: A square matrix A ∈ M_n(F) is **invertible** if there exists a matrix S ∈ M_n(F) such that **AS = SA = I**, where I is the n×n identity matrix. The matrix S is denoted as A⁻¹.
*   **Proposition 1.2.11**: Let A ∈ M_m×n(F) be both **left-invertible and right-invertible**. Then, the left and right inverses of A **match**. Moreover, A is **invertible** (i.e. m = n).
*   **Definition 1.2.14 (Determinant)**: The **determinant** of a square matrix A = [aᵢⱼ] is defined using Laplace expansion, which sums **(–1)ⁱ⁺ʲaᵢⱼMᵢⱼ(A)**, where j is fixed arbitrarily, and Mᵢⱼ(A) is the determinant of the minor submatrix obtained by removing the i-th row and j-th column.
*   **Definition 1.2.15 (Determinant - Alternate)**: An alternative definition for the **determinant** of A ∈ M_n×n is given by **det(A) = ∑_{ω∈S_n} sgn(ϖ) Π_{i=1}^n a_{i,ω(i)}**, where S_n is the set of all permutations of {1, 2, ..., n} and sgn(ϖ) is the sign of the permutation.
*   **Theorem 1.2.16**: Let A,B ∈ M_n(F) and R₁, ..., R_n be the rows of A. Then the **determinant** satisfies the following properties:
    *   (i) **det(I) = 1** where I ∈ M_n(F) is the identity matrix.
    *   (ii) For all B ∈ M_n(F), **det(AB) = det(A) det(B)**.
    *   (iii) Swapping two rows of a matrix negates its determinant: **det([R₁ | ... | Rᵢ | ... | Rⱼ | ... | R_n]ᵀ) = –1 det([R₁ | ... | Rⱼ | ... | Rᵢ | ... | R_n]ᵀ)**.
    *   (iv) Determinant is linear in each row: **det([R₁ | ... | Rᵢ + ϑK | ... | R_n]ᵀ) = det([R₁ | ... | Rᵢ | ... | R_n]ᵀ) + ϑ det([R₁ | ... | K | ... | R_n]ᵀ)** for any ϑ ∈ F and row matrix K.
*   **Definition 1.2.20 (Singular and non-singular matrix)**: A matrix A ∈ M_n(F) is said to be **singular** if **det(A) = 0**. The matrix A is said to be **non-singular** if **det(A) ≠ 0**.
*   **Definition 1.2.23 (Trace)**: The **trace** trA of a matrix A ∈ M_n(F) is defined as the sum of its diagonal entries: **trA = ∑_{i=1}^n (aᵢᵢ)**.

### **1.3 Solutions to system of linear equations**

*   **Definition 1.3.1 (Homogeneous System of equation)**: A system of linear equations AX = C is said to be **homogeneous** if each cᵢ in the right-hand side vector C is identically zero. Otherwise, it is called an **inhomogeneous** equation.
*   **Theorem 1.3.3 (Cramer’s rule)**: Let A ∈ M_n(F) be an invertible matrix. Then there is a **unique solution** to the system of equations **AX = C**, for any C ∈ M_m×1. If [b₁ ... b_n]ᵀ ∈ M_n×1 is a solution, then **b_k = (1/det(A)) det[A₁ |A₂| · · · | C (k-th column) | · · · |A_n]** for 1 ≤ k ≤ n, where A_k(C) is the matrix achieved by replacing the k-th column of A with C.
*   **Corollary 1.3.3.1**: Let A ∈ M_n(F) be an invertible matrix. The i,j-th entry of the matrix A⁻¹ is given by **[A⁻¹]ᵢⱼ = (1/detA) det[A₁ | · · · | Eⱼ (i-th column) | · · · | A_n]**, where Eⱼ is the j-th column of the identity matrix.
*   **Definition 1.3.5 (Elementary Row operations)**: The following row operations on any matrix A are called **elementary row operations**:
    *   1. **Replacing the i-th row of A with the j-th row of A** (denoted Rᵢ ⇔ Rⱼ).
    *   2. **Multiplying any row j by a non-zero scalar ϑ** (denoted ϑRⱼ for the j-th row).
    *   3. **Replacing the i-th row of A with ϑ times the j-th row plus the i-th row of A** for any ϑ ∈ F (denoted Rⱼ ⇑ Rⱼ + ϑRᵢ).
*   **Definition 1.3.6 (Elementary Matrix)**: An **elementary matrix** is a matrix that is formed by performing a single elementary row operation on the identity matrix.
*   **Proposition 1.3.8**: Every elementary operation on an m×n matrix is the same as **pre-multiplying by the corresponding m×m elementary matrix**.
*   **Corollary 1.3.8.1**: Every elementary matrix is **invertible**.
*   **Proposition 1.3.11**: Let A ∈ M_m×n(F) and C ∈ M_m×1(F). Let AX = C denote a system of equations. If B|D is an augmented matrix obtained by elementary row operations on A|C, then the solution sets are identical: **{X : AX = C} = {X : BX = D}**.
*   **Definition 1.3.12 (Row Echelon Form (REF))**: A matrix is in **row echelon form (REF)** if it satisfies the following conditions:
    *   (i) All non-zero rows are above any rows of all zeros.
    *   (ii) The leading entry of each non-zero row (called the **pivot**) is strictly to the right of the leading entry of the previous row.
    *   (iii) The leading entry in any non-zero row is 1 (sometimes this condition is omitted).
*   **Theorem 1.3.13**: Let A ∈ M_m×n(F). Then, there exist finitely many elementary matrices E₁, ..., E_p such that **E₁ · · · E_p · A is in REF**.
*   **Definition 1.3.14 (Reduced Row Echelon Form (RREF))**: A matrix is in **reduced row echelon form (RREF)** if it satisfies the following conditions:
    *   1. The matrix is in **row echelon form**.
    *   2. Each leading (or pivot) 1 is the **only non-zero entry in its column**.
*   **Theorem 1.3.17**: Let A ∈ M_n(F). Then, A is **non-singular** (i.e. det(A) ≠ 0) if and only if A is **invertible**.
*   **Corollary 1.3.17.1**: If A ∈ M_n×n is either **right-invertible or left-invertible**, then A must be **invertible**.
*   **Corollary 1.3.17.2**: Let A ∈ M_n×n(F). Then, A is **invertible** if and only if its Row Reduced Echelon Form (RREF) is the **identity matrix I**. In particular, the homogeneous system AX = 0 has a unique solution if and only if the RREF of A is I.
*   **Theorem 1.3.20**: Let A ∈ M_m×n(F). Then, the **row reduced echelon form of A exists, and it is unique**.
*   **Theorem 1.3.24**: Let A ∈ M_m×n(F) such that m < n. Then, the system **AX = 0 has at least one non-zero solution**. Moreover, if the cardinality of F is infinite, then it has **infinitely many solutions**.
*   **Corollary 1.3.24.1**: Let A ∈ M_m×n(R) or (C) such that m < n. If the system AX = C has at least one solution, then it has **infinitely many solutions**.
*   **Proposition 1.3.25**: Let A ∈ M_m×n(F) be both **left-invertible and right-invertible**. Then, the left and right inverses of A match. Moreover, A is **invertible** (i.e. m = n).

### **2.1 Introduction to vector spaces**

*   **Definition 2.1.1 (Vector Space)**: A **vector space V over a field F** is a set equipped with two operations (vector addition and scalar multiplication) that satisfy eight specific axioms:
    *   (i) Vector addition is **commutative**: u + v = v + u.
    *   (ii) Vector addition is **associative**: (u + v) + w = u + (v + w).
    *   (iii) There exists a unique **zero vector 0** ∈ V such that v + 0 = v for all v ∈ V.
    *   (iv) For each v ∈ V, there exists a unique **additive inverse –v** ∈ V such that v + (–v) = 0.
    *   (v) Scalar multiplication is **distributive over vector addition**: ϑ · (u + v) = ϑ · u + ϑ · v.
    *   (vi) Scalar multiplication is **distributive over scalar addition**: (ϑ + ϱ) · u = ϑ · u + ϱ · u.
    *   (vii) **Scalar compatibility**: ϑ · (ϱ · u) = (ϑ · ϱ) · u.
    *   (viii) **Multiplicative identity**: 1 · u = u for all u ∈ V, where 1 is the multiplicative identity in F.
*   **Proposition 2.1.3**: The following hold for all v ∈ V and ϑ ∈ F:
    *   (i) **0 · v = ϑ · 0 = 0**.
    *   (ii) **ϑ · v = 0 ⇔ ϑ = 0 or v = 0**.
    *   (iii) **(–1) · v = –v**.
*   **Definition 2.1.5 (Subspace)**: A non-empty subset W of a vector space V over F is called a **subspace** if W itself is a vector space under the operations inherited from V. Specifically, W must be **closed under vector addition** (if u, v ∈ W, then u + v ∈ W) and **closed under scalar multiplication** (if u ∈ W and ϑ ∈ F, then ϑ · u ∈ W).
*   **Definition 2.1.8 (Column Space)**: For a matrix A ∈ M_m×n(F), the **column space** col(A) is a subspace of M_m×1(F) defined as the set of all possible linear combinations of the columns of A: **Col(A) = {A·B : B ∈ M_n×1(F)}**.
*   **Definition 2.1.9 (Row Space)**: For a matrix A ∈ M_m×n(F), the **row space** row(A) is a subspace of M_1×n(R) (or M_1×n(C)) defined as the set of all possible linear combinations of the rows of A: **Row(A) = {B·A : B ∈ M_1×n(F)}**.
*   **Definition 2.1.10 (Null space)**: For a matrix A ∈ M_m×n(F), the **null space** or **kernel** ker(A) is a subspace of M_n×1(F) defined as the set of all vectors B such that AB = 0: **ker(A) = {B ∈ M_n×1(F) : AB = 0}**.

### **2.2 Basis and dimension**

*   **Definition 2.2.1 (Span)**: For a set S ⊆ V in a vector space V, the **span of S**, denoted span(S), is the set of all finite linear combinations of vectors from S. By convention, the span of an empty set is the zero vector: **span(∅) = {0}**.
*   **Proposition 2.2.8**: Let A be an m×n matrix. Then:
    *   (i) **Col(A) = M_m×1(F)** if and only if A is **right invertible**.
    *   (ii) **Row(A) = M_1×n(F)** if and only if A is **left invertible**.
*   **Corollary 2.2.8.1**: Let A be an n×n matrix. Then, **Row(A) = M_1×n(F) and Col(A) = M_n×1(F)** if and only if A is **invertible**.
*   **Proposition 2.2.10**: Let V be a vector space over F, and S ⊆ V be any subset. If v ∈ V such that v ∈ span(S), then **span(S ∪ {v}) = span(S)**.
*   **Definition 2.2.12 (Linear Independence)**: A set S ⊆ V is said to be **linearly independent** if for any finite subset {v₁, v₂, ..., v_n} ⊆ S, the equation **ϑ₁v₁ + ϑ₂v₂ + · · · + ϑ_nv_n = 0** implies that all scalars **ϑ₁, ϑ₂, ..., ϑ_n must be zero**. Any set of vectors that is not linearly independent is linearly dependent.
*   **Proposition 2.2.19**: Let A ∈ M_n×n(F). Then, **det(A) ≠ 0** if and only if the **columns of A are linearly independent**.
*   **Proposition 2.2.20**: Let A ∈ M_m×n(F). Then the following statements are equivalent:
    *   (i) **Columns of A are linearly independent**.
    *   (ii) The system **AX = 0 has a unique solution**.
*   **Corollary 2.2.20.1**: Let A ∈ M_m×n(F). If **n > m**, then the **columns of A are linearly dependent**.
*   **Definition 2.2.21 (Minimal spanning set)**: A subset S ⊆ V is called a **minimal spanning set** for V if it spans V (span(S) = V) and removing any single element from S results in a set that no longer spans V (span(S \ {a}) ≠ V for any a ∈ S).
*   **Definition 2.2.22 (Maximal Linearly Independent set)**: A linearly independent subset S ⊆ V is called a **maximal independent subset** if, for any non-zero vector w ∈ V, the set **S ∪ {w} becomes linearly dependent**.
*   **Theorem 2.2.23**: Let V be a vector space over F. Let B = {b₁, ..., b_n} ⊆ V be any subset. Then, the following statements are equivalent:
    *   (i) For every v ∈ V there exist **unique scalars** ϑ₁, ϑ₂, ..., ϑ_n such that **v = ∑_{i=1}^n ϑᵢbᵢ**.
    *   (ii) **B is a minimal spanning set for V**.
    *   (iii) **B is a maximal linearly independent subset of V**.
*   **Definition 2.2.24 (Basis)**: Let V be a vector space over F. A set B ⊆ V is said to be a **basis of V** if it is both **linearly independent** and **spans V**.
*   **Theorem 2.2.25 (Existence of Basis)**: Let V be a vector space over F. Then **V contains a basis**.
*   **Proposition 2.2.26**: Let B be a basis of V. Then for any v ∈ V there exists **unique scalars** ϑ₁, ..., ϑ_n ∈ F and vectors b₁, ..., b_n ∈ B such that **v = ∑_{i=1}^n ϑᵢbᵢ**.
*   **Lemma 2.2.28**: Let V be a vector space over F. Let {b₁, ..., b_n} be a spanning set of V. Then **any set of cardinality greater than n is linearly dependent in V**.
*   **Theorem 2.2.30 (Dimension Theorem)**: Let V be a vector space over F. Let B₁, B₂ be two bases of V of finite cardinality then their cardinalities are equal: **card(B₁) = card(B₂)**.
*   **Definition 2.2.31 (Dimension of Vector space)**: Let V be a vector space over F. Let B be a basis of V with finite cardinality. Then the **dimension of V**, denoted **dim(V)**, is defined as the **cardinality of B**.
*   **Proposition 2.2.33**: Let V be a finite-dimensional vector space. The following statements hold true:
    *   (i) Let W ⊆ V be a subspace, then **dim(W) ≤ dim(V)**.
    *   (ii) If **dim(V) = n**, then any **n linearly independent vectors form a basis for V**.
*   **Theorem 2.2.34 (Extension to Basis)**: Let V be an n-dimensional vector space over F. And let {f₁, ..., f_r} be a set of linearly independent vectors. Then **{f₁, ..., f_r} is contained in a basis of V**.

### **2.3 Inner product and Normed Linear spaces**

*   **Definition 2.3.1 (Complex Inner Product)**: Let V be a vector space over C. An **inner product** on V is a function ⟨·, ·⟩ : V × V → C satisfying the following properties for all u, v, w ∈ V and all scalars ϑ ∈ C:
    *   (i) **Conjugate symmetry**: **⟨u, v⟩ = ⟨v, u⟩**.
    *   (ii) **Linearity in the first argument**: **⟨ϑu + v, w⟩ = ϑ⟨u, w⟩ + ⟨v, w⟩**.
    *   (iii) **Positive-definiteness**: **⟨v, v⟩ ≥ 0** and **⟨v, v⟩ = 0 if and only if v = 0**.
*   **Definition 2.3.2 (Real Inner Product)**: Let V be a vector space over R. An **inner product** on V is a function ⟨·, ·⟩ : V × V → C (Note: The source explicitly states C for the codomain, but for a real inner product space, it typically maps to R, and scalars ϑ would be real) satisfying the following properties for all u, v, w ∈ V and all scalars ϑ ∈ C (or R for real inner product):
    *   1. **Symmetry**: **⟨u, v⟩ = ⟨v, u⟩**.
    *   2. **Linearity in the first argument**: **⟨ϑu + v, w⟩ = ϑ⟨u, w⟩ + ⟨v, w⟩**.
    *   3. **Positive-definiteness**: **⟨v, v⟩ ≥ 0** and **⟨v, v⟩ = 0 if and only if v = 0**.
*   **Definition 2.3.3 (Inner Product Space)**: A vector space over C (or R) with a complex (respectively real) inner product is called an **Complex (respectively real) inner product space**.
*   **Definition 2.3.7 (Orthogonal Vectors)**: Let V be an inner product space over C (or R). Two vectors v, w ∈ V are said to be **orthogonal** to each other if their inner product **⟨v, w⟩ = 0**.
*   **Definition 2.3.10 (Orthogonal and Orthonormal Basis)**: A spanning set B = {b₁, ..., b_n} of an n-dimensional inner product space V is called an **orthogonal basis** if **⟨bᵢ, bⱼ⟩ = 0 for all i ≠ j**. It is called an **orthonormal basis** if, in addition, **⟨bᵢ, bⱼ⟩ = 1 for i = j**.
*   **Definition 2.3.11 (Unitary and Orthogonal Matrix)**: A matrix U ∈ M_n(C) is called a **unitary matrix** if **UᴴU = UUᴴ = I**. A matrix O ∈ M_n(R) is called an **orthogonal matrix** if **OᵀO = OOᵀ = I**.
*   **Definition 2.3.16 (Norm)**: Let V be a vector space over F. A **norm** on V is a function ‖·‖ : V → R⁺ such that:
    *   (i) **Positive-definiteness**: **‖v‖ ≥ 0 for all v ∈ V** and **‖v‖ = 0 if and only if v = 0**.
    *   (ii) **Absolute homogeneity**: **‖ϑv‖ = |ϑ| · ‖v‖** for any scalar ϑ ∈ F and vector v ∈ V.
    *   (iii) **Triangle inequality**: **‖v + w‖ ≤ ‖v‖ + ‖w‖** for all v, w ∈ V.