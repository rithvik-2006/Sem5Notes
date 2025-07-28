Here are detailed revision notes on the specified topics from Chapter 1 of the provided sources:

### 1 Linear Programming (LP)

#### 1.1 Introduction
*   **Definition**: Linear programming (LP) is the problem of **optimising (maximising or minimising) a linear function subject to linear constraints**.
*   **Broad Applicability**: LP models can be applied to a wide variety of practical problems across numerous areas, including **nutrition, transportation, production planning, and finance**.
*   **Key Components of an LP Problem**: In general, an LP consists of:
    *   **Decision variables**: Quantities that must be determined.
    *   An **objective**: A goal, such as minimising cost or maximising revenue. This objective is represented by a **linear objective function**.
    *   A set of **linear constraints**: These represent the requirements or limitations of the problem.
    *   **Sign restrictions on variables**: These specify whether variables must be non-negative, non-positive, or unrestricted.

#### 1.1.1 The Diet Problem
*   **Concept**: This is one of the earliest examples of an LP. It involves finding the **most economical mix of food items** to provide **sufficient daily nutrition**.
*   **Example Formulation**:
    *   **Decision Variables**: For example, `xpb` (servings of peanut butter), `xb` (servings of bananas), `xc` (servings of chocolate). These must be **non-negative** (`xpb ≥ 0`, `xb ≥ 0`, `xc ≥ 0`).
    *   **Objective Function**: To minimise the total cost, e.g., `.20xpb + .10xb + .15xc`. This function is **linear**.
    *   **Constraints**: Linear inequalities ensuring sufficient nutrient intake, e.g., for fat: `130xpb + 1xb + 12xc ≥ 35`. Similarly for carbohydrates and protein.
*   **General Matrix Form**: The general diet problem with `n` food items and `m` nutritional requirements can be written as:
    *   **Minimise** `cTx`
    *   **Subject to** `Ax ≥ b`
    *   `x ≥ 0`
    *   Where `x` is the vector of food items, `c` is the vector of costs, `A` is the matrix of nutrient amounts per serving, and `b` is the vector of minimum nutrient requirements.

#### 1.1.2 Embedded Assumptions
LP models are characterised by four key assumptions:
*   **Proportionality**: The contribution of decisions to the objective function and constraints is **directly proportional to their values**. There are **no economies of scale** (e.g., no quantity-based discounts). Decision variables are **raised to the first power only**.
*   **Divisibility**: Decision variables can take on **any real number**, including fractional amounts.
*   **Additivity**: The contribution of a decision variable to the objective or constraints **does not depend on other decision variables**; the total contribution is the sum of individual contributions.
*   **Certainty**: All **data used as coefficients** (objective `c`, constraint matrix `A`, and right-hand side `b`) are **known with certainty**.
*   **Relaxation of Certainty**: Recent advances, specifically in **stochastic programming and robust optimization**, allow for the incorporation of **uncertainty of coefficients** in LP models. These topics are covered in Chapter 8.

#### 1.2 General Linear Programming Problems
*   **Variations**: LP problems can vary in:
    *   **Objective Function**: May be to **maximise or minimise**.
    *   **Constraint Types**: Can be **greater than or equal to (`≥`)**, **less than or equal to (`≤`)**, or **equality (`=`)**.
    *   **Variable Restrictions**: Variables can be **non-negative (`≥ 0`)**, **non-positive (`≤ 0`)**, or **unrestricted** (can be negative, positive, or zero).
*   **Equivalence of Forms**:
    *   An **equality constraint** (`aTx = b`) can be represented as two inequalities (`aTx ≤ b` and `aTx ≥ b`).
    *   A **greater than or equal to inequality** (`aTx ≥ b`) can be converted to a less than or equal to type by multiplying by -1 (`-aTx ≤ -b`).

#### 1.2.1 Standard Form of a Linear Program
*   **Definition**: A linear programming problem is in **standard form** if:
    1.  The objective is to **minimise**.
    2.  All constraints are of the **equality type**.
    3.  All variables are **non-negative** (`x ≥ 0`).
