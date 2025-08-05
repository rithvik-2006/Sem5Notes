Here are detailed revision notes for Lecture 2 and Lecture 3, drawing directly from the provided sources:

### Lecture 2: Linear Algebra: Solving Ax = b via Gaussian Elimination

Lecture 2 focuses on formulating linear optimization problems and, more specifically, on **understanding and solving systems of linear equations of the form Ax = b**.

**1. Formulation of a Linear Optimization Problem**
A linear optimization problem can be formally expressed as:
*   **Maximise cᵀx**
*   **Subject to Ax ≤ b**
    *   Here, **A is an m×n matrix**, **c is an n×1 vector**, **b is an m×1 vector**, and **x is an n×1 vector**.
    *   The goal is to find an **x** that satisfies **Ax ≤ b** and **maximises cᵀx**.
*   The initial goal in the course is to understand the set {x : Ax ≤ b}, but the lecture begins by focusing on a simpler set: {x : Ax = b}. This is done by recalling procedures for finding solutions or recognising instances without solutions.

**2. Solving Ax = b**
The notation **Ax = b** is a shorthand for a system of **m** equalities:
A₁₁x₁ + A₁₂x₂ + ... + A₁nxn = b₁
A₂₁x₁ + A₂₂x₂ + ... + A₂nxn = b₂
...
Am₁x₁ + Am₂x₂ + ... + Amnxn = bm

**Gaussian Elimination** is a method used to solve such systems of equations.

*   **Example 1** (Illustrating Gaussian Elimination):
    2x + 7y = 13 (I)
    x + 3y = 4 (II)
    Replacing equation (II) with (-1/2) * (I) + (II) yields:
    (-7/2)y + 3y = -13/2 + 4
    y = 5 (2)
    From this, x can then be solved using the first equation.

*   **Phases of Gaussian Elimination**:
    1.  **First Phase (Crux)**: Iteratively replace the current set of equations with an **equivalent set of equations** (meaning they have the same solution sets) that are **simpler to analyse**.
        *   **Goal**: To get an equivalent set of equations where, except for the first row, all others have their first coordinate zero (assuming A₁₁ ≠ 0; if not, exchange rows).
        *   This is achieved by multiplying the first equation by a suitable constant and subtracting it from each of the other equations.
        *   The process then recursively ignores the first equation and the first variable, working with the remaining equations.
        *   **Operations used**:
            1.  **Exchanging two rows**.
            2.  **Replacing row_j with α * row_i + row_j**, where α is a constant.
        *   **Resulting Form**: After the first phase, the set of equations will look like a "staircase" or **row echelon form**.
        *   **Observations after First Phase**:
            1.  All **zero rows occur after the non-zero rows**.
            2.  If the first 't' rows are non-zero, and the **first non-zero entry of the i-th row is at the k-th column, then kᵢ > kᵢ₋₁** for i = 2, ..., t. This means first non-zero entries appear later and later from top to bottom.
    2.  **Second Phase**: Once the matrix is in this simplified form, it's easier to find solutions, if they exist.
        *   **Existence of a Solution**: **Ax = b does not have a solution if**, in a particular row 'i', **all coefficients Aᵢⱼ = 0 but bᵢ ≠ 0**. This condition is both necessary and sufficient for non-existence.
        *   If a solution exists, one can **assign arbitrary values to certain variables** (those not corresponding to the first non-zero entry in each row) and then **solve for the remaining variables in reverse order**.
        *   If the system has 'n' non-zero rows, it has **only one solution**. Otherwise, the set {x : Ax = b} generally has **many solutions**.

