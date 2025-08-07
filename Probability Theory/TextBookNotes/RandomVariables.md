Here are detailed revision notes on Chapter 4: "Random Variables and Expectation", drawing directly from the provided source.

---

### Chapter 4: Random Variables and Expectation

This chapter introduces the fundamental concept of a **random variable**, which transforms the outcomes of an experiment into numerical values, allowing for quantitative analysis of probabilistic phenomena. It then delves into the different types of random variables, their distributions, and key measures such as **expectation** and **variance**, which summarise their properties. The chapter also covers important theorems like the **Weak Law of Large Numbers**, providing insights into the behaviour of sample averages.

### 4.1 & 4.2 Random Variables and Their Types

*   **Random Variable**: A numerical quantity determined by the result of an experiment. Instead of being interested in all the details of an experimental result, we are often only interested in the value of some numerical quantity derived from it.
    *   *Example*: When rolling two fair dice, we might be interested in the sum of the dice (X), rather than the individual outcomes like (1,6) or (2,5).
*   **Probability Assignment**: Since the value of a random variable is determined by the outcome of the experiment, probabilities can be assigned to its possible values.

**Types of Random Variables**:

1.  **Discrete Random Variable**: A random variable whose set of possible values is a sequence (countable).
    *   **Probability Mass Function (PMF), p(a)**: For a discrete random variable X, p(a) = P{X = a}.
        *   Properties: p(xi) > 0 for a countable number of values xi, and p(x) = 0 for all other values.
        *   **Axiom**: The sum of probabilities for all possible values must equal 1: ∑i p(xi) = 1.
2.  **Continuous Random Variable**: A random variable whose set of possible values is an interval, and there exists a non-negative function f(x) (probability density function) defined for all real x.
    *   **Probability Density Function (PDF), f(x)**: For any set B of real numbers, P{X ∈ B} = ∫B f(x) dx.
        *   Properties: The total probability over all possible values must be 1: ∫∞−∞ f(x) dx = 1.
        *   For any specific value 'a', the probability P{X = a} = ∫a_a f(x) dx = 0.
    *   **Cumulative Distribution Function (CDF), F(x)**: For any type of random variable, F(x) = P{X ≤ x}.
        *   **Relationship between CDF and PDF**: For a continuous random variable, d/dx F(x) = f(x).
        *   **Probability of an Interval**: P{a < X ≤ b} = F(b) - F(a).

### 4.3 Jointly Distributed Random Variables

Often, we are interested in the relationship between two or more random variables from a single experiment.

*   **Joint Cumulative Probability Distribution Function (F(x, y))**: Defined for two random variables X and Y as F(x, y) = P{X ≤ x, Y ≤ y}.
    *   **Marginal CDFs**: Fx(x) = P{X ≤ x} = P{X ≤ x, Y ≤ ∞} = lim(y→∞) F(x, y).
*   **Joint Probability Mass Function (p(x, y))**: For discrete random variables X and Y, p(x, y) = P{X = x, Y = y}.
    *   **Marginal Probability Mass Functions**: Obtained by summing over the other variable:
        *   Px(xi) = P{X = xi} = ∑j p(xi, yj)
        *   Py(yj) = P{Y = yj} = ∑i p(xi, yj)
    *   *Note*: Knowledge of marginal PMFs does not uniquely determine the joint PMF.
*   **Joint Probability Density Function (f(x, y))**: For continuous random variables X and Y, defined such that P{X ∈ A, Y ∈ B} = ∫B ∫A f(x, y) dx dy.
    *   **Relationship to Joint CDF**: f(a, b) = ∂²/∂a∂b F(a, b).
    *   **Interpretation**: f(a, b)da db ≈ P{a < X < a + da, b < Y < b + db} for small da, db.

### 4.3.1 Independent Random Variables

*   **Definition**: Two random variables X and Y are **independent** if, for any two sets of real numbers A and B, P{X ∈ A, Y ∈ B} = P{X ∈ A}P{Y ∈ B}.
    *   **Equivalent Condition for Independence (using CDFs)**: F(a, b) = Fx(a)Fy(b) for all a, b.
    *   **Equivalent Condition for Discrete Variables**: p(x, y) = px(x)py(y) for all x, y.
    *   **Equivalent Condition for Continuous Variables**: f(x, y) = fx(x)fy(y) for all x, y.
    *   **Interpretation**: Knowing the value of one independent random variable does not change the distribution of the other.
    *   **Dependent Events**: Random variables that are not independent are said to be dependent.
*   **Independence for Multiple Random Variables**: Events E1, E2, ..., En are independent if for every subset, the probability of their intersection is the product of their individual probabilities.

### 4.3.2 Conditional Distributions (Optional Section)