*   **Importance**: Some important algorithms, such as the **simplex method**, require LPs to be in standard form.
*   **Conversion Rules**: Any LP can be converted to an equivalent standard form LP:
    1.  **Unrestricted Variables**: If `x` is unrestricted, replace every occurrence of `x` with `x+ - x-`, where `x+ ≥ 0` and `x- ≥ 0`.
    2.  **Maximisation Objective**: To convert `maximise cTx` to minimisation, transform it to `minimise -cTx`.
    3.  **Inequality Constraints**:
        *   **`≤` (less than or equal to)**: Add a **slack variable** (`s1 ≥ 0`) to the left-hand side to make it an equality, e.g., `x1 + x2 ≤ 6` becomes `x1 + x2 + s1 = 6`.
        *   **`≥` (greater than or equal to)**: Add a **surplus variable** (`s2 ≥ 0`) to the left-hand side and subtract it to make it an equality, e.g., `x2 + x3 ≥ 7` becomes `x2 + x3 - s2 = 7`.
*   **Note**: The MATLAB `linprog` function has its own specific form for input, which is **not necessarily the same as the mathematical definition of standard form** required for algorithms like the simplex method.

#### 1.2.2 Linear Programming Terminology
Assuming an LP in standard form (`minimise cTx` subject to `Ax = b, x ≥ 0`):
*   **Constraint Matrix (`A`)**: The matrix of coefficients for the constraints. Dimension `m × n`.
*   **Cost Vector (`c`)**: Vector of coefficients for the objective function. Dimension `n × 1`.
*   **Right-Hand Side Vector (`b`)**: Column vector representing the constant terms in the constraints. Dimension `m × 1`.
*   **Decision Vector (`x`)**: Vector of variables to be determined. Dimension `n × 1`.
*   **Feasible Set (`F`)**: The set of all vectors `x` that satisfy all constraints and sign restrictions (`F = {x ∈ Rn|Ax = b, x ≥ 0}`).
*   **Feasible/Infeasible**: A vector `x` is **feasible** if `x ∈ F`, otherwise it is **infeasible**.
*   **Consistent/Inconsistent**: An LP is **consistent** if `F ≠ ∅` (feasible set is not empty), otherwise it is **inconsistent**.
*   **Bounded Feasible Set**: `F` is bounded if `‖x‖ ≤ M` for some positive constant `M` for all `x ∈ F`. Intuitively, it can be completely contained within a sphere or rectangle.
*   **Optimal Solution (`x*`)**: A vector `x*` is an optimal solution if `x* ∈ F` and `cTx* ≤ cTx` for all `x ∈ F` (for a minimisation problem). Otherwise, `x*` is **sub-optimal**.
*   **Bounded LP**: An LP is **bounded** if `L ≤ cTx` for all `x ∈ F` for some constant `L` (for a minimisation problem). If `F` is bounded, the LP is bounded.
*   **Unbounded LP**: If the objective function can be made arbitrarily small (for minimisation) or large (for maximisation) while remaining feasible.
*   **Geometric Interpretation**:
    *   A **closed halfspace** is a set of the form `{x ∈ Rn|aTx ≤ β}` or `{x ∈ Rn|aTx ≥ β}`. Individual constraints define closed halfspaces.
    *   A **hyperplane** is a set of the form `{x ∈ Rn|aTx = β}`. Equality constraints correspond to hyperplanes.
    *   The **feasible set (`P`) of any linear program is a polyhedral set** (the intersection of a finite number of closed halfspaces). A **bounded polyhedron is called a polytope**.
    *   The feasible set of an LP is always a **convex set**. This is because the intersection of convex sets is convex, and each closed halfspace is a convex set.

