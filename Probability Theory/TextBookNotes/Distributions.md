Here are detailed revision notes for Chapter 6, "Distributions of Sampling Statistics," including key concepts, theorems, and proof sketches, as found in the sources:

### Chapter 6: Distributions of Sampling Statistics

**6.1 Introduction**

*   **Statistics** is the science of drawing conclusions from observed data.
*   A common scenario in technological studies involves a **population** of items with measurable values. By sampling from this collection and analysing the sampled items, conclusions about the entire collection can be drawn.
*   A **random sample** is a critical concept, indicating that sampling is done in a manner where all possible choices of items for a group are equally likely.
*   **Statistical problems** can be broadly categorised:
    *   **Parametric inference problems**: Assume a specific functional form for the population distribution (e.g., normal, exponential), with unknown parameters to be estimated from data. For instance, if a distribution is assumed to be normal, its mean and variance would be estimated.
    *   **Nonparametric inference problems**: Do not assume a specific form for the population distribution.
*   **Probability theory** forms the basis of statistical inference, as statistical inference relies on formulating a probability model to describe the data and then using data to make inferences about these probabilities.

**6.2 The Sample Mean**

*   Let $X_1, X_2, ..., X_n$ be a **random sample** from a distribution with mean $\mu$ and variance $\sigma^2$.
*   The **sample mean**, denoted by $\bar{X}$, is defined as the arithmetic average of these values:
    *   $\bar{X} = \frac{X_1 + \dots + X_n}{n}$.
*   **Expected Value of the Sample Mean**:
    *   **$E[\bar{X}] = \mu$**.
    *   **Proof Sketch**: This is derived from the linearity of expectation: $E[\bar{X}] = E[\frac{X_1 + \dots + X_n}{n}] = \frac{1}{n}(E[X_1] + \dots + E[X_n])$. Since all $X_i$ are from the same distribution, $E[X_i] = \mu$, so $E[\bar{X}] = \frac{1}{n}(n\mu) = \mu$.
*   **Variance of the Sample Mean**:
    *   **$Var(\bar{X}) = \frac{\sigma^2}{n}$**.
    *   **Proof Sketch**: This is derived using the property of variance for independent random variables: $Var(\bar{X}) = Var(\frac{X_1 + \dots + X_n}{n}) = \frac{1}{n^2}[Var(X_1) + \dots + Var(X_n)]$ by independence. Since $Var(X_i) = \sigma^2$, we get $\frac{1}{n^2}(n\sigma^2) = \frac{\sigma^2}{n}$.
*   The sample mean $\bar{X}$ is centred about the population mean $\mu$, and its spread reduces as the sample size $n$ increases. Figure 6.1 illustrates how the probability density function of the sample mean from a standard normal population becomes narrower with increasing sample size.

**6.3 The Central Limit Theorem**

*   **Theorem 6.3.1: The Central Limit Theorem**
    *   Let $X_1, X_2, \dots, X_n$ be a sequence of independent and identically distributed random variables, each having mean $\mu$ and variance $\sigma^2$.
    *   For large $n$, the distribution of $X_1 + \dots + X_n$ is **approximately normal** with mean $n\mu$ and variance $n\sigma^2$.
    *   **Implication**: It follows that $\frac{X_1 + \dots + X_n - n\mu}{\sigma\sqrt{n}}$ is approximately a **standard normal random variable** for large $n$.
*   The central limit theorem provides a simple method for computing approximate probabilities for sums of independent random variables and explains why many natural phenomena exhibit a bell-shaped (normal) curve.
*   **Approximate Distribution of the Sample Mean**:
    *   Since $\bar{X} = \frac{1}{n}\sum_{i=1}^n X_i$, and a constant multiple of a normal random variable is also normal, $\bar{X}$ will be approximately normal when $n$ is large.
    *   Because $E[\bar{X}] = \mu$ and $Var(\bar{X}) = \sigma^2/n$, it implies that $\frac{\bar{X} - \mu}{\sigma/\sqrt{n}}$ approximately has a **standard normal distribution**.
    *   **Example (6.3d)**: For weights of workers with mean 167 and standard deviation 27, the probability of the sample mean (for a sample of 36) being between 163 and 170 is approximated using the normal distribution for $\bar{X}$.
*   **Normal Approximation to Binomial Random Variables**:
    *   If $X$ is a binomial random variable with parameters $n$ and $p$, then $X$ can be viewed as the sum of $n$ independent Bernoulli random variables.
    *   For large $n$, $\frac{X - np}{\sqrt{np(1-p)}}$ will approximately be a **standard normal random variable**.
    *   **Continuity Correction**: When approximating a discrete binomial distribution with a continuous normal distribution, it's best to compute $P\{X=i\}$ as $P\{i-0.5 < X < i+0.5\}$.
    *   Figure 6.3 graphically illustrates this convergence.
*   The approximation given by the central limit theorem is often valid for smaller sample sizes (e.g., $n=5$ for exponential populations).

**6.4 The Sample Variance**

