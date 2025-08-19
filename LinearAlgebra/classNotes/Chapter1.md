Here are revision notes on all the definitions and propositions from Chapter 1 of the provided sources:

### Chapter 1: Matrices and Systems of Linear Equations

This chapter introduces **matrices** and **systems of linear equations**, establishing key notations and fundamental concepts.

**Notations Established:**
*   **C**: Set of all **complex numbers**.
*   **R**: Set of all **real numbers**.
*   **Q**: Set of all **rational numbers**.
*   **N**: Set of all **natural numbers**.
*   **Z2**: Set of all **binary numbers**.
*   **F**: Represents **R, C, Z2, or Q** (a field).
*   **Lowercase letters (a, b, c, x, y, z)**: Denote **general vectors**.
*   **Uppercase letters (A, B, C, D, P, Q, R, X, Y, Z)**: Denote **general matrices**.
*   **Uppercase T, S, U**: Denote **linear transformations**.
*   **Calligraphic font (V, W, Z)**: Denote **general vector spaces**.
*   **n-tuples**: Can represent various physical quantities, e.g., (Latitude, Longitude) as a 2-tuple, (x, y, z) as a 3-tuple, (Name, Age, Height, Weight) as a 4-tuple.

---

### 1.1 Systems of Linear Equations

*   **Definition 1.1.1 (Euclidean Real Space)**: For any natural number *n* > 0, **Rⁿ** is defined as the set of all **n-tuples of real numbers** (x₁, x₂, ..., xₙ) where each xᵢ ∈ R. This is also called the real Euclidean space of dimension *n*.
*   **Definition 1.1.2 (Euclidean Complex Space)**: For any natural number *n* > 0, **Cⁿ** is defined as the set of all **n-tuples of complex numbers** (x₁, x₂, ..., xₙ) where each xᵢ ∈ C.
*   A **typical system of linear equations (LS)** is given by:
    a₁₁x₁ + ··· + a₁nxn = c₁
    a₂₁x₁ + ··· + a₂nxn = c₂
    ...
    am₁x₁ + ··· + amnxn = cm
    *   **Parts of a linear system**:
        1.  **x₁, ..., xₙ**: Indeterminates or variables.
        2.  **aᵢ,ⱼ**: Fixed coefficients belonging to F.
        3.  **cᵢs**: Fixed right-hand side values in F.
*   A **solution to the system (LS)** is a tuple (b₁, ..., bₙ) ∈ Fⁿ that satisfies all equations.
*   **Matrix Multiplication (MM) Version**: The system (LS) can be written compactly as **AX = C**, where A is the coefficient matrix (m×n), X is the column vector of variables (n×1), and C is the column vector of right-hand side values (m×1). This form (ω) is used frequently due to its compact nature.
*   **Linear Combination (LC) Version**: The system can also be expressed as a linear combination of the columns of A, where x₁ * (column 1 of A) + x₂ * (column 2 of A) + ... = C.

---

### 1.2 Matrices

*   **Definition 1.2.1 (Matrix)**: A **matrix** is a **rectangular array of numbers, symbols, or expressions, arranged in rows and columns**.
    *   Typically denoted by a **capital letter (e.g., A)**.
    *   Elements are **lowercase letters with two subscripts (aᵢⱼ)**, indicating row *i* and column *j*. The notation **[A]ᵢ,ⱼ** or **[aᵢⱼ]ₘ×ₙ** may be used.
    *   Matrix entries usually belong to a **field F (R, C, Z2, or Q)**.
    *   The **size of a matrix** is **m × n** (m rows by n columns), where m and n are non-zero natural numbers. **Aₘ×ₙ** notation can clarify size.
    *   **Mₘ×ₙ(F)** denotes the collection of all m×n matrices with entries in F. For square matrices, **Mₙ(F)** denotes Mₙ×ₙ(F).
