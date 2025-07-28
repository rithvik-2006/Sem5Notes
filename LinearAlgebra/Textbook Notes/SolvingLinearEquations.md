Here are revision notes on the requested topics from Chapter 2 of the sources:

### 2 Solving Linear Equations
The central problem of linear algebra is to **solve a system of linear equations**. These equations are linear, meaning unknowns are only multiplied by numbers, never by each other (e.g., no 'x times y'). The goal is to find numbers that satisfy all equations simultaneously.

### 2.1 Vectors and Linear Equations
*   **Row Picture**: Each linear equation (e.g., x - 2y = 1) represents a **straight line** in a 2D plane. For three unknowns, each equation represents a **plane** in 3D space. The **solution** to the system is the point (or points) where these lines or planes **intersect**. If the planes do not meet at a point, there is no solution.
*   **Column Picture**: The system of equations can be written as a **vector equation** where the right-hand side is a **linear combination of the column vectors** of the coefficient matrix. The unknowns (x, y, z, etc.) are the **coefficients** of this linear combination. This perspective asks for a combination of columns that produces the right-hand side vector `b`.
*   **Matrix Form**: A system of linear equations can be compactly written as **Ax = b**.
    *   **Matrix-vector multiplication Ax** is defined as a **linear combination of the columns of A**, with the components of `x` as coefficients.
    *   Alternatively, `Ax` can be computed by taking the **dot product of each row of A with the vector x**.

### 2.2 The Idea of Elimination
*   **Elimination**: This is a **systematic way to solve linear equations** by transforming the original system `Ax = b` into an **upper triangular system U x = c**.
*   **Process**: It involves **subtracting a multiple** (called a **multiplier** `ℓij`) of one equation (row `j`) from another equation (row `i`) to create a **zero** in a specific position (the `(i, j)` entry).
*   **Pivots**: The **first nonzero entry** in a row during elimination is called a **pivot**. We aim to have `n` pivots for an `n` by `n` system. **Pivots cannot be zero**.
*   **Breakdown**:
    *   **Temporary Failure**: If a pivot position becomes zero, but a **row exchange** (permutation) can bring a non-zero element into that position, elimination can continue.
    *   **Permanent Failure**: If a pivot position becomes zero and there's **no non-zero element below it to exchange**, elimination breaks down permanently. This indicates a **singular system**, which has either **no solution** or **infinitely many solutions**.
*   **Back Substitution**: Once the system is in upper triangular form (`U x = c`), the unknowns can be solved starting from the last equation and working upwards.

### 2.3 Elimination Using Matrices
*   **Matrix Representation of Steps**: Each step of elimination can be represented by multiplying the matrix `A` (and vector `b`) by an **elimination matrix E**.
*   **Identity Matrix (I)**: A matrix with `1`s on the diagonal and `0`s elsewhere. Multiplying by `I` leaves the vector unchanged (`Ib = b`).
*   **Elimination Matrix (Eij)**: Formed by starting with the identity matrix `I` and changing one of its zeros to the **negative of the multiplier (-ℓ)**. For example, `E21` subtracts `ℓ21` times row 1 from row 2.
*   **Permutation Matrix (Pij)**: Used to **exchange rows** (e.g., `P13` exchanges rows 1 and 3). These are needed when a zero appears in a pivot position.
*   **Augmented Matrix ([A b])**: To perform the same row operations on both `A` and `b` simultaneously, they are combined into an augmented matrix `[A b]`. Elimination on `[A b]` results in `[U c]`.

### 2.4 Rules for Matrix Operations
*   **Matrix Definition**: A **rectangular array of numbers** or "entries". An `m` by `n` matrix has `m` rows and `n` columns.
*   **Matrix Addition**: Matrices can be added if they have the **same shape**; addition is done component by component.
*   **Scalar Multiplication**: Multiplying a matrix by a number (scalar `c`) involves multiplying **every entry** of the matrix by `c`.
*   **Matrix Multiplication (AB)**:
    *   The most common method: The `(i, j)` entry of `AB` is the **dot product of row `i` of A with column `j` of B**.
    *   The **column picture**: `AB` can be viewed as `A` multiplying **each column of B separately**, so the columns of `AB` are linear combinations of the columns of `A`.
    *   The **row picture**: `AB` can be viewed as **each row of A multiplying the matrix B**, so the rows of `AB` are linear combinations of the rows of `B`.
    *   **Columns times rows (Outer Product)**: `AB` can be expressed as the sum of `n` matrices, where each is a product of a column of `A` and a row of `B`.
