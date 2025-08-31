Here are detailed revision notes for Chapter 4, "Continuity," from "Principles of Mathematical Analysis, Third Edition" by Walter Rudin, drawing upon the provided source material:

**Chapter 4: Continuity**

This chapter introduces the fundamental concept of continuity for functions within the framework of metric spaces. It builds upon the definitions of limits, sets, and topological properties established in earlier chapters, exploring how continuity interacts with other important mathematical concepts such as compactness and connectedness.

---

### **Limits of Functions**

This section lays the groundwork by defining what it means for a function to approach a certain value as its input approaches a specific point.

*   **Definition 4.1: Limit of a Function**
    *   Let `X` and `Y` be metric spaces, `E` be a subset of `X`, and `f` be a function mapping `E` into `Y`.
    *   Let `p` be a limit point of `E`.
    *   We write `lim (x→p) f(x) = q` (where `q ∈ Y`) if, for every `ε > 0`, there exists a `δ > 0` such that:
        *   `dY(f(x), q) < ε` (the distance in `Y` between `f(x)` and `q` is less than `ε`)
        *   for all `x ∈ E` satisfying `0 < dX(x, p) < δ` (the distance in `X` between `x` and `p` is greater than 0 and less than `δ`).
    *   `dX` and `dY` refer to the distance functions in spaces `X` and `Y`, respectively.
    *   **Important Notes:**
        *   `p` must be in `X`, but it **need not be a point of E**.
        *   Even if `p ∈ E`, it is possible that `f(p) ≠ lim (x→p) f(x)`.

*   **Theorem 4.2: Sequential Criterion for Limits**
    *   `lim (x→p) f(x) = q` if and only if, for every sequence `{pn}` in `E` such that `pn ≠ p` and `lim (n→∞) pn = p`, the sequence `{f(pn)}` converges to `q`.
    *   **Corollary:** If `f` has a limit at `p`, this limit is **unique**. (This follows from Theorem 3.2(b) about the uniqueness of sequence limits.)

*   **Definition 4.3: Operations on Functions**
    *   For complex functions `f` and `g` defined on `E`:
        *   ` (f + g)(x) = f(x) + g(x)`
        *   ` (f - g)(x) = f(x) - g(x)`
        *   ` (fg)(x) = f(x)g(x)`
        *   ` (f/g)(x) = f(x)/g(x)` (defined only where `g(x) ≠ 0`)
    *   A function `f` is a **constant function** (`f = c`) if `f(x) = c` for all `x ∈ E`.
    *   For real functions, `f > g` means `f(x) > g(x)` for all `x ∈ E`.
    *   For `f, g` mapping `E` into `Rk`:
        *   ` (f + g)(x) = f(x) + g(x)`
        *   ` (f · g)(x) = f(x) · g(x)` (dot product, resulting in a real function)
        *   ` (λf)(x) = λf(x)` for a real scalar `λ`.

*   **Theorem 4.4: Properties of Limits for Combined Functions**
    *   If `lim (x→p) f(x) = A` and `lim (x→p) g(x) = B` (for complex functions `f, g` on `E`):
        *   `(a) lim (x→p) (f + g)(x) = A + B`
        *   `(b) lim (x→p) (fg)(x) = AB`
        *   `(c) lim (x→p) (f/g)(x) = A/B` (if `B ≠ 0`)
    *   **Remark:** If `f, g` map `E` into `Rk`, then (a) remains true, and (b) becomes `lim (x→p) (f · g)(x) = A · B`. (These follow from Theorem 3.3 and 3.4 for sequences.)

---

### **Continuous Functions**

This section defines continuity and explores its properties, particularly how it relates to the structure of the domain and codomain.

