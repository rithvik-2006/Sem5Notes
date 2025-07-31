

# CS 435: Linear Optimization, Lecture 4 - The Nullspace

This lecture, CS 435: Linear Optimization, Lecture 4, focuses on understanding the set of all solutions to the system $Ax = 0$, where $A$ is an $m \times n$ matrix and $x$ is a vector in $\mathbb{R}^n$. This set is denoted as $S = \{x : Ax = 0\}$.

## The Nullspace as a Subspace:

The lecture establishes that $S$ (the set of solutions to $Ax=0$) is a subspace of $\mathbb{R}^n$.
This is demonstrated by showing that:
* If $x \in S$, then any scalar multiple $\alpha x$ is also in $S$, since $A(\alpha x) = \alpha(Ax) = \alpha \cdot 0 = 0$.
* Additionally, if $x_1 \in S$ and $x_2 \in S$, their sum $x_1 + x_2$ is also in $S$, since $A(x_1 + x_2) = Ax_1 + Ax_2 = 0 + 0 = 0$.

The subspace $\{x : Ax = 0\}$ is formally called the **nullspace of the matrix $A$**.

## Dimension of the Nullspace:

A key question addressed is the dimension of $S$.

* **Theorem 1** states that if $k$ is the number of linearly independent columns in matrix $A$, then $\dim(S) = n - k$.
* **Theorem 3** presents a "row version," stating that if $k$ is the number of linearly independent rows in matrix $A$, then $\dim(S) = n - k$.

An interesting corollary of these theorems is that the number of linearly independent rows in a matrix is equal to the number of linearly independent columns. This number is defined as the **rank of the matrix $A$**.

## Relationship with the Column Space:

The **column space of $A$** is defined as the vector space spanned by the columns of $A$.

A crucial equivalence is presented: $Ax = b$ has a solution if and only if $b$ is in the column space of $A$. This is because $Ax = b$ can be written as a linear combination of the columns of $A$:
$A^{(1)}x_1 + A^{(2)}x_2 + \dots + A^{(n)}x_n = b$, where $A^{(i)}$ is the $i$-th column of $A$ and $x_i$ is the $i$-th component of vector $x$.

The objective of the lecture is to relate the dimension of the nullspace to the dimension of the space spanned by the columns of $A$. Specifically, the goal is to prove that the dimension of $\{x : Ax = 0\}$ is $n - k$, where $k$ is the dimension of the column space of $A$.

## Proof Strategy and Insights:

One observation that helps with the proof is that a vector $x = (x_1, x_2, \ldots, x_n)^T$ is in $S$ (i.e., $Ax = 0$) if and only if the linear combination of the columns of $A$ with $x$ as coefficients sums to zero: $\sum_{i=1}^n x_i A^{(i)} = 0$.

To prove that a subspace has dimension $n - k$, the strategy is to exhibit a basis of size $n - k$ for that subspace.

Assume that $A^{(1)}, A^{(2)}, \ldots, A^{(k)}$ form a basis for the column space of $A$. This implies that the other columns ($A^{(k+1)}$ through $A^{(n)}$) can be written as a linear combination of these basis columns.

Consider the equation $A^{(1)}x_1 + A^{(2)}x_2 + \dots + A^{(k)}x_k + A^{(k+1)}x_{k+1} + \dots + A^{(n)}x_n = 0$.

A key insight: If the values of $x_{k+1}$ through $x_n$ are set arbitrarily (these are $n - k$ variables, often called "free variables"), then the term $A^{(k+1)}x_{k+1} + \dots + A^{(n)}x_n$ will be a vector in the column space of $A$. Since it's in the column space, it can be expressed as a linear combination of the basis columns $A^{(1)}, \ldots, A^{(k)}$, allowing $x_1, \ldots, x_k$ to be determined to satisfy the equation. This "freeness" of the last $n - k$ variables is the reason the dimension is $n - k$.

## Formal Proof Steps for $\dim(S) = n - k$:

### Identifying $n - k$ Linearly Independent Vectors:

The columns not in the basis are written as linear combinations of the basis columns:
$A^{(k+1)} = \sum_{j=1}^k U_{1,j}A^{(j)}$
$A^{(k+2)} = \sum_{j=1}^k U_{2,j}A^{(j)}$
$\vdots$
$A^{(n)} = \sum_{j=1}^k U_{n-k,j}A^{(j)}$

These equations "in a disguised way" give $n - k$ linearly independent vectors in the nullspace. For example:
* The first vector, called $U_1$, is $\{-U_{1,1}, -U_{1,2}, \ldots, -U_{1,k}, 1, 0, \ldots, 0\}^T$.
* Similarly, $U_2$ is $\{-U_{2,1}, -U_{2,2}, \ldots, -U_{2,k}, 0, 1, \ldots, 0\}^T$, and so on, up to $U_{n-k}$ being $\{-U_{n-k,1}, -U_{n-k,2}, \ldots, -U_{n-k,k}, 0, 0, \ldots, 1\}^T$.

These vectors are in the nullspace because their construction directly stems from the equations $A^{(k+i)} - \sum_{j=1}^k U_{i,j}A^{(j)} = 0$, which is a linear combination of columns of $A$ that sums to zero, implying the vector of coefficients is in the nullspace.

They are linearly independent because of their structure, specifically the "last $n - k$ coordinates" (which contain a 1 in a different position for each vector and zeros elsewhere), which resemble parts of an identity matrix.

### Proving Spanning Property (Basis Completion):

To prove that these $n - k$ vectors form a basis for the nullspace, it must be shown that every other vector in $\{x : Ax = 0\}$ can be written as a linear combination of these $U_i$ vectors.

The lecture suggests a "reverse engineering" trick. If $x$ is in the nullspace ($Ax = 0$) and can be written as $\alpha_1 U_1 + \dots + \alpha_{n-k}U_{n-k}$, then the coefficients $\alpha_i$ must be equal to $x_{k+i}$ (the $(k+i)$-th component of $x$).

Consider a vector $x' = x_{k+1}U_{k+1} + \dots + x_n U_n$. It is noted that $Ax' = 0$.

Since $Ax = 0$ and $Ax' = 0$, it follows that $A(x - x') = 0$.

Crucially, the last $n - k$ components of $x - x'$ are zero due to how $x'$ is constructed (matching the free variables of $x$).

This implies that the linear combination of the first $k$ columns of $A$ (which correspond to the first $k$ components of $x - x'$) must be zero.

Since the first $k$ columns ($A^{(1)}, \ldots, A^{(k)}$) are linearly independent (as they form a basis for the column space), their linear combination can only be zero if all the coefficients are zero. This means the first $k$ components of $x - x'$ must also be zero.

Therefore, $x$ and $x'$ must coincide on their first $k$ coordinates as well, meaning they are the same vector. This completes the proof that any vector in the nullspace can be expressed as a linear combination of $U_1, \ldots, U_{n-k}$.

## Conclusion of the Proof:

Through these steps, the lecture formally proves that the dimension of $\{x : Ax = 0\}$ is exactly $n - k$. This links the dimension of the nullspace (the "nullity") to the number of columns ($n$) and the rank of the matrix ($k$).