**3. Correctness of Gaussian Elimination**
The procedure is correct because the values obtained satisfy the original equations, meaning the **solution set does not change when applying Gaussian Elimination operations**.
*   **Exchanging two rows** clearly does not change the solution set.
*   **Theorem 1**: If equation Aⱼ is replaced by α * Aᵢ + Aⱼ, the **solution set does not change**.
    *   **Proof (Two parts)**:
        1.  **Original solution satisfies new set**: If (x'₁, ..., x'ₙ) is a solution to the original set, it satisfies Aᵢ and Aⱼ. By algebraic manipulation, it can be shown that (x'₁, ..., x'ₙ) also satisfies α * Aᵢ + Aⱼ.
        2.  **New solution satisfies original set**: If (x'₁, ..., x'ₙ) is a solution to the new set, it satisfies α * Aᵢ + Aⱼ and Aᵢ. Through algebraic steps, it is proven that it must also satisfy Aⱼ.

**4. Geometric Interpretation of Ax = b**
*   In two variables (x₁, x₂), linear equations (e.g., a₁₁x₁ + a₁₂x₂ = b₁) represent **straight lines in two dimensions**. The solution to a system of such equations can be a single point, a line, or the empty set. It cannot look like anything else.
*   This concept extends to three or more variables, aiming for a **geometric interpretation and algebraic description of these sets**.
*   Geometrically, **Ax = b represents the intersection of hyperplanes**.
*   The operation of adding a constant times another equation to an equation **rotates one of the hyperplanes in Rⁿ about the region of intersection**.
*   Gaussian Elimination can thus be described as **rotating the hyperplanes about their region of intersection** such that at each step, one hyperplane is made parallel to one axis.

### Lecture 3: Linear Algebra Basics

Lecture 3 introduces fundamental concepts from Linear Algebra to help understand the structure of the set of all solutions to linear equations.

**1. Vector Space**
A **vector space** is defined as a **set of vectors V** and the **real numbers R (scalars)**, with two defined operations:
*   **Vector Addition (V × V → V)**: Represented as **u + v**, where **u, v ∈ V**.
    *   This operation must follow **Abelian Group laws**:
        1.  **Associativity**: u + (v + w) = (u + v) + w.
        2.  **Identity**: There exists a **zero vector 0** such that **0 + u = u**.
        3.  **Inverse**: For every **u ∈ V**, there exists an **additive inverse -u** such that **u + (-u) = 0**.
        4.  **Commutativity**: u + v = v + u.
*   **Scalar Multiplication (R × V → V)**: Represented as **a ⋅ u**, where **a ∈ R** and **u ∈ V**.
    *   This operation must follow these **laws**:
        1.  **Multiplication by 0**: 0 ⋅ u = 0.
        2.  **Multiplication by -1**: (-1) ⋅ u = -u.
        3.  **Identity multiplication**: 1 ⋅ u = u.
        4.  **Distributivity of vector sum**: a ⋅ (u + v) = a ⋅ u + a ⋅ v (a ∈ R, u, v ∈ V).
        5.  **Distributivity of scalar sum**: (a + b) ⋅ u = a ⋅ u + b ⋅ u.
        6.  **Associativity of scalar multiplication**: a ⋅ (b ⋅ u) = (ab) ⋅ u.
*   The subject of linear algebra can be developed without explicit coordinates.

**2. Subspace**
A **subspace (U)** is a **subset of vectors (U ⊆ V)** that is also a **vector space in its own right**.
*   The laws of vector addition and scalar multiplication are inherited.
*   **Condition for a subset U to be a subspace**: For all **u₁, u₂ ∈ U** and **α ∈ R**:
    *   **u₁ + u₂ ∈ U**
    *   **α ⋅ u₁ ∈ U**
*   **Insight**: If u₁ ∈ U, then α = -1 implies -u₁ ∈ U. Consequently, -u₁ + u₁ = 0 ∈ U. Therefore, the **zero vector 0 is always a member of any subspace**.
*   **Example**: In a **2-dimensional space**, any **line passing through the origin is a subspace**. The origin itself is also a subspace. If a subspace contains a vector not on a line through the origin, it must be the entire plane. Thus, there are three types of subspaces in 2D: the origin, lines through the origin, and the entire plane.

**3. Linear Dependence, Independence, and Basis**
These definitions are crucial for developing the subject.

