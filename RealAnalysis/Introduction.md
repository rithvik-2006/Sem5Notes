Here are brief revision notes on Chapter 0: "Introduction" from *Basic Analysis I: Introduction to Real Analysis, Volume I* by Jiří Lebl.

### Chapter 0: Introduction

This foundational chapter sets the stage for the rigorous study of real analysis, outlining the book's purpose and the fundamental mathematical language needed.

#### 0.1 About this book
*   **Purpose**: This first volume is designed for a **one-semester basic analysis course**. Combined with Volume II, it forms a year-long course. The primary goal is to familiarise the reader with **rigorous proofs in analysis** and to establish a **firm foundation for calculus of one variable**. It aims to explain "why calculus is true" by providing a deep understanding of concepts like limits, derivatives, and integrals.
*   **Origin & Structure**: The book originated from lecture notes for Math 444 at UIUC (University of Illinois at Urbana-Champaign) in 2009. The metric space chapter was added for Math 521 at UW (University of Wisconsin–Madison). Its initial chapters somewhat mirror the UIUC Math 444 syllabus and share similarities with Bartle and Sherbert's *Introduction to Real Analysis*.
*   **Distinctions**: A notable difference from some other texts (like Bartle and Sherbert) is the definition of the Riemann integral using **Darboux sums** instead of tagged partitions, which the author considers more appropriate for this level.
*   **Prerequisites**: A basic proof course is typically a prerequisite.
*   **Licensing**: The book is dual licensed under Creative Commons Attribution-Noncommercial-Share Alike 4.0 International and Creative Commons Attribution-Share Alike 4.0 International licenses. This allows users to use, print, duplicate, share, and base derivative works on the book, provided the license is maintained and derivative works are marked.

#### 0.2 About analysis
*   **Definition**: Analysis is the branch of mathematics that deals primarily with **inequalities and limits**.
*   **Core Goal**: The course aims to teach **rigorous proofs in analysis** and to build a strong foundation for single-variable calculus.
*   **Contrast with Calculus**: Calculus focuses on *using* mathematics without necessarily explaining *why* it is true. Analysis provides this understanding.
*   **Key Approach**: In analysis, proving equalities (e.g., *x* = 0) often involves proving two inequalities (e.g., *x* ≤ 𝜖 for all 𝜖 > 0, which implies *x* ≤ 0, and *x* ≥ -𝜖 for all 𝜖 > 0, which implies *x* ≥ 0).
*   **Content Flow**: The course starts with the real number system and its completeness, then progresses to limits of sequences, functions, continuity, derivatives, the Riemann integral, sequences of functions, and finally, an introduction to metric spaces.

#### 0.3 Basic set theory
*   **Informal Approach**: The book uses "naïve set theory," an informal approach to sets that is commonly used by mathematicians.
*   **Fundamental Definitions**:
    *   **Set**: A collection of objects (elements or members).
    *   **Empty Set (∅ or {})**: A set with no objects.
    *   **Equality of Sets (A = B)**: Two sets are equal if they contain exactly the same elements.
    *   **Subset (A ⊂ B)**: Every member of A is also a member of B.
    *   **Proper Subset (A ⊊ B)**: A ⊂ B and A ≠ B.
    *   **Universe**: The overarching set from which all elements under consideration come (often ℝ in this course).
    *   **Set-builder notation ({x ∈ A : P(x)})**: Defines a subset of A containing elements satisfying property P(x).
*   **Standard Number Sets**:
    *   **Natural Numbers (ℕ)**: {1, 2, 3, ...}.
    *   **Integers (ℤ)**: {0, -1, 1, -2, 2, ...}.
    *   **Rational Numbers (ℚ)**: {m/n : m, n ∈ ℤ and n ≠ 0}.
    *   **Real Numbers (ℝ)**: The subject of the book.
    *   **Inclusion**: ℕ ⊂ ℤ ⊂ ℚ ⊂ ℝ.
*   **Set Operations**:
    *   **Union (A ∪ B)**: Elements in A or B (or both).
    *   **Intersection (A ∩ B)**: Elements in both A and B.
    *   **Complement relative to A (A \ B)**: Elements in A but not in B.
    *   **Complement (Bᶜ)**: Elements not in B, understood from context (e.g., ℝ \ B).
    *   **Disjoint Sets**: A and B are disjoint if A ∩ B = ∅.
*   **Mathematical Induction**: A proof technique to show a statement P(n) is true for all natural numbers n, by proving a basis statement (P(1) is true) and an induction step (if P(n) is true, then P(n+1) is true). Strong induction is a variation where P(n+1) is proved assuming P(k) is true for all k = 1, 2, ..., n.
*   **Functions**:
    *   **Definition**: A mapping from a set A (domain) to a set B (codomain), assigning a unique y ∈ B to each x ∈ A. Written as f: A → B.
    *   **Cartesian Product (A × B)**: Set of ordered pairs (x, y) where x ∈ A, y ∈ B. Used for rigorous function definition.
    *   **Direct Image (f(A))**: The set of all f(x) for x ∈ A.
    *   **Inverse Image (f⁻¹(C))**: The set of all x ∈ A such that f(x) ∈ C. Useful properties for inverse images of unions, intersections, and complements.
    *   **Injective (One-to-one)**: f(x₁) = f(x₂) implies x₁ = x₂.
*   **Relations**:
    *   **Binary Relation**: A subset R ⊂ A × A, where (a, b) ∈ R means a R b.
    *   **Equivalence Relation**: A binary relation that is **reflexive** (a R a), **symmetric** (a R b implies b R a), and **transitive** (a R b and b R c implies a R c).
    *   **Equivalence Class ([a])**: The set of all elements related to 'a'.
*   **Cardinality ("Size" of Sets)**:
    *   **Same Cardinality (|A| = |B|)**: Exists a **bijection** (one-to-one and onto function) between A and B.
    *   **Finite Set**: Has the same cardinality as {1, 2, ..., n} for some n ∈ ℕ, or is empty.
    *   **Infinite Set**: Not finite.
    *   **Countable Set**: Has the same cardinality as ℕ (countably infinite) or is finite.
        *   **Examples**: ℕ × ℕ is countable. The set of rational numbers (ℚ) is countable.
    *   **Uncountable Set**: Not countable.
        *   **Example**: The set of real numbers (ℝ) is **uncountable**. This is a key result shown using Cantor's diagonalization argument.
*   **Important Concepts/Theorems Mentioned**: Archimedean property (related to Density of Rational Numbers), uniqueness of real numbers with least-upper-bound property, Cantor-Bernstein-Schröder theorem (stated without proof).