*   **Definition 4.5: Continuity at a Point and on a Set**
    *   Let `X` and `Y` be metric spaces, `E` be a subset of `X`, and `p ∈ E`.
    *   `f` is **continuous at p** if, for every `ε > 0`, there exists a `δ > 0` such that:
        *   `dY(f(x), f(p)) < ε`
        *   for all `x ∈ E` satisfying `dX(x, p) < δ`.
    *   `f` is **continuous on E** if it is continuous at every point of `E`.
    *   **Important Notes:**
        *   `f` **must be defined at p** to be continuous at `p`.
        *   If `p` is an **isolated point of E**, any function `f` defined on `E` is automatically continuous at `p`. This is because `δ` can be chosen small enough such that the only `x ∈ E` with `dX(x, p) < δ` is `x = p`, making `dY(f(x), f(p)) = 0 < ε` trivially true.

*   **Theorem 4.6: Continuity at a Limit Point**
    *   If `p` is a limit point of `E`, then `f` is continuous at `p` if and only if `lim (x→p) f(x) = f(p)`. (This directly links continuity to the limit definition.)

*   **Theorem 4.7: Continuity of Compositions (Chain Rule for Continuity)**
    *   If `f` maps `E ⊂ X` into `Y` and is continuous at `p ∈ E`.
    *   If `g` maps `f(E) ⊂ Y` into `Z` and is continuous at `f(p)`.
    *   Then the composite function `h(x) = g(f(x))` mapping `E` into `Z` is continuous at `p`.

*   **Theorem 4.8: Topological Characterization of Continuity**
    *   A mapping `f` of a metric space `X` into a metric space `Y` is continuous on `X` if and only if the inverse image `f⁻¹(V)` is **open in X** for every **open set V in Y**.
    *   **Corollary:** `f` is continuous on `X` if and only if `f⁻¹(F)` is **closed in X** for every **closed set F in Y**.

*   **Theorem 4.9: Continuity of Algebraic Combinations (Complex Functions)**
    *   If `f` and `g` are complex continuous functions on a metric space `X`, then `f + g`, `fg`, and `f/g` are continuous on `X`. (For `f/g`, `g(x) ≠ 0` for all `x ∈ X` must be assumed.)

*   **Theorem 4.10: Continuity of Vector-Valued Functions**
    *   **(a)** Let `f1, ..., fk` be real functions on `X`, and `f` be the mapping `f(x) = (f1(x), ..., fk(x))` into `Rk`. Then `f` is continuous if and only if each component function `f1, ..., fk` is continuous.
    *   **(b)** If `f` and `g` are continuous mappings of `X` into `Rk`, then `f + g` and `f · g` are continuous on `X`.

*   **Examples 4.11: Continuous Functions**
    *   Coordinate functions `φj(x) = xj` are continuous on `Rk`.
    *   Monomials are continuous.
    *   Polynomials are continuous.
    *   Rational functions are continuous (where their denominator is non-zero).

*   **Remark 4.12:** The discussion of continuity can often be simplified by considering mappings between metric spaces themselves, rather than subsets, as properties of the complement of the domain are not relevant for continuity.

---

### **Continuity and Compactness**

This section investigates the powerful implications of continuity when the domain is a compact set.

*   **Definition 4.13: Bounded Mapping**
    *   A mapping `f` of a set `E` into `Rk` is **bounded** if there exists a real number `M` such that `|f(x)| < M` for all `x ∈ E`.

*   **Theorem 4.14: Image of a Compact Set is Compact**
    *   If `f` is a continuous mapping of a compact metric space `X` into a metric space `Y`, then the image `f(X)` is **compact**.

*   **Theorem 4.15: Continuous Functions into Rk on Compact Sets are Bounded**
    *   If `f` is a continuous mapping of a compact metric space `X` into `Rk`, then `f(X)` is **closed and bounded**. Consequently, `f` is a **bounded** mapping. (This follows from Theorem 2.41, which states that a subset of `Rk` is compact iff it is closed and bounded.)

*   **Theorem 4.16: Extreme Value Theorem**
    *   If `f` is a continuous **real function** on a compact metric space `X`, then `f` attains its maximum and minimum values on `X`. That is, there exist points `p, q ∈ X` such that `f(q) ≤ f(x) ≤ f(p)` for all `x ∈ X`. (This relies on Theorem 2.28, which states that a closed and bounded set of real numbers contains its supremum and infimum.)