*   **Admissible Operations on Matrices**:
    *   **(a) Addition**: Matrices of the **same size** are added by **adding corresponding elements**. C = A + B means cᵢⱼ = aᵢⱼ + bᵢⱼ.
    *   **(b) Scalar Multiplication**: Each element of the matrix is **multiplied by a scalar**. B = ϑ ⋅ A means bᵢⱼ = ϑ ⋅ aᵢⱼ.
    *   **(c) Matrix Multiplication**: The product of two matrices A (m×n) and B (n×p) is a new matrix C of size **m×p**. C = AB where cᵢⱼ = ∑ⁿₖ₌₁ aᵢₖbₖⱼ.
    *   **(d) Transpose**: The **transpose of a matrix A (Aᵀ)** is a new matrix obtained by **swapping rows and columns**. (Aᵀ)ᵢⱼ = aⱼᵢ.
*   **Definition 1.2.2 (Identity Matrix)**: The **n×n identity matrix (I)** has **1s on its main diagonal and 0s elsewhere**. It satisfies **I ⋅ A = A ⋅ I = A** for any n×n matrix A.
*   **Properties of Matrix Operations**:
    *   **(a) Associativity**: For applicable sizes, **(AB)C = A(BC)**.
    *   **(b) Distributivity**: Matrix multiplication distributes over addition: **A(B + C) = AB + AC** and **(A + B)C = AC + BC**.
    *   **(c) Non-commutativity**: Matrix multiplication is **generally not commutative**; **AB ≠ BA**.
    *   **(d) Identity Matrix**: Multiplying any matrix by an identity matrix of appropriate size leaves the original matrix unchanged: **AI = IA = A**.
*   **Definition 1.2.4 (Left Invertible Matrix)**: A matrix A (m×n) is **left-invertible** if there exists a matrix L (n×m) such that **LA = Iₙ×ₙ** (the n×n identity matrix).
*   **Definition 1.2.5 (Right Invertible Matrix)**: A matrix A (m×n) is **right-invertible** if there exists a matrix R (n×m) such that **AR = Iₘ×ₘ** (the m×m identity matrix).
*   **Definition 1.2.7 (Invertible Matrix)**: A **square matrix A (n×n)** is **invertible** if there exists a matrix S (n×n) such that **AS = SA = I** (the n×n identity matrix). This matrix S is denoted as **A⁻¹**.
*   **Proposition 1.2.9**: If a matrix A (m×n) is **both left-invertible and right-invertible**, then its left and right inverses **match (L = R)**. Moreover, **A is invertible (meaning m = n)**. (The proof for m=n is deferred to Theorem 1.3.24).
*   **Definition 1.2.12 (Determinant - Laplace Expansion)**: The determinant of a square matrix A (n×n) is defined using a **cofactor expansion** along an arbitrary column *j*: det(A) = ∑ⁿᵢ₌₁ (-1)ⁱ⁺ʲ aᵢⱼMᵢⱼ(A), where Mᵢⱼ(A) is the **minor** (determinant of the submatrix obtained by removing row *i* and column *j*).
*   **Definition 1.2.13 (Determinant - Leibniz Expansion)**: An alternative definition for the determinant of A (n×n) is det(A) = ∑ᵽ∈Sₙ sgn(ᵽ) ∏ⁿᵢ₌₁ aᵢ,ᵽ(ᵢ), where Sₙ is the set of all permutations and sgn(ᵽ) is the sign of the permutation.
*   **Theorem 1.2.14 (Properties of Determinant)**: For matrices A, B ∈ Mₙ(F):
    *   **(i) det(I) = 1** (where I is the identity matrix).
    *   **(ii) det(AB) = det(A)det(B)** (the most useful property).
    *   **(iii) Swapping two rows of a matrix changes the sign of its determinant**.
    *   **(iv) The determinant is linear with respect to rows** (e.g., det([...|Rᵢ + ϑK|...]) = det([...|Rᵢ|...]) + ϑ det([...|K|...])).
