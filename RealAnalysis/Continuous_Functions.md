
### Chapter 3: Continuous Functions

#### 3.1 Limits of functions

*   **Cluster Point:**
    *   A point **c** is a **cluster point** of a set *S* ⊂ ℝ if for every *ϵ* > 0, the set *B*(*c*, *ϵ*) ∩ *S* \ {*c*} is not empty. This means there are points of *S* arbitrarily close to *c*, other than *c* itself.

*   **Definition of Limit of a Function:**
    *   Let *f* : *S* → ℝ be a function and *c* a cluster point of *S* ⊂ ℝ. *f*(*x*) converges to a number **L** ∈ ℝ as *x* goes to *c* if for every *ϵ* > 0, there exists a *δ* > 0 such that whenever *x* ∈ *S* \ {*c*} and |*x* - *c*| < *δ*, we have |*f*(*x*) - *L*| < *ϵ*.
    *   If such an *L* exists and is unique, we write **lim*ₓ→*c* *f*(*x*) = *L***.

*   **Uniqueness of the Limit:**
    *   If *f*(*x*) converges as *x* goes to *c*, the limit *L* is **unique**.

*   **Sequential Limits and Function Limits (Lemma 3.1.7):**
    *   **f*(*x*) → *L* as *x* → *c*** if and only if for every sequence {*x*ₙ}∞ₙ₌₁ such that *x*ₙ ∈ *S* \ {*c*} for all *n* and lim*ₙ→∞* *x*ₙ = *c*, the sequence {*f*(*x*ₙ)}∞ₙ₌₁ converges to *L*.

*   **Properties of Limits (Corollaries 3.1.9, 3.1.10, 3.1.11, 3.1.12, 3.1.13):**
    *   **Inequalities:** If *f*(*x*) ≤ *g*(*x*) for all *x* ∈ *S* \ {*c*} and their limits exist, then **lim*ₓ→*c* *f*(*x*) ≤ lim*ₓ→*c* *g*(*x*)**.
    *   **Boundedness:** If *a* ≤ *f*(*x*) ≤ *b* for all *x* ∈ *S* \ {*c*} and lim*ₓ→*c* *f*(*x*) exists, then **a ≤ lim*ₓ→*c* *f*(*x*) ≤ b**.
    *   **Squeeze Lemma (Sandwich Theorem):** If *f*(*x*) ≤ *g*(*x*) ≤ *h*(*x*) for all *x* ∈ *S* \ {*c*}, and lim*ₓ→*c* *f*(*x*) = lim*ₓ→*c* *h*(*x*), then **lim*ₓ→*c* *g*(*x*) also exists and equals the same limit**.
    *   **Algebra of Limits:** If lim*ₓ→*c* *f*(*x*) and lim*ₓ→*c* *g*(*x*) both exist, then:
        *   lim*ₓ→*c* (*f*(*x*) + *g*(*x*)) = (lim*ₓ→*c* *f*(*x*)) + (lim*ₓ→*c* *g*(*x*)).
        *   lim*ₓ→*c* (*f*(*x*) - *g*(*x*)) = (lim*ₓ→*c* *f*(*x*)) - (lim*ₓ→*c* *g*(*x*)).
        *   lim*ₓ→*c* (*f*(*x*)*g*(*x*)) = (lim*ₓ→*c* *f*(*x*)) (lim*ₓ→*c* *g*(*x*)).
        *   If lim*ₓ→*c* *g*(*x*) ≠ 0 and *g*(*x*) ≠ 0 for all *x* ∈ *S* \ {*c*}, then lim*ₓ→*c* (*f*(*x*)/ *g*(*x*)) = (lim*ₓ→*c* *f*(*x*)) / (lim*ₓ→*c* *g*(*x*)).
    *   **Absolute Value:** If lim*ₓ→*c* *f*(*x*) exists, then **lim*ₓ→*c* |*f*(*x*)| = |lim*ₓ→*c* *f*(*x*)|**.

