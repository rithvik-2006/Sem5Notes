# Chapter 4: Random Variables and Expectation

This chapter introduces the fundamental concepts of random variables and their expected values, which are crucial for understanding probability theory and statistics.

## 4.1 Random Variables

**Definition:** A **random variable** is a numerical quantity determined by the result of a random experiment. We are often interested in a specific numerical outcome of an experiment rather than all its intricate details.

- **Example:** In tossing two dice, the sum of the two dice (e.g., 7) is a random variable, irrespective of the individual die outcomes (e.g., (1,6) or (2,5)).

**Probabilities of Values:** Since a random variable's value is determined by the experiment's outcome, probabilities can be assigned to its possible values.

- **Example (Sum of two fair dice):** If $X$ is the sum of two fair dice:
  - $P\{X=2\} = P\{(1,1)\} = \frac{1}{36}$
  - $P\{X=7\} = P\{(1,6), (2,5), (3,4), (4,3), (5,2), (6,1)\} = \frac{6}{36}$
  - The sum of probabilities for all possible values of $X$ must equal 1.

**Cumulative Distribution Function (CDF):** For a random variable $X$, its cumulative distribution function $F(x)$ is defined as $F(x) = P\{X \leq x\}$.

Properties of $F(x)$:
- $F(x)$ is non-decreasing
- $F(x) \to 0$ as $x \to -\infty$ and $F(x) \to 1$ as $x \to \infty$
- $P\{a < X \leq b\} = F(b) - F(a)$

**Example:** If $F(x) = \begin{cases} 0 & \text{for } x \leq 0 \\ 1 - \exp\{-x^2\} & \text{for } x > 0 \end{cases}$, then $P\{X > 1\} = 1 - F(1) = e^{-1} \approx 0.368$.

## 4.2 Types of Random Variables

Random variables are classified based on their set of possible values.

### Discrete Random Variables

A random variable whose set of possible values is a sequence (e.g., integers 0, 1, 2, ...).

**Probability Mass Function (PMF):** For a discrete random variable $X$, $p(a) = P\{X = a\}$.

The CDF for a discrete variable is a step function (e.g., Figure 4.2 illustrates this with jumps at each possible value).

### Continuous Random Variables

A random variable whose set of possible values is an interval.

**Probability Density Function (PDF):** A non-negative function $f(x)$ such that for any set $B$ of real numbers, $P\{X \in B\} = \int_B f(x) \, dx$.

Properties of $f(x)$:
- $f(x) \geq 0$ for all $x$
- $\int_{-\infty}^{\infty} f(x) \, dx = 1$

$P\{a < X < b\} = \int_a^b f(x) \, dx$

**Example:** If $f(x) = C(4x - 2x^2)$ for $0 < x < 2$ (and $0$ otherwise):
- To find $C$, set $\int_0^2 C(4x - 2x^2) \, dx = 1$, yielding $C = \frac{3}{8}$
- Then $P\{X > 1\} = \int_1^2 \frac{3}{8}(4x - 2x^2) \, dx = \frac{1}{2}$

## 4.3 Jointly Distributed Random Variables

Often, we are interested in the relationships between two or more random variables.

**Joint Cumulative Probability Distribution Function:** For random variables $X$ and $Y$, $F(x, y) = P\{X \leq x, Y \leq y\}$.

The marginal distribution function of $X$ can be found from the joint CDF: $F_X(x) = P\{X \leq x\} = \lim_{y \to \infty} F(x, y)$.

### Discrete Case

**Joint Probability Mass Function:** $p(x, y) = P\{X = x, Y = y\}$

**Marginal Probability Mass Functions:**
- $P\{X = x_i\} = \sum_j p(x_i, y_j)$ (row sums in a table)
- $P\{Y = y_j\} = \sum_i p(x_i, y_j)$ (column sums in a table)
- Knowledge of individual PMFs does *not* determine the joint PMF

