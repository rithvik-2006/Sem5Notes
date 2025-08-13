Here are detailed revision notes on Lecture 10, drawing on the provided sources:

Lecture 10 focuses on proving that **any point within a convex set defined by linear inequalities can be expressed as a convex combination of its extreme points**. This lecture also establishes that **a linear function maximised over such a convex set will attain its maximum at one of these extreme points**. These findings are crucial for developing algorithms for Linear Programming (LP) problems, such as the Simplex Algorithm.

### Theorem: Convex Hull of Extreme Points

**Theorem 1**: Let $p_1, p_2, \ldots, p_t$ be the extreme points of the convex set $S = \{x : Ax \le b\}$. Then **every point in $S$ can be represented as a convex combination of these extreme points**: $\sum_{i=1}^{t} \lambda_i p_i$, where $\sum_{i=1}^{t} \lambda_i = 1$ and $0 \le \lambda_i \le 1$.

**Proof Outline (by Induction on Dimension)**:

1.  **Base Case**: The proof begins with a base case where the dimension of the object $\{x : Ax \le b\}$ is zero, which is considered trivial. (Lecture 9 also suggests an exercise for dimensions 0 and 1).

2.  **Inductive Step**:
    *   Consider a convex set $S = \{x : Ax \le b\}$ in $n$-dimensions.
    *   Let $p$ be any point in $S$. For simplicity, assume all inequalities $Ap < b$ are strict for $p$.
    *   **Construction of a Boundary Point**: Join an extreme point $p_1$ to $p$ and extend this line segment until it intersects the boundary of $S$ at a point, say $q$.
        *   The line segment between $p_1$ and $p$ must lie within the set due to convexity.
        *   Such a point $q$ must exist because the convex set is assumed to be bounded.
        *   Being a boundary point means at least one inequality becomes an equality at $q$ (e.g., $A_1q = b_1$). The remaining inequalities are strict ($A''q < b''$).
    *   **Reduction to Lower Dimension**: The object defined by $A_1x = b_1$ is an $(n-1)$-dimensional hyperplane.
        *   The intersection of this hyperplane with the original convex set forms a new convex set $S'$ of a smaller dimension (e.g., $n-1$).
        *   By solving for one variable (say $x_i$ where $A_{1i} \ne 0$) from the equality $A_1x=b_1$ and substituting it into the remaining inequalities ($A''x < b''$), a new set of inequalities in one less variable is obtained. This new set defines $S'$.
    *   **Applying Induction Hypothesis**: Point $q$ lies in this new, lower-dimensional convex set $S'$. By the induction hypothesis, $q$ can be written as a convex combination of the extreme points of $S'$. Let these extreme points be $q_1, q_2, \ldots, q_{t'}$. So, $q = \sum_{i=1}^{t'} \lambda'_i q_i$.
    *   **Relating Extreme Points**: It is necessary to show that the extreme points of $S'$ are also extreme points of the original set $S$.
        *   Assume, for contradiction, that $p'$ is an extreme point of $S'$ but not of $S$.
        *   If $p'$ is not extreme in $S$, it can be expressed as $p' = \mu p'_1 + (1-\mu) p'_2$ for distinct $p'_1, p'_2 \in S$ and $0 < \mu < 1$.
        *   Since $p' \in S'$, it satisfies $A_1p' = b_1$.
        *   Using the linearity of $A_1$ and the fact that $p'_1, p'_2 \in S$ (so $A_1p'_1 \le b_1$ and $A_1p'_2 \le b_1$), it can be shown that $A_1p'_1 = b_1$ and $A_1p'_2 = b_1$. This means $p'_1$ and $p'_2$ must also be in $S'$.
        *   This contradicts the assumption that $p'$ is an extreme point of $S'$, because it can be expressed as a convex combination of two other points within $S'$. Therefore, extreme points of $S'$ must also be extreme points of $S$.
    *   **Final Combination**: Since $p$ lies on the segment joining $p_1$ and $q$, $p$ can be expressed as a convex combination of $p_1$ and $q$ (e.g., $p = \alpha p_1 + (1-\alpha)q$).
        *   By substituting the convex combination for $q$, $p$ can then be expressed as a convex combination of $p_1$ and the extreme points of $S'$ (which are also extreme points of $S$). This shows that $p$ can be written as a convex combination of the extreme points of $S$.

### Theorem: Maximisation of Linear Functions

**Theorem 2**: A linear function on $S = \{x : Ax \le b\}$ is **maximised at an extreme point**.

**Proof**:
*   Let $f$ be a linear function, and suppose it attains its maximum value at a point $p \in S$.
*   From Theorem 1 (above), $p$ can be written as a convex combination of the extreme points of $S$: $p = \sum_{i=1}^{t} \lambda_i p_i$, where $p_i$ are extreme points and $\lambda_i$ are non-negative weights summing to 1.
*   Since $f$ is a linear function, $f(p) = f(\sum_{i=1}^{t} \lambda_i p_i) = \sum_{i=1}^{t} \lambda_i f(p_i)$. (This is a property of linear functions: the value at a convex combination is the weighted average of the values at the constituent points).
*   If all $f(p_i)$ were strictly smaller than $f(p)$, then their weighted average $\sum \lambda_i f(p_i)$ could not equal $f(p)$.
*   Therefore, for at least one extreme point $p_i$, $f(p_i)$ must be equal to $f(p)$. This means that the maximum value of the function is attained at an extreme point.

### Implications for Algorithm Design

These theorems provide a **finite algorithm for solving Linear Programming problems**. Since the maximum of a linear function over a convex set defined by linear inequalities occurs at an extreme point, one can theoretically find the optimum by:

1.  **Identifying Extreme Points**: An extreme point is defined by the intersection of $n$ linearly independent hyperplanes (equalities) out of the given constraints.
2.  **Brute-Force Approach**:
    *   Examine all combinations of $n$ rows from the matrix $A$ (there are $\binom{m}{n}$ such combinations, where $m$ is the number of constraints and $n$ is the number of variables).
    *   For each combination, solve the system of $n$ linear equations ($A'x_0 = b'$) using Gaussian Elimination to find a candidate point $x_0$.
    *   **Verify Feasibility**: Check if this candidate solution $x_0$ satisfies *all* other inequalities in the original system ($A''x_0 \le b''$). This verification step is important because not all intersections of $n$ hyperplanes define feasible points within the specified convex set.
    *   **Calculate Cost**: If $x_0$ is feasible, calculate the objective function value $c^Tx_0$.
3.  **Determine Maximum**: The maximum among all calculated $c^Tx_0$ values from feasible extreme points will be the optimal solution.

This brute-force method, while theoretically correct, can be computationally expensive due to the combinatorial explosion of $\binom{m}{n}$ possibilities. The Simplex Algorithm, discussed in subsequent lectures, provides a more efficient approach by moving iteratively between "neighbouring" extreme points while improving the cost.