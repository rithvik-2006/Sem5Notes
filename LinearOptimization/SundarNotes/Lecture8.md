Here are detailed lecture notes on Lecture 8: Extreme Points, drawing from the provided sources:

## Lecture 8: Extreme Points

This lecture introduces the concept of **extreme points** within convex sets, particularly in the context of linear optimization problems where the feasible region is defined by linear inequalities (Ax ≤ b).

### 1. Convex Hull

A foundational concept for understanding extreme points is the **convex hull**.
*   **Definition**: Given a set of points p1, p2, ..., pn, their **convex hull is the smallest convex set containing these points**.
*   **Alternative Definition**: The convex hull of points p1, ..., pn can also be defined as the set of all points that can be expressed as a **convex combination** of these points. This is represented as {Σiλipi; Σiλi = 1; 0 ≤ λi ≤ 1}, where λi are the weights. This essentially means taking all possible weighted averages of the points.
    *   For two points, their convex hull is the line segment joining them.
    *   For three points, it forms all points within the triangle defined by them.

### 2. Assumptions on the Convex Set Ax ≤ b

To simplify discussion throughout the course, certain assumptions are made regarding the nature of the convex set defined by Ax ≤ b, unless otherwise stated. These assumptions are often justified because slight perturbations of input typically maintain these properties.
*   **Assumption 1: Boundedness**: The set Ax ≤ b is **bounded**, meaning there exists a real number B such that for every point x satisfying Ax ≤ b, all its coordinates xi are less than or equal to B (xi ≤ B).
*   **Assumption 2: No Degeneracies**: The set has **no degeneracies**. This implies that in an n-dimensional space, **not more than n hyperplanes pass through a single point**.
*   **Assumption 3: Full Dimensionality**: The set is **full dimensional**. This means it is possible to place an n-dimensional sphere, no matter how small, entirely within the region defined by Ax ≤ b. In two dimensions, this means the convex set has area; in three dimensions, it has volume; and in n dimensions, it has n-dimensional volume.

### 3. Extreme Points and Their Algebraic Interpretation

When considering objects like polygons in a plane or cubes in three dimensions, the **vertices or corners are special points**. It has been observed that when maximizing a linear function (cTx) over a convex body, the maximum value will occur at the **boundary**, and more specifically, at one of these **corners**. This lecture aims to rigorously prove this intuition.

*   **Definition**: An **extreme point** in a convex set is defined as **a point that cannot be represented as a convex combination of any two distinct points within the same convex set**. In simpler terms, an extreme point does not lie on the line segment connecting two other distinct points of the convex set.

*   **Theorem 1: Characterisation of Extreme Points**: Given a convex set Ax ≤ b in n-dimensional space that satisfies the assumptions mentioned in Section 1, the **extreme points of this convex set are precisely those points within Ax ≤ b that can be expressed as an intersection of n linearly independent hyperplanes** from the set of hyperplanes that define Ax ≤ b.

#### Proof of Theorem 1 (Part 1)

**Part 1: Proving that an intersection of n linearly independent hyperplanes is an extreme point**.
1.  Let x0 be a point that is the **intersection of n linearly independent hyperplanes** that define the convex set Ax ≤ b.
2.  The inequalities satisfied by x0 can be split into two groups:
    *   **A'x0 = b'**: Inequalities that are satisfied as equalities at x0.
    *   **A''x0 < b''**: Inequalities that are satisfied as strict inequalities at x0.
3.  Since x0 is the intersection of n linearly independent hyperplanes, the matrix A' (formed by the coefficients of these equalities) has **n linearly independent rows**. This means that **x0 is the unique solution** to the system of equations A'x = b'.
4.  Assume, for the sake of contradiction, that x0 can be expressed as a convex combination of two *distinct* points, x1 and x2, both within the given convex set. So, x0 = λx1 + (1 − λ)x2, where 0 < λ < 1.
5.  Applying the matrix A' to this convex combination:
    b' = A'x0
    = λA'x1 + (1 − λ)A'x2
6.  Since x1 and x2 are part of the convex set, they must satisfy all the original inequalities, including those in A'. Therefore, A'x1 ≤ b' and A'x2 ≤ b'.
7.  Combining these facts, we get:
    b' = λA'x1 + (1 − λ)A'x2 ≤ λb' + (1 − λ)b' = b'.
8.  The sequence of inequalities showing b' ≤ b' implies that the inequality must, in fact, be an **equality throughout**. This can only hold if **A'x1 = b' and A'x2 = b'**.
9.  Since x0 is the *only* solution to the system A'x = b', it follows directly that **x0 = x1 = x2**.
10. This contradicts our initial assumption that x1 and x2 were distinct points. Therefore, x0 cannot be expressed as a convex combination of two other distinct points in the convex set, proving that **x0 is an extreme point**.

*   **Illustrative Analogy for the Proof Step**: The proof's critical step (b' = λA'x1 + (1 − λ)A'x2 ≤ b') can be understood with an analogy:
    *   Suppose the average age of students in a class is 21. If you are also told that no student is older than 21, you can infer that **every student's age must be exactly 21**.
    *   This logic extends to weighted averages and multiple criteria (e.g., average height is 5 and average age is 21, with no student taller than 5 or older than 21, then all students must be exactly 5 tall and 21 years old).
    *   Similarly, if a vector x0 is a weighted average of x1 and x2, and a linear function (like A') applied to x0 equals a value (b') which is also the maximum possible value for A' applied to x1 or x2, then A' applied to x1 and x2 must also equal b'.

#### Proof of Theorem 1 (Part 2)

**Part 2: Proving that every extreme point can be expressed as an intersection of n linearly independent hyperplanes**.
*   This part of the proof aims to show the converse: if x0 is an extreme point, then A' (the matrix of equalities satisfied by x0) must have n linearly independent rows.
*   The lecture notes indicate that this part of the proof is typically done by **contradiction** (i.e., proving the contrapositive).
*   The detailed proof for Part 2 is explicitly **deferred to Lecture 9**.