*   **Conditional Probability Mass Function**: For discrete X and Y, pX|Y(x|y) = P{X = x | Y = y} = P{X = x, Y = y} / P{Y = y} = p(x, y) / pY(y), provided pY(y) > 0.
*   **Conditional Probability Density Function**: For continuous X and Y, fX|Y(x|y) = f(x, y) / fY(y), provided fY(y) > 0.

### 4.4 Expectation

The expectation, or expected value, of a random variable is a crucial concept representing the "average" value in the long run.

*   **Definition for Discrete Random Variable**: If X takes possible values x1, x2, ..., then the expectation, denoted E[X], is defined by:
    **E[X] = ∑i xi P{X = xi}**.
    *   *Interpretation*: A weighted average of the possible values, weighted by their probabilities.
    *   *Example (Fair Die)*: E[X] = 1(1/6) + ... + 6(1/6) = 7/2.
    *   *Example (Indicator Variable)*: If I is an indicator variable for event A (I=1 if A occurs, I=0 otherwise), then **E[I] = P(A)**.
*   **Definition for Continuous Random Variable**: If X has PDF f(x), then:
    **E[X] = ∫∞−∞ x f(x) dx**.
    *   *Interpretation*: The centre of gravity of the probability distribution.

### 4.5 Properties of the Expected Value

*   **Expectation of a Function of a Random Variable (Proposition 4.5.1)**:
    *   If X is discrete with PMF p(x), then **E[g(X)] = ∑x g(x)p(x)**.
    *   If X is continuous with PDF f(x), then **E[g(X)] = ∫∞−∞ g(x)f(x) dx**.
    *   *Proof Sketch*: (Intuitive) The expected value of g(X) is a weighted average of the possible values g(x), with the weight for g(x) being the probability or probability density that X equals x.
*   **Linearity of Expectation (Corollary 4.5.2)**: For any constants a and b, **E[aX + b] = aE[X] + b**.
    *   *Proof Sketch*: Substitute `ax+b` for `g(x)` in Proposition 4.5.1 and apply the properties of summation/integration.
    *   **Corollaries**: E[b] = b and E[aX] = aE[X].
*   **Expected Value of Sums of Random Variables**: For any random variables X and Y, **E[X + Y] = E[X] + E[Y]**.
    *   *Proof Sketch*: For continuous case, E[X+Y] = ∫∫ (x+y)f(x,y) dx dy = ∫∫ xf(x,y) dx dy + ∫∫ yf(x,y) dx dy = E[X] + E[Y].
    *   **Generalization**: For any n random variables X1, ..., Xn, **E[∑ni=1 Xi] = ∑ni=1 E[Xi]**.
*   **Best Predictor**: The mean μ is the best predictor of a random variable X in terms of minimizing the expected square of its error, E[(X - c)²].
    *   *Proof Sketch*: E[(X - c)²] = E[(X - μ + μ - c)²] = E[(X - μ)²] + 2(μ - c)E[X - μ] + (μ - c)². Since E[X - μ] = 0, this simplifies to E[(X - μ)²] + (μ - c)², which is minimized when c = μ.

### 4.6 Variance

*   **Definition**: The **variance** of a random variable X, denoted Var(X), measures the spread or variation of its values around its mean (μ = E[X]).
    **Var(X) = E[(X - μ)²] = E[X²] - (E[X])²**.
*   **Standard Deviation**: The quantity **√Var(X)** is called the standard deviation of X. It has the same units as the mean.
*   **Variance of an Indicator Random Variable**: If I is an indicator variable for event A, then **Var(I) = P(A)[1 - P(A)]**.
*   **Properties of Variance**: For any constants a and b, **Var(aX + b) = a²Var(X)**.
    *   *Proof Sketch*: Var(aX + b) = E[(aX + b - E[aX + b])²] = E[(aX + b - (aμ + b))²] = E[(aX - aμ)²] = E[a²(X - μ)²] = a²E[(X - μ)²] = a²Var(X).
    *   **Corollaries**: Var(b) = 0 (variance of a constant is zero), Var(X + b) = Var(X) (adding a constant does not change variance), Var(aX) = a²Var(X).

### 4.7 Covariance and Variance of Sums of Random Variables

*   **Covariance (Cov(X, Y))**: A measure of the joint variability of two random variables.
    **Cov(X, Y) = E[(X - E[X])(Y - E[Y])] = E[XY] - E[X]E[Y]**.
    *   **Properties**:
        *   Cov(X, Y) = Cov(Y, X)
        *   Cov(X, X) = Var(X)
        *   Cov(aX, Y) = aCov(X, Y)
        *   **Proposition 4.7.2**: Cov(∑ni=1 Xi, ∑mj=1 Yj) = ∑ni=1 ∑mj=1 Cov(Xi, Yj).