*   **One-Sided Limits (Proposition 3.1.17):**
    *   A limit at *c* exists if and only if **both one-sided limits (lim*ₓ→*c*⁻ *f*(*x*) and lim*ₓ→*c*⁺ *f*(*x*)) exist and are equal** to *L*.

#### 3.2 Continuous functions

*   **Definition of Continuity at a Point:**
    *   A function *f* : *S* → ℝ is **continuous at c ∈ S** if for every *ϵ* > 0, there exists a *δ* > 0 such that whenever *x* ∈ *S* and |*x* - *c*| < *δ*, we have **|*f*(*x*) - *f*(*c*)| < *ϵ***.
    *   If *f* is continuous at all *c* ∈ *S*, then *f* is a **continuous function**.

*   **Relationship between Continuity, Cluster Points, and Sequential Limits (Proposition 3.2.2):**
    *   If *c* is not a cluster point of *S*, then *f* is **automatically continuous at c**.
    *   If *c* is a cluster point of *S*, then *f* is continuous at *c* if and only if **lim*ₓ→*c* *f*(*x*) exists and equals *f*(*c*)**.
    *   *f* is continuous at *c* if and only if for every sequence {*x*ₙ}∞ₙ₌₁ where *x*ₙ ∈ *S* and lim*ₙ→∞* *x*ₙ = *c*, the sequence **{*f*(*x*ₙ)}∞ₙ₌₁ converges to *f*(*c*)**.

*   **Continuity of Common Functions:**
    *   **Polynomials** are continuous functions.
    *   **sin(*x*) and cos(*x*)** are continuous functions.
    *   The function *f*(*x*) = 1/*x* is continuous on (0,∞).

*   **Properties of Continuous Functions (Proposition 3.2.5):**
    *   If *f* and *g* are continuous at *c* ∈ *S*, then:
        *   **f* + *g*** is continuous at *c*.
        *   **f* - *g*** is continuous at *c*.
        *   **f*g*** is continuous at *c*.
        *   If *g*(*x*) ≠ 0 for all *x* ∈ *S*, then **f*/*g*** is continuous at *c*.

*   **Composition of Continuous Functions (Proposition 3.2.7):**
    *   If *g* : *A* → *B* is continuous at *c* ∈ *A* and *f* : *B* → ℝ is continuous at *g*(*c*), then the **composition *f* ◦ *g* : *A* → ℝ is continuous at *c***.

*   **Discontinuous Functions:**
    *   A function *f* is **discontinuous at c** if there exists a sequence {*x*ₙ}∞ₙ₌₁ in *S* such that lim*ₙ→∞* *x*ₙ = *c* but {*f*(*x*ₙ)}∞ₙ₌₁ does not converge to *f*(*c*).
    *   **Dirichlet function** (1 if *x* is rational, 0 if *x* is irrational) is discontinuous at all *c* ∈ ℝ.
    *   **Thomae function (popcorn function)** is continuous at all irrational numbers and discontinuous at all rational numbers.
    *   A **removable discontinuity** occurs if lim*ₓ→*c* *f*(*x*) exists but is not equal to *f*(*c*) (or *f*(*c*) is undefined).

#### 3.3 Extreme and intermediate value theorems

*   **Boundedness of Continuous Functions (Lemma 3.3.1):**
    *   A **continuous function *f* : [a, b] → ℝ is bounded** on the closed and bounded interval [a, b].

*   **Absolute Minimum and Maximum:**
    *   *f* achieves an **absolute minimum** at *c* ∈ *S* if *f*(*x*) ≥ *f*(*c*) for all *x* ∈ *S*.
    *   *f* achieves an **absolute maximum** at *c* ∈ *S* if *f*(*x*) ≤ *f*(*c*) for all *x* ∈ *S*.