*   **Theorem 4.17: Continuity of Inverse Mappings**
    *   If `f` is a continuous **one-to-one** mapping of a compact metric space `X` **onto** a metric space `Y`, then the inverse mapping `f⁻¹` (from `Y` onto `X`) is also **continuous**.

*   **Definition 4.18: Uniform Continuity**
    *   A mapping `f` of a metric space `X` into a metric space `Y` is **uniformly continuous on X** if, for every `ε > 0`, there exists a `δ > 0` such that:
        *   `dY(f(x), f(y)) < ε`
        *   for all `x, y ∈ X` satisfying `dX(x, y) < δ`.
    *   **Key difference from continuity:** `δ` depends only on `ε`, not on the specific point `x`.

*   **Theorem 4.19: Continuity on Compact Sets Implies Uniform Continuity**
    *   If `f` is a continuous mapping of a compact metric space `X` into a metric space `Y`, then `f` is **uniformly continuous on X**.

*   **Theorem 4.20: Importance of Compactness (Counterexamples)**
    *   If `E` is a **noncompact set** in `R1`, then:
        *   `(a)` There exists a continuous function on `E` which is **not bounded**.
        *   `(b)` There exists a continuous and bounded function on `E` which has **no maximum**.
        *   If, additionally, `E` is bounded, then:
            *   `(c)` There exists a continuous function on `E` which is **not uniformly continuous**.
    *   **Example 4.21:** Demonstrates that Theorem 4.17 fails if `X` is not compact. The mapping `f(t) = (cos t, sin t)` from `X = [0, 2π)` to the unit circle `Y` is continuous and 1-1, but `f⁻¹` is not continuous at the point `(1, 0) ∈ Y`.

---

### **Continuity and Connectedness**

This section explores how continuity preserves the topological property of connectedness.

*   **Theorem 4.22: Image of a Connected Set is Connected**
    *   If `f` is a continuous mapping of a connected metric space `X` into a metric space `Y`, then `f(X)` is **connected**.

*   **Theorem 4.23: Intermediate Value Theorem**
    *   If `f` is a continuous **real function** on the interval `[a, b]`, and if `f(a) < c < f(b)` (or `f(a) > c > f(b)`), then there exists a point `x ∈ (a, b)` such that `f(x) = c`.
    *   Roughly, a continuous real function on an interval assumes all values between its endpoints.

*   **Remark 4.24:** The converse of Theorem 4.23 is **not true**. A function can have the intermediate value property without being continuous. An example is provided in Example 4.27(d).

---

### **Discontinuities**

This section classifies the different types of points where a function fails to be continuous.

*   **Definition: Discontinuity**
    *   If `x` is a point in the domain where `f` is not continuous, `f` is discontinuous at `x` or has a discontinuity at `x`.

*   **Definition 4.25: Right-hand and Left-hand Limits**
    *   For a function `f` defined on `(a, b)` and a point `x` such that `a < x < b`:
        *   `f(x+) = q` if `f(tn) → q` for all sequences `{tn}` in `(x, b)` such that `tn → x`.
        *   `f(x-) = q` if `f(tn) → q` for all sequences `{tn}` in `(a, x)` such that `tn → x`.
    *   The limit `lim (t→x) f(t)` exists if and only if `f(x+) = f(x-) = lim (t→x) f(t)`.

*   **Definition 4.26: Types of Discontinuities**
    *   `f` has a **discontinuity of the first kind (or simple discontinuity)** at `x` if `f(x+)` and `f(x-)` both exist.
    *   Otherwise, the discontinuity is of the **second kind**.
    *   **Simple discontinuities** can occur in two ways:
        *   `f(x+) ≠ f(x-)` (the value `f(x)` is immaterial)
        *   `f(x+) = f(x-) ≠ f(x)`.