*   **Consequence (from Problem 1.2.17)**: If A is invertible, then **det(A⁻¹) = 1 / det(A)**. In particular, if **det(A) ≠ 0**, then A cannot be invertible. (Note: the text clarifies this is a verification, not a full proof of iff at this point)
*   **Definition 1.2.18 (Singular and Non-singular Matrix)**:
    *   A matrix A ∈ Mₙ(F) is **singular** if **det(A) = 0**.
    *   A matrix A is **non-singular** if **det(A) ≠ 0**.
*   **Definition 1.2.21 (Trace)**: The **trace (trA)** of a square matrix A (n×n) is the **sum of its diagonal elements**: trA = ∑ⁿᵢ₌₁ (aᵢᵢ).
*   **Properties of Trace (from Problem 1.2.22)**:
    *   **(i)** **tr(A+B) = tr(A) + tr(B)** and **tr(cA) = c ⋅ tr(A)**.
    *   **(ii)** **tr(AB) = tr(BA)**. More generally, tr(ABC) = tr(CAB) = tr(BCA).
    *   **(iii)** If P is invertible, **tr(P⁻¹AP) = tr(A)**.
    *   **(iv)** **tr(Aᵀ) = tr(A)**.
    *   **(v)** **tr([A,B]) = tr(AB - BA) = 0**.

---

### 1.3 Solutions to Systems of Linear Equations

*   **Definition 1.3.1 (Homogeneous System of Equation)**: A system of linear equations (AX=C) is **homogeneous** if all **cᵢ in the right-hand side are identically zero (C=0)**, i.e., **AX = 0**. Otherwise, it is an **inhomogeneous equation**.
    *   Every homogeneous equation has a **trivial solution**: **X = 0** (each indeterminate xᵢ = 0).
    *   **Property of Homogeneous Solutions**: If V₁ and V₂ are solutions to AX=0, then any **linear combination ϑ₁V₁ + ϑ₂V₂** is also a solution. The set of solutions of AX=0 is denoted as S.
*   **General Solution of Inhomogeneous Systems**: If W₀ is a **particular solution** to AX=C, then any other solution W can be written as **W = W₀ + U**, where U is a solution to the corresponding homogeneous system AX=0 (i.e., U ∈ S). This is called a **general solution**.
*   **Remark 1.3.2**: A system **A(X) = C has a unique solution if and only if the only solution for A(X) = 0 is X = 0**.

#### 1.3.1 Cramer’s Rule and Applications

*   **Theorem 1.3.3 (Cramer’s Rule)**: If A ∈ Mₙ(F) is an **invertible matrix**, then the system **AX = C** has a **unique solution**. The *k*th entry of the solution vector, **bₖ**, is given by **bₖ = det(Aₖ(C)) / det(A)**, where Aₖ(C) is the matrix A with its *k*th column replaced by C.
*   **Corollary 1.3.3.1**: The *i, j*th entry of the inverse matrix **A⁻¹** is given by **[A⁻¹]ᵢⱼ = (1 / det(A)) * det(A_j(E_i))**, where E_i is the *i*th column of the identity matrix.
*   **Remark 1.3.4 (Adjugate)**: The **adjugate of matrix A** is defined based on the determinants of the minors used in the inverse formula: **[adj(A)]ᵢⱼ = det(A_j(E_i))** (the *i, j*th entry of the adjugate is the determinant of A with the *j*th column replaced by the *i*th column of the identity matrix).

#### 1.3.2 Elementary Row Operations

*   **Definition 1.3.5 (Elementary Row Operations)**: These are fundamental operations performed on the rows of a matrix:
    1.  **Replacing row *i* with row *j*** (swapping): Rᵢ ⇔ Rⱼ.
    2.  **Multiplying row *j* by a non-zero scalar ϑ**: ϑRⱼ.
    3.  **Replacing row *i* with ϑ times row *j* plus row *i***: Rᵢ ⇐ Rᵢ + ϑRⱼ.
