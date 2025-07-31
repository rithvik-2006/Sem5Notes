
# Lecture 1: Introduction to Linear Optimization



## 1. What is Optimization?
* **Optimization problems** involve determining the maximum or minimum value of a function.
* **Example**:
    * Maximize $\sin(x)$.
    * If the domain of $x$ is not specified, it's assumed to be all real numbers, and the maximum value is 1.
    * If it were minimize $\sin(x)$, the answer would be $-1$.



## 2. Types of Optimization Problems
* **Unconstrained Optimization Problems**: These seek to find the maximum or minimum of a function defined over the set of all real values of the argument.
    * **Example**: Maximize $\sin(x)$ (over all real $x$).
* **Constrained Optimization Problems**: These involve determining the maximum or minimum of a function where there are specific restrictions on the range of the argument.
    * **Example**: Maximize $\sin(x)$ where $-0.02 \le x \le 0.06$. Here, the maximum value can still be determined within the given range.
* In this course, the focus will be on very special kinds of functions and special restrictions on the range of variables.



## 3. Linear Optimization or Linear Programming
* This subject first emerged for study in the manufacturing and industrial engineering areas in the 1940s.
* The name "**Linear Optimization**" comes from the fact that:
    * The quantity to be optimized (the **objective function**) is a **linear function** of the unknown vector $x$.
    * The **constraints** on the variables ($x_j$) are **linear inequalities**.


## 4. Core Example: Factory Production Problem
This is a classic problem in algorithm design that Linear Optimization addresses.

* **Scenario**: A factory produces $n$ different goods from $m$ different kinds of raw materials.
* **Problem**: Determine how much quantity of each good to produce to maximize the total profit on the goods, given limited raw materials.
* **Key Assumptions**: Fractional amounts of goods are allowed to be produced.
* **Given Information (Inputs)**:
    * **Raw Materials Available**: $M_1, M_2, ..., M_m$.
    * **Quantity of each material available**: $b_1, b_2, ..., b_m$.
    * **Goods to be produced**: $G_1, G_2, ..., G_n$.
    * **Profit per unit of each good**: $p_1, p_2, ..., p_n$.
    * $A_{ij}$: Proportion of material $M_i$ required to produce one unit of good $G_j$.
* **Unknown Quantity**:
    * Let $x_j$ denote the amount of good $j$ that should be produced.
* **Constraints (Restrictions on $x_j$)**:
    * **Raw Material Constraints**: For each raw material $i$, the total amount used cannot exceed the available quantity.
        * $A_{i1}x_1 + A_{i2}x_2 + \cdots+ A_{in}x_n \le b_i$ (for each $i$ from 1 to $m$).
    * **Non-negativity Constraints**: The amount of goods produced cannot be negative.
        * $x_j \ge 0$ (for each $j$ from 1 to $n$).
* **Objective Function (To Maximize)**:
    * The goal is to maximize the total profit.
        * $p_1x_1 + p_2x_2 + \cdots+ p_nx_n$.
* **Mathematical Formulation (More succinctly)**:
    * Maximize $c^Tx$
    * Subject to:
        * $Ax \le b$
        * $x \ge 0$
    * Where:
        * $c$ and $x$ are $n$-dimensional vectors (profit per unit and quantity of goods, respectively).
        * $b$ is an $m$-dimensional vector (available raw materials).
        * $A$ is an $m \times n$ matrix (proportions of materials needed per unit of good).
    * The problem is to find a vector $x$ that satisfies $Ax \le b$ and $x \ge 0$, and also maximizes the quantity $c^Tx$.



## 5. Nature of the Solution Space
* Unlike some discrete algorithmic problems, the number of possible $x$ values that satisfy the constraints ($x \ge 0$ and $Ax \le b$) can be infinite.
* This means a simple brute-force algorithm to find the answer is not obvious. This is a key challenge to be addressed in the course.
* To solve this, it's essential to understand the geometric shape of the set $\{x : Ax \le b\}$.
* The approach begins by considering the simpler set $\{x : Ax = b\}$, which represents the set of all solutions to a collection of $m$ equalities, and can also be an infinite set.
* **Geometric Interpretation (Two Variables - $x_1$ and $x_2$)**:
    * Linear equations of the form $a_{i1}x_1 + a_{i2}x_2 = b_i$ represent straight lines in two dimensions (with $x_1$ and $x_2$ as coordinates).
    * The solution to these equations can be:
        * A single point in the plane.
        * A line.
        * The empty set.
    * Importantly, it "cannot look like anything else".
    * This concept can be extended to three or more variables.
* The goal is to develop both a geometric interpretation and an algebraic description for these sets of solutions.