**Example (Batteries):** If $X$ is the number of new batteries and $Y$ is the number of used-but-working batteries in a sample, their joint probabilities can be represented in a table, with marginal PMFs as row and column sums.

### Continuous Case

**Joint Probability Density Function:** $f(x, y)$ such that $P\{(X, Y) \in C\} = \iint_{(x,y) \in C} f(x, y) \, dx \, dy$ for any set $C$ in the 2D plane.

**Marginal Probability Density Functions:**
- $f_X(x) = \int_{-\infty}^{\infty} f(x, y) \, dy$
- $f_Y(y) = \int_{-\infty}^{\infty} f(x, y) \, dx$

$f(a, b) \, da \, db \approx P\{a < X < a+da, b < Y < b+db\}$, so $f(a, b)$ measures the likelihood of $(X, Y)$ being near $(a, b)$.

**Example:** If $f(x, y) = 2e^{-x}e^{-2y}$ for $x>0, y>0$:
- $P\{X > 1, Y < 1\} = \int_0^1 \int_1^\infty 2e^{-x}e^{-2y} \, dx \, dy = e^{-1}(1 - e^{-2})$
- $P\{X < Y\} = \int_0^\infty \int_0^y 2e^{-x}e^{-2y} \, dx \, dy = \frac{1}{3}$

### 4.3.1 Independent Random Variables

**Definition:** $X$ and $Y$ are **independent** if $P\{X \in A, Y \in B\} = P\{X \in A\}P\{Y \in B\}$ for any sets of real numbers $A$ and $B$.

- **Discrete Equivalence:** $p(x, y) = p_X(x)p_Y(y)$ for all $x, y$
- **Continuous Equivalence:** $f(x, y) = f_X(x)f_Y(y)$ for all $x, y$

Loosely, knowing the value of one independent random variable does not change the distribution of the other.

The concept extends to multiple random variables: $X_1, \ldots, X_n$ are independent if $P\{X_1 \in A_1, \ldots, X_n \in A_n\} = \prod_{i=1}^n P\{X_i \in A_i\}$.

### 4.3.2 Conditional Distributions

#### Discrete Case (Conditional PMF)

The conditional probability mass function of $X$ given $Y=y$ is:
$$p_{X|Y}(x|y) = P\{X=x|Y=y\} = \frac{p(x, y)}{p_Y(y)}$$
(for $p_Y(y) > 0$)

**Example:** If a family has one girl ($G=1$), the conditional PMF for the number of boys ($B$) can be calculated. For instance, $P\{B=0|G=1\} = \frac{P\{B=0, G=1\}}{P\{G=1\}} = \frac{0.10}{0.3875} = \frac{8}{31}$.

#### Continuous Case (Conditional PDF)

The conditional probability density function of $X$ given $Y=y$ is:
$$f_{X|Y}(x|y) = \frac{f(x, y)}{f_Y(y)}$$
(for $f_Y(y) > 0$)

**Example:** For a joint density $f(x, y) = \frac{12}{5}x(2-x-y)$ ($0<x<1, 0<y<1$), if $f_Y(y) = \int_0^1 \frac{12}{5}x(2-x-y) \, dx = \frac{12}{5}\left(\frac{2}{3} - \frac{y}{2}\right) = \frac{2}{5}(4-3y)$, then $f_{X|Y}(x|y) = \frac{6x(2-x-y)}{4-3y}$.

## 4.4 Expectation

### Definition for Discrete Random Variables

The **expectation** or **expected value** of $X$, denoted $E[X]$, is a weighted average of its possible values:
$$E[X] = \sum_i x_i P\{X=x_i\}$$

**Example (Fair Die):** If $X$ is the outcome of a fair die, $E[X] = 1 \cdot \frac{1}{6} + 2 \cdot \frac{1}{6} + \cdots + 6 \cdot \frac{1}{6} = \frac{7}{2}$.

**Example (Indicator Variable):** If $I=1$ if event $A$ occurs and $I=0$ otherwise, then $E[I] = 1 \cdot P(A) + 0 \cdot P(A^c) = P(A)$.

