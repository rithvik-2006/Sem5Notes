Here are revision notes on the requested topics from Chapter 1 of the "Introduction to Linear Algebra" excerpts:

### 1 Introduction to Vectors
The front cover of the textbook visually represents a central concept of linear algebra: the equation **Ax = b is solvable when b is in the (orange) column space of A**. The core of linear algebra lies in two fundamental operations involving vectors: **vector addition (v + w)** and **scalar multiplication (cv)**. Combining these two operations creates a **linear combination (cv + dw)**. The textbook emphasises that linear algebra handles n-dimensional space smoothly, allowing mental pictures to remain correct even for higher dimensions where drawing is impossible.

### 1.1 Vectors and Linear Combinations
*   **Vectors as pairs/triplets of numbers**: A two-dimensional vector **v** is represented as a pair of numbers (v1, v2) (or as a column [v1; v2]). Similarly, a three-dimensional vector has three components (v1, v2, v3). The boldface italic 'v' denotes the vector, while lightface italic 'v1' and 'v2' denote its components.
*   **Vector Operations**:
    *   **Vector Addition**: Vectors are added component by component. For **v = [v1; v2]** and **w = [w1; w2]**, their sum is **v + w = [v1+w1; v2+w2]**. This means adding 'apples to apples', keeping components separate.
    *   **Scalar Multiplication**: A vector can be multiplied by any number 'c' (called a scalar), which involves multiplying each component by 'c'. For example, **cv = [cv1; cv2]**.
    *   **Zero Vector**: The sum of **-v** and **v** is the **zero vector (0)**, which has all components as zero (e.g., [0; 0] for 2D). The zero vector is always included in a "space" of vectors.
*   **Linear Combinations**: The sum of **cv** and **dw** is a **linear combination of v and w**. This operation is described as 'all-important'.
*   **Visualising Linear Combinations**:
    *   Vectors can be represented by arrows starting from the origin (0,0) and ending at the point corresponding to their components.
    *   Vector addition **v + w** can be visualised by placing the start of **w** at the end of **v**, with **v + w** forming the diagonal of a parallelogram.
    *   **All combinations of cu** (multiples of a single vector **u**) fill a **line**.
    *   **All combinations of cu + dv** (two vectors **u** and **v**) typically fill a **plane**, unless **w** is on the line of **u**.
    *   **All combinations of cu + dv + ew** (three vectors **u, v, w**) typically fill **three-dimensional space**, unless the third vector lies in the plane of the first two. The zero vector is always on these lines or planes because coefficients can be zero.
*   **Example Application**: The linear combinations of **v = (1,1,0)** and **w = (0,1,1)** fill a plane in **R3**, where the second component (c+d) is always the sum of the first (c) and third (d) components.

### 1.2 Lengths and Dot Products
*   **Dot Product Definition**: The **dot product (or inner product) of v and w** is a single number obtained by multiplying corresponding components and then summing these products. For **v = (v1, v2)** and **w = (w1, w2)**, **v ⋅ w = v1w1 + v2w2**. The order of vectors does not matter: **w ⋅ v = v ⋅ w**.
*   **Perpendicular Vectors**: A **zero dot product (v ⋅ w = 0)** signifies that the two vectors are **perpendicular** (or orthogonal), meaning the angle between them is 90°. This is related to the Pythagoras Law, where for perpendicular vectors, **||v||² + ||w||² = ||v - w||²**.
*   **Length of a Vector**: The **dot product of a vector with itself (v ⋅ v)** gives the **length of v squared (||v||²)**. The **length ||v|| is the square root of v ⋅ v**. In 2D, this relates to Pythagoras' theorem: **v1² + v2² = ||v||²**. In n dimensions, **||v|| = √(v1² + v2² + ... + vn²)**.
*   **Unit Vectors**: A **unit vector (u)** is a vector with **length 1**. To obtain a unit vector **u** in the direction of any non-zero vector **v**, divide **v** by its length: **u = v / ||v||**.
*   **Angle Between Vectors**: The dot product can also determine the angle **θ** between any two non-zero vectors **v** and **w**. The formula is **cos θ = (v ⋅ w) / (||v|| ||w||)**.
    *   If **v ⋅ w** is positive, the angle is less than 90°.
    *   If **v ⋅ w** is negative, the angle is greater than 90°.
    *   For **unit vectors u** and **U**, their **dot product u ⋅ U is cos θ**.
*   **Schwarz Inequality**: This inequality states that **|v ⋅ w| ≤ ||v|| ||w||** (or **|u ⋅ U| ≤ 1** for unit vectors).
*   **Triangle Inequality**: This states that **||v + w|| ≤ ||v|| + ||w||**.

### 1.3 Matrices
*   **Matrices and Linear Combinations**: A matrix **A** can be used to represent linear combinations of its columns. When a matrix **A** multiplies a vector **x = [c; d; e]**, the product **Ax** is defined as the linear combination of the columns of **A** using the components of **x** as coefficients.
    *   **Ax = [u v w] [c; d; e] = cu + dv + ew**.
*   **Matrix-Vector Multiplication**:
    *   **Column Picture**: **Ax** is understood as a **linear combination of the columns of A**. The equation **Ax = b** asks for a combination of the columns of **A** that produces **b**.
    *   **Row Picture (Dot Products)**: **Ax** can also be computed by taking the **dot product of each row of A with the vector x**.
*   **Invertible vs. Singular Matrices**:
    *   A matrix **A** is **invertible** if, for every **b**, there is exactly one solution to **Ax = b**. This occurs when its columns are **independent**, meaning **Ax = 0** has only the **zero solution (x = 0)**.
    *   A matrix **A** is **singular** if its columns are **dependent**, meaning **Ax = 0** has **many solutions (non-zero x)**. In this case, **A** has no inverse.
*   **Inverse Matrix**: If **A** is invertible, the solution to **Ax = b** can be found by multiplying **b** by the **inverse matrix A-1**, so **x = A-1b**.
*   **Example: Difference Matrix**: A difference matrix can find differences between components of a vector. Its inverse is a sum matrix.
*   **Key Idea**: The choice of understanding **Ax** as a combination of columns is highlighted as key to linear algebra, especially for higher dimensions where row picture visualisation becomes difficult.