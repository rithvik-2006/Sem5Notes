Here are detailed revision notes on **Lecture 7: Maximising cTx Over a Convex Set**.

This lecture transitions from understanding the structure of solution sets to linear equations (`Ax = b`) to addressing the core problem of **Linear Optimization**: maximizing a linear function (`cTx`) subject to linear inequality constraints (`Ax ≤ b` and `x ≥ 0`).

### **1. Understanding the Feasible Region: Convex Sets**

*   **The Problem Formulation**: A linear optimization problem is typically formulated as `max cTx` subject to `Ax ≤ b`. The primary goal is to understand the set of all `x` that satisfy `Ax ≤ b`. This set is often referred to as the **feasible region**.
*   **Convexity of the Feasible Region**:
    *   The set ` {x : Ax ≤ b} ` is a **convex set**.
    *   **Definition of a Convex Set (recalled from previous lecture)**: A set `S` is convex if, for any two points `x1, x2` within `S`, any convex combination of `x1` and `x2` (i.e., `λx1 + (1 − λ)x2` where `0 ≤ λ ≤ 1`) also lies within `S`.
    *   **Proof that ` {x : Ax ≤ b} ` is Convex**: This follows from the property that the intersection of convex sets is also a convex set.
        *   Each individual inequality `Ajx ≤ bj` defines a **half-plane** (or half-space in higher dimensions). All points satisfying this inequality lie on one side of the hyperplane `Ajx = bj`. This set itself is convex; if you take any two points satisfying the inequality, their convex combination will also satisfy it.
        *   Since the feasible region `Ax ≤ b` is the **intersection** of all these individual convex half-spaces (one for each row `Aj` of `A`), it must also be a convex set.

### **2. Understanding the Objective Function: `cTx`**

*   **Linear Function Definition**: A function `f : R^n → R` is called **linear** if it satisfies two properties:
    1.  **Additivity**: `f(x + y) = f(x) + f(y)`.
    2.  **Homogeneity of Degree 1**: `f(αx) = αf(x)` for any real `α`.
*   **`cTx` as a Linear Function**: The function `gc(x) = cTx` is a linear function. This can be verified by checking the two properties of linearity.
*   **Geometric Interpretation of `cTx`**:
    *   In two dimensions (`c1x + c2y`), the equation `c1x + c2y = γ` (for any constant `γ`) represents a **line**. These lines are all parallel to `c1x + c2y = 0` (the line passing through the origin).
    *   The **value of the function `cTx` increases monotonically in a direction perpendicular to the lines `cTx = γ`** and decreases in the reverse direction.
    *   The **vector `c` itself is perpendicular to the hyperplane `cTx = 0`**. In fact, the value of `cTx` increases along the direction of `c` and decreases along `-c`. This means `c` points in the direction of maximum increase for the function `cTx`.

### **3. Maximizing a Linear Function over a Convex Set**

*   **Geometric Intuition for Maximization**: To maximize `cTx` over a convex set, one should **"keep moving along c"**. The **last point where `cTx` touches the convex set** will be the point of maxima.
    *   For a simple convex set like a unit sphere (`xTx ≤ 1`), the maximum value of `cTx` occurs where `cTx` is **tangent to the sphere**, in the direction of `c`.
    *   For a convex polygon in a plane, the maximum value is expected to occur at a **boundary point**, specifically at a **corner** (or vertex). This is a crucial insight for linear programming algorithms.
*   **Local Maxima vs. Global Maxima**:
    *   **Definition of Local Maxima**: A point `x0` in a set `S` is a local maximum for a function `f` if there exists a small neighbourhood `N` around `x0` where `f(x0) ≥ f(x)` for all `x` in `N`.
    *   **Theorem**: If `f` is a linear function over a convex set `S`, then a **local maximum is a global maximum**.
    *   **Proof Summary**: This proof relies on the properties of linear functions and convex sets.
        *   Assume `x0` is a local maximum and `y` is a global maximum, with `f(y) > f(x0)`.
        *   Consider a point `P` on the line segment connecting `x0` and `y`: `P = (1-ε)x0 + εy` for a small `ε > 0`. Since `S` is convex, `P` is also in `S`.
        *   Due to linearity, `f(P) = (1-ε)f(x0) + εf(y)`.
        *   Rearranging, `f(P) = f(x0) + ε(f(y) - f(x0))`.
        *   If `f(y) > f(x0)`, then `f(P)` would be strictly greater than `f(x0)`.
        *   However, if `ε` is chosen small enough, `P` lies within the neighbourhood `N` where `x0` is a local maximum, meaning `f(x0) ≥ f(P)`. This creates a contradiction unless `f(y) - f(x0)` is not positive, i.e., `f(y) = f(x0)`.
        *   Therefore, a local maximum `x0` must also be a global maximum. This is a critical property for optimization algorithms, as it implies that finding any local maximum guarantees finding the overall global maximum.