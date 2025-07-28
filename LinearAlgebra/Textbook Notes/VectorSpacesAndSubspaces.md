Here are revision notes on the specified topics from Chapter 3, drawing on the provided sources:

### Chapter 3: Vector Spaces and Subspaces
This chapter moves beyond individual vectors and matrices to introduce the concept of "spaces" of vectors, which is considered the highest level of understanding in linear algebra. The central ideas revolve around understanding `Ax = b` more deeply, especially when `A` is not invertible.

### 3.1 Spaces of Vectors
*   **Vector Space Definition**: A **vector space** is a collection of "vectors" with rules for vector addition and scalar multiplication, such that the results of these operations remain within the space. This means the set of vectors is "closed" under these operations. There are eight required conditions for a set to be a vector space, ensuring basic arithmetic properties are satisfied.
    *   **Examples**: `Rⁿ` (column vectors with `n` real components), `M` (matrices), and `F` (functions) are examples of vector spaces.
*   **Subspace Definition**: A **subspace** of a vector space `V` is a set of vectors within `V` that itself satisfies the two closure requirements:
    1.  If `v` and `w` are in the subspace, then `v + w` is also in the subspace.
    2.  If `v` is in the subspace and `c` is any scalar, then `cv` is also in the subspace.
    *   **Key Property**: Every subspace must **contain the zero vector**. This is because if `v` is in the subspace, then `0v = 0` must also be in it. Planes or lines that do not pass through the origin are **not** subspaces.
    *   **Subspaces of R³**: All possible subspaces of `R³` are: any line through `(0,0,0)`, any plane through `(0,0,0)`, the whole space `R³`, and the single vector `(0,0,0)` (the zero subspace).
*   **Column Space C(A)**: The **column space** of a matrix `A` consists of **all linear combinations of its column vectors**.
    *   **Solvability**: The equation `Ax = b` has a solution **if and only if** the vector `b` is in the column space of `A`. If `b` is in the column space, the coefficients `x` in the linear combination provide a solution to `Ax = b`.
    *   **Dimension**: If `A` is an `m` by `n` matrix, its columns have `m` components, so the column space `C(A)` is a **subspace of `Rᵐ`**.
*   **Span**: A set of vectors `S` "spans" a subspace `SS` if `SS` contains all possible linear combinations of the vectors in `S`. The column space `C(A)` is spanned by the columns of `A`.

### 3.2 The Nullspace of A: Solving Ax = 0
*   **Nullspace Definition N(A)**: The **nullspace** of a matrix `A`, denoted `N(A)`, is the set of **all solutions `x` to the equation `Ax = 0`**.
    *   **Subspace Property**: The nullspace `N(A)` is always a **subspace of `Rⁿ`** (where `n` is the number of columns in `A`). This is because if `x` and `y` are in the nullspace, `A(x+y) = Ax + Ay = 0+0 = 0`, and `A(cx) = c(Ax) = c0 = 0`.
    *   **Non-zero `b`**: If `b` is not the zero vector, the solutions to `Ax = b` **do not form a subspace**, because `x = 0` is not a solution unless `b = 0`.
*   **Finding the Nullspace (Elimination)**:
    1.  **Forward elimination**: Transform `A` into an echelon matrix `U` (or its reduced form `R`).
    2.  **Special Solutions**: Identify **pivot variables** (columns with pivots) and **free variables** (columns without pivots). For each free variable, set it to 1 and all other free variables to 0, then solve `Ux = 0` (or `Rx = 0`) by back substitution to find the pivot variables. These solutions are called **special solutions**.
    *   **Complete Solution for `Ax=0`**: Every solution to `Ax = 0` is a **linear combination of these special solutions**.
*   **Wide Matrices (`n > m`)**: If a matrix `A` has more columns than rows (`n > m`), it must have **at least one free variable**. This means `Ax = 0` will have at least one **non-zero special solution**, and thus **infinitely many solutions** (the nullspace contains at least a line of solutions).

### 3.3 The Rank and the Row Reduced Form
*   **Rank Definition (r)**: The **rank `r` of a matrix `A` is the number of pivots** obtained during Gaussian elimination.
    *   **Row Echelon Form (U)**: Elimination brings `A` to an upper triangular echelon form `U`. The number of nonzero rows in `U` is the rank `r`.
    *   **Reduced Row Echelon Form (R)**: Further elimination (Gauss-Jordan) leads to `R = rref(A)`. In `R`, pivots are 1s, and all other entries in pivot columns are 0s. The number of 1s on the diagonal of `R` is also the rank `r`.
*   **Rank One Matrices**: A matrix has rank `r = 1` if all its rows are multiples of a single row, and all its columns are multiples of a single column. Such a matrix can be written as an **outer product `A = uvᵀ`** (a column vector times a row vector).
*   **Pivot Columns**: The **pivot columns** of `A` (corresponding to the pivot columns in `R`) are **linearly independent**. The non-pivot columns (free columns) are linear combinations of the pivot columns.
*   **Nullspace and Rank**: If an `m` by `n` matrix `A` has rank `r`, there are `n - r` free variables. This means the nullspace `N(A)` has a dimension of **`n - r`**, and it is spanned by `n - r` special solutions.

