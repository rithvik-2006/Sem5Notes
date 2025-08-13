Here are detailed lecture notes for Lecture 9, drawing from the provided sources:

---

## Lecture 9: Extreme Points and Duality Theorem

This lecture covers two main topics: completing the characterisation of extreme points from Lecture 8 by proving the second part of Theorem 1, and introducing the fundamental Duality Theorem in Linear Programming.

### 1. Extreme Points (Continuation from Lecture 8)

Recall from Lecture 8 that we introduced the concept of **extreme points** as the "corners" of a convex set, particularly in the context of the feasible region defined by linear inequalities, Ax ≤ b.

We also established **Theorem 1**: Given a convex set Ax ≤ b in n-dimensional space satisfying certain assumptions (boundedness, no degeneracies, full dimensionality), the extreme points of this set are **precisely those points in Ax ≤ b which can be expressed as an intersection of n linearly independent hyperplanes** from the set of hyperplanes that define Ax ≤ b.

Lecture 8 provided the proof for **Part 1**: showing that any point formed by the intersection of n linearly independent hyperplanes is an extreme point. This lecture completes the proof of Theorem 1 by addressing **Part 2**.

#### Proof of Theorem 1 (Part 2)

**Part 2: Proving that every extreme point can be expressed as an intersection of n linearly independent hyperplanes.**
The goal here is to show the converse: if x0 is an extreme point of the convex set Ax ≤ b, then the set of inequalities that are active (satisfied as equalities) at x0 must correspond to n linearly independent hyperplanes. The proof strategy for this part is by **contradiction**, specifically by proving the contrapositive.

1.  Let x0 be an extreme point in the set {x : Ax ≤ b}.
2.  We classify the inequalities at x0 into two sets:
    *   **A'x0 = b'**: Inequalities that are satisfied as equalities at x0.
    *   **A''x0 < b''**: Inequalities that are satisfied as strict inequalities at x0.
3.  **Assume for contradiction** that x0, an extreme point, **cannot** be expressed as an intersection of n linearly independent hyperplanes.
4.  This assumption implies that the matrix A' (formed by the coefficients of the active inequalities) has a **rank strictly less than n**.
5.  A direct consequence of A' having rank less than n is that the system of homogeneous equations **A'x = 0 will have a non-zero solution**. Let's call such a non-zero solution **x_vec** (denoted as 'x0' in the source, which can be confusing but refers to a direction vector here).
6.  Since A''x0 < b'' (the strict inequalities), it means there is some "slack" or "wiggle room" around x0. We can find a sufficiently small positive value **ε** such that any point x within a small sphere of radius ε around x0 will still satisfy A''x < b''. This means if we move a small amount in any direction, the strictly satisfied inequalities will remain satisfied.
7.  Now, consider two points: **x0 + εx_vec** and **x0 - εx_vec**.
    *   Applying A' to these points:
        *   A'(x0 + εx_vec) = A'x0 + εA'x_vec = b' + ε(0) = b'.
        *   A'(x0 - εx_vec) = A'x0 - εA'x_vec = b' - ε(0) = b'.
        This means both x0 + εx_vec and x0 - εx_vec satisfy the active inequalities as equalities.
    *   For a sufficiently small ε, both x0 + εx_vec and x0 - εx_vec will also satisfy the strict inequalities (A''x < b'') because x0 does and the points are close to x0.
    *   Therefore, both **x0 + εx_vec** and **x0 - εx_vec are points within the original convex set {x : Ax ≤ b}**.
8.  Finally, we can express x0 as a convex combination of these two points:
    **x0 = (1/2)(x0 + εx_vec) + (1/2)(x0 - εx_vec)**