### Definition for Continuous Random Variables

$$E[X] = \int_{-\infty}^{\infty} x f(x) \, dx$$

**Example:** If $f(x) = \frac{1}{1.5}$ for $0 < x < 1.5$ (and $0$ otherwise), $E[X] = \int_0^{1.5} x \cdot \frac{1}{1.5} \, dx = 0.75$. On average, one waits $0.75$ hours.

**Interpretation:** Expectation is analogous to the physical concept of the **center of gravity** of a mass distribution. $E[X]$ has the same units as $X$.

**Entropy (Optional):** The amount of information in a message about a random variable's value. For an event with probability $p$, information $I(p)$ is defined such that $I(pq) = I(p) + I(q)$. This leads to $I(p) = -\log_2(p)$.

## 4.5 Properties of the Expected Value

### Expectation of a Function of a Random Variable (Proposition 4.5.1)

- **Discrete:** $E[g(X)] = \sum_x g(x)p(x)$
- **Continuous:** $E[g(X)] = \int_{-\infty}^{\infty} g(x)f(x) \, dx$

**Example:** If $p(0)=0.2, p(1)=0.5, p(2)=0.3$, then $E[X^2] = 0^2(0.2) + 1^2(0.5) + 2^2(0.3) = 1.7$.

### Linearity of Expectation (Corollary 4.5.2)

For constants $a, b$: $E[aX + b] = aE[X] + b$

Special cases:
- $E[b] = b$ (expected value of a constant is itself)
- $E[aX] = aE[X]$

### Moments

$E[X^n]$ is the **nth moment** of $X$.

### Expected Value of Sums of Random Variables

$E[X + Y] = E[X] + E[Y]$. This holds for any random variables, regardless of independence.

This extends to any number of random variables: $E\left[\sum_{i=1}^n X_i\right] = \sum_{i=1}^n E[X_i]$

**Example (Sum of Two Dice):** If $X = X_1 + X_2$ (where $X_i$ is the value on die $i$), $E[X] = E[X_1] + E[X_2] = \frac{7}{2} + \frac{7}{2} = 7$.

**Example (Total Profit):** For 3 jobs with profits $X_1, X_2, X_3$ and winning probabilities, $E[\text{total profit}] = E[X_1] + E[X_2] + E[X_3]$.

### Best Predictor

The mean $\mu = E[X]$ is the best predictor of a random variable $X$ in terms of minimizing the expected square of its error, $E[(X-c)^2]$.

## 4.6 Variance

**Definition:** The **variance** of a random variable $X$, denoted $\text{Var}(X)$ or $\sigma^2$, measures its spread or variation around its mean $\mu = E[X]$:
$$\text{Var}(X) = E[(X - \mu)^2]$$

**Alternative Formula:** $\text{Var}(X) = E[X^2] - (E[X])^2$

**Standard Deviation:** The **standard deviation** is $\sigma = \sqrt{\text{Var}(X)}$.

**Example (Fair Die):** If $X$ is the outcome of a fair die, $E[X] = \frac{7}{2}$, $E[X^2] = \frac{91}{6}$. $\text{Var}(X) = \frac{91}{6} - \left(\frac{7}{2}\right)^2 = \frac{35}{12}$.

**Example (Indicator Variable):** If $I$ is an indicator variable for event $A$ with $P(A)=p$, then $E[I]=p$. $\text{Var}(I) = E[I^2] - (E[I])^2 = p - p^2 = p(1-p)$.

### Properties of Variance

For constants $a, b$:
$$\text{Var}(aX + b) = a^2 \text{Var}(X)$$