*   **Definition 1.3.6 (Elementary Matrix)**: An **elementary matrix** is a matrix formed by performing a **single elementary row operation on the identity matrix**.
*   **Proposition 1.3.8**: Every elementary operation on an m×n matrix is equivalent to **pre-multiplying the matrix by the corresponding m×m elementary matrix**.
*   **Corollary 1.3.8.1**: Every **elementary matrix is invertible**.
*   **Proposition 1.3.11**: Performing elementary row operations on an **augmented matrix A|C** results in a new augmented matrix B|D, but the **solution set of the system remains unchanged**: **{X : AX = C} = {X : BX = D}**.

#### 1.3.3 Gaussian Elimination by Row Echelon Form

*   **Definition 1.3.12 (Row Echelon Form (REF))**: A matrix is in **row echelon form** if it satisfies:
    *   **(i) All non-zero rows are above any rows of all zeros**.
    *   **(ii) The leading entry (pivot) of each non-zero row is strictly to the right of the leading entry of the previous row**.
    *   **(iii) The leading entry in any non-zero row is 1** (sometimes optional).
*   **Theorem 1.3.13**: For any matrix A (m×n), there exist a **finite number of elementary matrices E₁, ..., Eₚ** such that **E₁ ⋅ ··· ⋅ Eₚ ⋅ A is in REF**. REF is not necessarily unique.

#### 1.3.4 Gauss-Jordan Elimination by Row Reduced Echelon Form

*   **Definition 1.3.14 (Reduced Row Echelon Form (RREF))**: A matrix is in **reduced row echelon form** if it satisfies:
    1.  The matrix is **in row echelon form**.
    2.  **Each leading (or pivot) 1 is the only non-zero entry in its column**.
*   **Theorem 1.3.17**: **A square matrix A (n×n) is non-singular (i.e., det(A) ≠ 0) if and only if A is invertible**. The proof involves showing that if det(A) ≠ 0, then the RREF of A is the identity matrix.
*   **Corollary 1.3.17.1**: If a square matrix A (n×n) is either **right-invertible or left-invertible**, then **A must be invertible**.
*   **Corollary 1.3.17.2**: A square matrix A (n×n) is **invertible if and only if its RREF is the identity matrix I**. Consequently, the homogeneous system **AX = 0 has a unique solution (X=0) if and only if the RREF of A is I**.
*   **Method to find A⁻¹ using RREF**: By augmenting the matrix A with the identity matrix, **[A|I]**, and performing Gauss-Jordan elimination (reducing A to I), the right side will transform into A⁻¹: **[I|A⁻¹]**.
*   **Theorem 1.3.20**: The **row reduced echelon form (RREF) of any matrix A exists, and it is unique**.
*   **Theorem 1.3.24**: For a matrix A (m×n) where **m < n** (fewer equations than variables), the **homogeneous system AX = 0 has at least one non-zero solution**. If the field F is infinite, then it has **infinitely many solutions**.
*   **Corollary 1.3.24.1**: For a matrix A (m×n) over R or C where **m < n**, if the system **AX = C has at least one solution, then it has infinitely many solutions**.
*   **Proposition 1.3.25**: This proposition completes the proof of Proposition 1.2.9: If a matrix A (m×n) is **both left-invertible and right-invertible**, then the left and right inverses match, and it is concluded that **A is invertible (which implies m = n)**.
*   **Remark 1.3.26**: If A (m×n) is left-invertible, then **m ≥ n**. If A (m×n) is right-invertible, then **n ≥ m**.
*   **Remark 1.3.27 (RREF and Solution Types)**: The RREF of an augmented matrix A|C indicates the nature of the solution set:
    *   **(a) The last column is a pivot column**: The system is **inconsistent** (no solutions).
    *   **(b) Every column except the last is a pivot column**: The system has a **unique solution**.
    *   **(c) The last column is not a pivot column, and some other column is also not a pivot column**: The system has **infinitely many solutions**, corresponding to the free variable(s).