9.  Since x_vec is a non-zero vector, x0 + εx_vec and x0 - εx_vec are two **distinct** points.
10. This contradicts the definition of an extreme point, which states that an extreme point cannot be represented as a convex combination of any two distinct points within the same convex set.
11. Thus, our initial assumption (that A' has rank strictly less than n) must be false. Therefore, A' must have **n linearly independent rows**, meaning x0 is indeed the intersection of n linearly independent hyperplanes.

### 2. Convex Hull of Extreme Points

A **convex hull** of a set of points (p1, ..., pn) is defined as the **smallest convex set containing these points**. Equivalently, it is the set of all points that can be expressed as a **convex combination** of these points: {Σiλipi; Σiλi = 1; 0 ≤ λi ≤ 1}.

The lecture then presents a crucial theorem regarding the relationship between any point in a bounded convex set (Ax ≤ b) and its extreme points.

#### Theorem 1: Every point in a convex set can be expressed as a convex combination of its extreme points

Let p1, p2, ..., pt be the extreme points of the convex set S = {x : Ax ≤ b}. Then any point x0 within S can be represented as a convex combination of these extreme points: x0 = Σiλipi, where Σiλi = 1 and 0 ≤ λi ≤ 1.

**Proof (by induction on the dimension of the object)**
This proof applies an inductive approach, building from lower-dimensional cases.

1.  **Base Case**: When the dimension of the object {x : Ax ≤ b} is zero (a single point) or one (a line segment), the theorem is trivially true. For a single point, it is its own extreme point. For a line segment, any point on it is a convex combination of its two extreme points (endpoints).

2.  **Inductive Step**: Assume the theorem holds for all convex sets of dimension less than n. Now consider an n-dimensional convex set S = {x : Ax ≤ b} and an arbitrary point **p ∈ S**.
    *   For simplicity, assume p is in the interior, meaning all inequalities are strict (Ap < b).
    *   Take any extreme point **p1** of S. Draw a line segment from p1, passing through p, and extend it until it intersects the boundary of S at a point **q**. Such a point q must exist because the set is bounded.
    *   Since p lies on the line segment connecting p1 and q, p can be expressed as a convex combination of p1 and q: **p = γp1 + (1 − γ)q** for some 0 ≤ γ ≤ 1.
    *   The point **q** lies on the boundary, meaning at least one inequality becomes an equality at q. Let's assume, for simplicity, that the first inequality becomes tight: A1q = b1, while others remain strict (A''q < b'').
    *   This implies that q belongs to the intersection of the set {x : Ax ≤ b} with the hyperplane {x : A1x = b1}. This intersection defines a **new convex set, S0**, which has a dimension of (n-1) or less.
    *   The set S0 can be redefined by substituting one variable using the equality A1x = b1 into the remaining inequalities, resulting in a new set of inequalities in (n-1) variables, say {x : Cx ≤ d}.
    *   By the **inductive hypothesis**, since S0 is a convex set of smaller dimension, q can be expressed as a convex combination of the extreme points of S0. Let these extreme points be q1, q2, ..., q_t0: **q = Σ_i=1^t0 δiqi** where Σδi = 1 and 0 ≤ δi ≤ 1.
    *   **Crucial Sub-proof**: It must be shown that the **extreme points of S0 are also extreme points of S**.
        *   Assume for contradiction that p0 is an extreme point of S0 but not of S.
        *   If p0 is not extreme in S, then p0 = λp1 + (1 − λ)p2 for some distinct p1, p2 ∈ S and 0 < λ < 1.
        *   Since p0 ∈ S0, A1p0 = b1. Substituting the convex combination:
            b1 = A1p0 = λA1p1 + (1 − λ)A1p2.
        *   Because p1, p2 ∈ S, they satisfy A1p1 ≤ b1 and A1p2 ≤ b1.
        *   The equality b1 = λA1p1 + (1 − λ)A1p2 can only hold if **A1p1 = b1 and A1p2 = b1**.
        *   This means p1 and p2 must also belong to S0.
        *   Therefore, p0 is a convex combination of two distinct points (p1, p2) within S0, which contradicts the assumption that p0 is an extreme point of S0.
        *   Hence, every extreme point of S0 is also an extreme point of S.
    *   Substituting the convex combination of q back into the expression for p:
        **p = γp1 + (1 − γ) (Σ_i=1^t0 δiqi)**
        This simplifies to p being a convex combination of p1 and q1, ..., q_t0. All these points (p1 and q_i's) are extreme points of the original set S.
    *   The sum of coefficients is γ + (1 − γ)Σδi = γ + (1 − γ)(1) = 1.
    *   Thus, any point in S can be expressed as a convex combination of the extreme points of S.

#### Maximizing a Linear Function on a Convex Set

A direct and powerful consequence of the previous theorem is a method for finding the maximum of a linear function over a convex set.

**Theorem 2: A linear function on a convex set is maximised at an extreme point.**
Let f be a linear function (f(x) = cᵀx) over a convex set S = {x : Ax ≤ b}. If f attains a maximum value on S, it will do so at one or more of the extreme points of S.

**Proof**:
1.  Let p be a point in S where the linear function f attains its maximum value, f(p).
2.  From Theorem 1 (Convex Hull of Extreme Points), we know that p can be expressed as a convex combination of the extreme points of S (p1, ..., pt): **p = Σ_i=1^t λipi**, where Σλi = 1 and 0 ≤ λi ≤ 1.
3.  Since f is a linear function, the value of f at p is the same convex combination of the values of f at the extreme points: **f(p) = Σ_i=1^t λif(pi)**.
4.  Assume, for the sake of contradiction, that f(p) is strictly greater than the value of f at all extreme points (f(p) > f(pi) for all i).
5.  If this were true, then the weighted average Σλif(pi) would necessarily be less than f(p) (because each f(pi) is less than f(p), and all λi ≥ 0, Σλi = 1).
6.  This contradicts the equality f(p) = Σλif(pi). Therefore, our assumption must be false.
7.  It must be that for at least one extreme point pi, **f(pi) = f(p)**. This shows that the maximum value of the linear function is indeed attained at an extreme point.

This theorem is fundamental because it implies that for linear optimization problems, instead of searching over an infinite feasible region, we only need to check the finite number of extreme points. An algorithm could, in principle, examine all combinations of n rows from A, solve for x, check feasibility, and calculate cTx to find the optimum. This forms the basis for algorithms like the Simplex Method (introduced later in Lecture 11).

### 3. Duality Theorem

The Duality Theorem is a cornerstone of Linear Programming, establishing a powerful relationship between a primal linear program (LP) and its corresponding dual LP.

**Theorem 1 (Duality Theorem)**
If a primal linear program is feasible and has a finite optimum solution, then its dual linear program is also feasible, has a finite optimum solution, and **their optimum values must be equal**.

**Proof**:
1.  **Dual Feasibility**: We need to show that if the primal has a finite optimum, then there exists a vector y that satisfies the dual constraints (Aᵀy = c and y ≥ 0).
    *   At the optimal point x0 of the primal LP, the cost vector **c can be written as a non-negative linear combination of the normals (rows of A) of the hyperplanes that define x0**. These defining hyperplanes form the matrix A' (from A'x0 = b').
    *   This non-negative linear combination of the rows of A' provides the coefficients (yᵢ values) for a feasible solution to the dual problem. That is, cᵀ = (y1, y2, ..., yn)A' where yᵢ ≥ 0, which can be extended to all m rows of A as cᵀ = ΣᵢyᵢAᵢ with yᵢ = 0 for non-defining hyperplanes.
    *   Since the primal has an optimal point x0, the set F (defined in Lecture 13 as points where the cost vector can be written as a non-negative linear combination of defining normals) is non-empty, thus the dual is feasible.

2.  **Dual has a Finite Optimum**: If the dual were unbounded, its objective function could go to negative infinity (for a minimisation problem).
    *   Let y be any feasible point in the dual. Let x0 be an optimal point in the primal.
    *   By the primal constraints, Ax0 ≤ b.
    *   Multiplying by yᵀ (which is non-negative), we get yᵀAx0 ≤ yᵀb.
    *   Since y satisfies the dual constraint Aᵀy = c (or yᵀA = cᵀ), we can substitute cᵀ for yᵀA: cᵀx0 ≤ yᵀb.
    *   This means that the dual cost yᵀb is an **upper bound** for the primal optimal cost cᵀx0.
    *   Since the primal has a finite optimum, the dual's objective function (yᵀb) is bounded below by cᵀx0. Therefore, the dual must have a finite optimum as well.

3.  **Optimum Values Coincide**:
    *   From the proof of dual feasibility, we know that at the primal optimal point x0, we can construct a dual feasible solution y0 such that cᵀx0 = y0ᵀb.
    *   Since y0 is a feasible solution for the dual and its cost equals the (lower-bounded) primal optimal cost, y0 must be the optimal solution for the dual.
    *   Therefore, the optimum values of the primal and dual are equal.

The Duality Theorem implies a crucial relationship between the behavior of the primal and dual LPs:
*   If P (primal) is feasible and has a finite maximum, then D (dual) is feasible and the two optimum values coincide.
*   If P is infeasible and D is feasible, then D is unbounded.
*   If P is feasible and unbounded, then D is infeasible.

### 4. The Dual of the Dual is the Primal

A significant property of duality is that taking the dual of the dual LP brings you back to the original primal LP.

To demonstrate this, one converts the dual problem into the standard primal format (maximisation with '≤' constraints) and then applies the dualisation rules.

Consider the general dual LP:
**Minimize:** yᵀb
**Subject to:** Aᵀy = c
y ≥ 0

1.  **Rephrase the dual:** To make it look like a "primal" for dualising purposes, we convert it to a maximisation problem by negating the objective function: `max -bᵀy`.
2.  **Handle equalities:** The equality constraint Aᵀy = c can be written as two inequalities: Aᵀy ≤ c and Aᵀy ≥ c. The latter can be rewritten as -Aᵀy ≤ -c.
3.  **Introduce dual variables:** When dualising, each constraint in the new "primal" corresponds to a variable in its dual.
    *   The variables corresponding to the inequalities (Aᵀy ≤ c and -Aᵀy ≤ -c) will be unconstrained in sign. If we let x be the vector of dual variables corresponding to these constraints, then the constraint Aᵀy = c in the primal implies that the corresponding dual variables (xᵢ) are **not sign-constrained**.
    *   The variables corresponding to the `y ≥ 0` inequality constraints will be sign-constrained (`z ≥ 0`).
4.  **Form the dual of the dual:** This process yields:
    **Maximize:** cᵀx
    **Subject to:** Ax + z = b
    z ≥ 0
    This can be simplified by substituting z = b - Ax, which, combined with z ≥ 0, becomes **Ax ≤ b**.
    Thus, the dual of the dual problem is indeed the original primal problem:
    **Maximize:** cᵀx
    **Subject to:** Ax ≤ b

This confirms the symmetric nature of the primal-dual relationship in linear programming.