*   **Variance of a Sum (Corollary 4.7.3)**: For any random variables X1, ..., Xn:
    **Var(∑ni=1 Xi) = ∑ni=1 Var(Xi) + ∑ni=1 ∑nj=1, j≠i Cov(Xi, Xj)**.
    *   *Proof Sketch*: Derived from Proposition 4.7.2 by expanding Cov(∑Xi, ∑Xj).
    *   For n=2: Var(X + Y) = Var(X) + Var(Y) + 2Cov(X, Y).
*   **Theorem 4.7.4 (Variance of Sums of Independent Random Variables)**: If X and Y are independent random variables, then **Cov(X, Y) = 0**. Consequently, for independent X1, ..., Xn:
    **Var(∑ni=1 Xi) = ∑ni=1 Var(Xi)**.
    *   *Proof Sketch*: If X and Y are independent, E[XY] = E[X]E[Y], which directly implies Cov(X, Y) = 0. The sum variance result then follows from Corollary 4.7.3.
*   **Correlation Coefficient (Corr(X, Y))**: A normalized measure of the linear relationship between X and Y.
    **Corr(X, Y) = Cov(X, Y) / (√Var(X)Var(Y))**.
    *   **Property**: The value always lies between -1 and +1 [-1 ≤ Corr(X,Y) ≤ 1].

### 4.8 Moment Generating Functions (Optional Section)

*   **Definition**: The **moment generating function (MGF)** φ(t) of a random variable X is defined for all values t by:
    **φ(t) = E[e^(tX)]**.
    *   **For Discrete X**: φ(t) = ∑x e^(tx)p(x).
    *   **For Continuous X**: φ(t) = ∫∞−∞ e^(tx)f(x) dx.
*   **Generating Moments**: The nth moment of X, E[Xⁿ], can be obtained by taking the nth derivative of φ(t) and evaluating it at t = 0:
    **E[Xⁿ] = φⁿ(0)**.
*   **MGF of a Sum of Independent Random Variables**: If X and Y are independent, then the MGF of their sum is the product of their individual MGFs:
    **φX+Y(t) = φX(t)φY(t)**.
    *   *Proof Sketch*: φX+Y(t) = E[e^(t(X+Y))] = E[e^(tX)e^(tY)]. By independence, E[e^(tX)e^(tY)] = E[e^(tX)]E[e^(tY)] = φX(t)φY(t).
*   **Uniqueness**: The moment generating function uniquely determines the distribution of a random variable.

### 4.9 Chebyshev’s Inequality and the Weak Law of Large Numbers

These inequalities provide bounds on probabilities when only the mean or both the mean and variance are known.

*   **Proposition 4.9.1 (Markov’s Inequality)**: If X is a nonnegative random variable, then for any value a > 0:
    **P{X ≥ a} ≤ E[X] / a**.
    *   *Proof Sketch*: For continuous X, E[X] = ∫∞0 xf(x) dx = ∫a0 xf(x) dx + ∫∞a xf(x) dx. Since x ≥ a in the second integral, ∫∞a xf(x) dx ≥ ∫∞a af(x) dx = aP{X ≥ a}. Thus, E[X] ≥ aP{X ≥ a], leading to the inequality.
*   **Proposition 4.9.2 (Chebyshev’s Inequality)**: If X is a random variable with mean μ and variance σ², then for any value k > 0:
    **P{|X - μ| ≥ k} ≤ σ² / k²**.
    *   *Proof Sketch*: Apply Markov’s inequality to the nonnegative random variable (X - μ)² with a = k². P{(X - μ)² ≥ k²} ≤ E[(X - μ)²]/k². Since (X - μ)² ≥ k² is equivalent to |X - μ| ≥ k, and E[(X - μ)²] = σ², the result follows.
    *   **Alternative Form**: P{|X - μ| > kσ} ≤ 1/k².
*   **Theorem 4.9.3 (The Weak Law of Large Numbers)**: Let X1, X2, ..., Xn be a sequence of independent and identically distributed random variables, each having mean E[Xi] = μ. Then, for any ε > 0:
    **P{|(X1 + ... + Xn)/n - μ| > ε} → 0 as n → ∞**.
    *   *Proof Sketch*: (Under assumption of finite variance σ²). Let X̄n = (X1 + ... + Xn)/n. We know E[X̄n] = μ and Var(X̄n) = σ²/n. By Chebyshev’s inequality, P{|X̄n - μ| > ε} ≤ Var(X̄n)/ε² = (σ²/n)/ε². As n → ∞, (σ²/n)/ε² → 0, proving the theorem.

---