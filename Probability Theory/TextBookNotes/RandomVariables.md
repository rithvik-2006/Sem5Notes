Here are detailed revision notes on Chapter 2, "Random Variables", drawing upon the provided source material:

### 2 Random Variables

This chapter introduces the **important concept of a random variable**. It often occurs that in an experiment, we are primarily interested in some **functions of the outcome** rather than the outcome itself. This chapter, along with Chapter 1 and Chapter 3, is concerned with the study of basic probability theory, which is essential to master both "model building" and subsequent analysis of probability models.

### 2.1 Random Variables

A **random variable** is a **real-valued function defined on the sample space**. Its value is determined by the outcome of an experiment, allowing probabilities to be assigned to its possible values.

*   **Examples**:
    *   If two fair dice are tossed, the **sum of the two dice** can be defined as a random variable, X. The probabilities for each possible sum (from 2 to 12) can be calculated based on the outcomes in the sample space.
    *   For two fair coin tosses, Y, the **number of heads appearing**, is a random variable taking values 0, 1, or 2 with their respective probabilities.
    *   If a coin with probability *p* of heads is tossed until the first head appears, N, the **number of flips required**, is a random variable. The probability for N=n is *(1-p)^(n-1)p*.
    *   Measuring a car's lifetime, where the sample space is [0, ∞), can be represented by a random variable.

Random variables can take on either a **finite or countable number of possible values (discrete)** or a **continuum of possible values (continuous)**.

The **cumulative distribution function (cdf)** or **distribution function**, F(*b*), of a random variable X is defined as **P{X ≤ b}**.
*   **Properties of the cdf F**:
    *   (i) **F(*b*) is a nondecreasing function of *b***.
    *   (ii) **lim F(*b*) as *b* → ∞ is F(∞) = 1**.
    *   (iii) **lim F(*b*) as *b* → -∞ is F(-∞) = 0**.
*   All probability questions about X can be answered using F(·). For instance, **P{a < X ≤ b} = F(*b*) - F(*a*)** for all *a* < *b*.
*   **P{X < b} = lim F(*b* - h) as h → 0+**. This is not necessarily equal to F(*b*) as F(*b*) includes P{X=b}.

### 2.2 Discrete Random Variables

A random variable is **discrete** if it can take on at most a countable number of possible values.
*   **Probability Mass Function (PMF)**: For a discrete random variable X, the PMF, *p*(*a*), is defined by **p(*a*) = P{X = *a*}**.
    *   *p*(*x*) is positive for at most a countable number of values *x*, and the sum of *p*(*xi*) for all possible values *xi* equals **1**.
*   The CDF F(*a*) can be expressed as the **sum of *p*(*xi*) for all *xi* ≤ *a***.

#### 2.2.1 The Bernoulli Random Variable

A **Bernoulli random variable** X takes on value **1 (success) with probability *p*** and **0 (failure) with probability 1-*p***. Its probability mass function is:
*   **p(0) = P{X = 0} = 1 - p**
*   **p(1) = P{X = 1} = p**

#### 2.2.2 The Binomial Random Variable

A **binomial random variable** X with **parameters (*n*, *p*)** represents the **number of successes** in *n* independent trials, where each trial results in a success with probability *p* and a failure with probability 1-*p*.
*   Its probability mass function is:
    **P{X = *i*} = (*n* choose *i*) *p*^(*i*) (1 - *p*)^(*n*-*i*)**.
*   The sum of these probabilities over all *i* (from 0 to *n*) is 1, as per the binomial theorem.
*   **Example**: Flipping four fair coins, the probability of two heads and two tails is (4 choose 2)(1/2)^2(1/2)^2 = 3/8.

#### 2.2.3 The Geometric Random Variable

A **geometric random variable** X with **parameter *p*** (0 ≤ *p* ≤ 1) represents the **number of trials required to obtain the first success** in a sequence of independent trials, where each trial is a success with probability *p*.
*   Its probability mass function is:
    **p(*n*) = P{X = *n*} = p(1 - p)^(*n*-1)**, for *n* ≥ 1.
*   This is a valid PMF, as the sum over all *n* equals 1.

