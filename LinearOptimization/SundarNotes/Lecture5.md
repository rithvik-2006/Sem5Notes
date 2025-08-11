Here are the revision notes on Lecture 5, drawing on the provided sources:

**Lecture 5: The Row Rank. All solutions to Ax = b**

This lecture focuses on understanding the null space of a matrix and the structure of solutions to linear systems, building upon concepts from previous lectures like Gaussian Elimination.

### 1. Row Rank and the Dimension of the Null Space

*   **Null Space Definition**: The space {x : Ax = 0} is called the **null space** of the matrix A.
*   **Previously Established Dimension**: It was already shown that the dimension of the null space of A is equal to *n - k*, where *k* is the number of linearly independent columns in matrix A.
*   **Main Goal of Lecture 5**: To demonstrate that the dimension of the null space is *also* equal to *n - r*, where *r* is the number of linearly independent rows of A.
*   **Geometric Intuition**:
    *   Both the solution vector `x` and the rows of matrix `A` are vectors in Rn.
    *   The condition Ax = 0 means that `x` is **perpendicular** (or orthogonal) to all rows of A.
    *   Therefore, the null space is the **orthogonal complement** of the row space of A (the space spanned by the rows of A).
    *   It is "believable" that the dimension of the orthogonal complement is *n - r*.

#### Gaussian Elimination's Role

Gaussian Elimination is a crucial tool in understanding these properties:
*   It **does not change** the set of solutions {x : Ax = 0}.
*   It **does not change** the number of linearly independent columns of A.
*   **Lemma 1**: Gaussian Elimination **does not change the row space** of a matrix.
    *   **Proof Summary**:
        *   Exchanging two rows clearly preserves the row space.
        *   Replacing row `j` with `α * row_i + row_j` also preserves the solution set. This is because any linear combination of the old rows can be formed from the new set, and vice versa. This argument is similar to the exchange lemma used for proving basis size consistency. Since the span (row space) remains unchanged, its dimension also remains unchanged.

#### Proving dim({x : Ax = 0}) = n − r

1.  **Lower Bound (dim({x : Ax = 0}) ≥ n − r)**:
    *   After applying Gaussian Elimination, the matrix `A` is transformed into a form where the first `r` rows are non-zero (assuming `r` is the row rank), and leading non-zero entries appear later and later from top to bottom.
    *   In this form, you can assign arbitrary values to the `n - r` "free" variables (x_{r+1} through x_n) and then solve for the remaining `r` variables (x_1 through x_r) to find a solution to Ax = 0.
    *   This process allows for the construction of `n - r` linearly independent vectors (U_1, ..., U_{n-r}) that are all solutions to Ax = 0. Their linear independence is evident from their structure, particularly their last `n - r` coordinates. This establishes that the dimension of the null space is at least `n - r`.

2.  **Equality (Theorem 2: dim({x : Ax = 0}) = n − r)**:
    *   To prove equality, it must be shown that *any* vector `x'` in the null space {x : Ax = 0} can be expressed as a linear combination of the `n - r` basis vectors (U_i's) constructed above.
    *   Let `x'` be an arbitrary solution to Ax' = 0.
    *   Construct a vector `x̃` which is a linear combination of the U_i's, using the last `n - r` components of `x'` as coefficients: `x̃ = x'_{r+1}U_1 + ... + x'_n U_{n-r}`.
    *   Define `x'' = x' - x̃`.
    *   By construction, the last `n - r` components of `x''` are zero.
    *   Since `Ax' = 0` and `A U_i = 0` (as U_i are solutions), it follows that `A x̃ = 0`.
    *   Therefore, `A(x' - x̃) = A x'' = 0`.
    *   Because the first `r` columns of the (Gaussian-eliminated) matrix `A` are linearly independent (implied by the rank `r`), and the last `n - r` components of `x''` are zero, the equation `A x'' = 0` implies that the first `r` components of `x''` must also be zero.
    *   Thus, `x''` must be the zero vector, which means `x' = x̃`. This proves that any solution `x'` can indeed be written as a linear combination of the U_i's, establishing the dimension as exactly `n - r`.

*   **Corollary 3: Row Rank equals Column Rank**: This is a significant result derived from the above proofs. Since the dimension of the null space is `n - k` (column rank) and also `n - r` (row rank), it directly implies that `k = r`, meaning the number of linearly independent rows in a matrix is equal to the number of linearly independent columns. This common number is defined as the **rank of the matrix A**.

### 2. Solutions to Ax = b

*   **Structure of Solutions**: The set of all solutions to `Ax = b` (where `b` is a non-zero column vector) has a specific structure: it **looks like a subspace shifted by a vector**. "Shifting a subspace" means taking all vectors in a subspace and adding a fixed vector to each of them.
*   **Theorem 4**: If `x0` is *any particular solution* to `Ax0 = b`, then *every solution* `x` to `Ax = b` can be written in the form `x = x0 + x'`, where `x'` is *any vector satisfying Ax' = 0` (i.e., `x'` belongs to the null space of A).
    *   **Proof**: If `x̃` is any solution such that `A x̃ = b`, and `x0` is a particular solution such that `A x0 = b`, then subtracting the two equations yields `A(x̃ - x0) = b - b = 0`. By setting `x' = x̃ - x0`, it is clear that `x'` is in the null space of A, and `x̃` (any solution) can be expressed as `x0 + x'`.