*   Let $X_1, \dots, X_n$ be a random sample from a distribution with mean $\mu$ and variance $\sigma^2$.
*   The **sample variance**, denoted by $S^2$, is defined as:
    *   **$S^2 = \frac{\sum_{i=1}^n (X_i - \bar{X})^2}{n-1}$**.
    *   The **sample standard deviation** is $S = \sqrt{S^2}$.
*   **Computational Identity for Sample Variance**:
    *   For any numbers $x_1, \dots, x_n$, $\sum_{i=1}^n (x_i - \bar{x})^2 = \sum_{i=1}^n x_i^2 - n\bar{x}^2$. This identity is crucial for calculating $S^2$.
*   **Expected Value of the Sample Variance**:
    *   **$E[S^2] = \sigma^2$**.
    *   **Proof Sketch**: Starting with $(n-1)S^2 = \sum_{i=1}^n X_i^2 - n\bar{X}^2$, take the expectation of both sides. Using the property $E[W^2] = Var(W) + (E[W])^2$, and knowing $E[X_i] = \mu$, $Var(X_i) = \sigma^2$, $E[\bar{X}] = \mu$, and $Var(\bar{X}) = \sigma^2/n$, the proof shows that $E[(n-1)S^2] = (n-1)\sigma^2$, which leads to $E[S^2] = \sigma^2$. This indicates that $S^2$ is an **unbiased estimator** of $\sigma^2$.

**6.5 Sampling Distributions from a Normal Population**

*   This section focuses on the distributions of the sample mean ($\bar{X}$) and sample variance ($S^2$) specifically when the underlying population is **normally distributed**.
*   **Distribution of the Sample Mean ($\bar{X}$)**:
    *   If $X_1, \dots, X_n$ are a sample from a normal population with mean $\mu$ and variance $\sigma^2$, then $\bar{X}$ is **normally distributed** with mean $\mu$ and variance $\sigma^2/n$.
    *   **Implication**: $\frac{\bar{X} - \mu}{\sigma/\sqrt{n}}$ has a **standard normal distribution**.
*   **Distribution of the Sample Variance ($S^2$)**:
    *   An identity is used: $\sum_{i=1}^n (X_i - \bar{X})^2 = \sum_{i=1}^n (X_i - \mu)^2 - n(\bar{X} - \mu)^2$.
    *   Dividing by $\sigma^2$ yields: $\frac{\sum_{i=1}^n (X_i - \mu)^2}{\sigma^2} = \frac{\sum_{i=1}^n (X_i - \bar{X})^2}{\sigma^2} + \left[\frac{\sqrt{n}(\bar{X} - \mu)}{\sigma}\right]^2$.
    *   The left side is a **chi-square random variable with $n$ degrees of freedom** (sum of squares of $n$ independent standard normal variables). The last term on the right is a **chi-square random variable with 1 degree of freedom** (square of a standard normal variable).
    *   **Theorem 6.5.1**:
        *   If $X_1, \dots, X_n$ is a sample from a normal population having mean $\mu$ and variance $\sigma^2$, then **$\bar{X}$ and $S^2$ are independent random variables**.
        *   $\bar{X}$ is **normal with mean $\mu$ and variance $\sigma^2/n$**.
        *   **$(n-1)S^2/\sigma^2$ is chi-square with $n-1$ degrees of freedom**.
    *   **Proof Sketch**: The independence of $\bar{X}$ and $S^2$ and the chi-square distribution of $(n-1)S^2/\sigma^2$ are fundamental results that "can indeed be established" (the source implies the full proof is beyond the scope of this particular explanation). This independence is a **unique property of the normal distribution**.
*   **Corollary 6.5.2 (t-distribution)**:
    *   Let $X_1, \dots, X_n$ be a sample from a normal population with mean $\mu$. If $\bar{X}$ denotes the sample mean and $S$ the sample standard deviation, then **$\frac{\sqrt{n}(\bar{X} - \mu)}{S} \sim t_{n-1}$**.
    *   **Proof Sketch**: A t-random variable with $n$ degrees of freedom is defined as $\frac{Z}{\sqrt{\chi_n^2/n}}$, where $Z$ is a standard normal and is independent of $\chi_n^2$. By Theorem 6.5.1, $\frac{\sqrt{n}(\bar{X} - \mu)}{\sigma}$ is standard normal, and $\frac{(n-1)S^2}{\sigma^2}$ is chi-square with $n-1$ degrees of freedom and is independent of $\bar{X}$. Substituting these into the definition of the t-distribution (with $Z = \frac{\sqrt{n}(\bar{X} - \mu)}{\sigma}$ and $\chi_n^2 = \frac{(n-1)S^2}{\sigma^2}$ and $n$ replaced by $n-1$) directly yields the result.

**6.6 Sampling from a Finite Population**

*   The chapter overview mentions that this section will explain what it means for the sample to be a "random sample" when sampling from a finite population of elements. It also discusses how a large population size in relation to the sample size often allows it to be treated as if it were of infinite size. However, the provided excerpts do not delve into the detailed content of this section.