#### 2.2.4 The Poisson Random Variable

A **Poisson random variable** X with **parameter λ** (λ > 0) takes on values 0, 1, 2, ....
*   Its probability mass function is:
    **p(*i*) = P{X = *i*} = e^(-λ) λ^(*i*) / *i***!**, for *i* = 0, 1, ....
*   This is a valid PMF, as the sum over all *i* equals 1.
*   **Approximation of Binomial**: An important property is that the Poisson random variable can **approximate a binomial random variable** when *n* is large and *p* is small, with **λ = *np***.
*   **Applications**: The Poisson random variable has a wide range of applications.
    *   **Example**: If typographical errors on a page follow a Poisson distribution with λ=1, the probability of at least one error is 1 - e^(-1) ≈ 0.633.

### 2.3 Continuous Random Variables

A random variable X is **continuous** if there exists a **nonnegative function *f*(*x*)**, called the **probability density function (PDF)**, such that for any set B of real numbers, **P{X ∈ B} = ∫*B* *f*(*x*) d*x***.
*   Since X must assume some value, *f*(*x*) must satisfy: **∫*−∞*^∞* *f*(*x*) d*x* = 1**.
*   **Interpretation**: The probability that X will be in an interval of length ε around point *a* is approximately ε*f*(*a*). Thus, *f*(*a*) measures how likely the random variable is to be near *a*.

#### 2.3.1 The Uniform Random Variable

A random variable X is **uniformly distributed over the interval (*α*, *β*)** if its PDF is:
*   ***f*(*x*) = 1 / (*β* - *α*)** for *α* < *x* < *β*, and 0 otherwise.
*   This means X is equally likely to be "near" any value within (*α*, *β*).
*   **P{a ≤ X ≤ b} = (*b* - *a*) / (*β* - *α*)** for *α* < *a* < *b* < *β*.
*   The **CDF** is:
    *   F(*a*) = 0, *a* ≤ *α*
    *   F(*a*) = (*a* - *α*) / (*β* - *α*), *α* < *a* < *β*
    *   F(*a*) = 1, *a* ≥ *β*

#### 2.3.2 Exponential Random Variables

An **exponential random variable** with **parameter λ** (λ > 0) has the PDF:
*   ***f*(*x*) = λe^(-λ*x*)**, if *x* ≥ 0, and 0 if *x* < 0.
*   The **CDF** is: **F(*x*) = 1 - e^(-λ*x*)** for *x* ≥ 0, and 0 for *x* < 0.

#### 2.3.3 Gamma Random Variables

The source mentions gamma random variables but does not provide details of their PDF or properties in this section.

#### 2.3.4 Normal Random Variables

A **normal random variable** (or normally distributed) with **parameters µ and σ²** has the PDF:
*   ***f*(*x*) = (1 / √(2π)σ) e^(-(x-µ)² / 2σ²)**, for -∞ < *x* < ∞.
*   This density function is a **bell-shaped curve** symmetric around µ.
*   If X is normally distributed with parameters µ and σ², then **Y = *α*X + *β*** is normally distributed with parameters ***α*µ + *β*** and ***α²σ²***.
*   If X is normal with parameters µ and σ², then **Y = (X-µ)/σ** is normally distributed with parameters **0 and 1**, known as the **standard or unit normal distribution**.

### 2.4 Expectation of a Random Variable

The **expected value of X**, denoted **E[X]**, is also known as the **mean** or the **first moment of X**. It is a weighted average of the possible values X can take, weighted by their probabilities.

#### 2.4.1 The Discrete Case

