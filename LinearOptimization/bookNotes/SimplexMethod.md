Here are detailed revision notes for Chapter 3 on "The Simplex Method":

### 3 The Simplex Method

### 3.1 Introduction
The simplex method is a **fundamental and well-known algorithm** used to solve linear programming (LP) problems. It was conceptualised by Dantzig (1948) and remains a powerful class of methods, often serving as the primary strategy in commercial software for solving LPs.

The core strategy of the simplex method is to **systematically explore the extreme points** of an LP's feasible region to identify the optimal extreme point. This is based on the **Fundamental Theorem of Linear Programming**, which states that if an LP has a finite optimal solution, it can be found at an extreme point (and thus, a basic feasible solution). In practice, the simplex method typically does not need to explore all possible extreme points.

The high-level steps of the simplex method are:
*   **Step 0 (Initialization):** Generate an initial **basic feasible solution (BFS)**.
*   **Step 1 (Optimality Check):** Determine if the current BFS is optimal. If it is, the method stops. If not, proceed to Step 2.
*   **Step 2 (Unboundedness Check):** Check if the LP is unbounded. If it is, the method stops. If not, proceed to Step 3.
*   **Step 3 (Improvement):** Generate another BFS that has an **objective function value that is better or no worse** than the current one.
*   Repeat from Step 1 until an optimal BFS is found or unboundedness is detected.

The simplex method requires the linear program to be in **standard form**.

### 3.1.1 Example of Simplex Method
Consider the LP: `minimize -x1 - x2 subject to x1 <= 1, x2 <= 1, x1, x2 >= 0`.
In standard form, by adding slack variables x3 and x4, it becomes: `minimize -x1 - x2 subject to x1 + x3 = 1, x2 + x4 = 1, x1, x2, x3, x4 >= 0`.

The method iterates through basic feasible solutions (which correspond to extreme points). For instance, a possible sequence of iterations could be:
1.  **Initial BFS (v(0)):** `x1=0, x2=0, x3=1, x4=1`. This is determined to be suboptimal.
2.  **Iteration 2 (v(1)):** A new BFS, `x1=0, x2=1, x3=1, x4=0`, is generated, which is also suboptimal.
3.  **Iteration 3 (v(3)):** Another BFS, `x1=1, x2=1, x3=0, x4=0`, is generated. This is found to be optimal, and the method terminates.
The simplex method can have multiple choices for the next BFS to move to.

### 3.1.2 Adjacent Basic Feasible Solutions
In the simplex method, movement is restricted to **neighbouring or "adjacent" basic feasible solutions**.
**Two different basic feasible solutions (x and y) are considered adjacent if they share exactly `m-1` basic variables in common**, where `m` is the number of equality constraints in the standard form. Graphically, adjacent extreme points are connected by an edge (boundary) of the feasible set, allowing direct movement along this edge.

### 3.2 Simplex Method Development
To fully describe the simplex method, efficient tests for optimality and unboundedness are needed, along with detailed procedures for generating new, improved adjacent BFS.

### 3.2.1 Checking Optimality of a Basic Feasible Solution
For an LP in standard form (`minimize cTx subject to Ax = b, x >= 0`), the optimality of a current BFS `x*` is determined by examining its **reduced costs**.
*   The problem is expressed by partitioning variables into **basic (`xB`) and non-basic (`xN`)** components, along with corresponding partitions of the constraint matrix (`A = [B|N]`) and cost vector (`c = [cB|cN]`).
*   The **reduced cost vector (`rN`)** is calculated as `rN = (cTN - cTBB-1N)`. Each component of `rN` is associated with a non-basic variable.
*   **Optimality Check:**
    *   **Case 1 (Optimal):** If `rq >= 0` for all non-basic variables `xq` (i.e., for all `q` in the set of non-basic indices `N`), then `x*` is an **optimal solution**.
    *   **Case 2 (Suboptimal):** If there is at least one non-basic variable `xq` with `rq < 0`, then `x*` is **not optimal**.

