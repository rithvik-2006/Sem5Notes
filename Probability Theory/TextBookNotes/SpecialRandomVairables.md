Here are detailed revision notes for Chapter 5, "SPECIAL RANDOM VARIABLES," from the provided sources. This chapter introduces several fundamental probability distributions that frequently arise in applications, along with their key properties, relationships, and the theorems that define them.

### Chapter 5: Special Random Variables

**5.1 The Bernoulli and Binomial Random Variables**

*   **Bernoulli Random Variable**
    *   **Definition**: A random variable *X* is a Bernoulli random variable if its outcome can be classified as either a "success" or a "failure".
    *   **Probability Mass Function (PMF)**: If the probability of success is *p*, then:
        *   **P{X = 1} = p** (for success)
        *   **P{X = 0} = 1 - p** (for failure)
*   **Binomial Random Variable**
    *   **Definition**: A Binomial random variable *X* represents the **number of successes in *n* independent Bernoulli trials**, where each trial has the same probability of success *p*.
    *   **Probability Mass Function (PMF)**:
        *   **P{X = i} = (n choose i) * p^i * (1 - p)^(n-i)**, for *i* = 0, 1, ..., *n*.
        *   Here, **(n choose i) = n! / [i!(n - i)!]** is the number of different groups of *i* objects that can be chosen from a set of *n* objects.
        *   **Proof Sketch for PMF Validity**: The probability of any particular sequence of *n* outcomes containing *i* successes and (*n - i*) failures is *p^i * (1 - p)^(n-i) due to the independence of trials. Since there are (n choose i) such sequences, the formula follows. The sum of all probabilities from *i = 0* to *n* is equal to 1, verified by the binomial theorem: **Σ (n choose i) * p^i * (1 - p)^(n-i) = [p + (1 - p)]^n = 1**.
    *   **Mean (Expected Value)**: **E[X] = np**.
    *   **Variance**: **Var(X) = np(1 - p)**.
    *   **Moment Generating Function (MGF)**: **φ(t) = (p*e^t + 1 - p)^n**.
        *   **Proof Sketch for MGF**: The MGF is defined as E[e^(tX)] = Σ e^(ti) * P{X=i} over all possible values *i*. Substituting the PMF gives Σ e^(ti) * (n choose i) * p^i * (1 - p)^(n-i). This can be rewritten as Σ (n choose i) * (p*e^t)^i * (1 - p)^(n-i), which is the binomial expansion of (p*e^t + 1 - p)^n. The mean and variance can then be derived by evaluating the first and second derivatives of φ(t) at *t = 0*.
    *   **Examples**: Calculating the probability of a certain number of packages being returned by a buyer, or the number of defective chips in an order.

**5.2 The Poisson Random Variable**

*   **Definition**: A random variable *X* is a Poisson random variable with parameter **λ (lambda > 0)** if it takes on values 0, 1, 2, .... The Poisson distribution often models the number of events occurring in a fixed interval of time or space if these events occur with a known constant mean rate and independently of the time since the last event.
*   **Probability Mass Function (PMF)**: **P{X = i} = e^(-λ) * λ^i / i!**, for *i* = 0, 1, .... (Here, *e* is approximately 2.7183).
*   **Mean (Expected Value)**: **E[X] = λ**.
*   **Variance**: **Var(X) = λ**.
*   **Moment Generating Function (MGF)**: **φ(t) = exp{λ(e^t - 1)}**.
    *   **Proof Sketch for MGF**: Summation of e^(ti) * P{X=i} over *i* = 0 to ∞. Factor out e^(-λ) from the summation. The remaining sum Σ (λe^t)^i / i! is the Taylor series expansion for e^(λe^t), leading to e^(-λ) * e^(λe^t) = exp{λ(e^t - 1)}.
*   **Relationship to Binomial Distribution**: The Poisson distribution can approximate the Binomial distribution when the number of trials (*n*) is large and the probability of success (*p*) is small, provided that the product *np* remains constant (λ = *np*). This approximation is useful for simplifying calculations in such scenarios.
*   **Examples**: The average number of accidents weekly on a highway.

**5.3 The Hypergeometric Random Variable**

*   **Definition**: A Hypergeometric random variable *X* represents the **number of acceptable batteries (or items) in a sample of size *n* randomly chosen (without replacement)** from a bin containing *N* acceptable and *M* defective batteries.
*   **Probability Mass Function (PMF)**:
    *   **P{X = i} = [(N choose i) * (M choose (n-i))] / (N+M choose n)**, for *i* = 0, 1, ..., min(*N*, *n*).
