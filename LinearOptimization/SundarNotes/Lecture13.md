Here are detailed revision notes for Lecture 13, "Introduction to Duality", including relevant theorems and their proofs, as presented in the sources:

---

### **Lecture 13: Introduction to Duality**

This lecture serves as an introduction to the concept of duality in linear optimization, building upon the simplex algorithm's correctness and offering a geometric interpretation.

#### **1. Proof of Correctness of Simplex Algorithm**

The lecture begins by revisiting and formally proving the correctness of the Simplex algorithm.

*   **Context**: Let x₀ be an extreme point defined by the system of equalities A'x₀ = b' (where A' consists of *n* linearly independent rows from the original matrix A, and b' are the corresponding values from *b*) and strict inequalities A''x₀ < b''. The directions of the neighbouring extreme points from x₀ are given by the columns of the matrix **−(A')⁻¹**.

*   **Theorem 1**: If the cost does not increase along any of the columns of −(A')⁻¹, then x₀ is optimal.

    *   **Proof**:
        1.  The columns of −(A')⁻¹ are significant because they form a **basis for Rⁿ**. This means any vector in Rⁿ can be expressed as a linear combination of these columns.
        2.  Let x_opt be an optimal point in the feasible region. We want to show that cᵀx_opt ≤ cᵀx₀. Since the columns of −(A')⁻¹ form a basis, the vector **x_opt − x₀** can be represented as a linear combination of these columns:
            x_opt − x₀ = Σⱼ λⱼ(−(A')⁻¹)(j) **(1)**
        3.  **Premultiply both sides by A'**:
            A'(x_opt − x₀) = Σⱼ λⱼA'(−(A')⁻¹)(j) **(2)**
        4.  **Analysis of the Left-Hand Side (LHS)**:
            *   We know that x_opt is a feasible point, so it satisfies the constraints A'x_opt ≤ b'.
            *   We also know that x₀ is an extreme point, and the defining hyperplanes are tight, so A'x₀ = b'.
            *   Therefore, A'(x_opt − x₀) = A'x_opt − A'x₀ ≤ b' − b' = **0**. This means the LHS is a vector whose components are all **non-positive**.
        5.  **Analysis of the Right-Hand Side (RHS)**:
            *   The product A'(−(A')⁻¹)(j) results in an n×1 vector where the j-th element is **−1** and all other elements are **0**. This is denoted as −eⱼ (where eⱼ is the standard basis vector with 1 in the j-th position).
            *   Substituting this back into the RHS of equation (2):
                A'(x_opt − x₀) = [−λ₁, −λ₂, ..., −λn]ᵀ **(3)**
        6.  **Combining LHS and RHS**: Since the LHS is a vector with non-positive components, and we found the RHS to be [−λ₁, ..., −λn]ᵀ, it implies that **−λⱼ ≤ 0** for all j. Consequently, **λⱼ ≥ 0** for all j.
        7.  **Multiply Equation (1) by cᵀ**:
            cᵀx_opt − cᵀx₀ = Σⱼ λⱼcᵀ(−(A')⁻¹)(j) **(4)**
        8.  **Final Conclusion**:
            *   The stopping condition of the simplex algorithm states that the cost does not increase along the directions of the neighbours. This means **cᵀ(−(A')⁻¹)(j) ≤ 0** for all j.
            *   Since we established that **λⱼ ≥ 0** and we know **cᵀ(−(A')⁻¹)(j) ≤ 0**, the entire summation on the RHS of equation (4) must be **less than or equal to zero** (Σⱼ λⱼcᵀ(−(A')⁻¹)(j) ≤ 0).
            *   Therefore, **cᵀx_opt − cᵀx₀ ≤ 0**, which simplifies to **cᵀx_opt ≤ cᵀx₀**. This proves that x₀ is indeed an optimal point, as no other feasible point (including the truly optimal x_opt) can have a higher cost than x₀.

*   **Note**: This theorem is crucial as it infers that when the Simplex algorithm terminates, it yields an optimal solution.

#### **2. A Geometric Introduction to Duality**

This section introduces the concept of duality by transforming the optimality condition of the primal LP into an equivalent algebraic form, leading to the definition of the dual problem.

*   **Optimality Condition and Algebraic Manipulation**:
    *   At an optimal point x₀, the Simplex algorithm's termination condition implies that the cost does not increase along the columns of −(A')⁻¹.
    *   Mathematically, this means: **cᵀ(−(A')⁻¹) ≤ 0ᵀ**.
    *   Multiplying by −1 (and reversing the inequality): **cᵀ(A')⁻¹ ≥ 0ᵀ**.
    *   Let's define a row vector **yᵀ = (γ₁, γ₂, ..., γn)** such that **yᵀ = cᵀ(A')⁻¹**. From the previous step, we know that **γᵢ ≥ 0** for each i.
    *   Now, post-multiply both sides of **yᵀ = cᵀ(A')⁻¹** by A':
        **yᵀA' = cᵀ**.
    *   Taking the transpose of both sides, we get:
        **(A')ᵀy = c** where **y ≥ 0**.

*   **Geometric Interpretation of Optimality**:
    *   The result **c = (A')ᵀy** with **y ≥ 0** reveals a key geometric insight: at the optimal point, the **cost vector c can be written as a non-negative linear combination of the rows of A'**.
    *   The rows of A' represent the normal vectors to the hyperplanes defining x₀. Specifically, for an inequality Aᵢx ≤ bᵢ, the vector Aᵢ is an **outward normal** to the hyperplane Aᵢx = bᵢ, pointing away from the feasible region.
    *   Thus, an extreme point x₀ is optimal if and only if **x₀ is feasible, and its cost vector c can be expressed as a non-negative linear combination of the normal vectors of its defining hyperplanes (rows of A')**. This geometric fact is illustrated in Figure 1, where the cost vector points "outward" from the feasible region, along a cone formed by the normals of the active constraints.

*   **Introducing the Set F**:
    *   The lecture defines a set **F** consisting of points *z* (not necessarily feasible) that are the intersection of *n* linearly independent hyperplanes from A, and for which the cost vector *c* can be written as a non-negative linear combination of the normals of these defining hyperplanes.
    *   It is asserted that among all points in F, the feasible points will have the lowest cost, thereby identifying the optimal points of the original LP.
    *   For any point *z* ∈ F, if B' are its defining hyperplanes, the feasible region of the LP lies within the cone generated by the columns of −(B')⁻¹. Since the cost is non-increasing along these directions (cᵀ(−(B')⁻¹) ≤ 0), no feasible point will have a cost greater than that of *z*. If *z* itself is feasible, it must be an optimum vertex for the LP.

*   **Cost at Points in F and the Dual LP**:
    *   Consider a point *z* ∈ F, characterized by A'z = b', and where cᵀ = Σᵢ γᵢA'ᵢ with γᵢ ≥ 0.
    *   A vector **y** with *m* coordinates can be constructed such that yⱼ = γ_s if the j-th row of A is the s-th row of A', and zero otherwise. For this **y**, we have cᵀ = Σᵢ yᵢAᵢ and y ≥ 0.
    *   The cost at *z* is cᵀz. Substituting cᵀ, we get cᵀz = (Σᵢ yᵢAᵢ)z.
    *   Since for any yᵢ > 0, Aᵢz = bᵢ (because these are the defining hyperplanes), the expression simplifies to **cᵀz = Σᵢ yᵢbᵢ = yᵀb**.
    *   This observation motivates the definition of a new Linear Program, called the **Dual LP**:

        **min yᵀb**
        **s.t. Aᵀy = c**
        **y ≥ 0**

*   **Connection between Primal and Dual**:
    *   The lecture states that for each point in F, there exists a feasible point in the newly defined Dual LP that shares the same cost.
    *   Conversely, for each extreme point of the Dual LP, a corresponding point *z* in F of the original LP can be found with the same cost (i.e., cᵀz = bᵀy).
    *   The dimension of the Dual LP is *m*. At an extreme point of the Dual LP, at least *m-n* of the *yᵢ* variables must be zero due to the *n* equality constraints (Aᵀy = c).
    *   The formal proof that the optimum points of both LPs coincide and their costs are equal is reserved for a future lecture, known as the **Duality Theorem**.

---