Here are detailed revision notes on Chapter 3: "Elements of Probability", drawing from the provided sources:

**Chapter 3: Elements of Probability**

This chapter introduces the fundamental concepts of probability theory, including the definition of sample spaces, events, axioms of probability, and methods for calculating probabilities, especially in scenarios with equally likely outcomes. It also delves into the crucial concepts of conditional probability and independent events, which are essential for understanding statistical inference.

### 3.2 Sample Space and Events

*   **Experiment**: An activity whose outcome is not predictable with certainty in advance.
*   **Sample Space (S)**: The set of all possible outcomes of an experiment.
    *   *Example*: For determining the sex of a newborn child, S = {g, b} (girl, boy).
*   **Event**: Any subset of the sample space. An event occurs if the outcome of the experiment is contained in that subset.
*   **Union (E ∪ F)**: The event consisting of all outcomes that are in E or in F or in both E and F. The event E ∪ F occurs if E occurs, or F occurs, or both occur.
*   **Intersection (EF or E ∩ F)**: The event consisting of all outcomes that are in both E and F. The event EF will occur only if both E and F occur.
*   **Null Event (∅)**: An event that contains no outcomes and hence cannot occur.
*   **Mutually Exclusive Events**: Two events E and F are mutually exclusive if their intersection is the null event (EF = ∅), implying they cannot both occur.
*   **Complement (Ec)**: For any event E, Ec consists of all outcomes in the sample space S that are not in E. Ec occurs if and only if E does not occur.
    *   *Note*: Sc = ∅.
*   **Subset (E ⊂ F)**: If all outcomes in E are also in F, then E is contained in F. The occurrence of E necessarily implies the occurrence of F.
*   **Equality (E = F)**: E and F are equal if E ⊂ F and F ⊂ E.

### 3.3 Venn Diagrams and the Algebra of Events

*   **Venn Diagram**: A graphical representation where the sample space S is a large rectangle, and events are represented as circles within it. Shaded regions indicate events of interest.
    *   *Example*: Shaded regions can represent E ∪ F, EF, or Ec.
*   **Laws of Event Algebra**:
    *   **Commutative Law**:
        *   E ∪ F = F ∪ E
        *   EF = FE
    *   **Associative Law**:
        *   (E ∪ F) ∪ G = E ∪ (F ∪ G)
        *   (EF)G = E(FG)
    *   **Distributive Law**:
        *   (E ∪ F)G = EG ∪ FG
        *   EF ∪ G = (E ∪ G)(F ∪ G)
        *   *Proof Sketch*: Verified by showing that any outcome in the left side is in the right side, and vice versa, often using Venn diagrams.
    *   **DeMorgan’s Laws**:
        *   (E ∪ F)c = EcFc
        *   (EF)c = Ec ∪ Fc

### 3.4 Axioms of Probability

The concept of probability is interpreted as a **constant limiting frequency** of an event when an experiment is continually repeated under the same conditions.
*   For each event E of an experiment, there is a number **P(E)** that adheres to the following axioms:
    *   **Axiom 1**: **0 ≤ P(E) ≤ 1**. (The probability of an event is between 0 and 1.)
    *   **Axiom 2**: **P(S) = 1**. (The outcome will be a member of the sample space with probability 1.)
    *   **Axiom 3**: For any sequence of mutually exclusive events E1, E2, ... (where EiEj = ∅ when i ≠ j):
        *   **P(⋃i=1 to n Ei) = ∑i=1 to n P(Ei)** for n = 1, 2, ..., ∞. (The probability that at least one of these events occurs is the sum of their probabilities.)

*   **Proposition 3.4.1**: **P(Ec) = 1 − P(E)**.
    *   **Proof Sketch**: E and Ec are mutually exclusive events, and their union is the sample space S (E ∪ Ec = S). By Axiom 3, P(E ∪ Ec) = P(E) + P(Ec). By Axiom 2, P(S) = 1. Therefore, 1 = P(E) + P(Ec), which implies P(Ec) = 1 - P(E).
*   **Proposition 3.4.2**: **P(E ∪ F) = P(E) + P(F) − P(EF)**.
    *   **Proof Sketch**: Using a Venn diagram, E ∪ F can be divided into three mutually exclusive regions: I (E and not F), II (E and F), and III (F and not E).
        *   P(E ∪ F) = P(I) + P(II) + P(III).
        *   P(E) = P(I) + P(II).
        *   P(F) = P(II) + P(III).
        *   Substitute to get P(E ∪ F) = P(E) + P(F) - P(II). Since region II is EF, the result follows.
*   **Odds of an event A**: Defined as **P(A) / P(Ac) = P(A) / (1 − P(A))**. It indicates how much more likely A is to occur than not to occur.

