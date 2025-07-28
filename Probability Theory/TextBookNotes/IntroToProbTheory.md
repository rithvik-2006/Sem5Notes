Here are detailed revision notes on the specified topics from "Introduction to Probability Theory":

### 1 Introduction to Probability Theory

This chapter introduces **elementary probability theory** and **stochastic processes**, particularly showing how probability theory can be applied in various fields like engineering, computer science, management science, and the physical, social, and operations research sciences. The text employs a **heuristic and nonrigorous approach** to develop an intuitive understanding, emphasizing the ability to "think probabilistically". Chapters 1 and 2 lay out the basic ideas, with Chapter 1 establishing an **axiomatic framework**.

### 1.1 Introduction

Any realistic model of a real-world phenomenon must account for **randomness**. Quantities of interest are often not predictable in advance but exhibit inherent variation, which is incorporated into the model by making it **probabilistic in nature**, leading to what is called a **probability model**. Mastering these models requires fundamental knowledge of basic probability theory, which is the focus of this chapter and the subsequent two.

### 1.2 Sample Space and Events

*   **Sample Space (S)**: This is the **set of all possible outcomes of an experiment** whose outcome is not predictable in advance, but whose set of possible outcomes is known.
    *   *Examples*:
        *   Flipping a coin: **S = {H, T}** (Head or Tail).
        *   Rolling a die: **S = {1, 2, 3, 4, 5, 6}**.
        *   Flipping two coins: **S = {(H, H), (H, T), (T, H), (T, T)}**.
        *   Rolling two dice: S consists of 36 points, e.g., (1,1) to (6,6).
*   **Event (E)**: An **event is any subset of the sample space S**. An event E is said to **occur when the outcome of the experiment lies in E**.
    *   *Examples*:
        *   From S = {H, T}: **E = {H}** (a head appears).
        *   From S = {1, 2, 3, 4, 5, 6}: **E = {2, 4, 6}** (an even number appears).
        *   From S = {(H, H), (H, T), (T, H), (T, T)}: **E = {(H, H), (H, T)}** (a head appears on the first coin).
        *   From rolling two dice: **E = {(1, 6), (2, 5), (3, 4), (4, 3), (5, 2), (6, 1)}** (sum of dice equals seven).
*   **Operations on Events**:
    *   **Union (E ∪ F)**: Consists of all outcomes that are **either in E or in F or in both E and F**. The event E ∪ F will occur if either E or F occurs.
        *   *Example*: If E = {1, 3, 5} and F = {1, 2, 3} (from rolling a die), then **E ∪ F = {1, 2, 3, 5}**.
    *   **Intersection (EF or E ∩ F)**: Consists of all outcomes that are **both in E and in F**. The event EF will occur only if both E and F occur.
        *   *Example*: If E = {1, 3, 5} and F = {1, 2, 3}, then **EF = {1, 3}**.
    *   **Complement (Ec)**: Consists of all outcomes in the sample space S that are **not in E**. Ec will occur if and only if E does not occur.
        *   *Example*: If E is the event that the sum of two dice equals seven, then **Ec occurs if the sum does not equal seven**.
    *   **Mutually Exclusive Events**: Events E and F are mutually exclusive if their intersection is empty (EF = Ø).

### 1.3 Probabilities Defined on Events

For each event E of the sample space S, a number P(E), called the **probability of the event E**, is defined and must satisfy three conditions (axioms):
*   **(i) 0 ≤ P(E) ≤ 1**: The probability of any event is a non-negative number between 0 and 1, inclusive.
*   **(ii) P(S) = 1**: The probability of the entire sample space (that some outcome occurs) is 1.
*   **(iii) For any sequence of mutually exclusive events E1, E2, ...**:
    **P(⋃∞ n=1 En) = ∑∞ n=1 P(En)**. The probability of the union of any sequence of mutually exclusive events is the sum of their individual probabilities.

*   **Intuitive Property**: If an experiment is repeated many times, the **proportion of time that event E occurs will (with probability 1) be P(E)**.
*   **Derived Properties**:
    *   **Probability of a Complement**: Since E and Ec are mutually exclusive and E ∪ Ec = S, it follows that **P(Ec) = 1 − P(E)**. This means the probability that an event does not occur is one minus the probability that it does occur.
    *   **Inclusion-Exclusion Identity (for two events)**: The probability of the union of two events E and F is given by **P(E ∪ F) = P(E) + P(F) − P(EF)**. This accounts for outcomes in the intersection EF being counted twice in P(E) + P(F).
        *   *Example*: For two coin flips, P(first head or second head) = P(first head) + P(second head) - P(both heads) = 1/2 + 1/2 - 1/4 = 3/4.
    *   **Inclusion-Exclusion Identity (for three events)**:
        **P(E ∪ F ∪ G) = P(E) + P(F) + P(G) − P(EF) − P(EG) − P(FG) + P(EFG)**.
    *   **General Inclusion-Exclusion Identity (for n events)**:
        **P(E1 ∪ E2 ∪ · · · ∪ En) = ∑i P(Ei) − ∑i<j P(EiEj) + ∑i<j<k P(EiEjEk) − · · · + (−1)n+1P(E1E2 · · · En)**. This formula states that the probability of the union of n events is the sum of probabilities taken one at a time, minus sums taken two at a time, plus sums taken three at a time, and so on.

### 1.4 Conditional Probabilities