#### 1.3 More Linear Programming Examples
*   **Production Planning**: Maximising revenue from producing multiple products given limited resources, where each product consumes a certain amount of each resource.
*   **Multi-period Production Planning**: Extends single-period models by considering production decisions over multiple periods, incorporating demand levels and future production, often involving inventory.
*   **Transportation Problem**: Finding the least-cost shipping pattern of a product from multiple plants (with supply) to multiple warehouses (with demand), constrained by supply limits and demand requirements.
*   **Assignment Problem**: A special case of the transportation problem where the number of "plants" equals the number of "warehouses", and each demands/produces exactly one unit.
*   **Personnel Scheduling Problem**: Scheduling workers to meet daily requirements at minimum cost. This often introduces **integer value requirements** on variables (e.g., number of workers), violating the divisibility assumption and turning it into an **integer program**.
*   **Bond Portfolio Optimization**: Forming a portfolio of bonds to meet future liabilities at minimum cost, assuming fractional bond amounts are allowed.

#### 1.3.1 Converting Minimisation Problems with Absolute Value
*   **Problem**: Minimising an objective function containing absolute value terms (e.g., `minimize c1|x1| + c2|x2| + ... + cn|xn|`) is **not a linear program** because absolute value terms are non-linear.
*   **Transformation Technique**: If `ci > 0` for all `i`, this can be converted to an equivalent LP by:
    1.  **Replacing** each `|xi|` with `x+i + x-i`.
    2.  **Adding a constraint** `xi = x+i - x-i`.
    3.  **Restricting** `x+i ≥ 0` and `x-i ≥ 0`.
*   **Rationale**: At optimality, `x+i * x-i = 0` will hold, ensuring the transformation is equivalent to the absolute value.
*   **Application Example**: This technique is used to formulate the **mean-absolute deviation (MAD) portfolio optimization model** as an LP, which avoids explicit covariance terms.

#### 1.3.2 Network Optimization Models
*   **Definition of a Network**: A network or graph `G = (N, E)` consists of a **set of nodes (or vertices) `N`** and a **set of edges (or arcs) `E`**.
*   **Types of Graphs**:
    *   **Undirected Graph**: Edges are unordered pairs of nodes, representing connections without a specific direction.
    *   **Directed Graph**: Edges are ordered pairs of nodes, representing connections with a specific direction (e.g., `(i, j)` means from `i` to `j`).
*   **Path**: A sequence of nodes and edges connecting two nodes, where no nodes are repeated.
*   **Connected Graph**: A graph is connected if there is a path between every pair of distinct nodes.

##### 1.3.2.1 Minimum Cost Flow Problem
*   **Definition**: Determining a **least-cost shipment (flow)** of a product through a connected directed network to satisfy demand at various nodes from supply nodes. It is a **generalisation of the transportation problem**.
*   **Types of Nodes**:
    *   **Supply Node**: Has a supply `bi > 0` units of the product.
    *   **Demand Node**: Requires a net amount `|bi|` of the product, where `bi < 0`.
    *   **Transshipment Node**: Does not have supply or demand (`bi = 0`); products can flow through it.
*   **LP Formulation**:
    *   **Objective**: Minimise the total cost of flow `∑(i,j)∈E cijxij`.
    *   **Constraints**:
        *   **Flow Conservation (Mass Balance) Constraints**: For each node `i`, the total flow out of `i` minus the total flow into `i` must equal `bi` (`∑{j:(i,j)∈E} xij - ∑{j:(j,i)∈E} xji = bi`).
        *   **Capacity Constraints**: Flow on each edge must be between a lower bound (`lij`) and an upper bound (`uij`) (`lij ≤ xij ≤ uij`).
*   **Assumption**: Sum of all `bi` must be zero (total supply equals total demand).

##### 1.3.2.2 Maximum Flow Problem
*   **Definition**: Finding the **maximum amount of flow** that can be shipped from a single **source node (`s`)** to a single **sink node (`t`)** in a directed graph with capacities on edges.
*   **LP Formulation**:
    *   **Objective**: Maximise the total flow `v` out of the source.
    *   **Constraints**:
        *   **Flow Conservation**: For all nodes *except* the source and sink, net flow is zero (transshipment nodes). For the source, flow out equals `v`; for the sink, net inflow equals `v`.
        *   **Capacity Constraints**: Flow `xij` on each edge `(i, j)` cannot exceed its capacity `uij` (`0 ≤ xij ≤ uij`).