*   **Minimum-Maximum Theorem / Extreme Value Theorem (Theorem 3.3.2):**
    *   A **continuous function *f* : [a, b] → ℝ achieves both an absolute minimum and an absolute maximum on [a, b]**.
    *   This theorem relies on the interval being **closed and bounded** and the function being **continuous**.

*   **Bolzano’s Intermediate Value Theorem (Lemma 3.3.7, Theorem 3.3.8):**
    *   **Lemma:** If *f* : [a, b] → ℝ is a continuous function such that *f*(*a*) < 0 and *f*(*b*) > 0, then there exists a number **c ∈ (a, b) such that *f*(*c*) = 0**.
    *   **Theorem:** If *f* : [a, b] → ℝ is a continuous function and *y* ∈ ℝ is such that *f*(*a*) < *y* < *f*(*b*) or *f*(*a*) > *y* > *f*(*b*), then there exists a **c ∈ (a, b) such that *f*(*c*) = *y***.
    *   This theorem states that a continuous function on a closed interval takes on **all values between its endpoint values**.
    *   The proof method (bisection method) is also a practical numerical technique for finding roots.

*   **Image of a Continuous Function (Corollary 3.3.13):**
    *   If *f* : [a, b] → ℝ is continuous, then the **direct image *f*([a, b]) is a closed and bounded interval or a single number**.

#### 3.4 Uniform continuity

*   **Definition of Uniform Continuity:**
    *   A function *f* : *S* → ℝ is **uniformly continuous** if for every *ϵ* > 0 there exists a *δ* > 0 such that whenever *x*, *c* ∈ *S* and |*x* - *c*| < *δ*, then **|*f*(*x*) - *f*(*c*)| < *ϵ***.
    *   The key difference from continuity is that *δ* depends **only on *ϵ***, not on the specific point *c*.

