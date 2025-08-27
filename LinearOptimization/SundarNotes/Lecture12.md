Here are detailed revision notes on Lecture 12, focusing on the Simplex Algorithm: Proof of Correctness:

**Lecture 12: The Simplex Algorithm: Proof of Correctness**

This lecture aims to analyse the stopping condition of the Simplex algorithm and prove its correctness.

**1. Recap of Simplex Algorithm Context**
*   **Extreme Point `x0`**: The algorithm starts and operates on extreme points.
*   **Defining Hyperplanes**: An extreme point `x0` is defined by `A'x0 = b'` and `A''x0 < b''`, where `A'` represents `n` linearly independent rows of matrix `A` satisfied as equalities by `x0`, and `b'` contains the corresponding entries from `b`.
*   **Directions of Neighbours**: The directions towards the neighbouring extreme points from `x0` are given by the columns of the matrix `-(A')^-1`.

**2. Stopping Condition**
*   The Simplex algorithm **stops at an extreme point `x0`** and returns it as the optimal point.
*   This occurs **when the cost at `x0` is greater than or equal to the cost at all of its neighbouring extreme points**.
*   It is important to note that this condition does not explicitly state that `x0` is a local maximum in the traditional sense (compared to all points in a small neighbourhood), but rather compared to its direct neighbours.

**3. Proof of Correctness**
The main theorem states that **if the cost does not increase along any of the columns of `-(A')^-1`, then `x0` is optimal**.

*   **Assumption**: Assume the algorithm terminates at `x0`. Let `xopt` be an optimal point. By definition of `xopt`, we know that `cTxopt >= cTx0`.
*   **Basis and Linear Combination**:
    *   `A'` has full rank, implying `-(A')^-1` also has full rank, meaning its columns form a basis for `R^n`.
    *   Therefore, the vector `(xopt - x0)` can be expressed as a linear combination of the columns of `-(A')^-1`:
        `xopt - x0 = Σᵢ λᵢ (-(A')^-1)ᵢ`.
*   **Analysing Coefficients (`λᵢ`)**:
    *   Premultiplying the equation `xopt - x0 = Σᵢ λᵢ (-(A')^-1)ᵢ` by `A'` gives:
        `A'(xopt - x0) = Σᵢ λᵢ A'(-(A')^-1)ᵢ`.
    *   **Left-Hand Side (LHS)**: Since `xopt` is a feasible point, `A'xopt ≤ b'`, and `A'x0 = b'` (because `x0` is an extreme point satisfying `A'x0 = b'`). Therefore, `A'xopt - A'x0` results in a vector where **each component is at most 0**.
    *   **Right-Hand Side (RHS)**: The product `A'(-(A')^-1)ᵢ` is a vector with `-1` at the `i`-th position and `0` elsewhere (i.e., `-eᵢ`). So, `Σᵢ λᵢ A'(-(A')^-1)ᵢ` simplifies to a vector `[ -λ₁ -λ₂ ... -λ_n ]^T`.
    *   **Conclusion on `λᵢ`**: By equating the LHS and RHS, we deduce that `A'xopt - A'x0` must equal `[-λ₁ -λ₂ ... -λ_n]^T`. Since each component of `A'xopt - A'x0` is at most 0, it follows that **`λⱼ ≥ 0` for all `j`**. These coefficients of the linear combination are non-negative.
*   **Analysing Cost Function (`cTx`)**:
    *   Now, multiplying the equation `xopt - x0 = Σᵢ λᵢ (-(A')^-1)ᵢ` by `c^T` yields:
        `cTxopt - cTx0 = Σᵢ λᵢ cT (-(A')^-1)ᵢ`.
    *   **Stopping Condition Application**: From the Simplex algorithm's stopping condition, we know that the cost does not increase along the directions of the neighbours. This means `cT (-(A')^-1)ᵢ ≤ 0` for all `i`.
    *   **Final Deduction**: Since `λⱼ ≥ 0` (as proven above) and `cT (-(A')^-1)ᵢ ≤ 0`, the entire right-hand side `Σᵢ λᵢ cT (-(A')^-1)ᵢ` must be **at most 0**.
    *   Therefore, `cTxopt - cTx0 ≤ 0`, which implies `cTxopt ≤ cTx0`.
*   **Optimality**: Combining this result with our initial assumption that `cTxopt ≥ cTx0`, we conclude that **`cTxopt = cTx0`**, proving that `x0` is indeed an optimal point.

**4. Intuition Behind the Proof**
*   Around an extreme point `x0` in the feasible region `R`, there are directions (e.g., vectors `a` and `b` in 2D) leading to its neighbours.
*   If the cost decreases along these directions `a` and `b`, then in any feasible direction within the region `R` bounded by these neighbour directions, the cost will also decrease.
*   The core idea is that any feasible point can be expressed as a non-negative linear combination of the direction vectors of the neighbours. Since the cost does not increase (or decreases) along these direction vectors, no feasible point can have a larger cost than `x0`. This is possible because the direction vectors are linearly independent.

**5. Degeneracy Considerations**
*   The proof relies on the assumption that only `n` hyperplanes meet at a point (non-degeneracy). If this assumption is not made, modifications would be needed, which can lead to issues like "cycling". However, the theorems are generally assumed to hold even with degeneracy, possibly requiring a modified Simplex description.