If X is a discrete random variable with PMF *p*(*x*), its expected value is:
*   **E[X] = ∑*x:p(x)>0* *x*p(*x*)**.
*   **Example**: For a fair die, E[X] = (1/6)(1+2+3+4+5+6) = 7/2.
*   **Expectation of a Bernoulli Random Variable**: E[X] = *p*.
*   **Expectation of a Binomial Random Variable**: E[X] = *np*.
*   **Expectation of a Geometric Random Variable**: E[X] = 1/*p*.
*   **Expectation of a Poisson Random Variable**: E[X] = λ.

#### 2.4.2 The Continuous Case

If X is a continuous random variable with PDF *f*(*x*), its expected value is:
*   **E[X] = ∫*−∞*^∞* *x*f*(*x*) d*x***.
*   **Example**: For a uniform random variable on (*α*, *β*), E[X] = (*α* + *β*) / 2.
*   **Expectation of an Exponential Random Variable**: E[X] = 1/λ.
*   **Expectation of a Normal Random Variable**: E[X] = µ.

#### 2.4.3 Expectation of a Function of a Random Variable

If X has a probability distribution and *g* is a real-valued function, the expected value of *g*(X) can be computed directly without first finding the distribution of *g*(X).
*   **Proposition 2.1**:
    *   For **discrete** X: **E[*g*(X)] = ∑*x:p(x)>0* *g*(*x*)*p*(*x*)**.
    *   For **continuous** X: **E[*g*(X)] = ∫*−∞*^∞* *g*(*x*)*f*(*x*) d*x***.
*   **Corollary 2.2**: For constants *a* and *b*, **E[*a*X + *b*] = *a*E[X] + *b***.
*   The quantity **E[X^*n*]** is called the **nth moment of X**.
*   **Variance of a Random Variable (Var(X))**: Defined as **E[(X - E[X])²]**. It measures the expected square of the deviation of X from its expected value.
    *   **Identity**: **Var(X) = E[X²] - (E[X])²**.
    *   **Example**: For a normal random variable, Var(X) = σ².

### 2.5 Jointly Distributed Random Variables

Often, we are interested in probability statements concerning two or more random variables.

#### 2.5.1 Joint Distribution Functions

*   **Joint Cumulative Probability Distribution Function**: For two random variables X and Y, defined as **F(*a*, *b*) = P{X ≤ *a*, Y ≤ *b*}**.
*   **Marginal Distributions**:
    *   **F*X*(*a*) = P{X ≤ *a*} = F(*a*, ∞)**.
    *   **F*Y*(*b*) = P{Y ≤ *b*} = F(∞, *b*)**.
*   **Joint Probability Mass Function (discrete)**: **p(*x*, *y*) = P{X = *x*, Y = *y*}**.
*   **Joint Probability Density Function (continuous)**: **f(*x*, *y*)**. **∂²F(*a*, *b*) / (*∂a* *∂b*) = *f*(*a*, *b*)**.
*   **Expectation of a function of two variables**:
    *   **E[*g*(X, Y)] = ∑*y* ∑*x* *g*(*x*, *y*)*p*(*x*, *y*)** (discrete)
    *   **E[*g*(X, Y)] = ∫*−∞*^∞* ∫*−∞*^∞* *g*(*x*, *y*)*f*(*x*, *y*) d*x* d*y*** (continuous)
*   **Additivity of Expectation**: **E[*a*X + *b*Y] = *a*E[X] + *b*E[Y]**. This generalizes to *n* random variables: **E[∑*n* *a*i*X*i*] = ∑*n* *a*i*E[X*i*]**.

#### 2.5.2 Independent Random Variables

Two events E and F are **independent if P(EF) = P(E)P(F)**. Similarly, X and Y are **independent** if:
*   **P{X ≤ *a*, Y ≤ *b*} = P{X ≤ *a*}P{Y ≤ *b*}** for all *a*, *b*.
*   This means **F(*a*, *b*) = F*X*(*a*)F*Y*(*b*)**.
*   For discrete variables, independence implies **p(*x*, *y*) = p*X*(*x*)*p*Y*(*y*)**.
*   **Proposition 2.3**: If X and Y are independent, then for any functions *h* and *g*, **E[*g*(X)*h*(Y)] = E[*g*(X)]E[*h*(Y)]**.
*   **Intuitive meaning**: Knowledge of one event occurring does not affect the probability of the other.
*   **Pairwise Independent vs. Mutually Independent**: Events can be pairwise independent but not mutually independent.

#### 2.5.3 Covariance and Variance of Sums of Random Variables

*   **Covariance (Cov(X, Y))**: Defined as **Cov(X, Y) = E[(X - E[X])(Y - E[Y])] = E[XY] - E[X]E[Y]**.
*   **Properties of Covariance**:
    1.  **Cov(X, X) = Var(X)**.
    2.  **Cov(X, Y) = Cov(Y, X)**.
    3.  **Cov(*c*X, Y) = *c*Cov(X, Y)**.
    4.  **Cov(X, Y + Z) = Cov(X, Y) + Cov(X, Z)**.
    *   Generalizes to **Cov(∑*n* Xi, ∑*m* Yj) = ∑*n* ∑*m* Cov(Xi, Yj)**.
*   **Variance of Sums**: **Var(∑*n* Xi) = ∑*n* Var(Xi) + 2 ∑*i*<*j* Cov(Xi, Xj)**.
*   If Xi are **independent**, then **Var(∑*n* Xi) = ∑*n* Var(Xi)**.
*   **Sample Mean**: For independent and identically distributed (i.i.d.) X1, ..., Xn, **X̄ = ∑*n* Xi/*n***.
    *   **Proposition 2.4**: If X1, ..., Xn are i.i.d. with mean µ and variance σ²:
        *   (a) **E[X̄] = µ**.
        *   (b) **Var(X̄) = σ²/n**.
        *   (c) **Cov(X̄, Xi - X̄) = 0**.
*   **Example**: **Variance of a Binomial Random Variable**: Var(X) = *np*(1-*p*).

#### 2.5.4 Joint Probability Distribution of Functions of Random Variables

To obtain the joint distribution of Y1 = *g*1(X1, X2) and Y2 = *g*2(X1, X2) from *f*X1,X2(*x*1, *x*2), assuming unique solutions *x*1 = *h*1(*y*1, *y*2) and *x*2 = *h*2(*y*1, *y*2), and continuous partial derivatives with a **non-zero Jacobian determinant J(*x*1, *x*2)**:
*   **fY1,Y2(*y*1, *y*2) = *f*X1,X2(*x*1, *x*2) |J(*x*1, *x*2)|^(-1)**.
*   **Jacobian**: J(*x*1, *x*2) = |∂*g*1/∂*x*1 ∂*g*1/∂*x*2; ∂*g*2/∂*x*1 ∂*g*2/∂*x*2|.
*   **Example**: Sum of two independent uniform random variables leads to a triangular density. Sum of independent Poisson random variables is also Poisson.
*   **Order Statistics**: For i.i.d. continuous random variables X1, ..., Xn with CDF F and density *f*, the density of X(*i*) (the *i*th smallest) is given by **n! / ((n-*i*)!(*i*-1)!) *f*(*x*)(F(*x*))^(i-1)(1-F(*x*))^(n-i)**.

### 2.6 Moment Generating Functions

The **moment generating function (MGF)** *φ*(*t*) of a random variable X is defined for all values *t* by **φ(*t*) = E[e^(tX)]**.
*   **Properties**:
    *   *φ*'(0) = E[X].
    *   *φ*''(*t*) = E[X²e^(tX)], so *φ*''(0) = E[X²].
    *   The MGF **uniquely determines the distribution**.
*   **MGF of common distributions**:
    *   **Binomial (*n*, *p*)**: *φ*(*t*) = (*pe*^t + 1 - *p*)^*n*. (Mean *np*, Variance *np*(1-*p*)).
    *   **Poisson (λ)**: *φ*(*t*) = exp{λ(*e*^t - 1)}. (Mean λ, Variance λ).
    *   **Exponential (λ)**: *φ*(*t*) = λ / (λ - *t*) for *t* < λ. (Mean 1/λ, Variance 1/λ²).
    *   **Normal (µ, σ²)**: *φ*(*t*) = exp{µ*t* + σ²*t*²/2}. (Mean µ, Variance σ²).
*   **MGF of a Sum of Independent Random Variables**: If X and Y are independent, *φ*X+Y(*t*) = *φ*X(*t*)*φ*Y(*t*).
    *   **Example**: Sum of independent binomials with same *p* is also binomial. Sum of independent Poissons is also Poisson. Sum of independent normals is also normal.
*   **Joint Moment Generating Function**: For X1, ..., Xn, defined as *φ*(*t*1, ..., *t*n) = E[exp{∑*n* *t*i*X*i*}]. It uniquely determines the joint distribution.
    *   **Multivariate Normal Distribution**: Defined for linear combinations of independent standard normal variables. Its joint MGF shows that the joint distribution is determined by means E[Xi] and covariances Cov(Xi, Xj).

### 2.6.1 The Joint Distribution of the Sample Mean and Sample Variance from a Normal Population

For i.i.d. random variables X1, ..., Xn with mean µ and variance σ², the **sample variance S² = ∑*n* (*X*i - X̄)² / (*n* - 1)**.
*   **E[S²] = σ²**.
*   **Chi-squared Random Variable**: If Z1, ..., Zn are independent standard normal random variables, then ∑*n* Z*i*² is a **chi-squared random variable with *n* degrees of freedom**. Its MGF is (1 - 2*t*)^(-*n*/2).
*   **Proposition 2.5**: If X1, ..., Xn are i.i.d. **normal** random variables with mean µ and variance σ²:
    *   The **sample mean X̄ and the sample variance S² are independent**.
    *   **X̄ is a normal random variable** with mean µ and variance σ²/n.
    *   **(*n* - 1)S²/σ² is a chi-squared random variable** with *n* - 1 degrees of freedom.

