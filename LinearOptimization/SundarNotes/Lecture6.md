Based on your query, and in line with the provided source material, I will provide revision notes for **Lecture 6: The Row Rank. All solutions to Ax = b**. It appears that the content for Lecture 6 in the provided document is identical to that of Lecture 5, which we have previously discussed. These notes will therefore reiterate and expand upon those concepts, with citations from both relevant sections where appropriate.

---

### **Lecture 6: The Row Rank. All solutions to Ax = b**

This lecture continues the exploration of linear systems, specifically focusing on the properties of a matrix's null space and the general form of solutions to `Ax = b`.

#### **1. Row Rank and the Dimension of the Null Space**

*   **Null Space Definition**: The null space of a matrix A is defined as the set of all vectors `x` such that `Ax = 0`. This set, denoted as `S = {x : Ax = 0}`, is a **subspace of R<sup>n</sup>**.
*   **Previously Established Dimension**: In prior lectures, it was established that the dimension of the null space of A is `n - k`, where `k` is the number of linearly independent columns in A.
*   **Key Objective of Lecture 6**: The primary goal is to demonstrate that the dimension of the null space is *also* equal to `n - r`, where `r` is the number of linearly independent rows of A. This ultimately leads to the significant conclusion that row rank equals column rank.

    *   **Geometric Intuition**:
        *   Both the solution vector `x` and the rows of matrix `A` are vectors in R<sup>n</sup>.
        *   The condition `Ax = 0` implies that `x` is **perpendicular (orthogonal)** to all rows of A.
        *   Consequently, the null space is the **orthogonal complement** of the row space of A (the space spanned by the rows of A).
        *   It is "believable" that the dimension of an orthogonal complement is `n - r`.

*   **Role of Gaussian Elimination**: Gaussian Elimination is a fundamental tool used to prove these relationships.
    *   It **does not change the set of solutions** `{x : Ax = 0}`.
    *   It **does not change the number of linearly independent columns** of A.
    *   **Lemma 1**: Gaussian Elimination **does not change the row space** of a matrix.
        *   **Proof Summary**: The two elementary operations of Gaussian Elimination – exchanging two rows, and replacing row `j` with `α * row_i + row_j` – preserve the row space. Any vector in the new space can be shown to be in the old space, and vice versa, similar to the exchange lemma used for basis size proofs. This preservation of the span ensures the dimension remains unchanged.

#### **Proving dim({x : Ax = 0}) = n − r**

The proof involves two main parts, building upon the properties of Gaussian Elimination:

1.  **Lower Bound (dim({x : Ax = 0}) ≥ n − r)**:
    *   Gaussian Elimination transforms matrix A into a form where the first `r` rows are non-zero (where `r` is the row rank), and the first non-zero entry in each of these `r` rows appears progressively later from top to bottom. For simplicity, it can be assumed these leading entries are 1s and located at positions `it = t` by renumbering variables or dividing equations.
    *   In this "row-echelon" like form, `n - r` variables can be assigned arbitrary values (the "free" variables, e.g., `x_r+1` to `x_n`). The remaining `r` variables (e.g., `x_1` to `x_r`) can then be uniquely determined to satisfy `Ax = 0`.
    *   This process allows for the construction of `n - r` linearly independent vectors (denoted `U_1, ..., U_{n-r}`) that are all solutions to `Ax = 0`. Their linear independence is easily observed from their structure, particularly their last `n - r` coordinates. This establishes that the dimension of the null space is at least `n - r`.

2.  **Equality (Theorem 2: dim({x : Ax = 0}) = n − r)**:
    *   To prove that the dimension is *exactly* `n - r`, it must be shown that *any* vector `x'` in the null space `{x : Ax = 0}` can be expressed as a linear combination of the `n - r` basis vectors (`U_i`'s) constructed in the lower bound proof.
    *   Let `x'` be an arbitrary solution to `Ax' = 0`.
    *   Construct a vector `x̃` as a linear combination of the `U_i`'s, using the last `n - r` components of `x'` as coefficients: `x̃ = x'_{r+1}U_1 + ... + x'_n U_{n-r}`.
    *   Define `x'' = x' - x̃`.
    *   By construction, the last `n - r` components of `x''` are zero.
    *   Since `Ax' = 0` (by assumption) and `A U_i = 0` (by construction of `U_i`s), it follows that `A x̃ = 0`.
    *   Therefore, `A(x' - x̃) = A x'' = 0`.
    *   Considering the Gaussian-eliminated form of A, and knowing that the first `r` columns are linearly independent (implied by the rank `r`), and the last `n - r` components of `x''` are zero, the equation `A x'' = 0` implies that the first `r` components of `x''` must also be zero.
    *   Thus, `x''` must be the zero vector, which means `x' = x̃`. This proves that any solution `x'` can be written as a linear combination of the `U_i`'s, thereby establishing the dimension as exactly `n - r`.

*   **Corollary 3: Row Rank equals Column Rank**: This is a direct and powerful consequence of the above proofs. Since `dim({x : Ax = 0}) = n - k` (where `k` is column rank) and also `dim({x : Ax = 0}) = n - r` (where `r` is row rank), it must be that `k = r`. This common number is called the **rank of the matrix A**.

#### **2. Solutions to Ax = b**

*   **Structure of Solutions**: The set of all solutions to `Ax = b` (where `b` is a non-zero column vector) has a distinct structure: it is a **subspace shifted by a particular vector**. Shifting a subspace means taking every vector in the subspace and adding a fixed vector to it.
*   **Theorem 4**: If `x_0` is *any particular solution* to `Ax_0 = b`, then *every solution* `x` to `Ax = b` can be written in the form `x = x_0 + x'`, where `x'` is *any vector satisfying Ax' = 0` (i.e., `x'` belongs to the null space of A).
    *   **Proof**: Let `x̃` be an arbitrary solution to `A x̃ = b`. We are given `x_0` as a particular solution such that `A x_0 = b`. Subtracting these two equations gives `A(x̃ - x_0) = b - b = 0`. By setting `x' = x̃ - x_0`, it becomes clear that `x'` is in the null space of A, and `x̃` (any solution) can be expressed as `x_0 + x'`.

In conclusion, Lecture 6 provides a comprehensive understanding of the null space dimension, the equality of row and column rank, and the complete structure of solutions to linear systems `Ax = b`. Gaussian Elimination serves as a central technique for demonstrating these fundamental linear algebra concepts.