### 3.2.2 Moving to an Improved Adjacent Basic Feasible Solution
If `x*` is not optimal (i.e., has a negative reduced cost), the simplex method can move to an improved adjacent BFS, `x_new`, such that its objective function value is lower (`cTx_new < cTx_current`).
*   The movement is represented as `x_new = x_current + alpha * d`, where `d` is a **search direction** and `alpha >= 0` is a **step length**.
*   To maintain adjacency, one non-basic variable (`xq`) is chosen to **enter the basis** (becomes positive), and one basic variable (`xl`) **leaves the basis** (becomes zero).
*   The search direction `dq` is derived from the constraint equation `xB = B-1b - B-1NxN`, where `xq` is the chosen entering non-basic variable. The direction `dq` is `[ -B-1Nq ; eq ]`, where `eq` is a vector with a `1` at the position corresponding to `xq` and zeros elsewhere.
*   The **objective function improves (decreases)** along `dq` if the associated reduced cost `rq` is negative (`cT d = rq`). This `dq` is called a **descent direction**.
*   The feasibility of `x_new` requires `Ax_new = b` (which is satisfied if `Adq = 0`) and `x_new >= 0`.
*   The **step length (`alpha`)** is determined by the **minimum ratio test**, calculated as `alpha = min(j in B) { -x_current_j / dq_j | dq_j < 0 }`. This test ensures that `x_new` remains non-negative and identifies the basic variable (`xj*`) that becomes zero first (leaves the basis).
*   If `dq >= 0` (all components of the direction vector are non-negative), the LP is **unbounded**. Otherwise, `x_new` is an adjacent BFS with a lower objective value.

### 3.2.3 Simplex Method (Detailed Steps)
1.  **Step 0 (Initialization):**
    *   Generate an initial BFS `x(0) = [xB; xN]`.
    *   Identify the basis matrix `B`, non-basis matrix `N`, corresponding cost vectors `cB`, `cN`, and index sets `B_set`, `N_set`.
    *   Set `k = 0`.
2.  **Step 1 (Optimality Check):**
    *   Compute **reduced costs** `rq = cq - cTBB-1Nq` for all `q` in `N_set`.
    *   If all `rq >= 0`, `x(k)` is optimal. **STOP**.
    *   Else, select one non-basic variable `xq` such that `rq < 0` to enter the basis.
3.  **Step 2 (Descent Direction Generation):**
    *   Construct `dq = [ -B-1Nq ; eq ]`.
    *   If `dq >= 0` (all components are non-negative), the LP is **unbounded**. **STOP**.
4.  **Step 3 (Step Length Generation):**
    *   Compute **step length `alpha`** using the **minimum ratio test**: `alpha = min(j in B_set) { -x_current_j / dq_j | dq_j < 0 }`.
    *   Identify `j*`, the index of the basic variable that achieves this minimum ratio.
5.  **Step 4 (Improved Adjacent BFS Computation):**
    *   Calculate the new BFS `x(k+1) = x(k) + alpha * dq`.
6.  **Step 5 (Basis Update):**
    *   The variable `xj*` (identified in Step 3) leaves the basis.
    *   The variable `xq` (selected in Step 1) enters the basis.
    *   Update `B`, `N`, `cB`, `cN`, `B_set`, `N_set` to reflect this change.
    *   Increment `k = k + 1` and return to Step 1.

### 3.2.4 Finite Termination under Non-Degeneracy
If all basic feasible solutions are **non-degenerate** (meaning all basic variables are strictly positive), then there is a **one-to-one correspondence between BFS and extreme points** of the LP. In this scenario, at each iteration, the simplex method generates a strictly monotonically improving sequence of objective function values, as `alpha` will always be positive. Since there is a finite number of BFS, the simplex method is guaranteed to **terminate in a finite number of steps** with an optimal solution or a conclusion of unboundedness.