*   **Continuous vs. Uniformly Continuous:**
    *   A uniformly continuous function is always continuous.
    *   The converse is not always true; for example, *f*(*x*) = *x*² is uniformly continuous on but not on ℝ, and *f*(*x*) = 1/*x* is continuous but not uniformly continuous on (0, 1).

*   **Theorem 3.4.4:**
    *   Let *f* : [a, b] → ℝ be a continuous function. Then **f is uniformly continuous**.
    *   This theorem is crucial and relies on the domain being a **closed and bounded interval**.

*   **Continuous Extension (Proposition 3.4.6):**
    *   A function *f* : (*a*, *b*) → ℝ is uniformly continuous if and only if the limits **L*a* = lim*ₓ→*a*⁺ *f*(*x*) and L*b* = lim*ₓ→*b*⁻ *f*(*x*) exist**, and the extended function *f̃* on [*a*, *b*] is continuous.
    *   Uniformly continuous functions **preserve Cauchy sequences**: If {*x*ₙ}∞ₙ₌₁ is a Cauchy sequence in *S* and *f* : *S* → ℝ is uniformly continuous, then {*f*(*x*ₙ)}∞ₙ₌₁ is also a Cauchy sequence.

*   **Lipschitz Continuous Functions:**
    *   A function *f* : *S* → ℝ is **Lipschitz continuous** if there exists a *K* ∈ ℝ, such that **|*f*(*x*) - *f*(*y*)| ≤ *K*|*x* - *y*|** for all *x* and *y* in *S*.
    *   A Lipschitz continuous function is **uniformly continuous**.
    *   Examples: sin(*x*) and cos(*x*) are Lipschitz with *K* = 1. *f*(*x*) = √*x* is Lipschitz on [1,∞) but not on (0,∞), though it is uniformly continuous on [0,∞).

#### 3.5 Limits at infinity

*   **Cluster Points at Infinity:**
    *   **∞** is a cluster point of *S* ⊂ ℝ if for every *M* ∈ ℝ, there exists an *x* ∈ *S* such that *x* ≥ *M*.
    *   **-∞** is a cluster point of *S* ⊂ ℝ if for every *M* ∈ ℝ, there exists an *x* ∈ *S* such that *x* ≤ *M*.

*   **Limits at Infinity (Definition 3.5.1):**
    *   *f*(*x*) converges to *L* ∈ ℝ as *x* goes to **∞** if for every *ϵ* > 0, there is an *M* ∈ ℝ such that |*f*(*x*) - *L*| < *ϵ* whenever *x* ∈ *S* and *x* ≥ *M*. We write **lim*ₓ→∞* *f*(*x*) = *L***.
    *   Similar definitions apply for *x* → -∞.
    *   The limit at ∞ or -∞, if it exists, is unique.

*   **Sequential Limits and Limits at Infinity (Lemma 3.5.5):**
    *   **lim*ₓ→∞* *f*(*x*) = *L*** if and only if **lim*ₙ→∞* *f*(*x*ₙ) = *L*** for all sequences {*x*ₙ}∞ₙ₌₁ in *S* such that lim*ₙ→∞* *x*ₙ = ∞.

*   **Infinite Limits (Definition 3.5.6):**
    *   *f*(*x*) **diverges to infinity** (lim*ₓ→∞* *f*(*x*) = ∞) if for every *N* ∈ ℝ there exists an *M* ∈ ℝ such that *f*(*x*) > *N* whenever *x* ∈ *S* and *x* ≥ *M*.
    *   Similar definitions exist for divergence to -∞.

*   **Composition of Functions with Infinite Limits (Proposition 3.5.8):**
    *   If lim*ₓ→*a* *f*(*x*) = *b* and lim*y*→*b* *g*(*y*) = *c* (where *a*, *b*, *c* can be finite or infinite), and if *b* is in the domain of *g*, *g* is continuous at *b*, then **lim*ₓ→*a* *g*(*f*(*x*)) = *c***.

#### 3.6 Monotone functions and continuity

*   **Monotone Functions (Definition 3.6.1):**
    *   *f* : *S* → ℝ is **increasing** if *x* < *y* implies *f*(*x*) ≤ *f*(*y*).
    *   *f* : *S* → ℝ is **strictly increasing** if *x* < *y* implies *f*(*x*) < *f*(*y*).
    *   **Decreasing** and **strictly decreasing** are defined analogously.
    *   A function is **monotone** if it is either increasing or decreasing. It is **strictly monotone** if it is strictly increasing or strictly decreasing.

*   **One-Sided Limits for Monotone Functions (Proposition 3.6.2):**
    *   For a monotone function, one-sided limits (including limits at ±∞) **always exist** where they make sense (i.e., if the point is a cluster point for the relevant side of the domain). For example, if *f* is increasing and *c* is a cluster point of *S* ∩ (-∞, *c*), then **lim*ₓ→*c*⁻ *f*(*x*) = sup{*f*(*x*) : *x* < *c*, *x* ∈ *S*}**.

*   **Continuity and Image of Monotone Functions (Corollary 3.6.3):**
    *   If *I* ⊂ ℝ is an interval and *f* : *I* → ℝ is monotone and not constant, then **f*(*I*) is an interval if and only if *f* is continuous**.
    *   Discontinuities of monotone functions create "gaps" in the image, preventing it from being an interval.

*   **Countability of Discontinuities (Corollary 3.6.4):**
    *   Let *I* ⊂ ℝ be an interval and *f* : *I* → ℝ be monotone. Then **f has at most countably many discontinuities**. This is a significant result showing that monotone functions are "almost" continuous.

*   **Continuity of Inverse Functions (Proposition 3.6.6):**
    *   If *I* ⊂ ℝ is an interval and *f* : *I* → ℝ is **strictly monotone**, then the **inverse *f*⁻¹ : *f*(*I*) → *I* is continuous**.
    *   Note that *f* itself does not need to be continuous for its inverse to be continuous if *f* is strictly monotone and its image *f*(*I*) is also an interval.