### 3.5 Sample Spaces Having Equally Likely Outcomes

*   **Assumption**: For a finite sample space S = {1, 2, ..., N}, each outcome is equally likely, meaning **P({i}) = 1/N** for all i.
*   **Probability Calculation**: For any event E, **P(E) = (Number of points in E) / N**.
*   **Basic Principle of Counting**: If experiment 1 has *m* outcomes, and for each outcome of experiment 1, experiment 2 has *n* outcomes, then there are **mn** total possible outcomes of the two experiments.
    *   **Proof Sketch**: Outcomes can be enumerated as (i, j) pairs, forming a matrix with *m* rows and *n* columns, totaling *mn* elements.
*   **Generalized Basic Principle of Counting**: If *r* experiments are performed sequentially, and the *k*-th experiment has *nk* outcomes regardless of prior outcomes, then there are a total of **n1 · n2 · · · nr** possible outcomes.
*   **Permutations**: The number of different ordered arrangements of *n* distinct objects is **n!** (n factorial), where n! = n(n-1)...(2)(1) and 0! = 1.
*   **Combinations**: The number of ways to choose *k* items from a set of *n* items is denoted by **(n k)** (n choose k).

### 3.6 Conditional Probability

*   **Conditional Probability (P(E | F))**: The probability of event E occurring given that event F has already occurred. It is defined as **P(E | F) = P(EF) / P(F)**, provided that P(F) > 0.
    *   **Interpretation**: If F occurs, F becomes the new sample space. For E to occur, the outcome must be in EF. The probability of EF relative to F is P(EF)/P(F). This is consistent with the long-run relative frequency interpretation.
*   **Multiplication Rule**: Derived from the definition of conditional probability, it states that the probability that both E and F occur is **P(EF) = P(F)P(E | F)**.

### 3.7 Bayes’ Formula

*   **Decomposition of an Event**: Any event E can be expressed as the union of two mutually exclusive events: **E = EF ∪ EFc**.
*   **Law of Total Probability**: This formula is used to compute P(E) by conditioning on whether or not another event F has occurred:
    *   **P(E) = P(EF) + P(EFc) = P(E | F)P(F) + P(E | Fc)[1 − P(F)]**.
    *   **Generalization**: If F1, F2, ..., Fn are mutually exclusive events such that their union is S (i.e., they form a partition of S), then:
        *   **P(E) = ∑i=1 to n P(EFi) = ∑i=1 to n P(E | Fi)P(Fi)**.
*   **Bayes’ Formula**: Used to re-evaluate an initial probability assessment (prior) in light of new information (evidence). If E has occurred, the conditional probability of Fj is:
    *   **P(Fj | E) = [P(E | Fj)P(Fj)] / [∑i=1 to n P(E | Fi)P(Fi)]**.
    *   **Interpretation**: Bayes' formula shows how **opinions about hypotheses P(Fj)** held *before* an experiment are modified by the evidence of the experiment to yield **posterior probabilities P(Fj | E)**.

### 3.8 Independent Events

*   **Definition**: Two events E and F are **independent** if knowledge that F has occurred does not change the probability that E occurs. Mathematically, **P(E | F) = P(E)**. This definition implies and is equivalent to **P(EF) = P(E)P(F)**.
    *   **Symmetry**: If E is independent of F, then F is independent of E.
    *   **Dependent Events**: Events that are not independent are said to be dependent.
*   **Proposition 3.8.1**: If E and F are independent, then E and Fc are also independent.
    *   **Proof Sketch**: Since E = EF ∪ EFc (mutually exclusive events), P(E) = P(EF) + P(EFc). Given E and F are independent, P(EF) = P(E)P(F). Substituting this yields P(E) = P(E)P(F) + P(EFc), which simplifies to P(EFc) = P(E)(1 - P(F)) = P(E)P(Fc). This shows E and Fc are independent.
*   **Independence of Multiple Events**:
    *   E, F, and G are **independent** if all pairwise independence conditions hold (P(EF) = P(E)P(F), P(EG) = P(E)P(G), P(FG) = P(F)P(G)) AND **P(EFG) = P(E)P(F)P(G)**.
    *   **Generalization**: Events E1, E2, ..., En are independent if for every subset of these events, the probability of their intersection is the product of their individual probabilities.
*   **Independent Subexperiments**: When a probability experiment consists of a sequence of subexperiments, and the outcomes of any group of subexperiments have no effect on the probabilities of outcomes of other subexperiments, the subexperiments are independent.
    *   *Example*: For a parallel system of *n* independent components, where component *i* functions with probability *pi*, the probability that the system functions (at least one component functions) is **1 − ∏i=1 to n (1 − pi)**.