*   **Definition 1: Linearly Dependent Vectors**
    *   Vectors **v₁, ..., vₙ** are linearly dependent if there exist scalars **α₁, ..., αₙ ∈ R**, **not all zero**, such that:
        **∑ᵢ₌₁ⁿ αᵢ ⋅ vᵢ = 0**
    *   The "not all zero" clause is important.

*   **Definition 2: Linearly Independent Vectors**
    *   Vectors **v₁, ..., vₙ** are linearly independent if they are not linearly dependent; meaning, for **α₁, ..., αₙ ∈ R**:
        **∑ᵢ₌₁ⁿ αᵢ ⋅ vᵢ = 0 ⇒ αᵢ = 0, ∀i**

*   **Definition 3: Basis of a Vector Space V**
    *   Vectors **v₁, ..., vₙ** form a basis for V if and only if:
        1.  They are **linearly independent**.
        2.  **Every other vector w ∈ V can be written as a linear combination** of them: **w = ∑ᵢ₌₁ⁿ βᵢ ⋅ vᵢ**.
    *   **Alternatively**: A set of vectors forms a basis if they are linearly independent, and **adding any other vector w ∈ V to this set makes the set linearly dependent**.

*   **Crucial Fact: Dimension**
    *   Though there can be **multiple bases for the same vector space, all of them will have the same size**. This is a fundamental property of vector spaces.
    *   The **number of vectors in a basis is called the dimension of the vector space**.
    *   **Insight**: This fact might seem obvious in 2D and 3D, but it requires a formal proof, and the proof technique is frequently used in mathematics and algorithm design.
    *   The course will only deal with **finite-dimensional vector spaces**.

*   **Proof that all Bases have the Same Size**
    *   **Method**: Proof by contradiction.
    *   **Assumption for contradiction**: Suppose there are two bases, S and T, for a vector space V, with |S| < |T|.
    *   **Idea**: Repeatedly replace elements of T with elements of S, always maintaining that the resulting set is a basis. After |S| substitutions, a contradiction is reached.
    *   **Key Lemma 1**: If S = {v₁, ..., vₙ} is a basis and x = ∑ᵢ₌₁ⁿ αᵢvᵢ with α₁ ≠ 0, then S' = {x, v₂, ..., vₙ} spans the same space as S (i.e., **span(S) = span(S')**). This lemma was also used in the proof of Gaussian Elimination's correctness.
    *   **Formal Proof (Theorem 1)**:
        *   Assume S = {u₁, ..., uₘ} and T = {v₁, ..., vₙ} are two bases, with m < n.
        *   An iterative process (m times) replaces a vector from Sᵢ (which is a basis) with a vector from Tᵢ (the remaining vectors from T) to form Sᵢ₊₁.
        *   At each step, a vector vᵢ₊₁ from T (which can be written as a linear combination of vectors in Sᵢ) replaces one of the uⱼ's in Sᵢ (specifically, one with a non-zero coefficient in the linear combination). This new set Sᵢ₊₁ is also a basis.
        *   After 'm' such steps, the resulting set Sₘ will consist solely of 'm' vectors from T, and these 'm' vectors will span V.
        *   This contradicts the initial assumption that T (which has 'n' vectors, with n > m) is a basis, because a subset of T (Sₘ) already spans V, implying the vectors in T are not linearly independent if n > m.
        *   Therefore, the initial assumption (m < n) must be false, proving that **m = n**.

**4. Span of a Set of Vectors**
*   The **span of a set of vectors (v₁, ..., vₖ)** is the **set of all vectors that can be obtained by taking linear combinations** of those vectors.
*   **Formally**: **span(v₁, ..., vₖ) = {∑ᵢ₌₁ⁿ αᵢvᵢ : αᵢ ∈ R}**.
*   **Insight**: The vectors in the set defining the span may or may not be linearly independent.
*   **Exercise**: The span of a set of vectors is always a subspace.