### 3.3 Generating an Initial Basic Feasible Solution (Two-Phase and Big M Methods)
The simplex method requires an initial BFS to start. While sometimes this is straightforward (e.g., when slack variables readily form an identity submatrix for `B`), often it is not immediately clear.
In such cases, **artificial variables** can be introduced to create an initial identity submatrix, thereby facilitating the start of the simplex method.

### 3.3.1 The Two-Phase Method
This method addresses the need for an initial BFS by dividing the problem into two phases:
*   **Phase I (Auxiliary Problem):** An auxiliary LP is solved to find an initial BFS for the original problem.
    *   **Objective:** `minimize sum(xia)` (sum of all artificial variables).
    *   **Constraints:** Original constraints with artificial variables added to form an identity matrix.
    *   **Initial BFS for Phase I:** Set original variables to zero, and artificial variables to the right-hand side values.
    *   **Outcome of Phase I:**
        *   If the optimal sum of artificial variables (`sum(x*a)`) is **not zero**, the original LP is **infeasible**.
        *   If `sum(x*a) = 0`, then a BFS for the original problem has been found.
            *   **Subcase 1:** If all artificial variables are non-basic and zero in the optimal solution of Phase I, they are simply discarded, and the resulting BFS is used for Phase II.
            *   **Subcase 2:** If some artificial variables are basic but have a value of zero, strategies are employed to exchange them with non-artificial variables or identify redundant constraints.
*   **Phase II:** The original LP is solved using the BFS obtained from Phase I as its starting point.

### 3.3.2 Big M Method
The Big M method is an **alternative approach that combines both phases into a single optimisation problem**.
*   **Objective:** `minimize cTx + M * sum(xa)`.
    *   Artificial variables (`xa`) are added to the constraints to create an identity submatrix for an initial BFS, similar to Phase I.
    *   A **large positive parameter `M`** is multiplied by the sum of artificial variables in the objective function. This large penalty `M` aims to drive the artificial variables to zero in the optimal solution, effectively making them non-basic.
*   **Initial BFS:** Artificial variables are set as basic variables, with values from the right-hand side, and original variables are non-basic (zero).
*   **Outcome:**
    *   **Case 1 (Finite Optimal Solution):** If the Big M problem yields a finite optimal solution where `xa = 0`, then `x*` is an **optimal solution for the original LP**. If `xa != 0`, the original LP is **infeasible**.
    *   **Case 2 (Unbounded Below):** If the Big M problem is unbounded below:
        *   If `xa = 0` along the unbounded direction, the **original LP is also unbounded below**.
        *   If at least one artificial variable is non-zero, the **original problem is infeasible**.

### 3.4 Degeneracy and Cycling
**Degeneracy** occurs in a basic feasible solution when **at least one of its basic variables has a value of zero**. Geometrically, this means an extreme point is "over-determined" by more constraints than necessary.
*   When degeneracy is present, the minimum ratio test in the simplex method may yield a step length (`alpha`) of **zero**.
*   If `alpha = 0`, the new BFS `x_new` will be distinct from `x_current`, but it will correspond to the **same extreme point**. Crucially, the objective function value **does not improve** (`cTxd = cTx_new`).
*   In practice, degeneracy is common. The concern with degeneracy is that the simplex method might enter a **"cycle"** – repeatedly visiting a sequence of distinct BFS that all represent the same degenerate extreme point, without improving the objective function, and thus **never terminating**.

### 3.4.1 Anti-Cycling Rules (Bland's Rule and the Lexicographic Method)
To guarantee termination, specific rules for choosing the entering and leaving variables can be implemented to prevent cycling.

### 3.4.1.1 Bland's Rule
Bland's Rule, proposed by Bland (1977), ensures termination by:
1.  **Entering Variable:** From all non-basic variables with negative reduced costs, select the one with the **smallest index** to enter the basis.
2.  **Leaving Variable:** If there is a tie in the minimum ratio test (multiple basic variables yield the same minimum `alpha`), select the basic variable with the **smallest index** to leave the basis.
**Theorem:** If the simplex method uses Bland's Rule, it **will not cycle**.