*   **Mean (Expected Value)**: **E[X] = n * N / (N + M)**.
*   **Variance**: **Var(X) = n * (N / (N + M)) * (M / (N + M)) * ((N + M - n) / (N + M - 1))**.
*   **Relationship to Binomial Distribution**: When the sample size (*n*) is small relative to the total population size (*N + M*), the Hypergeometric distribution can be approximated by a Binomial distribution with parameters *n* and *p = N / (N + M)*. This is because sampling without replacement from a large population mimics sampling with replacement, making the trials nearly independent.
*   **Examples**: Sampling batteries from a bin. Estimating the size of an animal population using a capture-recapture method.

**5.4 The Uniform Random Variable**

*   **Definition**: A continuous random variable *X* has a uniform distribution over the interval **(a, b)** if its probability density function is constant within this interval and zero elsewhere.
*   **Probability Density Function (PDF)**:
    *   **f(x) = 1 / (b - a)**, for *a < x < b*
    *   **f(x) = 0**, otherwise
*   **Cumulative Distribution Function (CDF)**:
    *   **F(x) = (x - a) / (b - a)**, for *a ≤ x < b*
    *   **F(x) = 0**, for *x < a*
    *   **F(x) = 1**, for *x ≥ b*
*   **Mean (Expected Value)**: **E[X] = (a + b) / 2**.
*   **Variance**: **Var(X) = (b - a)^2 / 12**.
*   **Random Numbers**: A key application is the generation of "random numbers," which are defined as outcomes of independent uniform (0, 1) random variables. These are fundamental to simulation studies. Methods exist to use these to generate random permutations or random subsets of a set of elements.

**5.5 Normal Random Variables**

*   **Definition**: A random variable *X* is said to be **normally distributed with parameters μ (mean) and σ^2 (variance)**, denoted as **X ~ N(μ, σ^2)**. The normal distribution is frequently observed in natural phenomena.
*   **Probability Density Function (PDF)**:
    *   **f(x) = (1 / sqrt(2πσ^2)) * e^(-(x-μ)^2 / (2σ^2))**, for -∞ < x < ∞.
    *   **Shape**: The normal density function is a **bell-shaped curve that is symmetric about μ** and attains its maximum value at *x = μ*.
*   **Mean (Expected Value)**: **E[X] = μ**.
*   **Variance**: **Var(X) = σ^2**.
*   **Standard Normal Random Variable (Z)**: A special case where **μ = 0** and **σ^2 = 1**.
    *   **Theorem**: If *X* is a normal random variable with mean *μ* and variance *σ^2*, then the random variable **Z = (X - μ) / σ** is a standard normal random variable.
        *   **Proof Sketch**: The proof involves showing that the cumulative distribution function (CDF) of (X - μ) / σ is equal to the CDF of a standard normal random variable. This is done by a change of variables in the integral definition of the CDF.
    *   Probabilities for the standard normal are widely tabulated (e.g., Table A1 in the Appendix).
*   **Sums of Normal Random Variables**: The sum of independent normal random variables is also normally distributed. This is a crucial property for statistical inference.
*   **Examples**: The height of a person, the velocity of a molecule in gas, or the error made in measuring a physical quantity. Noise in signal transmission.

**5.6 Exponential Random Variables (Optional Section)**

*   **Definition**: A continuous random variable *X* has an exponential distribution with parameter **λ (rate > 0)** if its probability density function is:
*   **Probability Density Function (PDF)**:
    *   **f(x) = λe^(-λx)**, for *x ≥ 0*
    *   **f(x) = 0**, otherwise
*   **Mean (Expected Value)**: **E[X] = 1/λ**.
*   **Variance**: **Var(X) = 1/λ^2**.
*   **Memoryless Property**: The exponential distribution is the **only continuous distribution with the property that P{X > s+t | X > s} = P{X > t}** for any *s, t ≥ 0*. This means the probability of an event occurring in the future is independent of how long it has already been observed without occurring.
    *   **Proof Sketch**: Using the definition of conditional probability P(A|B) = P(A ∩ B) / P(B) and the CDF for the exponential distribution. P{X > s+t | X > s} = P{X > s+t} / P{X > s}. Since P{X > x} = e^(-λx), this becomes e^(-λ(s+t)) / e^(-λs) = e^(-λt) = P{X > t}.