*   **Definition**: The **conditional probability of E given F**, denoted **P(E|F)**, is defined as the probability that E occurs given that F has occurred. It is calculated as:
    **P(E|F) = P(EF) / P(F)**, provided P(F) > 0.
    *   *Interpretation*: If F is known to have occurred, F becomes the new sample space. For E to occur, the outcome must be in EF. Thus, P(E|F) is the probability of EF relative to the probability of F.
    *   *Example*: If two fair dice are tossed, and the first die is a four (F), the conditional probability that the sum is six (E) is 1/6, because out of the 6 possible outcomes where the first die is a four, only (4,2) sums to six. Using the formula: P(EF) = P({(4,2)}) = 1/36, P(F) = P({(4,1), ..., (4,6)}) = 6/36. So P(E|F) = (1/36) / (6/36) = 1/6.
*   **Multiplication Rule**: From the definition, we can also write **P(EF) = P(F)P(E|F)**. This is useful for calculating the probability of both events occurring.
    *   *Example*: Drawing two black balls from an urn (7 black, 5 white) without replacement. P(first black and second black) = P(first black) * P(second black | first black) = (7/12) * (6/11) = 42/132.
*   **Law of Total Probability**: If F is an event, we can express the probability of any event E as:
    **P(E) = P(EF) + P(EFc) = P(E|F)P(F) + P(E|Fc)P(Fc)**. This means P(E) is a weighted average of the conditional probabilities of E given F and E given Fc.
*   **Generalization of Total Probability**: If F1, F2, . . . , Fn are mutually exclusive events such that their union covers the entire sample space S (meaning exactly one of them must occur), then:
    **P(E) = ∑n i=1 P(EFi) = ∑n i=1 P(E|Fi)P(Fi)**.
Here's a cleaned up and more readable version of your README:

# Probability Theory: Independent Events and Bayes' Formula

## 1.5 Independent Events

### Definition
Two events E and F are **independent** if:
```
P(E ∩ F) = P(E) × P(F)
```

### Key Properties
When events E and F are independent:
- **P(E|F) = P(E)** (if P(F) > 0)
- **P(F|E) = P(F)** (if P(E) > 0)
- Knowledge that F has occurred does not affect the probability that E occurs

### Dependent Events
Events that are **not independent** are called **dependent**.

#### Example: Dice Rolling
Consider tossing two fair dice:
- Let E₁ = event that the sum equals 6
- Let F = event that the first die equals 4

**Calculations:**
- P(E₁ ∩ F) = P({(4,2)}) = 1/36
- P(E₁) = P({(1,5), (2,4), (3,3), (4,2), (5,1)}) = 5/36
- P(F) = 1/6

**Independence Test:**
- P(E₁) × P(F) = (5/36) × (1/6) = 5/216
- Since P(E₁ ∩ F) = 1/36 ≠ 5/216, the events are **dependent**

**Intuition:** The outcome of the first die affects the probability of getting a sum of 6.

### Multiple Events
Events E₁, E₂, ..., Eₙ are **mutually independent** if for any subset of these events, the probability of their intersection equals the product of their individual probabilities.

**Important Distinction:**
- **Pairwise independent**: Any two events are independent
- **Mutually independent**: All possible combinations are independent
- Events can be pairwise independent but not mutually independent

## 1.6 Bayes' Formula

### Purpose
Bayes' formula calculates the conditional probability of one event from a set of mutually exclusive and exhaustive events, given that another event has occurred.

### Formula
For mutually exclusive events F₁, F₂, ..., Fₙ where ⋃ᵢ₌₁ⁿ Fᵢ = S:

```
P(Fⱼ|E) = [P(E|Fⱼ) × P(Fⱼ)] / [∑ᵢ₌₁ⁿ P(E|Fᵢ) × P(Fᵢ)]
```

This combines:
- **Conditional probability definition**: P(Fⱼ|E) = P(E ∩ Fⱼ)/P(E)
- **Law of Total Probability** for the denominator

### Examples

#### 1. Urn Problem
**Setup:**
- Urn 1: 2 white, 7 black balls
- Urn 2: 5 white, 6 black balls
- Fair coin flip determines which urn to use

**Question:** If a white ball is drawn, what's the probability the coin was heads?

**Solution:**
```
P(H|W) = [P(W|H) × P(H)] / [P(W|H) × P(H) + P(W|Hͨ) × P(Hͨ)]
       = [(2/9) × (1/2)] / [(2/9) × (1/2) + (5/11) × (1/2)]
       = 22/67
```

#### 2. Multiple-Choice Test
**Setup:**
- Student knows answer with probability p
- Otherwise guesses with probability (1-p)
- Correct guess probability = 1/m

**Question:** Given a correct answer, what's the probability the student knew it?

**Solution:**
```
P(K|C) = [P(C|K) × P(K)] / [P(C|K) × P(K) + P(C|Gͨ) × P(Gͨ)]
       = [1 × p] / [1 × p + (1/m) × (1-p)]
       = pm / [pm + 1 - p]
```

#### 3. Disease Testing
**Setup:**
- Disease probability: P(D) = 0.005
- Test sensitivity: P(E|D) = 0.95 (95% of diseased test positive)
- False positive rate: P(E|Dͨ) = 0.01 (1% of healthy test positive)

**Question:** Given a positive test, what's the probability of having the disease?

**Solution:**
```
P(D|E) = [P(E|D) × P(D)] / [P(E|D) × P(D) + P(E|Dͨ) × P(Dͨ)]
       = [(0.95) × (0.005)] / [(0.95) × (0.005) + (0.01) × (0.995)]
       ≈ 0.323
```

**Key Insight:** Even with a positive test result, there's only a 32.3% chance of having the disease due to its low prior probability. This demonstrates the importance of considering base rates in medical testing.