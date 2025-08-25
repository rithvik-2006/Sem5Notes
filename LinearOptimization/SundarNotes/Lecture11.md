Here are detailed revision notes on Lecture 11, focusing on the Simplex Algorithm, drawing from the provided sources:

**Lecture 11: The Simplex Algorithm**

The Simplex Algorithm is designed to solve **Linear Programming (LP) problems** by finding an extreme point where the cost function is maximised amongst all extreme points of the feasible region. The algorithm operates by iteratively moving between extreme points. It does not necessarily visit all extreme points but is guaranteed to find the optimum upon termination.

**Core Algorithm Steps:**
1.  **Start at an extreme point**.
2.  **Move to a neighbouring extreme point of greater cost** if one exists, and repeat this step.
3.  **If no such neighbour exists, then exit** with the current point as the optimum.

**Key Questions Addressed by the Lecture:**
The lecture sets out to answer four main questions regarding the Simplex Algorithm:
1.  **How to identify the first extreme point?** (This is left as an exercise).
2.  **What constitutes "neighbouring extreme points," and how are they found?**.
3.  **Is the algorithm correct?** That is, does it guarantee an optimum upon termination?.
4.  **What is the worst-case number of iterations** before the algorithm stops?.

---

### 1. The Notion of Directions: Understanding Neighbouring Extreme Points

**Geometric Intuition:**
*   In a **2-dimensional space**, an extreme point is the intersection of boundary lines. Its neighbours are found along specific directions from this intersection.
*   For a **3-dimensional cube**, the neighbours of any corner are the three corners connected by edges meeting at that point. Each edge is formed by the intersection of two of the three planes that define the corner.

**Generalisation to n Dimensions:**
*   In a linear optimization problem with constraints `Ax ≤ b` and objective `cᵀx`, an extreme point `x0` is defined by a set of `n` linearly independent active constraints (equalities).
*   Let `A'` be the matrix formed by these `n` linearly independent rows of `A`, and `b'` be the corresponding entries from `b`. Then `x0` satisfies `A'x0 = b'`.
*   The remaining inequalities form `A''`, where `A''x0 < b''`.
*   The equalities `A'x0 = b'` constitute the **support** of the extreme point.

**Determining Neighbours of `x0`:**
*   Neighbouring extreme points of `x0` **share `n - 1` hyperplanes** in their support with `x0`.
*   To find a neighbour:
    1.  **Remove one hyperplane** (row) from `A'`.
    2.  **Add one hyperplane** from `A''`.
    3.  Check if the new set of `n` hyperplanes defines a feasible point.
*   Under the course's assumptions, for each hyperplane removed from `A'`, there is exactly one hyperplane from `A''` that, when added, results in a feasible neighbouring point.
*   A naive approach using Gaussian elimination for each combination (`O(mn)` operations) is slow; a faster method is desired.

**Direction Vectors for Faster Neighbour Identification:**
*   There are `n` "rays" or **direction vectors** emanating from `x0` that point towards its neighbours. The goal is to determine these vectors rapidly.
*   Consider a line `li` from `x0` to a neighbour `xi`. This line is formed by `n-1` of the `n` defining hyperplanes of `x0` holding as equalities, while the `i`-th hyperplane is relaxed (becomes a strict inequality for points moving away from `x0`):
    *   `A'jxj = b'j` for `1 ≤ j ≤ n, j ≠ i`.
    *   `A'ixi < b'i` (for `x` on the line beyond `x0`).
*   The direction vector is `xi - x0`.
*   When evaluating `A'(xi - x0)`:
    *   For `j ≠ i`, `A'j(xi - x0) = 0` because `A'jxi = A'jx0 = b'j`.
    *   For `j = i`, `A'i(xi - x0) < 0` because `A'ixi < b'i` and `A'ix0 = b'i`.
*   By choosing `xi` appropriately, we can standardise `A'(xi - x0) = -ei`, where `-ei` is a vector with `0`s everywhere except for a `-1` in the `i`-th position.
*   Let `Z` be a matrix whose columns are these `n` direction vectors `(x1 - x0), ..., (xn - x0)`. Then, `A'Z = -I`.
*   **Theorem 1:** The **direction vectors are the columns of the negative of the inverse of matrix `A'`**. Finding these vectors thus involves computing `-(A')^-1`.

---

### 2. Finding Neighbouring Points with Greater Cost

Once direction vectors are known, the algorithm needs to identify which direction leads to a neighbour with a higher cost.

**Cost Increase Along a Direction:**
*   If a neighbour `xi` has a greater cost than `x0` (i.e., `cᵀxi > cᵀx0`), then **any point `x'` on the line segment** between `x0` and `xi` will also have a greater cost than `x0`.
*   This is proven by the linearity of the cost function: If `x' = λxi + (1 - λ)x0` for `λ > 0`, then `cᵀx' = λcᵀxi + (1 - λ)cᵀx0`. Rearranging gives `cᵀx' = λ(cᵀxi - cᵀx0) + cᵀx0`. Since `cᵀxi - cᵀx0 > 0` and `λ > 0`, it follows that `cᵀx' > cᵀx0`.
*   Therefore, to determine if a direction increases cost, we simply **check the sign of `cᵀ(xi - x0)`**.

**Finding the New Neighbouring Point:**
*   Once a direction vector `vi` (a column of `-(A')^-1`) is chosen because `cᵀvi > 0`, we need to find the actual neighbour along this direction.
*   A point `x'` along this direction can be expressed as `x' = x0 + t*vi`, where `t ≥ 0`.
*   We need to find the **maximum `t`** such that `x'` remains feasible (i.e., `A(x0 + t*vi) ≤ b`).
*   The point `x'` already satisfies most of the `A'` equalities. Thus, we only need to check the remaining **inactive constraints in `A''`** (`A''x0 < b''`).
*   As `t` increases, `x'` moves away from `x0`. The feasible region is left when one of the inequalities in `A''` becomes an equality.
*   To find this `t`, we calculate `t` for each constraint `s` in `A''` that `vi` approaches: `tk = (bs - Asx0) / (Asvi)`.
*   We take the **minimum positive `t`** across all such constraints. This `t` value, `t = min(tk)`, gives the new neighbouring extreme point `x_new = x0 + t*vi`.
*   **Important Note:** Only rows `s` from `A''` where `Asvi > 0` are considered. If `Asvi < 0`, moving in direction `vi` would take `x'` *away* from the hyperplane `Asx = bs`, meaning the inequality `Asx ≤ bs` would remain satisfied or become even more strict, so it would not limit `t`.