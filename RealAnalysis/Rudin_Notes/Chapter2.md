Here are detailed revision notes on Chapter 2, "Basic Topology," from "Principles of Mathematical Analysis" by Walter Rudin, Third Edition. This chapter introduces fundamental concepts regarding sets and spaces essential for understanding mathematical analysis.

***

### Chapter 2: Basic Topology

This chapter lays the groundwork for understanding concepts like convergence, continuity, differentiation, and integration by defining various types of sets and spaces and their properties.

---

### 1. Finite, Countable, and Uncountable Sets

This section begins by formalising the notion of function and then uses it to classify sets based on their "size" or cardinality.

**1.1. Core Definitions**

*   **Function (Mapping)**: A function `f` from a set `A` to a set `B` associates with each element `x` in `A` a unique element `f(x)` in `B` [2.1, p. 57].
    *   **Domain**: The set `A` on which `f` is defined [2.1, p. 57].
    *   **Range**: The set of all values `f(x)` in `B` [2.1, p. 57].
    *   **Onto (Surjective)**: `f` maps `A` *onto* `B` if its range is all of `B` [2.2, p. 57].
    *   **One-to-One (Injective)**: `f` is one-to-one (1-1) if `f(x_1) = f(x_2)` implies `x_1 = x_2` [2.2, p. 57-58].
*   **Equivalence of Sets**: Two sets `A` and `B` are said to have the same *cardinal number*, or be *equivalent* (denoted `A ~ B`), if there exists a 1-1 mapping of `A` onto `B` [2.3, p. 58].
    *   This relation is an *equivalence relation*, meaning it is reflexive (`A ~ A`), symmetric (`if A ~ B, then B ~ A`), and transitive (`if A ~ B and B ~ C, then A ~ C`) [2.3, p. 58].
*   **Classification of Sets** [2.4, p. 59]:
    *   `J_n`: The set of integers `{1, 2, ..., n}` for a positive integer `n`.
    *   `J`: The set of all positive integers `{1, 2, 3, ...}`.
    *   **Finite Set**: A set `A` is finite if `A ~ J_n` for some `n`. The empty set is also considered finite [2.4a, p. 59].
    *   **Infinite Set**: A set `A` is infinite if it is not finite [2.4b, p. 59]. Notably, an infinite set *can* be equivalent to one of its proper subsets (e.g., the set of all integers `A` and `J` (positive integers) are equivalent, and `J` is a proper subset of `A`) [2.6, p. 61].
    *   **Countable Set**: A set `A` is countable if `A ~ J` [2.4c, p. 59]. These are also called enumerable or denumerable [2.4, p. 59].
    *   **Uncountable Set**: A set `A` is uncountable if it is neither finite nor countable [2.4d, p. 59].
    *   **At Most Countable Set**: A set `A` is at most countable if it is finite or countable [2.4e, p. 59].
*   **Sequence**: A function `f` defined on the set `J` of all positive integers. If `f(n) = x_n`, the sequence is denoted `{x_n}` [2.7, p. 62]. Countable sets can be regarded as the range of a 1-1 sequence of distinct terms [2.7, p. 62].
*   **Collection of Sets (Family of Sets)** [2.9, p. 65]:
    *   **Union**: The set `S` such that `x ∈ S` if and only if `x ∈ E_α` for at least one `α` in the index set `A` (`S = ⋃_{α∈A} E_α`) [2.9, p. 65]. The symbol `∞` in `⋃_{m=1}^∞ E_m` merely indicates a countable union and should not be confused with `+∞` or `-∞` [2.9, p. 66].
    *   **Intersection**: The set `P` such that `x ∈ P` if and only if `x ∈ E_α` for *every* `α` in `A` (`P = ⋂_{α∈A} E_α`) [2.9, p. 66].
    *   **Disjoint Sets**: Two sets `A` and `B` are disjoint if `A ∩ B = ∅` [2.9, p. 67].

**1.2. Key Theorems and Proof Sketches**

*   **Theorem 2.8: Every infinite subset of a countable set is countable.** [2.8, p. 63]
    *   **Proof Sketch**: Let `E` be an infinite subset of a countable set `A`. Since `A` is countable, its elements can be arranged into a sequence `{x_n}` of distinct elements. We construct a sequence of distinct elements for `E` by letting `n_1` be the smallest positive integer such that `x_{n_1} ∈ E`, and generally, `n_k` is the smallest integer greater than `n_{k-1}` such that `x_{n_k} ∈ E`. The function `f(k) = x_{n_k}` establishes a 1-1 correspondence between `J` and `E`, thus `E` is countable [2.8, p. 63].