Special cases:
- $\text{Var}(b) = 0$ (variance of a constant is zero)
- $\text{Var}(X+b) = \text{Var}(X)$ (adding a constant doesn't change spread)
- $\text{Var}(aX) = a^2 \text{Var}(X)$

## 4.7 Covariance and Variance of Sums of Random Variables

### Covariance

The **covariance** of two random variables $X$ and $Y$, denoted $\text{Cov}(X, Y)$, measures the degree to which they vary together:
$$\text{Cov}(X, Y) = E[(X - \mu_X)(Y - \mu_Y)]$$

**Alternative Formula:** $\text{Cov}(X, Y) = E[XY] - E[X]E[Y]$

### Properties of Covariance

- $\text{Cov}(X, Y) = \text{Cov}(Y, X)$
- $\text{Cov}(X, X) = \text{Var}(X)$
- $\text{Cov}(aX, Y) = a\text{Cov}(X, Y)$
- **If $X$ and $Y$ are independent, then $\text{Cov}(X, Y) = 0$** (The converse is not always true: $\text{Cov}(X,Y)=0$ does not necessarily imply independence)

### Variance of Sums

**General Case:** $\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y) + 2\text{Cov}(X, Y)$

**For Independent Random Variables (Theorem 4.7.4):** If $X_1, \ldots, X_n$ are independent, then:
$$\text{Var}\left(\sum_{i=1}^n X_i\right) = \sum_{i=1}^n \text{Var}(X_i)$$

**Example:** For 10 independent rolls of a fair die, $X_i$:
$$\text{Var}\left(\sum_{i=1}^{10} X_i\right) = \sum_{i=1}^{10} \text{Var}(X_i) = 10 \cdot \frac{35}{12} = \frac{175}{6}$$

**Example:** For 10 independent tosses of a fair coin (number of heads):
$$\text{Var}\left(\sum_{j=1}^{10} I_j\right) = \sum_{j=1}^{10} \text{Var}(I_j) = 10 \cdot \frac{1}{4} = \frac{10}{4}$$

### Covariance of Indicator Variables

If $X, Y$ are indicator variables for events $A, B$, then:
$$\text{Cov}(X, Y) = P\{X=1, Y=1\} - P\{X=1\}P\{Y=1\}$$

## 4.8 Moment Generating Functions

**Definition:** The **moment generating function (MGF)** of a random variable $X$ is $\phi(t) = E[e^{tX}]$ for all values of $t$ for which the expectation is finite.

### Properties

- The $n$th derivative of $\phi(t)$ evaluated at $t=0$ gives the $n$th moment of $X$: $\phi^{(n)}(0) = E[X^n]$
- **For Independent Random Variables:** If $X$ and $Y$ are independent, the MGF of their sum is the product of their individual MGFs: $\phi_{X+Y}(t) = \phi_X(t)\phi_Y(t)$
- **Uniqueness:** The MGF uniquely determines the distribution of a random variable

## 4.9 Chebyshev's Inequality and The Weak Law of Large Numbers

These provide bounds on probabilities and describe the behavior of sample averages.

### Markov's Inequality

For a non-negative random variable $X$:
$$P\{X \geq a\} \leq \frac{E[X]}{a}$$
for any $a > 0$.

### Chebyshev's Inequality

For a random variable $X$ with mean $\mu$ and variance $\sigma^2$:
$$P\{|X - \mu| \geq k\} \leq \frac{\sigma^2}{k^2}$$
for any $k > 0$.

This implies $P\{|X - \mu| > k\sigma\} \leq \frac{1}{k^2}$.

**Example (Production):** If weekly production $X$ has $E[X]=50$ and $\text{Var}(X)=25$, then:
$$P\{|X-50| \geq 10\} \leq \frac{25}{10^2} = \frac{1}{4}$$

So, $P\{40 < X < 60\} \geq \frac{3}{4}$.

### The Weak Law of Large Numbers (Theorem 4.9.3)

Let $X_1, X_2, \ldots$ be a sequence of independent and identically distributed (i.i.d.) random variables, each with mean $\mu$. Then, for any $\varepsilon > 0$:
$$P\left\{\left|\frac{X_1 + \cdots + X_n}{n} - \mu\right| > \varepsilon\right\} \to 0 \text{ as } n \to \infty$$

This means that the sample average converges to the population mean in probability. The proof (under the assumption of finite variance) uses Chebyshev's inequality.# Chapter 4: Random Variables and Expectation