### 2.7 The Distribution of the Number of Events that Occur

For arbitrary events A1, ..., An, let X be the number of these events that occur. Let **Sk = ∑ P(A*i*1 ... A*i*k)** be the sum of probabilities of all (*n* choose *k*) intersections of *k* distinct events.
*   The **inclusion-exclusion identity** states **P(X > 0) = S1 - S2 + S3 - ... + (-1)^(n+1)Sn**.
*   The probability mass function of X is given by:
    **P(X = *k*) = Sk - (*k*+1 choose *k*)Sk+1 + (*k*+2 choose *k*)Sk+2 - ... + (-1)^(n-*k*) (*n* choose *k*)Sn**.
    This can be written as **P(X = *k*) = ∑*j*=*k*^n* (-1)^(k+j) (*j* choose *k*)Sj**.
*   The probability that at least *k* events occur is:
    **P(X ≥ *k*) = ∑*j*=*k*^n* (-1)^(k+j) (*j*-1 choose *k*-1)Sj**.

### 2.8 Limit Theorems

#### Proposition 2.6 (Markov’s Inequality)

If X is a **nonnegative random variable**, then for any value *a* > 0:
*   **P{X ≥ *a*} ≤ E[X] / *a***.
*   **Example**: If mean weekly production is 500, the probability of at least 1000 units is ≤ 500/1000 = 0.5.