*   **Theorem 2.12: The union of a countable collection of countable sets is countable.** [2.12, p. 68]
    *   **Proof Sketch**: Let the countable sets be `E_1, E_2, E_3, ...`. Since each `E_n` is countable, its elements can be arranged in a sequence: `E_n = {x_{n,1}, x_{n,2}, x_{n,3}, ...}`. We can then list all elements of the union `S = ⋃ E_n` by arranging them in an infinite array and traversing it diagonally (`x_{1,1}, x_{1,2}, x_{2,1}, x_{1,3}, x_{2,2}, x_{3,1}, ...`). This creates a sequence containing all elements of `S`. If there are common elements, `S` is equivalent to a subset of `J`, making `S` at most countable. Since `E_1 ⊂ S` and `E_1` is infinite, `S` must be infinite, and therefore countable [2.12, p. 69].
    *   **Corollary**: If `A` is at most countable, and, for every `α ∈ A`, `E_α` is at most countable, then `⋃_{α∈A} E_α` is at most countable. [2.12, p. 69]
        *   **Proof Sketch**: This union `T` is equivalent to a subset of the union of a countable number of countable sets (from the proof of Theorem 2.12) [2.12, p. 69].
*   **Theorem 2.13: The set of all n-tuples `(a_1, ..., a_n)` where `a_k` belongs to a countable set `A` is countable.** [2.13, p. 70]
    *   **Proof Sketch**: The proof proceeds by induction. `B_1 = A` is countable. Assume `B_{n-1}` is countable. Elements of `B_n` are of the form `(b, a)` where `b ∈ B_{n-1}` and `a ∈ A`. For each fixed `b`, the set of pairs `(b, a)` is equivalent to `A` (and hence countable). Since `B_n` is the union of a countable set (`B_{n-1}`) of countable sets (the sets `{(b, a) | a ∈ A}`), it is countable by Theorem 2.12 [2.13, p. 70].
    *   **Corollary**: The set of all rational numbers is countable. [2.13, p. 71]
        *   **Proof Sketch**: Any rational number `r` can be written as `b/a`, where `a` and `b` are integers. The set of all integers is countable (Example 2.5). Thus, the set of pairs `(a, b)` (or `(b, a)`) is countable by Theorem 2.13 (with `n=2` and `A` being the set of integers). Therefore, the set of all fractions `b/a` (rational numbers) is countable [2.13, p. 71].
*   **Theorem 2.14: The set of all sequences whose elements are the digits 0 and 1 is uncountable.** [2.14, p. 71]
    *   **Proof Sketch**: This uses Cantor's diagonal process. Assume, for contradiction, that the set `A` of all such sequences is countable. Then its elements can be listed as a sequence of sequences `s_1, s_2, s_3, ...`. Let `s_n = (s_{n,1}, s_{n,2}, s_{n,3}, ...)`. Construct a new sequence `t = (t_1, t_2, t_3, ...)` where `t_n = 1` if `s_{n,n} = 0` and `t_n = 0` if `s_{n,n} = 1`. This new sequence `t` consists only of 0s and 1s, so it must be in `A`. However, by construction, `t` differs from `s_n` in the `n`-th position for every `n`. Thus `t` is not in the list, which is a contradiction. Therefore, the set `A` is uncountable [2.14, p. 72].
    *   This theorem implies that the set of all real numbers is uncountable (as they can be represented in binary using 0s and 1s) [2.14, p. 72].

---

### 2. Metric Spaces

This section introduces the concept of a metric space, which generalizes the notion of distance from Euclidean space.

**2.1. Core Definitions**

*   **Metric Space**: A set `X` (whose elements are called *points*) is a metric space if, for any two points `p` and `q` in `X`, there is an associated real number `d(p, q)`, called the *distance* from `p` to `q`, satisfying the following properties [2.15, p. 73]:
    *   (a) `d(p, q) > 0` if `p ≠ q`; `d(p, p) = 0`.
    *   (b) `d(p, q) = d(q, p)` (Symmetry).
    *   (c) `d(p, q) ≤ d(p, r) + d(r, q)` for any `r ∈ X` (Triangle Inequality).
    *   Any function `d` with these properties is called a *distance function* or a *metric* [2.15, p. 73].
*   **Examples of Metric Spaces**: Euclidean spaces `R^k` (with `d(x, y) = |x - y|`), and any subset `Y` of a metric space `X` (with the same distance function) [2.16, p. 73-74].
*   **Intervals and Cells** [2.17, p. 75]:
    *   **Segment (a, b)**: ` {x ∈ R^1 | a < x < b} `.
    *   **Interval [a, b]**: ` {x ∈ R^1 | a ≤ x ≤ b} `.
    *   **Half-open intervals [a, b) and (a, b]**: ` {x ∈ R^1 | a ≤ x < b} ` and ` {x ∈ R^1 | a < x ≤ b} `, respectively.
    *   **k-cell**: For `a_i < b_i`, the set of all points `x = (x_1, ..., x_k)` in `R^k` whose coordinates satisfy `a_i ≤ x_i ≤ b_i` for `1 ≤ i ≤ k`. A 1-cell is an interval, a 2-cell is a rectangle, etc.