This chapter introduces the fundamental concepts of random variables and their expected values, which are crucial for understanding probability theory and statistics.

## 4.1 Random Variables

**Definition:** A **random variable** is a numerical quantity determined by the result of a random experiment. We are often interested in a specific numerical outcome of an experiment rather than all its intricate details.

- **Example:** In tossing two dice, the sum of the two dice (e.g., 7) is a random variable, irrespective of the individual die outcomes (e.g., (1,6) or (2,5)).

**Probabilities of Values:** Since a random variable's value is determined by the experiment's outcome, probabilities can be assigned to its possible values.

- **Example (Sum of two fair dice):** If $X$ is the sum of two fair dice:
  - $P\{X=2\} = P\{(1,1)\} = \frac{1}{36}$
  - $P\{X=7\} = P\{(1,6), (2,5), (3,4), (4,3), (5,2), (6,1)\} = \frac{6}{36}$
  - The sum of probabilities for all possible values of $X$ must equal 1.

**Cumulative Distribution Function (CDF):** For a random variable $X$, its cumulative distribution function $F(x)$ is defined as $F(x) = P\{X \leq x\}$.

Properties of $F(x)$:
- $F(x)$ is non-decreasing
- $F(x) \to 0$ as $x \to -\infty$ and $F(x) \to 1$ as $x \to \infty$
- $P\{a < X \leq b\} = F(b) - F(a)$

**Example:** If $F(x) = \begin{cases} 0 & \text{for } x \leq 0 \\ 1 - \exp\{-x^2\} & \text{for } x > 0 \end{cases}$, then $P\{X > 1\} = 1 - F(1) = e^{-1} \approx 0.368$.

## 4.2 Types of Random Variables

Random variables are classified based on their set of possible values.

### Discrete Random Variables

A random variable whose set of possible values is a sequence (e.g., integers 0, 1, 2, ...).

**Probability Mass Function (PMF):** For a discrete random variable $X$, $p(a) = P\{X = a\}$.

The CDF for a discrete variable is a step function (e.g., Figure 4.2 illustrates this with jumps at each possible value).

### Continuous Random Variables

A random variable whose set of possible values is an interval.

**Probability Density Function (PDF):** A non-negative function $f(x)$ such that for any set $B$ of real numbers, $P\{X \in B\} = \int_B f(x) \, dx$.

Properties of $f(x)$:
- $f(x) \geq 0$ for all $x$
- $\int_{-\infty}^{\infty} f(x) \, dx = 1$

$P\{a < X < b\} = \int_a^b f(x) \, dx$

**Example:** If $f(x) = C(4x - 2x^2)$ for $0 < x < 2$ (and $0$ otherwise):
- To find $C$, set $\int_0^2 C(4x - 2x^2) \, dx = 1$, yielding $C = \frac{3}{8}$
- Then $P\{X > 1\} = \int_1^2 \frac{3}{8}(4x - 2x^2) \, dx = \frac{1}{2}$

## 4.3 Jointly Distributed Random Variables

Often, we are interested in the relationships between two or more random variables.

**Joint Cumulative Probability Distribution Function:** For random variables $X$ and $Y$, $F(x, y) = P\{X \leq x, Y \leq y\}$.

The marginal distribution function of $X$ can be found from the joint CDF: $F_X(x) = P\{X \leq x\} = \lim_{y \to \infty} F(x, y)$.

### Discrete Case

**Joint Probability Mass Function:** $p(x, y) = P\{X = x, Y = y\}$

**Marginal Probability Mass Functions:**
- $P\{X = x_i\} = \sum_j p(x_i, y_j)$ (row sums in a table)
- $P\{Y = y_j\} = \sum_i p(x_i, y_j)$ (column sums in a table)
- Knowledge of individual PMFs does *not* determine the joint PMF

**Example (Batteries):** If $X$ is the number of new batteries and $Y$ is the number of used-but-working batteries in a sample, their joint probabilities can be represented in a table, with marginal PMFs as row and column sums.