#### Theorem 2.1 (Strong Law of Large Numbers)

Let X1, X2, ... be a sequence of **independent random variables having a common distribution**, and let E[Xi] = µ. Then, **with probability 1**:
*   **(X1 + X2 + ... + Xn) / n → µ as n → ∞**.
*   This implies that the **limiting proportion of time an event E occurs is P(E)**.

#### Theorem 2.2 (Central Limit Theorem)

Let X1, X2, ... be a sequence of **independent, identically distributed random variables**, each with mean µ and variance σ². Then the distribution of:
*   **(X1 + X2 + ... + Xn - nµ) / (σ√*n*)** **tends to the standard normal as n → ∞**.
*   **P{(X1 + ... + Xn - nµ) / (σ√*n*) ≤ *a*} → (1 / √(2π)) ∫*−∞*^a* e^(-x²/2) d*x*** as n → ∞.
*   This theorem is powerful because it holds for any distribution of the Xis.
*   **Approximation**: The binomial distribution can be approximated by a normal distribution for large *n*.

### 2.9 Stochastic Processes

A **stochastic process {X(*t*), *t* ∈ T}** is a **collection of random variables**. For each *t* ∈ T, X(*t*) is a random variable.
*   The index *t* is often interpreted as **time**, and X(*t*) as the **state of the process at time *t***.
*   A stochastic process describes the **evolution through time of some (physical) process**.
*   **Example**: A particle moving along a set of *m* + 1 nodes arranged in a circle, where its position at step *n* is X*n*.