*   **Properties of Sets in a Metric Space** [2.18, p. 76-78]:
    *   **Neighborhood**: A set `N_r(p)` consisting of all points `q` such that `d(p, q) < r`. `r` is the *radius* [2.18a, p. 76]. In `R^1`, neighborhoods are segments; in `R^2`, they are interiors of circles [2.18, p. 78].
    *   **Limit Point**: A point `p` is a limit point of `E` if every neighborhood of `p` contains a point `q ∈ E` such that `q ≠ p` [2.18b, p. 76].
    *   **Isolated Point**: If `p ∈ E` and `p` is not a limit point of `E`, then `p` is an isolated point of `E` [2.18c, p. 76].
    *   **Closed Set**: A set `E` is closed if every limit point of `E` is a point of `E` [2.18d, p. 77].
    *   **Interior Point**: A point `p` is an interior point of `E` if there is a neighborhood `N` of `p` such that `N ⊂ E` [2.18e, p. 77].
    *   **Open Set**: A set `E` is open if every point of `E` is an interior point of `E` [2.18f, p. 77].
    *   **Complement**: The set of all points `p ∈ X` such that `p ∉ E` (denoted `E^c`) [2.18g, p. 77].
    *   **Perfect Set**: A set `E` is perfect if `E` is closed and if every point of `E` is a limit point of `E` [2.18h, p. 77].
    *   **Bounded Set**: A set `E` is bounded if there is a real number `M` and a point `q ∈ X` such that `d(p, q) < M` for all `p ∈ E` [2.18i, p. 77].
    *   **Dense Set**: A set `E` is dense in `X` if every point of `X` is a limit point of `E` or a point of `E` (or both) [2.18j, p. 77-78].
    *   **Closure (`E`)**: The closure of a set `E` is the union of `E` and its set of limit points `E'` (`E = E ∪ E'`) [2.26, p. 85].

**2.2. Key Theorems and Proof Sketches**

*   **Theorem 2.19: Every neighborhood is an open set.** [2.19, p. 78]
    *   **Proof Sketch**: Let `E = N_r(p)` be a neighborhood of `p`. Take any point `q ∈ E`. Then `d(p, q) < r`. Let `h = r - d(p, q) > 0`. For any `s` such that `d(q, s) < h`, by the triangle inequality, `d(p, s) ≤ d(p, q) + d(q, s) < d(p, q) + h = d(p, q) + (r - d(p, q)) = r`. So `s ∈ E`. This means `N_h(q) ⊂ E`, making `q` an interior point of `E`. Since every point in `E` is an interior point, `E` is open [2.19, p. 78].
*   **Theorem 2.20: If `p` is a limit point of `E`, then every neighborhood of `p` contains infinitely many points of `E`.** [2.20, p. 78-79]
    *   **Proof Sketch**: Proof by contradiction. Assume there is a neighborhood `N` of `p` containing only a finite number of points of `E` (distinct from `p`). Let these points be `q_1, ..., q_n`. Define `r = min_{1≤m≤n} d(p, q_m)`. Since `r > 0`, the neighborhood `N_r(p)` contains no points of `E` other than possibly `p` itself. This contradicts the definition of `p` as a limit point of `E` (which requires infinitely many points `q ≠ p` in every neighborhood) [2.20, p. 79].
    *   **Corollary**: A finite point set has no limit points [2.20, p. 80].