*   **Examples 4.27: Illustrations of Discontinuities**
    *   **(a)** Dirichlet function (`1` for rationals, `0` for irrationals) has a discontinuity of the second kind everywhere.
    *   **(b)** Modified Dirichlet function (`x` for rationals, `0` for irrationals) is continuous at `x=0`, and has a discontinuity of the second kind everywhere else.
    *   **(c)** A piecewise function demonstrating a simple discontinuity where `f(x+) ≠ f(x-)` at `x=0`.
    *   **(d)** `f(x) = (sin (1/x))` for `x ≠ 0`, `f(0) = 0`. This function has a discontinuity of the second kind at `x=0` because neither `f(0+)` nor `f(0-)` exists.

---

### **Monotonic Functions**

This section focuses on functions that are always increasing or always decreasing, and their special properties regarding discontinuities.

*   **Definition 4.28: Monotonically Increasing/Decreasing Functions**
    *   `f` is **monotonically increasing** on `(a, b)` if `a < x < y < b` implies `f(x) ≤ f(y)`.
    *   `f` is **monotonically decreasing** if `f(x) ≥ f(y)`.
    *   **Monotonic functions** comprise both increasing and decreasing functions.

*   **Theorem 4.29: Existence of One-Sided Limits for Monotonic Functions**
    *   If `f` is monotonically increasing on `(a, b)`, then `f(x+)` and `f(x-)` exist at every point `x ∈ (a, b)`.
    *   Specifically, `sup (a<t<x) f(t) = f(x-) ≤ f(x) ≤ f(x+) = inf (x<t<b) f(t)`.
    *   Furthermore, if `a < x < y < b`, then `f(x+) ≤ f(y-)`.
    *   **Corollary:** Monotonic functions have **no discontinuities of the second kind**.

*   **Theorem 4.30: Countability of Discontinuities of Monotonic Functions**
    *   If `f` is monotonic on `(a, b)`, then the set of points of `(a, b)` at which `f` is discontinuous is at most **countable**. (This is proven by associating a unique rational number to each discontinuity.)

*   **Remark 4.31: Constructing Monotonic Functions with Dense Discontinuities**
    *   It is possible to construct a monotonic function that is discontinuous at every point of a given countable set `E ⊂ (a, b)` (which can be dense) and continuous elsewhere.
    *   This is done by defining `f(x) = Σ cn` where the sum is over `n` such that `xn < x`, and `Σ cn` converges. `cn` represents the "jump" at `xn`.

---

### **Infinite Limits and Limits at Infinity**

This section extends the concept of limits to include `±∞` for both function values and input points, allowing for operations within the extended real number system.

*   **Definition 4.32: Neighborhoods of ±∞**
    *   A neighborhood of `+∞` is any set `(c, +∞)` for a real `c`.
    *   A neighborhood of `-∞` is any set `(-∞, c)` for a real `c`.

*   **Definition 4.33: Generalized Limit Concept**
    *   `f(t) → A` as `t → x` (where `A, x` are in the extended real number system) if for every neighborhood `U` of `A`, there is a neighborhood `V` of `x` such that `f(t) ∈ U` for all `t ∈ V ∩ E`, `t ≠ x`.
    *   This definition is consistent with Definition 4.1 when `A` and `x` are real.

*   **Theorem 4.34: Properties of Generalized Limits**
    *   If `f(t) → A` and `g(t) → B` as `t → x` (where `A, B, x` are in the extended real number system):
        *   `(a) f(t) → A'` implies `A' = A`.
        *   `(b) (f + g)(t) → A + B`.
        *   `(c) (fg)(t) → AB`.
        *   `(d) (f/g)(t) → A/B`.
    *   These hold **provided the right members are defined**. Note that `∞ - ∞`, `0 · ∞`, `∞/∞`, `A/0` are undefined.

---

This concludes the detailed revision notes for Chapter 4, "Continuity", based on the provided "Math_Rudin.pdf" source.