### Continuous Case

**Joint Probability Density Function:** $f(x, y)$ such that $P\{(X, Y) \in C\} = \iint_{(x,y) \in C} f(x, y) \, dx \, dy$ for any set $C$ in the 2D plane.

**Marginal Probability Density Functions:**
- $f_X(x) = \int_{-\infty}^{\infty} f(x, y) \, dy$
- $f_Y(y) = \int_{-\infty}^{\infty} f(x, y) \, dx$

$f(a, b) \, da \, db \approx P\{a < X < a+da, b < Y < b+db\}$, so $f(a, b)$ measures the likelihood of $(X, Y)$ being near $(a, b)$.

**Example:** If $f(x, y) = 2e^{-x}e^{-2y}$ for $x>0, y>0$:
- $P\{X > 1, Y < 1\} = \int_0^1 \int_1^\infty 2e^{-x}e^{-2y} \, dx \, dy = e^{-1}(1 - e^{-2})$
- $P\{X < Y\} = \int_0^\infty \int_0^y 2e^{-x}e^{-2y} \, dx \, dy = \frac{1}{3}$

### 4.3.1 Independent Random Variables

**Definition:** $X$ and $Y$ are **independent** if $P\{X \in A, Y \in B\} = P\{X \in A\}P\{Y \in B\}$ for any sets of real numbers $A$ and $B$.

- **Discrete Equivalence:** $p(x, y) = p_X(x)p_Y(y)$ for all $x, y$
- **Continuous Equivalence:** $f(x, y) = f_X(x)f_Y(y)$ for all $x, y$

Loosely, knowing the value of one independent random variable does not change the distribution of the other.

The concept extends to multiple random variables: $X_1, \ldots, X_n$ are independent if $P\{X_1 \in A_1, \ldots, X_n \in A_n\} = \prod_{i=1}^n P\{X_i \in A_i\}$.

### 4.3.2 Conditional Distributions

#### Discrete Case (Conditional PMF)

The conditional probability mass function of $X$ given $Y=y$ is:
$$p_{X|Y}(x|y) = P\{X=x|Y=y\} = \frac{p(x, y)}{p_Y(y)}$$
(for $p_Y(y) > 0$)

**Example:** If a family has one girl ($G=1$), the conditional PMF for the number of boys ($B$) can be calculated. For instance, $P\{B=0|G=1\} = \frac{P\{B=0, G=1\}}{P\{G=1\}} = \frac{0.10}{0.3875} = \frac{8}{31}$.

#### Continuous Case (Conditional PDF)

The conditional probability density function of $X$ given $Y=y$ is:
$$f_{X|Y}(x|y) = \frac{f(x, y)}{f_Y(y)}$$
(for $f_Y(y) > 0$)

**Example:** For a joint density $f(x, y) = \frac{12}{5}x(2-x-y)$ ($0<x<1, 0<y<1$), if $f_Y(y) = \int_0^1 \frac{12}{5}x(2-x-y) \, dx = \frac{12}{5}\left(\frac{2}{3} - \frac{y}{2}\right) = \frac{2}{5}(4-3y)$, then $f_{X|Y}(x|y) = \frac{6x(2-x-y)}{4-3y}$.

## 4.4 Expectation

### Definition for Discrete Random Variables

The **expectation** or **expected value** of $X$, denoted $E[X]$, is a weighted average of its possible values:
$$E[X] = \sum_i x_i P\{X=x_i\}$$

**Example (Fair Die):** If $X$ is the outcome of a fair die, $E[X] = 1 \cdot \frac{1}{6} + 2 \cdot \frac{1}{6} + \cdots + 6 \cdot \frac{1}{6} = \frac{7}{2}$.

**Example (Indicator Variable):** If $I=1$ if event $A$ occurs and $I=0$ otherwise, then $E[I] = 1 \cdot P(A) + 0 \cdot P(A^c) = P(A)$.

### Definition for Continuous Random Variables

