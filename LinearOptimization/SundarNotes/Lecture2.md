


# Lecture 2: Solving Systems of Linear Equations ($Ax = b$)

Lecture 2 focuses on a fundamental aspect of Linear Optimization: solving systems of linear equations of the form $Ax = b$. This is a crucial step towards understanding the solution set of $Ax \le b$, which forms the basis for Linear Programming problems like the factory production problem.

## Overview of Solving $Ax = b$ via Gaussian Elimination

The system $Ax = b$ is shorthand for a set of $m$ linear equations with $n$ unknown variables $x_1, x_2, ..., x_n$:

$A_{11}x_1 + A_{12}x_2 + \dots + A_{1n}x_n = b_1$
$A_{21}x_1 + A_{22}x_2 + \dots + A_{2n}x_n = b_2$
$\vdots$
$A_{m1}x_1 + A_{m2}x_2 + \dots + A_{mn}x_n = b_m$

These systems are solved using a method called **Gaussian Elimination**.

### 1. Phases of Gaussian Elimination

Gaussian Elimination comprises two iterative phases, with the **first phase being the most critical**. In each step of the first phase, the original set of equations is replaced with an **equivalent set**, meaning the new set has the **same solution set** but is **simpler to analyze**.

### 2. First Phase: The Crux of Gaussian Elimination

The primary goal of the first phase is to systematically eliminate variables to transform the system into a simpler "echelon form".

* **Initial Step (Pivot Selection)**:
    * Ensure the coefficient $A_{11}$ (the first coefficient of the first equation) is **non-zero**. If it is zero, you must **exchange the first row with any other row** that has a non-zero coefficient in the first position.
* **Elimination Step**:
    * For every equation **except** the first, **multiply the first equation by a suitable constant and subtract it from that respective equation**.
    * The aim is to make the **first coefficient of every equation (except the first) zero**.
* **Recursion**:
    * Once the first variable ($x_1$) has been eliminated from all but the first equation, you then **ignore the first equation and the first variable** and **repeat the process on the remaining subsystem of equations**.
* **Handling Zeroed Coefficients**:
    * It is possible that during this process, the coefficients of some variables (e.g., $x_2$) might become zero in all rows except one. In such cases, you identify the **first non-zero entry ($A_{ij} \ne 0$) with the smallest column index $j$** in the next relevant row and restart the elimination process from that column.

**Example 1: Demonstrating the First Phase**

Consider the system:
(I) $2x + 7y = 13$
(II) $x + 3y = 4$

To eliminate $x$ from equation (II), we replace (II) with $(-1/2) \cdot \text{(I)} + \text{(II)}$. This calculation yields:
$(-1/2)(2x + 7y) + (x + 3y) = (-1/2)(13) + 4$
$-x - (7/2)y + x + 3y = -13/2 + 8/2$
$- (1/2)y = -5/2$
$y = 5$

Now the system is effectively:
$2x + 7y = 13$
$y = 5$
(which is in an echelon-like form for a 2x2 system).

### 3. Operations Used in Gaussian Elimination

Two fundamental operations are used during this transformation process:

1.  **Exchanging two rows.**
2.  **Replacing `row_j` with $\alpha \cdot \text{row_i} + \text{row_j}$, where $\alpha$ is some constant.**

### 4. Final Form After the First Phase (Echelon Form)

After the first phase, the equations will be in a specific structure known as **echelon form**. Key observations about this form include:

* All zero rows occur after the non-zero rows.
* For non-zero rows, if $t$ is the number of non-zero rows, and the first non-zero entry (called a pivot) of the $i$-th row is at the $k_i$-th column, then $k_i > k_{i-1}$ for $i = 2, ..., t$. This means the **first non-zero entries in the rows appear later and later** (further to the right) as you move down the matrix.

### 5. Existence of a Solution for $Ax = b$

A system $Ax = b$ does not have a solution if, after Gaussian Elimination, you end up with a **particular row $i$ where all coefficients $A_{ij}$ are zero, but the corresponding $b_i$ is non-zero**. This translates to an impossible equation like $0 = b_i$ where $b_i \ne 0$. This condition is both **necessary and sufficient** for the non-existence of a solution.

### 6. Second Phase: Finding Solutions (if they exist)

If solutions exist, they can be easily found from the echelon form:

* Identify the variables that correspond to the "pivots" (the first non-zero entry in each row).
* Set arbitrary values to the "**other variables**" (those not corresponding to pivots).
* Then, **solve for the pivot variables in reverse order** using back-substitution.
* If the system results in $n$ non-zero rows (where $n$ is the number of variables), the system has **only one solution**. Otherwise, the set $\{x : Ax = b\}$ generally has **many solutions**.

### 7. Correctness of the Procedure

The correctness of Gaussian Elimination means that any solutions obtained by the procedure indeed satisfy the **original** set of equations. This relies on proving that the **solution set does not change** when applying the Gaussian Elimination operations.

* **Exchanging two rows** clearly does not alter the solution set.
* **Theorem 1** states that if an equation $A_j$ is replaced by $\alpha \cdot A_i + A_j$ (where $A_i$ is another equation and $\alpha$ is a constant), then the **solution set does not change**.
    * **Proof**: The proof involves two parts.
        1.  **If a solution satisfies the original set, it satisfies the new set**: If a value $(x_{01}, ..., x_{0n})$ satisfies $A_i = b_i$ and $A_j = b_j$, then it logically follows that $\alpha \cdot (A_i - b_i) + (A_j - b_j) = \alpha \cdot 0 + 0 = 0$, which rearranges to $\alpha \cdot A_i + A_j = \alpha \cdot b_i + b_j$, satisfying the new $j$-th equation.
        2.  **If a solution satisfies the new set, it satisfies the original set**: If a value $(x_{01}, ..., x_{0n})$ satisfies $\alpha \cdot A_i + A_j = \alpha \cdot b_i + b_j$ and $A_i = b_i$, then substituting $A_i - b_i = 0$ into the first equality leads to $(A_j - b_j) = 0$, meaning $A_j = b_j$. Thus, the original equation $A_j$ is also satisfied.

### 8. Geometrical Understanding of $Ax = b$

From a geometric perspective, $Ax = b$ represents the intersection of $m$ hyperplanes in $n$-dimensional space ($\mathbb{R}^n$).

* The operation of **adding a constant times another equation to an equation** can be viewed as **rotating one of the hyperplanes about the region of intersection**.
* In the **2D x-y plane ($\mathbb{R}^2$)**, this is illustrated as the **rotation of lines**. For Example 1 (where $2x + 7y = 13$ and $x + 3y = 4$), the operation that transforms $x + 3y = 4$ into $y = 5$ can be seen as rotating the line corresponding to $x + 3y = 4$ to become the line $y = 5$.
* Ultimately, Gaussian Elimination can be described as **rotating the hyperplanes about their intersection region such that, at each step, one of the hyperplanes becomes parallel to one of the axes.**

This understanding of $Ax = b$ and its solution set is the **first goal in comprehending the larger set $\{x : Ax \le b\}$**, which is central to linear optimization problems such as the factory production scenario (where $Ax \le b$ represents raw material constraints and $x \ge 0$ represents non-negative production quantities to maximize profit $c^Tx$).