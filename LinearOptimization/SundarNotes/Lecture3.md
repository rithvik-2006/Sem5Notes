

# Lecture 3: Foundational Concepts of Linear Algebra

Lecture 3 delves into the foundational concepts of Linear Algebra, providing the essential vocabulary needed to understand the set of all solutions to a system of linear equations, which was the focus of Lecture 2. While acknowledging that many might associate vector spaces with explicit coordinates like $(3, 4.55, 0.76, 0, \ldots, 4)^T$, the lecture initially treads a more abstract path, developing the subject without explicit coordinates.

## Key Concepts from Lecture 3:

### 1. Vector Space Definition

A **vector space** is formally defined as a set of **vectors $V$** and the **real numbers $\mathbb{R}$** (referred to as **scalars**), with two fundamental operations defined:

* **Vector Addition**: An operation $V \times V \to V$, represented as $u + v$, where $u, v \in V$.
* **Scalar Multiplication**: An operation $\mathbb{R} \times V \to V$, represented as $a \cdot u$, where $a \in \mathbb{R}$ and $u \in V$.

### 2. Axioms of a Vector Space

These operations must adhere to specific laws (axioms):

* **Abelian Group Laws (for Vector Addition)**:
    1.  **Associativity**: $u + (v + w) = (u + v) + w$
    2.  **Identity**: There exists a **zero vector $0$** such that $0 + u = u$.
    3.  **Inverse**: For every $u \in V$, there exists an **additive inverse $-u$** such that $u + (-u) = 0$.
    4.  **Commutativity**: $u + v = v + u$.
* **Scalar Multiplication Laws**:
    1.  **Multiplication by 0**: $0 \cdot u = 0$ (where the first 0 is the scalar, the second is the zero vector).
    2.  **Multiplication by -1**: $(-1) \cdot u = -u$.
    3.  **Identity multiplication**: $1 \cdot u = u$.
    4.  **Distributivity of vector sum**: $a \cdot (u + v) = a \cdot u + a \cdot v$.
    5.  **Distributivity of scalar sum**: $(a + b) \cdot u = a \cdot u + b \cdot u$.
    6.  **Associativity of scalar multiplication**: $a \cdot (b \cdot u) = (ab) \cdot u$.
    It's important to **check that familiar vectors obey these laws.**

### 3. Subspace

A **subspace $U$** is a **subset of vectors $U \subseteq V$** that is itself a vector space. The laws of vector addition and scalar multiplication are inherited. A subset $U$ qualifies as a subspace if, for any two vectors $u_1, u_2 \in U$ and any real scalar $\alpha \in \mathbb{R}$, the following conditions hold:

* $u_1 + u_2 \in U$ (closure under vector addition).
* $\alpha \cdot u_1 \in U$ (closure under scalar multiplication).

An important implication is that the **zero vector $0$ is always a member of any subspace.**

### 4. Example 1 (Subspaces in 2-dimensions):

In a 2-dimensional space, the subspaces are:

* Any **line passing through the origin**.
* The **origin by itself** (which can be seen as a line of zero length).
* The **entire plane** itself.

If a subspace contains any vector that does not lie on a specific line passing through the origin, then the subspace must encompass the entire plane.

### 5. Linear Dependence, Independence, and Basis

These definitions are crucial for understanding vector spaces.

* **Linear Dependence (Definition 1)**: Vectors $v_1, \ldots, v_n$ are **linearly dependent** if there exist scalars $\alpha_1, \ldots, \alpha_n \in \mathbb{R}$, **not all zero**, such that their linear combination equals the zero vector: $\sum_{i=1}^{n} \alpha_i \cdot v_i = 0$. The "not all zero" clause is key.
* **Linear Independence (Definition 2)**: Vectors $v_1, \ldots, v_n$ are **linearly independent** if they are not linearly dependent. This means that if $\sum_{i=1}^{n} \alpha_i \cdot v_i = 0$, then it must imply that all $\alpha_i = 0$.
* **Basis (Definition 3)**: A set of vectors $v_1, \ldots, v_n$ forms a **basis** of a vector space $V$ if and only if:
    1.  They are **linearly independent**.
    2.  Every other vector $w \in V$ can be written as a **linear combination** of these vectors: $w = \sum_{i=1}^{n} \beta_i \cdot v_i$.
    Alternatively, a set forms a basis if they are linearly independent, and if any other vector $w \in V$ is added to this set, the expanded set becomes linearly dependent.

### 6. Dimension of a Vector Space

A **crucial fact** regarding bases is that, although a vector space can have **multiple different bases**, **all of them will have the exact same size**. This fact might seem intuitive in two or three dimensions, but it requires a formal proof, which is often used in mathematics and algorithm design.

The **number of vectors in any basis** for a vector space $V$ is called the **dimension of the vector space**. While infinite-dimensional vector spaces exist, Lecture 3 indicates that the course will only deal with **finite-dimensional vector spaces**.

### 7. Proof of Dimension Invariance (Theorem 1)

Lecture 3 provides a detailed proof for the theorem stating that if two sets of vectors, $S$ and $T$, are both bases for the same vector space $V$, then they must have the same size ($m = n$).

* The proof uses a **contradiction strategy**. It assumes that $|S| < |T|$ (i.e., $m < n$) and then proceeds to show this leads to a contradiction.
* The core idea is to **repeatedly replace elements of the larger set $T$ with elements from the smaller set $S$**, while continuously ensuring that the resulting set remains a basis.
* This process relies on **Lemma 1**, which states that if $S = \{v_1, \ldots, v_n\}$ is a basis and $x$ is a linear combination of these vectors with $\alpha_1 \ne 0$ (i.e., $x = \sum_{i=1}^{n} \alpha_i v_i$), then replacing $v_1$ with $x$ to form $S' = \{x, v_2, \ldots, v_n\}$ will result in a set $S'$ that spans the same space as $S$. This demonstrates how one vector in a basis can be substituted by another to maintain the span and basis property. The lecture notes explicitly mention that **"We did something like this during the proof that Gaussian Elimination works. Do go over it."**, directly linking this proof technique back to the material covered in Lecture 2 regarding the correctness of solving $Ax=b$.
* The proof proceeds iteratively: starting with $S_0 = S$, elements from $S$ are systematically replaced by elements from $T$. The crucial step involves showing that if $S_i$ is a basis, and a vector $v_{i+1}$ from $T_i$ (the remaining part of $T$) is expressed as a linear combination of vectors in $S_i$, then at least one of the original $u_j$ coefficients must be non-zero. This allows $u_j$ to be replaced by $v_{i+1}$ using Lemma 1, forming a new basis $S_{i+1}$.
* After $m$ such substitutions, the resulting set $S_m$ would consist entirely of $m$ vectors from $T$ that span $V$. Since $m < n$, this means that $T$ still contains $n-m$ vectors which are not used in $S_m$ and could be expressed in terms of vectors in $S_m$, contradicting the linear independence of $T$ as a basis. This proves that $m$ must equal $n$.

### 8. Span of a Set of Vectors

The **span of a set of vectors $v_1, \ldots, v_k$** is defined as the **set of all vectors that can be obtained by taking linear combinations** of the vectors in the set. Formally, $\text{span}(v_1, \ldots, v_k)$ is the set $\{\sum_{i=1}^{n} \alpha_i v_i : \alpha_i \in \mathbb{R}\}$. Importantly, it's an exercise to prove that the **span of any set of vectors is always a subspace.**

---