$$E[X] = \int_{-\infty}^{\infty} x f(x) \, dx$$

**Example:** If $f(x) = \frac{1}{1.5}$ for $0 < x < 1.5$ (and $0$ otherwise), $E[X] = \int_0^{1.5} x \cdot \frac{1}{1.5} \, dx = 0.75$. On average, one waits $0.75$ hours.

**Interpretation:** Expectation is analogous to the physical concept of the **center of gravity** of a mass distribution. $E[X]$ has the same units as $X$.

**Entropy (Optional):** The amount of information in a message about a random variable's value. For an event with probability $p$, information $I(p)$ is defined such that $I(pq) = I(p) + I(q)$. This leads to $I(p) = -\log_2(p)$.

## 4.5 Properties of the Expected Value

### Expectation of a Function of a Random Variable (Proposition 4.5.1)

- **Discrete:** $E[g(X)] = \sum_x g(x)p(x)$
- **Continuous:** $E[g(X)] = \int_{-\infty}^{\infty} g(x)f(x) \, dx$

**Example:** If $p(0)=0.2, p(1)=0.5, p(2)=0.3$, then $E[X^2] = 0^2(0.2) + 1^2(0.5) + 2^2(0.3) = 1.7$.

### Linearity of Expectation (Corollary 4.5.2)

For constants $a, b$: $E[aX + b] = aE[X] + b$

Special cases:
- $E[b] = b$ (expected value of a constant is itself)
- $E[aX] = aE[X]$

### Moments

$E[X^n]$ is the **nth moment** of $X$.

### Expected Value of Sums of Random Variables

$E[X + Y] = E[X] + E[Y]$. This holds for any random variables, regardless of independence.

This extends to any number of random variables: $E\left[\sum_{i=1}^n X_i\right] = \sum_{i=1}^n E[X_i]$

**Example (Sum of Two Dice):** If $X = X_1 + X_2$ (where $X_i$ is the value on die $i$), $E[X] = E[X_1] + E[X_2] = \frac{7}{2} + \frac{7}{2} = 7$.

**Example (Total Profit):** For 3 jobs with profits $X_1, X_2, X_3$ and winning probabilities, $E[\text{total profit}] = E[X_1] + E[X_2] + E[X_3]$.

### Best Predictor

The mean $\mu = E[X]$ is the best predictor of a random variable $X$ in terms of minimizing the expected square of its error, $E[(X-c)^2]$.

## 4.6 Variance

**Definition:** The **variance** of a random variable $X$, denoted $\text{Var}(X)$ or $\sigma^2$, measures its spread or variation around its mean $\mu = E[X]$:
$$\text{Var}(X) = E[(X - \mu)^2]$$

**Alternative Formula:** $\text{Var}(X) = E[X^2] - (E[X])^2$

**Standard Deviation:** The **standard deviation** is $\sigma = \sqrt{\text{Var}(X)}$.

**Example (Fair Die):** If $X$ is the outcome of a fair die, $E[X] = \frac{7}{2}$, $E[X^2] = \frac{91}{6}$. $\text{Var}(X) = \frac{91}{6} - \left(\frac{7}{2}\right)^2 = \frac{35}{12}$.

**Example (Indicator Variable):** If $I$ is an indicator variable for event $A$ with $P(A)=p$, then $E[I]=p$. $\text{Var}(I) = E[I^2] - (E[I])^2 = p - p^2 = p(1-p)$.

### Properties of Variance

For constants $a, b$:
$$\text{Var}(aX + b) = a^2 \text{Var}(X)$$