*   **Relationship to Poisson Process**: In a Poisson process, events occur continuously and independently at a constant average rate λ. The **time between successive events (interarrival times) in a Poisson process are independent and identically distributed exponential random variables with rate λ**.
    *   **Proposition 5.6.2**: For a Poisson process with rate λ, the **number of events *N(t)* occurring in any interval of length *t* has a Poisson distribution with mean λt**.
        *   **Proof Sketch**: This involves dividing the interval [0, *t*] into *n* small subintervals. The probability of an event in a subinterval is approximately λ*t*/*n*, and the probability of more than one event is negligible for small subintervals. As *n* approaches infinity, the number of events in [0, *t*] can be approximated by a Binomial distribution which converges to a Poisson distribution.

**5.7 The Gamma Distribution (Optional Section)**

*   **Definition**: A random variable *X* has a gamma distribution with parameters **α (shape parameter > 0)** and **λ (rate parameter > 0)**.
*   **Probability Density Function (PDF)**:
    *   **f(x) = [λe^(-λx) * (λx)^(α-1)] / Γ(α)**, for *x ≥ 0*
    *   **f(x) = 0**, otherwise
    *   **Γ(α)** is the gamma function, defined as **Γ(α) = ∫(from 0 to ∞) e^(-x) * x^(α-1) dx**. For positive integers *n*, Γ(*n*) = (*n*-1)!.
*   **Mean (Expected Value)**: **E[X] = α/λ**.
*   **Variance**: **Var(X) = α/λ^2**.
*   **Relationship to Exponential Distribution**: The sum of *n* independent exponential random variables, each with rate λ, follows a gamma distribution with parameters *n* and λ.
    *   **Corollary 5.7.2**: If *X1, ..., Xn* are independent exponential random variables with mean 1/λ, then their sum **ΣXi** has a gamma distribution with parameters *n* and λ.
*   **Shape**: As the shape parameter *α* becomes large, the gamma density function starts to resemble the normal density function, explained by the Central Limit Theorem.

**5.8 Distributions Arising from the Normal (Optional Section)**

*   **5.8.1 The Chi-Square (χ^2) Distribution**
    *   **Definition**: If **Z1, Z2, ..., Zn** are independent **standard normal random variables**, then the random variable **X = Z1^2 + Z2^2 + ... + Zn^2** has a **chi-square distribution with *n* degrees of freedom** (denoted as **χn^2**).
    *   **Mean**: **E[X] = n**.
    *   **Variance**: **Var(X) = 2n**.
    *   **Moment Generating Function (MGF)**: **φ(t) = (1 - 2t)^(-n/2)**.
        *   **Proof Sketch for MGF**: Derived using the MGF of a standard normal squared variable (E[e^(tZ^2)]) and the property that the MGF of a sum of independent random variables is the product of their individual MGFs. This resulting MGF is identical to that of a gamma random variable with parameters (n/2, 1/2), proving the identity between the two distributions.
    *   **Notation**: **χ^2(α,n)** is the value such that **P{X ≥ χ^2(α,n)} = α**. (Values are in Table A2 in the Appendix).

*   **5.8.2 The t-Distribution**
    *   **Definition**: If **Z** is a standard normal random variable and **χn^2** is a chi-square random variable with *n* degrees of freedom, and **Z and χn^2 are independent**, then the random variable **T = Z / sqrt(χn^2 / n)** has a **t-distribution with *n* degrees of freedom** (denoted as **Tn**).
    *   **Shape**: The t-distribution density function is **symmetric about zero** and bell-shaped, but has **"fatter tails"** than the standard normal distribution, especially for small *n* [193, 194f]. As *n* (degrees of freedom) increases, the t-distribution **approximates the standard normal distribution**.
    *   **Notation**: **t(α,n)** is the value such that **P{Tn ≥ t(α,n)} = α**. (Values are in Table A3 in the Appendix).

*   **5.8.3 The F-Distribution**
    *   **Definition**: If **χn^2** and **χm^2** are independent chi-square random variables with *n* and *m* degrees of freedom, respectively, then the random variable **F_n,m = (χn^2 / n) / (χm^2 / m)** has an **F-distribution with *n* and *m* degrees of freedom**.
    *   **Notation**: **F(α,n,m)** is the value such that **P{F_n,m > F(α,n,m)} = α**. (Values are in Table A4 in the Appendix).