### 3.4.1.2 Lexicographic (Perturbation) Method
This method, by Dantzig, Orden, and Wolfe (1955), aims to eliminate degeneracy by **perturbing the right-hand side values** of the LP's constraints with infinitesimally small positive constants.
*   The original `b` vector is replaced by `b + epsilon`, where `epsilon` is a vector of small positive constants (`0 < epsilon_m << ... << epsilon_2 << epsilon_1`).
*   This perturbation ensures that all basic variables will always have **strictly positive values**, thereby preventing degeneracy at any intermediate BFS.
*   The minimum ratio test will always have a **unique leaving variable** due to these distinct perturbed values.
*   Once the optimal solution for the perturbed problem is found, the **perturbation terms are dropped** to recover the optimal solution for the original problem.
*   **Theorem:** If the leaving variable is determined by the lexicographic method, the simplex method **will always terminate**.

### 3.5 Revised Simplex Method
The simplex method, at each iteration, requires calculating `B-1` (the inverse of the basis matrix) to compute reduced costs and search directions. Explicitly computing matrix inverses is numerically unstable and computationally undesirable.
The **revised simplex method** modifies the process by **solving equivalent linear systems of equations** rather than directly computing the inverse `B-1`.
*   To compute reduced costs: solve `BT * pi = cB` for `pi`, then `rN = cN - piT * N`.
*   To compute search direction: solve `B * d = -Nq` for `d`, then `dq = [d; eq]`.

### 3.5.1 Detailed Steps of the Revised Simplex Method
The steps are largely the same as the detailed simplex method, but with modifications in Steps 1 and 2 to avoid explicit `B-1` computation:
1.  **Step 0 (Initialization):** Same as Simplex Method.
2.  **Step 1 (Optimality Check):**
    *   **Solve `BT * pi = cB` for `pi`**.
    *   Compute `rq = cq - piT * Nq` for all `q` in `N_set`.
    *   If all `rq >= 0`, `x(k)` is optimal. **STOP**.
    *   Else, select one non-basic `xq` such that `rq < 0`.
3.  **Step 2 (Descent Direction Generation):**
    *   **Solve `B * d = -Nq` for `d`**.
    *   Construct `dq = [ d ; eq ]`.
    *   If `dq >= 0`, the LP is **unbounded**. **STOP**.
4.  **Steps 3, 4, 5:** Same as Simplex Method.

### 3.5.2 Advantages of the Revised Simplex Method
*   **Numerical Stability:** Avoids explicit calculation of `B-1`, which can lead to round-off and truncation errors.
*   **Computational Efficiency (Memory):** Requires substantially less computer memory, especially when the number of variables (`n`) is much larger than the number of constraints (`m`), and when `B` is large and sparse.
*   **Factorization Methods:** Performance is enhanced by using **triangular factorization methods** (e.g., LU decomposition) to solve the linear systems involving `B`. These methods efficiently update the factorization as the basis changes by one column, avoiding recalculating from scratch.

### 3.6 Complexity of the Simplex Method
The complexity of an algorithm refers to the time or resources needed to solve a problem. Algorithms can have **polynomial complexity** (time grows polynomially with problem size) or **exponential complexity** (time grows exponentially with problem size).
*   **Worst-Case Scenario (Klee-Minty Problems):** Klee and Minty (1972) demonstrated that for a specific class of LPs (Klee-Minty problems with `2m` variables and `m` constraints), the simplex method, following certain pivot rules (e.g., selecting the non-basic variable with the most negative reduced cost), can **visit all `C(2m, m)` possible bases**. This number **grows exponentially** with `m`, proving that the simplex method has **exponential worst-case complexity**. For example, a problem with `m=50` (100 variables) would take an impossibly long time (more than 3 trillion years at 1 billion iterations/second).
*   **Practical Performance:** Despite its exponential worst-case complexity, the simplex method **performs exceptionally well in practice**, typically requiring a small multiple of the number of constraints in most cases.