Special cases:
- $\text{Var}(b) = 0$ (variance of a constant is zero)
- $\text{Var}(X+b) = \text{Var}(X)$ (adding a constant doesn't change spread)
- $\text{Var}(aX) = a^2 \text{Var}(X)$

## 4.7 Covariance and Variance of Sums of Random Variables

### Covariance

The **covariance** of two random variables $X$ and $Y$, denoted $\text{Cov}(X, Y)$, measures the degree to which they vary together:
$$\text{Cov}(X, Y) = E[(X - \mu_X)(Y - \mu_Y)]$$

**Alternative Formula:** $\text{Cov}(X, Y) = E[XY] - E[X]E[Y]$

### Properties of Covariance

- $\text{Cov}(X, Y) = \text{Cov}(Y, X)$
- $\text{Cov}(X, X) = \text{Var}(X)$
- $\text{Cov}(aX, Y) = a\text{Cov}(X, Y)$
- **If $X$ and $Y$ are independent, then $\text{Cov}(X, Y) = 0$** (The converse is not always true: $\text{Cov}(X,Y)=0$ does not necessarily imply independence)

### Variance of Sums

**General Case:** $\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y) + 2\text{Cov}(X, Y)$

**For Independent Random Variables (Theorem 4.7.4):** If $X_1, \ldots, X_n$ are independent, then:
$$\text{Var}\left(\sum_{i=1}^n X_i\right) = \sum_{i=1}^n \text{Var}(X_i)$$

**Example:** For 10 independent rolls of a fair die, $X_i$:
$$\text{Var}\left(\sum_{i=1}^{10} X_i\right) = \sum_{i=1}^{10} \text{Var}(X_i) = 10 \cdot \frac{35}{12} = \frac{175}{6}$$

**Example:** For 10 independent tosses of a fair coin (number of heads):
$$\text{Var}\left(\sum_{j=1}^{10} I_j\right) = \sum_{j=1}^{10} \text{Var}(I_j) = 10 \cdot \frac{1}{4} = \frac{10}{4}$$

### Covariance of Indicator Variables

If $X, Y$ are indicator variables for events $A, B$, then:
$$\text{Cov}(X, Y) = P\{X=1, Y=1\} - P\{X=1\}P\{Y=1\}$$

## 4.8 Moment Generating Functions

**Definition:** The **moment generating function (MGF)** of a random variable $X$ is $\phi(t) = E[e^{tX}]$ for all values of $t$ for which the expectation is finite.

### Properties

- The $n$th derivative of $\phi(t)$ evaluated at $t=0$ gives the $n$th moment of $X$: $\phi^{(n)}(0) = E[X^n]$
- **For Independent Random Variables:** If $X$ and $Y$ are independent, the MGF of their sum is the product of their individual MGFs: $\phi_{X+Y}(t) = \phi_X(t)\phi_Y(t)$
- **Uniqueness:** The MGF uniquely determines the distribution of a random variable

## 4.9 Chebyshev's Inequality and The Weak Law of Large Numbers

These provide bounds on probabilities and describe the behavior of sample averages.

### Markov's Inequality

For a non-negative random variable $X$:
$$P\{X \geq a\} \leq \frac{E[X]}{a}$$
for any $a > 0$.

### Chebyshev's Inequality

For a random variable $X$ with mean $\mu$ and variance $\sigma^2$:
$$P\{|X - \mu| \geq k\} \leq \frac{\sigma^2}{k^2}$$
for any $k > 0$.

This implies $P\{|X - \mu| > k\sigma\} \leq \frac{1}{k^2}$.

**Example (Production):** If weekly production $X$ has $E[X]=50$ and $\text{Var}(X)=25$, then:
$$P\{|X-50| \geq 10\} \leq \frac{25}{10^2} = \frac{1}{4}$$

So, $P\{40 < X < 60\} \geq \frac{3}{4}$.

### The Weak Law of Large Numbers (Theorem 4.9.3)

Let $X_1, X_2, \ldots$ be a sequence of independent and identically distributed (i.i.d.) random variables, each with mean $\mu$. Then, for any $\varepsilon > 0$:
$$P\left\{\left|\frac{X_1 + \cdots + X_n}{n} - \mu\right| > \varepsilon\right\} \to 0 \text{ as } n \to \infty$$

This means that the sample average converges to the population mean in probability. The proof (under the assumption of finite variance) uses Chebyshev's inequality.