### 3.4 The Complete Solution to Ax = b
*   **Solvability Condition**: The system `Ax = b` is **solvable if and only if** `b` is in the **column space of `A`**. This means that the last `m - r` rows of the augmented matrix `[A b]` reduce to `0 = 0` (no contradiction like `0 = 1`).
*   **Complete Solution Form**: If `Ax = b` is solvable, its complete solution `x` is the sum of a **particular solution `xₚ`** and any vector from the **nullspace `xₙ`**:
    **`x = xₚ + xₙ`**.
    *   **Particular Solution (`xₚ`)**: One way to find `xₚ` is to set all **free variables to zero** and solve for the pivot variables using back substitution on `Ux = c` (or `Rx = d`). The solution `x = A⁻¹b` for an invertible matrix `A` is a special case where `xₙ = 0`.
    *   **Nullspace Solution (`xₙ`)**: The nullspace part `xₙ` is any linear combination of the special solutions to `Ax = 0`.
*   **Rank and Number of Solutions**:
    *   **Full Column Rank (`r = n`)**: If `A` has full column rank, there are no free variables (`n - r = 0`), so `N(A)` contains only the zero vector. If `Ax = b` is solvable, it has a **unique solution** (`x = xₚ`). If not solvable, it has no solution (often for `m > n`, an overdetermined system).
    *   **Full Row Rank (`r = m`)**: If `A` has full row rank, elimination produces no zero rows. The system `Ax = b` is **always solvable**. If `m = n`, it has a unique solution. If `m < n`, it has infinitely many solutions (an underdetermined system).

### 3.5 Independence, Basis and Dimension
*   **Linear Independence**: A set of vectors `v₁, ..., vₙ` is **linearly independent** if the only linear combination that produces the zero vector (`x₁v₁ + ... + xₙvₙ = 0`) is when **all coefficients `xᵢ` are zero**.
    *   **Connection to Nullspace**: For a matrix `A` whose columns are `v₁, ..., vₙ`, the columns are linearly independent **if and only if its nullspace `N(A)` contains only the zero vector (`x = 0`)**.
    *   **Linear Dependence**: If a non-zero combination gives the zero vector, the vectors are **linearly dependent**. This happens if one vector can be written as a combination of the others. In `Rⁿ`, any set of `n+1` or more vectors is linearly dependent.
*   **Span**: A set of vectors **spans a space** if their linear combinations fill that space. The columns of `A` span its column space `C(A)`.
    *   **Row Space**: The **row space** of `A` is the subspace spanned by its row vectors. It is equivalent to the **column space of `Aᵀ`** (`C(Aᵀ)`). The rows of an `m` by `n` matrix are vectors in `Rⁿ`.
*   **Basis**: A **basis** for a vector space is a set of vectors that has two properties:
    1.  The basis vectors are **linearly independent**.
    2.  They **span the space**.
    *   **Uniqueness**: Every vector in the space can be written as a **unique** linear combination of the basis vectors.
    *   **Standard Basis**: The columns of the identity matrix `I` form the **standard basis** for `Rⁿ`.
    *   **Basis for Column Space**: The **pivot columns of `A`** form a basis for its column space `C(A)`.
    *   **Basis for Row Space**: The **nonzero rows of `R`** (the row echelon form) form a basis for the row space `C(Aᵀ)`.
    *   **Basis for Nullspace**: The **`n - r` special solutions** form a basis for the nullspace `N(A)`.
*   **Dimension**: The **dimension of a vector space** is the **number of vectors in any basis** for that space. All bases for a given vector space will always contain the same number of vectors.
    *   The dimension of `Rⁿ` is `n`.
    *   The dimension of the space of `n` by `n` matrices is `n²`.

### 3.6 Dimensions of the Four Subspaces
This section presents the **Fundamental Theorem of Linear Algebra, Part 1**, which details the dimensions of the four fundamental subspaces associated with a matrix `A` and its transpose `Aᵀ`.

1.  **Column Space (`C(A)`)**: This is the space of all possible outputs `Ax` (linear combinations of the columns of `A`).
    *   **Dimension**: **`r`** (the rank of `A`).
    *   **Basis**: The **`r` pivot columns of `A`**.
    *   **Location**: Subspace of `Rᵐ`.

2.  **Nullspace (`N(A)`)**: This is the space of all solutions `x` to `Ax = 0`.
    *   **Dimension**: **`n - r`** (number of columns minus the rank).
    *   **Basis**: The **`n - r` special solutions**.
    *   **Location**: Subspace of `Rⁿ`.

3.  **Row Space (`C(Aᵀ)`)**: This is the space of all linear combinations of the rows of `A` (equivalent to `C(Aᵀ)`).
    *   **Dimension**: **`r`** (the rank of `A`).
    *   **Basis**: The **`r` non-zero rows of the echelon form `R`**.
    *   **Location**: Subspace of `Rⁿ`.

4.  **Left Nullspace (`N(Aᵀ)`)**: This is the space of all solutions `y` to `Aᵀy = 0`. It's called the "left" nullspace because `Aᵀy = 0` is equivalent to `yᵀA = 0ᵀ` (row vector `yᵀ` multiplying `A` from the left). This space contains combinations of rows of `A` that result in the zero row.
    *   **Dimension**: **`m - r`** (number of rows minus the rank).
    *   **Basis**: The `m - r` rows of the elimination matrix `E` that produce the zero rows in `R` form a basis for `N(Aᵀ)`.
    *   **Location**: Subspace of `Rᵐ`.

*   **Dimension Sums**:
    *   In `Rⁿ` (input space): `dim(C(Aᵀ)) + dim(N(A)) = r + (n - r) = n`.
    *   In `Rᵐ` (output space): `dim(C(A)) + dim(N(Aᵀ)) = r + (m - r) = m`.

*   **Key Insight**: The dimensions of the four fundamental subspaces for a matrix `A` are the **same as those for its row reduced form `R`**.