*   **Dimensions for Multiplication**: An `m` by `n` matrix `A` can multiply an `n` by `p` matrix `B` to produce an `m` by `p` matrix `AB`. The number of columns in `A` must equal the number of rows in `B`.
*   **Properties**:
    *   **Associative Law**: **A(BC) = (AB)C**. This is **extremely useful**.
    *   **Distributive Laws**: `A(B + C) = AB + AC` and `(A + B)C = AC + BC`.
    *   **Not Commutative**: In general, **AB ≠ BA**.
*   **Block Multiplication**: Matrices can be divided into blocks and multiplied as if the blocks were individual entries, provided the block dimensions are compatible.

### 2.5 Inverse Matrices
*   **Definition**: For a square matrix `A`, its **inverse matrix A⁻¹** (of the same size) satisfies **A⁻¹A = I** and **AA⁻¹ = I** (where `I` is the identity matrix). The inverse **undoes** what `A` does.
*   **Existence of Inverse (Invertibility)**:
    *   `A⁻¹` exists if and only if elimination produces **`n` pivots**. Row exchanges are allowed.
    *   If there is a **nonzero vector `x` such that Ax = 0**, then `A` **cannot have an inverse**. If `A` is invertible, `Ax = 0` implies `x = 0`.
    *   A matrix is invertible if its **determinant is not zero**.
*   **Uniqueness of Inverse**: A matrix can only have **one inverse**.
*   **Solution using Inverse**: If `A` is invertible, the unique solution to `Ax = b` is **x = A⁻¹b**.
*   **Properties of Inverses**:
    *   **(AB)⁻¹ = B⁻¹A⁻¹**. The inverse of a product is the product of the inverses in reverse order.
    *   The inverse of a **diagonal matrix** exists if no diagonal entries are zero.
*   **Gauss-Jordan Method**: This method finds `A⁻¹` by solving `AA⁻¹ = I`. It augments `A` with `I` to form `[A I]` and then uses row operations to reduce `A` to `I`. The result is `[I A⁻¹]`.

### 2.6 Elimination = Factorization: A = LU
*   **The LU Factorization**: Gaussian elimination (without row exchanges) transforms a matrix `A` into an upper triangular matrix `U`. The **multipliers** used during elimination can be stored in a **lower triangular matrix L** such that **A = LU**.
    *   `L` has `1`s on its diagonal and the multipliers `ℓij` in the lower triangular part.
    *   `U` is the upper triangular matrix obtained from `A` after elimination (its echelon form).
*   **Why it's useful**: This factorization separates the elimination process into two matrices. `L` remembers the steps to get from `A` to `U`.
*   **Solving Ax = b with LU**: Once `A = LU` is known, solving `Ax = b` becomes two triangular systems, which are faster to solve:
    1.  **Lc = b** (forward substitution to find `c`).
    2.  **U x = c** (back substitution to find `x`).
*   **Computational Cost**: Factorisation takes about `(1/3)n³` multiplications/subtractions, and solving takes about `n²` multiplications/subtractions.

### 2.7 Transposes and Permutations
*   **Transpose (Aᵀ)**: The transpose of a matrix `A` is obtained by **interchanging its rows and columns**. If `A` is `m` by `n`, `Aᵀ` is `n` by `m`.
    *   The `(i, j)` entry of `Aᵀ` is the `(j, i)` entry of `A`.
*   **Properties of Transpose**:
    *   **(Aᵀ)ᵀ = A**.
    *   **(A + B)ᵀ = Aᵀ + Bᵀ**.
    *   **(AB)ᵀ = BᵀAᵀ**. The transpose of a product is the product of the transposes in reverse order.
    *   **Symmetric Matrices**: A matrix `A` is **symmetric** if **Aᵀ = A**.
    *   **Skew-symmetric Matrices**: A matrix `A` is **skew-symmetric** if **Aᵀ = -A**.
*   **Transpose and Inverse**: The inverse of the transpose is the transpose of the inverse: **(A⁻¹)ᵀ = (Aᵀ)⁻¹**.
*   **PA = LU Factorization**: When row exchanges (permutations) are necessary during elimination, the factorization becomes **PA = LU**, where `P` is a **permutation matrix** that reorders the rows of `A` before elimination. This ensures that no zero pivots are encountered.