*   **Theorem 2.22 (De Morgan's Laws for Complements):**
    *   `(⋃_α E_α)^c = ⋂_α (E_α)^c`
    *   `(⋂_α E_α)^c = ⋃_α (E_α)^c` [2.22, p. 82]
    *   **Proof Sketch**: This is shown by demonstrating set equality: `A ⊂ B` and `B ⊂ A`. For example, for the first law, if `x ∈ (⋃_α E_α)^c`, then `x ∉ ⋃_α E_α`, which means `x ∉ E_α` for any `α`. Thus `x ∈ E_α^c` for every `α`, so `x ∈ ⋂_α (E_α)^c`. This shows the left side is a subset of the right. The reverse inclusion is shown similarly [2.22, p. 82].
*   **Theorem 2.23: A set `E` is open if and only if its complement `E^c` is closed.** [2.23, p. 82-83]
    *   **Proof Sketch**:
        *   **(If `E^c` is closed implies `E` is open)**: Let `x ∈ E`. Then `x ∉ E^c`. Since `E^c` is closed, `x` is not a limit point of `E^c`. Thus, there is a neighborhood `N` of `x` that contains no points of `E^c` (except possibly `x`, but `x` is not in `E^c`). This means `N ⊂ E`, so `x` is an interior point of `E`. Since this holds for all `x ∈ E`, `E` is open [2.23, p. 83].
        *   **(If `E` is open implies `E^c` is closed)**: Let `x` be a limit point of `E^c`. By definition, every neighborhood of `x` contains points of `E^c`. This implies `x` cannot be an interior point of `E`. Since `E` is open, this means `x ∉ E`, so `x ∈ E^c`. Thus, `E^c` contains all its limit points, making it closed [2.23, p. 83].
    *   **Corollary**: A set `F` is closed if and only if its complement `F^c` is open [2.23, p. 83].
*   **Theorem 2.24: Properties of unions and intersections of open/closed sets.** [2.24, p. 84]
    *   (a) The union of any collection of open sets is open.
        *   **Proof Sketch**: Let `G = ⋃_α G_α`. If `x ∈ G`, then `x ∈ G_α` for some `α`. Since `G_α` is open, `x` is an interior point of `G_α`. This implies `x` is also an interior point of `G`, so `G` is open [2.24, p. 84].
    *   (b) The intersection of any collection of closed sets is closed.
        *   **Proof Sketch**: Let `F = ⋂_α F_α`. By Theorem 2.22, `F^c = ⋃_α F_α^c`. Since `F_α` is closed, `F_α^c` is open (Theorem 2.23). By part (a), `⋃_α F_α^c` is open, so `F^c` is open. Therefore, `F` is closed (Theorem 2.23) [2.24, p. 84].
    *   (c) The intersection of any finite collection of open sets is open.
        *   **Proof Sketch**: Let `H = ⋂_{i=1}^n G_i`. For any `x ∈ H`, since each `G_i` is open, there exist neighborhoods `N_i` of `x` with radii `r_i` such that `N_i ⊂ G_i`. Let `r = min(r_1, ..., r_n)`. Then `r > 0`. The neighborhood `N_r(x)` is contained in all `G_i`, so `N_r(x) ⊂ H`. Thus `H` is open [2.24, p. 84].
    *   (d) The union of any finite collection of closed sets is closed.
        *   **Proof Sketch**: This follows from (c) by taking complements and using Theorem 2.23 (De Morgan's Laws) [2.24, p. 85].
    *   **Important Remark**: The finiteness condition in (c) and (d) is *essential*. For example, the intersection of infinitely many open intervals `G_n = (-1/n, 1/n)` is `{0}`, which is closed, not open. The union of infinitely many closed intervals `F_n = [0, 1 - 1/n]` is `[0, 1)`, which is open (relative to `R^1`), not closed [2.25, p. 85].
*   **Theorem 2.26: Properties of closure.** [2.26, p. 85]
    *   (a) `E` is closed.
        *   **Proof Sketch**: If `p ∉ E`, then `p` is neither in `E` nor a limit point of `E`. So there exists a neighborhood of `p` that does not intersect `E`. This implies `E^c` is open, hence `E` is closed [2.26, p. 86].
    *   (b) `E = E` if and only if `E` is closed.
        *   **Proof Sketch**: If `E = E`, by (a) `E` is closed. If `E` is closed, then `E'` (its limit points) are in `E`, so `E ⊂ E`. As `E ⊂ E` is always true, `E = E` [2.26, p. 86].
    *   (c) If `F` is closed and `F ⊃ E`, then `F ⊃ E`.
        *   **Proof Sketch**: If `F` is closed and `F ⊃ E`, then `F ⊃ E'` (since all limit points of `E` must be in `F` if `E` is in `F`). Thus `F ⊃ E ∪ E' = E` [2.26, p. 86].
*   **Theorem 2.28: If `E` is a nonempty set of real numbers which is bounded above, let `γ = sup E`. Then `γ ∈ E`. Hence, `γ ∈ E` if `E` is closed.** [2.28, p. 86]
    *   **Proof Sketch**: If `γ ∈ E`, then `γ ∈ E` is trivially true. Assume `γ ∉ E`. For every `h > 0`, `γ - h` is not an upper bound of `E`, so there must be an `x ∈ E` such that `γ - h < x ≤ γ`. This shows that every neighborhood of `γ` contains a point `x ∈ E` (distinct from `γ` if `γ ∉ E`). Thus `γ` is a limit point of `E`. If `E` is closed, then `γ` must be in `E` [2.28, p. 86].
*   **Theorem 2.30: Suppose `Y ⊂ X` (X is a metric space). A subset `E` of `Y` is open relative to `Y` if and only if `E = Y ∩ G` for some open subset `G` of `X`.** [2.30, p. 88]
    *   **Proof Sketch**:
        *   **(If E is open relative to Y implies E = Y ∩ G)**: For each `p ∈ E`, there exists `r_p > 0` such that `N_{r_p}(p) ∩ Y ⊂ E`. Let `V_p = N_{r_p}(p)` be the neighborhood in `X`. Define `G = ⋃_{p∈E} V_p`. `G` is open in `X` (by Theorem 2.19 and 2.24a). By construction, `E ⊂ G ∩ Y`. Also, `V_p ∩ Y ⊂ E` for every `p ∈ E` implies `G ∩ Y ⊂ E`. Thus `E = G ∩ Y` [2.30, p. 89].
        *   **(If E = Y ∩ G implies E is open relative to Y)**: If `G` is open in `X` and `E = G ∩ Y`, then for any `p ∈ E`, `p ∈ G`. Since `G` is open, there is a neighborhood `V_p ⊂ G`. Then `V_p ∩ Y ⊂ G ∩ Y = E`, so `E` is open relative to `Y` [2.30, p. 89].

---

### 3. Compact Sets

Compactness is a crucial property in analysis, linking boundedness and "closedness" in a powerful way, especially in Euclidean spaces.

**3.1. Core Definitions**

*   **Open Cover**: An *open cover* of a set `E` in a metric space `X` is a collection `{G_α}` of open subsets of `X` such that `E ⊂ ⋃_α G_α` [2.31, p. 89].
*   **Compact Set**: A subset `K` of a metric space `X` is *compact* if every open cover of `K` contains a *finite subcover* [2.32, p. 90]. That is, if `{G_α}` covers `K`, then there exist finitely many indices `α_1, ..., α_n` such that `K ⊂ G_{α_1} ∪ ... ∪ G_{α_n}` [2.32, p. 90].

**3.2. Key Theorems and Proof Sketches**

*   **Theorem 2.33: Suppose `K ⊂ Y ⊂ X`. Then `K` is compact relative to `X` if and only if `K` is compact relative to `Y`.** [2.33, p. 92]
    *   **Proof Sketch**:
        *   **(If K is compact relative to X implies K is compact relative to Y)**: Let `{V_α}` be an open cover of `K` relative to `Y`. By Theorem 2.30, each `V_α = Y ∩ G_α` for some `G_α` open in `X`. Since `{G_α}` covers `K` and `K` is compact relative to `X`, there is a finite subcover `G_{α_1}, ..., G_{α_n}`. Then `K ⊂ G_{α_1} ∪ ... ∪ G_{α_n}`. Since `K ⊂ Y`, this implies `K ⊂ (G_{α_1} ∪ ... ∪ G_{α_n}) ∩ Y = (G_{α_1} ∩ Y) ∪ ... ∪ (G_{α_n} ∩ Y) = V_{α_1} ∪ ... ∪ V_{α_n}`. So a finite subcover exists relative to `Y` [2.33, p. 93].
        *   **(Converse)**: Let `{G_α}` be an open cover of `K` in `X`. Let `V_α = Y ∩ G_α`. Then `{V_α}` is an open cover of `K` relative to `Y`. Since `K` is compact relative to `Y`, there is a finite subcover `V_{α_1}, ..., V_{α_n}`. As `V_α ⊂ G_α`, this implies `K ⊂ G_{α_1} ∪ ... ∪ G_{α_n}`. So a finite subcover exists relative to `X` [2.33, p. 93-94].
*   **Theorem 2.34: Compact subsets of metric spaces are closed.** [2.34, p. 94]
    *   **Proof Sketch**: We prove `K^c` is open. Let `p ∈ X` such that `p ∉ K`. For each `q ∈ K`, `p ≠ q`, so `d(p, q) > 0`. We can find disjoint open neighborhoods `V_q` of `p` and `W_q` of `q` (e.g., radius `d(p,q)/2`) [This step implicitly relies on `X` being a metric space and thus Hausdorff, a property directly supported by the metric definition]. The collection `{W_q | q ∈ K}` is an open cover of `K`. Since `K` is compact, there's a finite subcover `W_{q_1}, ..., W_{q_n}`. Let `W = ⋃_{i=1}^n W_{q_i}`. Let `V = ⋂_{i=1}^n V_{q_i}`. `V` is open (finite intersection of open sets) and `p ∈ V`. By construction, `V` is disjoint from `W`. Since `K ⊂ W`, `V` is disjoint from `K`. Thus `V ⊂ K^c`. This shows `p` is an interior point of `K^c`, so `K^c` is open, and `K` is closed [2.34, p. 94-95].
*   **Theorem 2.35: Closed subsets of compact sets are compact.** [2.35, p. 95]
    *   **Proof Sketch**: Let `F ⊂ K ⊂ X`, where `F` is closed (in `X`) and `K` is compact. Let `{V_α}` be an open cover of `F`. Consider the collection `Ω = {V_α} ∪ {F^c}`. `Ω` is an open cover of `K` because `F ⊂ ⋃ V_α` and `F^c` covers the rest of `K`. Since `K` is compact, there's a finite subcollection `Φ ⊂ Ω` that covers `K` (and thus `F`). If `F^c ∈ Φ`, we can remove it, and the remaining finite subcollection (from `{V_α}`) still covers `F`. Thus `F` is compact [2.35, p. 95].
    *   **Corollary**: If `F` is closed and `K` is compact, then `F ∩ K` is compact. [2.35, p. 96]
        *   **Proof Sketch**: `F ∩ K` is closed (intersection of closed sets by Theorem 2.24b). Since `F ∩ K ⊂ K` and `K` is compact, by Theorem 2.35, `F ∩ K` is compact [2.35, p. 96].
*   **Theorem 2.36: If `{K_α}` is a collection of compact subsets of a metric space `X` such that the intersection of every finite subcollection of `{K_α}` is nonempty, then `⋂ K_α` is nonempty.** [2.36, p. 96]
    *   **Proof Sketch**: Proof by contradiction. Fix `K_1` from the collection. Assume `⋂ K_α = ∅`. Then `K_1 ∩ (⋂_{α≠1} K_α) = ∅`, which means `K_1 ⊂ ⋃_{α≠1} K_α^c`. The sets `G_α = K_α^c` are open (since `K_α` are closed by Theorem 2.34). Thus `{G_α}` forms an open cover of `K_1`. Since `K_1` is compact, there's a finite subcover `G_{α_1}, ..., G_{α_n}` such that `K_1 ⊂ G_{α_1} ∪ ... ∪ G_{α_n}`. This implies `K_1 ∩ G_{α_1}^c ∩ ... ∩ G_{α_n}^c = ∅`, which means `K_1 ∩ K_{α_1} ∩ ... ∩ K_{α_n} = ∅`. This contradicts the hypothesis that the intersection of every finite subcollection is nonempty [2.36, p. 96-97].
    *   **Corollary**: If `{K_n}` is a sequence of nonempty compact sets such that `K_n ⊃ K_{n+1}` for all `n`, then `⋂ K_n` is not empty. [2.36, p. 97]
*   **Theorem 2.37: If `E` is an infinite subset of a compact set `K`, then `E` has a limit point in `K`.** [2.37, p. 97]
    *   **Proof Sketch**: Proof by contradiction. Assume no point of `K` is a limit point of `E`. Then for each `q ∈ K`, there exists a neighborhood `V_q` that contains at most one point of `E` (namely `q`, if `q ∈ E`). The collection `{V_q | q ∈ K}` is an open cover of `K`. Since `K` is compact, there's a finite subcover `V_{q_1}, ..., V_{q_n}`. This finite collection can only cover a finite number of points of `E`, which contradicts `E` being an infinite set. Therefore, `E` must have a limit point in `K` [2.37, p. 97].
*   **Theorem 2.38: If `{I_n}` is a sequence of intervals in `R^1` such that `I_n ⊃ I_{n+1}`, then `⋂ I_n` is not empty.** [2.38, p. 98]
    *   **Proof Sketch**: Let `I_n = [a_n, b_n]`. Since `I_n ⊃ I_{n+1}`, we have `a_n ≤ a_{n+1}` and `b_{n+1} ≤ b_n`. The set `E = {a_n}` is non-empty and bounded above by `b_1`. Let `x = sup E`. For any `m`, `a_m ≤ x`. Also, for any `m`, `a_n ≤ b_m` for all `n`. So `x ≤ b_m`. Thus `x ∈ [a_m, b_m]` for all `m`, meaning `x ∈ ⋂ I_n` [2.38, p. 98].
*   **Theorem 2.39: If `{I_n}` is a sequence of k-cells such that `I_n ⊃ I_{n+1}`, then `⋂ I_n` is not empty.** [2.39, p. 98-99]
    *   **Proof Sketch**: Let `I_n` be `[a_{n,1}, b_{n,1}] × ... × [a_{n,k}, b_{n,k}]`. For each coordinate `j`, the sequence of intervals `{I_{n,j}} = {[a_{n,j}, b_{n,j}]}` satisfies the hypotheses of Theorem 2.38. Thus, for each `j`, there exists `x_j ∈ R^1` such that `x_j ∈ ⋂_n I_{n,j}`. The point `x = (x_1, ..., x_k)` is then in `⋂_n I_n` [2.39, p. 99].
*   **Theorem 2.40: Every k-cell is compact.** [2.40, p. 99]
    *   **Proof Sketch**: Proof by contradiction. Let `I` be a k-cell. Assume `I` is not compact. Then there exists an open cover `{G_α}` of `I` that has no finite subcover. Subdivide `I` into `2^k` smaller k-cells by bisecting its sides. At least one of these smaller k-cells, say `I_1`, cannot be covered by a finite subcollection of `{G_α}`. Repeat this process: subdivide `I_1` to find `I_2`, and so on. This generates a sequence of k-cells `I_n` such that `I_n ⊃ I_{n+1}`, and no `I_n` can be covered by a finite subcollection. Also, the diameter of `I_n` approaches 0 (specifically, `diam(I_n) = 2^{-n} diam(I)`). By Theorem 2.39, there's a point `x* ∈ ⋂ I_n`. Since `{G_α}` covers `I`, `x* ∈ G_α` for some `α`. Since `G_α` is open, there's a neighborhood `N_r(x*) ⊂ G_α`. For `n` large enough, `diam(I_n) < r`, so `I_n ⊂ N_r(x*) ⊂ G_α`. This implies `I_n` *is* covered by a finite subcollection (just one `G_α`), which contradicts our construction. Therefore, every k-cell is compact [2.40, p. 99-100].
*   **Theorem 2.41 (Heine-Borel Theorem): If a set `E` in `R^k` has one of the following three properties, then it has the other two:** [2.41, p. 101]
    *   (a) `E` is closed and bounded.
    *   (b) `E` is compact.
    *   (c) Every infinite subset of `E` has a limit point in `E`.
    *   **Proof Sketch**:
        *   **(a) implies (b)**: If `E` is closed and bounded, `E` must be contained in some k-cell `I`. By Theorem 2.40, `I` is compact. Since `E` is a closed subset of a compact set, `E` is compact by Theorem 2.35 [2.41, p. 101].
        *   **(b) implies (c)**: This is exactly Theorem 2.37 [2.41, p. 101].
        *   **(c) implies (a)**:
            *   **`E` is closed**: Assume `E` satisfies (c). Let `x_0` be a limit point of `E`. Then there's a sequence of distinct points `{x_n}` in `E` converging to `x_0` (Theorem 3.2d). If `E` does not contain `x_0`, then `{x_n}` is an infinite subset of `E`. By (c), it must have a limit point `y ∈ E`. The only limit point of `{x_n}` is `x_0`. Thus `y = x_0`. But if `x_0 ∉ E`, this is a contradiction. Therefore, `E` must contain all its limit points, so `E` is closed [2.41, p. 102].
            *   **`E` is bounded**: Assume `E` is not bounded. Then there exists a sequence `{x_n}` in `E` such that `|x_n| > n` for all `n`. This sequence is infinite. By (c), it must have a limit point `x* ∈ E`. However, any neighborhood of `x*` cannot contain infinitely many points of `{x_n}` because the points are arbitrarily far apart. This contradicts `x*` being a limit point. Therefore, `E` must be bounded [2.41, p. 102].
*   **Theorem 2.42 (Weierstrass): Every bounded infinite subset of `R^k` has a limit point in `R^k`.** [2.42, p. 103]
    *   **Proof Sketch**: If `E` is bounded, it is a subset of some k-cell `I` in `R^k`. By Theorem 2.40, `I` is compact. Since `E` is an infinite subset of a compact set, by Theorem 2.37, `E` has a limit point in `I`, and thus in `R^k` [2.42, p. 103].

---

### 4. Perfect Sets

Perfect sets are a special type of closed set where every point is a limit point. They are particularly interesting in the study of cardinality.

**4.1. Key Theorem and Proof Sketch**

*   **Theorem 2.43: Let `P` be a nonempty perfect set in `R^k`. Then `P` is uncountable.** [2.43, p. 103-104]
    *   **Proof Sketch**: Proof by contradiction. Since `P` is perfect, it has limit points, so it must be infinite. Assume `P` is countable, and denote its points as `x_1, x_2, x_3, ...`. Construct a sequence of nested closed neighborhoods `V_n` (closures of open balls) and corresponding compact sets `K_n = V_n ∩ P` such that:
        1.  `V_{n+1} ⊂ V_n`
        2.  `x_n ∉ V_{n+1}` (so `x_n ∉ K_{n+1}`)
        3.  `K_n` is nonempty for all `n`.
        Since `P` is perfect, every point in `P` is a limit point of `P`, allowing us to always find a `V_{n+1}` inside `V_n` that avoids `x_n` and still contains points of `P`.
        The sets `K_n` are nonempty and compact (being closed subsets of `V_n`, which are compact, by 2.35). They are also nested: `K_n ⊃ K_{n+1}`. By the Corollary to Theorem 2.36, `⋂_n K_n` must be nonempty. However, by construction, `x_n ∉ K_{n+1}` for all `n`, which implies `x_n ∉ ⋂_k K_k` for all `n`. This contradicts the fact that `⋂_n K_n` is nonempty and is supposed to contain elements of `P` (since `K_n ⊂ P`). Therefore, the assumption that `P` is countable must be false, meaning `P` is uncountable [2.43, p. 103-104].
    *   **Corollary**: Every interval `[a, b]` (`a < b`) is uncountable. In particular, the set of all real numbers is uncountable. [2.43, p. 105]
        *   **Proof Sketch**: Any interval `[a,b]` is a nonempty perfect set in `R^1`. By Theorem 2.43, it is uncountable. The set of all real numbers is `(-∞, ∞)`, which contains any interval `[a,b]` and is therefore also uncountable [2.43, p. 105].

**4.2. Example: The Cantor Set** [2.44, p. 105-107]

*   The Cantor set `P` is a classic example of a perfect set in `R^1` that contains no segment.
*   **Construction**: Start with `E_0 =`. Remove the open middle third `(1/3, 2/3)` to get `E_1 = [0, 1/3] ∪ [2/3, 1]`. Continue this process for each remaining interval, removing its open middle third. `E_n` is the union of `2^n` intervals, each of length `3^{-n}`. The Cantor set `P = ⋂_{n=1}^∞ E_n`.
*   **Properties** [2.44, p. 106-107]:
    *   **Compact**: As an intersection of compact sets (`E_n` are compact), `P` is compact (Theorem 2.24b).
    *   **Nonempty**: By Corollary to Theorem 2.36 (since `E_n` are nonempty compact nested sets).
    *   **Contains no segment**: Each segment `(3k+1)/3^m, (3k+2)/3^m` is removed during construction. Since every segment `(a,b)` contains such a segment, `P` cannot contain any segment.
    *   **Perfect**: Show `P` has no isolated points. For any `x ∈ P` and any segment `S` containing `x`, choose `n` large enough so `I_n ⊂ S` where `I_n` is the interval of `E_n` containing `x`. An endpoint `x_n` of `I_n` (distinct from `x`) also belongs to `P`. Thus, `x` is a limit point of `P`. Since `P` is closed, `P` is perfect.
    *   **Uncountable**: As a nonempty perfect set, it is uncountable by Theorem 2.43.
    *   **Measure Zero**: The total length of intervals in `E_n` is `2^n * 3^{-n} = (2/3)^n`. As `n → ∞`, this length approaches 0, implying the Lebesgue measure of the Cantor set is zero.

---

### 5. Connected Sets

This section defines connectedness, which captures the intuitive idea of a "single piece" or "unbroken" set.

**5.1. Core Definitions**

*   **Separated Sets**: Two subsets `A` and `B` of a metric space `X` are *separated* if `A ∩ B` is empty and `A ∩ B` is empty [2.45, p. 108]. That is, no point of `A` lies in the closure of `B`, and no point of `B` lies in the closure of `A` [2.45, p. 108].
    *   **Remark**: Separated sets are necessarily disjoint, but disjoint sets are not necessarily separated (e.g., `` and `(1, 2)` are disjoint but not separated because `1` is a limit point of `(1, 2)` and is in ``). However, `(0, 1)` and `(1, 2)` are separated [2.46, p. 108].
*   **Connected Set**: A set `E ⊂ X` is *connected* if `E` is not a union of two nonempty separated sets [2.45, p. 108].

**5.2. Key Theorem and Proof Sketch**

*   **Theorem 2.47: A subset `E` of the real line `R^1` is connected if and only if it has the following property: If `x ∈ E`, `y ∈ E`, and `x < z < y`, then `z ∈ E`.** [2.47, p. 109-110]
    *   **Proof Sketch**:
        *   **(If `E` is connected implies property holds)**: Proof by contradiction. Assume `E` is connected but the property fails. So there exist `x, y ∈ E` with `x < y` and some `z` such that `x < z < y` but `z ∉ E`. Define `A_z = E ∩ (-∞, z)` and `B_z = E ∩ (z, ∞)`. Since `x ∈ A_z` and `y ∈ B_z`, `A_z` and `B_z` are nonempty. It is straightforward to show that `A_z` and `B_z` are separated (as `A_z ⊂ (-∞, z)` and `B_z ⊂ (z, ∞)`, their closures are disjoint except possibly at `z`, which is not in `E`). Thus `E = A_z ∪ B_z` is a union of two nonempty separated sets, contradicting `E` being connected [2.47, p. 109-110].
        *   **(If property holds implies `E` is connected)**: Proof by contradiction. Assume `E` has the property but is not connected. Then `E = A ∪ B` where `A` and `B` are nonempty separated sets. Pick `x ∈ A` and `y ∈ B`. Without loss of generality, assume `x < y`. Define `z = sup(A ∩ [x, y])`. By Theorem 2.28, `z ∈ A` (since `A` is a subset of `E`, which is metric, and `A ∩ [x,y]` is bounded). Since `A` and `B` are separated, `z ∉ B`. As `z ∈ A` and `y ∈ B` (and `A ∩ B = ∅`), we must have `z < y`. Also `x ≤ z`. If `z ∉ E`, then `x < z < y` with `z ∉ E`, which contradicts the given property. If `z ∈ E`, then `z ∈ A`. Since `A` and `B` are separated, `z` is not a limit point of `B`. This means there exists a neighborhood `N_δ(z)` such that `N_δ(z) ∩ B = ∅`. Since `z ∈ A`, and `y ∈ B` with `z < y`, the interval `(z, y)` must contain elements of `B` if `E` has the specified property. This is a contradiction. The detailed argument (in Rudin) shows that a point `z` (or `z_1` slightly larger than `z`) will fall outside `E`, contradicting the property [2.47, p. 110].

***