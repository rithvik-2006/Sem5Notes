Here are detailed revision notes for Chapter 1, "Graph Theory," drawing on the provided sources:

### **Chapter 1: Graph Theory**

This chapter serves as an introduction to the fundamental concepts and applications of graph theory. It begins with the historical Königsberg Bridge Problem, which is considered the origin of the field.

#### **1.1 Introductory Concepts**

This section defines what a graph is and introduces basic terminology and related structures.

*   **Graphs and Their Relatives**:
    *   A **graph G** consists of two finite sets: a set of **vertices V** and a set of **edges E**, where each edge is an unordered pair of vertices.
    *   **Visual Representation**: Vertices are small circles, and edges are lines connecting them.
    *   **Variations**:
        *   **Directed graph (digraph)**: Edges are ordered pairs, having a specific orientation.
        *   **Multigraph**: Allows repeated edges (multiset of edges).
        *   **Pseudograph**: Allows edges to connect a vertex to itself (loops).
        *   **Hypergraph**: Edges can be arbitrary subsets of vertices.
        *   **Infinite graphs**: V or E can be infinite sets (studied in Chapter 3).
    *   **Focus**: This chapter primarily focuses on **finite, simple graphs**, meaning those without loops or multiple edges.

*   **The Basics**:
    *   **Notation**:
        *   **Vertex set**: *V(G)* or *V*.
        *   **Edge set**: *E(G)* or *E*.
        *   An edge between *u* and *v* is denoted *uv*.
    *   **Order**: The cardinality of *V(G)*.
    *   **Size**: The cardinality of *E(G)*.
    *   **Degree of a vertex (deg(v))**: The number of edges incident with *v*.
    *   **First Theorem of Graph Theory (Theorem 1.1)**:
        *   **The sum of the degrees of the vertices in a graph G is equal to twice the number of edges** (*Σ deg(v) = 2|E|*).
        *   **Consequently, the number of vertices with odd degree is always even**.

*   **Perambulation and Connectivity**:
    *   **Walk**: A sequence of alternating vertices and edges, starting and ending with a vertex.
    *   **Trail**: A walk that does not repeat any edges.
    *   **Path**: A trail that does not repeat any vertices (all vertices are distinct).
    *   **Circuit**: A closed trail (starts and ends at the same vertex).
    *   **Cycle**: A closed path (all vertices are distinct except the start/end vertex).
    *   **Length**: Number of edges in the sequence. The minimum length of a circuit or cycle is 3.
    *   **Theorem 1.2**: **Every u–v walk contains a u–v path**.
    *   **Graph Operations**:
        *   **Vertex deletion (G − v or G − S)**: Removes vertex *v* (or set *S*) and all incident edges.
        *   **Edge deletion (G − e or G − T)**: Removes only the edge *e* (or set *T*).
    *   **Connectivity**:
        *   A graph is **connected** if every pair of vertices can be joined by a path.
        *   **Disconnected** (or not connected) graphs have multiple separate parts.
        *   **Connected component**: Each maximal connected piece of a graph.
    *   **Special Vertices and Edges**:
        *   **Cut vertex**: A vertex *v* whose deletion increases the number of components in *G*.
        *   **Bridge**: An edge *e* whose deletion increases the number of components in *G*.
    *   **Cut Set and Connectivity Number**:
        *   **Vertex cut set (cut set)**: A proper subset *S* of vertices such that *G − S* is disconnected.
        *   **Connectivity of G (κ(G))**: The minimum size of a cut set in a non-complete graph. *κ(G) = 0* if disconnected; *κ(G) = n − 1* if *G* is complete of order *n*.
        *   **k-connected**: A graph is *k*-connected if *k ≤ κ(G)*.
    *   **Facts about Connectivity**:
        *   A graph is connected if and only if *κ(G) ≥ 1*.
        *   *κ(G) ≥ 2* if and only if *G* is connected and has no cut vertices.
        *   **Every 2-connected graph contains at least one cycle**.
        *   **For every graph G, κ(G) ≤ δ(G)** (minimum degree).

*   **Special Types of Graphs**:
    *   **Complete Graphs (Kn)**: Every vertex is adjacent to every other vertex. A *Knn* has *n(n-1)/2* edges.
    *   **Empty Graphs (En)**: A graph of order *n* with no edges.
    *   **Complements (Ḡ)**: Same vertex set as *G*, but edges are those *not* present in *G*.
    *   **Regular Graphs**: Every vertex has the same degree (*r*-regular). *Kn* is (*n*-1)-regular, *En* is 0-regular.
    *   **Cycles (Cn)**: A cycle on *n* vertices.
    *   **Paths (Pn)**: A path on *n* vertices.
    *   **Subgraphs (H ⊆ G)**: *H* is a subgraph of *G* if *V(H) ⊆ V(G)* and *E(H) ⊆ E(G)*.
    *   **Induced Subgraphs (⟨S⟩)**: Subgraph with vertex set *S* and all edges of *G* whose both end vertices are in *S*.
    *   **Bipartite Graphs**: Vertex set can be partitioned into two sets (*X* and *Y*) such that every edge has one end in *X* and the other in *Y*. *X* and *Y* are **partite sets**.
        *   **Theorem 1.3**: **A graph with at least two vertices is bipartite if and only if it contains no odd cycles**.
    *   **Complete Bipartite Graphs (K|X|,|Y| or Km,n)**: A bipartite graph where every vertex in *X* is connected to every vertex in *Y*. If *Kr,s* is regular, then *r=s*.
    *   **Isomorphism**: Two graphs *G* and *H* are **isomorphic** if there is a one-to-one and onto function (a bijection) between their vertex sets that preserves adjacency.
        *   **Necessary conditions**: Isomorphic graphs must have the same order, size, and identical degree sequences (these are not sufficient conditions on their own).
        *   **Property**: If *G* and *H* are isomorphic, then their complements *Ḡ* and *H̄* are also isomorphic.

#### **1.2 Distance in Graphs**

This section explores the concept of distance between vertices in graphs.

*   **Distance Function (Metric)**: A function *M(x, y)* satisfying:
    *   *M(x, y) ≥ 0*, and *M(x, y) = 0* if and only if *x = y*.
    *   *M(x, y) = M(y, x)*.
    *   *M(x, y) ≤ M(x, z) + M(z, y)* (triangle inequality).
*   **Key Concepts**:
    *   **Eccentricity (ecc(v))**: The maximum distance from vertex *v* to any other vertex in the graph.
    *   **Radius (rad(G))**: The smallest eccentricity among all vertices in *G*.
    *   **Diameter (diam(G))**: The greatest eccentricity among all vertices in *G*.
    *   **Center (C(G))**: The set of vertices whose eccentricity equals the radius.
    *   **Periphery (P(G))**: The set of vertices whose eccentricity equals the diameter.
    *   **Disconnected Graphs**: Distance between vertices in different components is considered infinity.
*   **Theorems on Center and Periphery**:
    *   **Theorem 1.5 (Hedetneimi)**: **Every graph is (isomorphic to) the center of some graph**.
    *   **Theorem 1.6 (Bielak and Sysło)**: **A graph G is (isomorphic to) the periphery of some graph if and only if either every vertex has eccentricity 1, or no vertex has eccentricity 1**.
*   **Graphs and Matrices**:
    *   **Adjacency Matrix (A)**: A square matrix where *A_ij = 1* if *v_i* and *v_j* are adjacent, and *0* otherwise.
    *   **Theorem 1.7**: **For any positive integer *k*, the (i, j) entry of *A^k* is equal to the number of walks from *v_i* to *v_j* that use exactly *k* edges**.
    *   **Distance Matrix (M)**: A matrix where the (i, j) entry is the distance from *v_i* to *v_j*.
*   **Social Networks**:
    *   **Mathematical Collaboration Graph (C)**: Vertices are researchers, edges connect coauthors. **Erdős number** is the distance from a researcher's vertex to Erdős's vertex.
    *   **Characteristic Path Length (LG)**: The average distance between all pairs of distinct vertices in a graph.

#### **1.3 Trees**

This section introduces trees, which are fundamental structures in graph theory, and their properties.

*   **Definitions and Examples**:
    *   A **tree** is a **connected graph that contains no cycles**.
    *   A **forest** is a collection of one or more trees.
    *   A **leaf** is a vertex of degree 1 in a tree.
    *   **Small trees**: *K1* (stump), *K2* (twig) are examples of trees. *P3* is the only tree of order 3.
    *   **Applications**: Modeling experiment outcomes, binary decision trees in programming, representing saturated hydrocarbons in chemistry.
*   **Properties of Trees**:
    *   **Theorem 1.10**: **If T is a tree of order n, then T has n− 1 edges**.
    *   **Theorem 1.11**: **If F is a forest of order n containing k connected components, then F contains n− k edges**.
    *   **Theorem 1.12**: **A graph of order n is a tree if and only if it is connected and contains n− 1 edges**.
    *   **Theorem 1.13**: **A graph of order n is a tree if and only if it is acyclic and contains n− 1 edges**.
    *   **Theorem 1.14**: **Every tree of order n ≥ 2 has at least two leaves**.
    *   **Theorem 1.15 (Jordan)**: **In any tree, the center is either a single vertex or a pair of adjacent vertices**.
    *   **Theorem 1.16**: If *G* is a graph whose minimum degree *δ(G) ≥ k*, then *G* contains every tree with *k* edges as a subgraph (or every tree of order at most *δ(G) + 1*).
*   **Spanning Trees**:
    *   A **spanning tree** *T* of a graph *G* is a tree that contains every vertex of *G*.
    *   **Weighted Graph**: A graph with a function *W* that maps edges to nonnegative real numbers (weights).
    *   Every connected graph has at least one spanning tree.
    *   **Minimum Weight Spanning Tree**: A spanning tree with the least total weight.
    *   **Algorithms for MST**:
        *   **Kruskal's algorithm**.
        *   **Prim's algorithm**.
    *   **Property**: An edge *e* is a **bridge** of *G* if and only if it is in every spanning tree of *G*.
*   **Counting Trees**:
    *   **Cayley’s Tree Formula (Theorem 1.18)**: **There are *n^(n−2)* distinct labeled trees of order *n***.
        *   **Prüfer’s Method**: Provides a one-to-one correspondence between labeled trees and sequences of length *n*-2 from the set {1, ..., *n*}. Each vertex *v* appears *deg(v)-1* times in the Prüfer sequence.
    *   **Matrix Tree Theorem (Kirchhoff, 1847)**: Counts spanning trees of labeled graphs.
        *   Uses the **adjacency matrix (A)** and the **degree matrix (D)** (diagonal matrix with vertex degrees).
        *   The **(i, j) cofactor of (D − A)** equals the number of spanning trees of *G*.

#### **1.4 Trails, Circuits, Paths, and Cycles**

This section revisits paths and cycles, focusing on specific types like Eulerian and Hamiltonian.

*   **The Bridges of Königsberg**:
    *   **Historical Problem**: In 18th-century Königsberg, residents tried to find a route crossing each of seven bridges exactly once.
    *   **Euler's Solution (1736)**: Modeled the land masses as points and bridges as connections. Argued based on the number of bridges connected to each land mass (degree of corresponding vertex). This problem is considered the beginning of graph theory.
*   **Eulerian Trails and Circuits**:
    *   **Eulerian trail**: A trail that includes every edge of *G*.
    *   **Eulerian circuit**: A circuit that includes every edge of *G*.
    *   **Eulerian graph**: A graph that contains an Eulerian circuit.
    *   **Theorem 1.20 (Euler, Hierholzer, Veblen)**: A **connected graph G is Eulerian if and only if every vertex has an even degree**. This is equivalent to saying that *E(G)* can be partitioned into a collection of disjoint cycles.
    *   **Corollary 1.21**: A **connected graph G contains an Eulerian trail if and only if there are at most two vertices of odd degree**.
    *   **Hierholzer’s Algorithm**: A method to find Eulerian circuits in Eulerian graphs.
*   **Hamiltonian Paths and Cycles**:
    *   **Hamiltonian path**: A path that spans all vertices of *G* (visits every vertex exactly once). A graph with a Hamiltonian path is **traceable**.
    *   **Hamiltonian cycle**: A cycle that spans all vertices of *G*. A graph with a Hamiltonian cycle is a **Hamiltonian graph**.
    *   **Difference from Eulerian**: Hamiltonicity does not depend on degree parity.
    *   **Theorem 1.22 (Dirac, 1952)**: If *G* is a graph of order *n ≥ 3* and its **minimum degree δ(G) ≥ n/2**, then *G* is Hamiltonian. (This bound is "best possible" and is not a characterization).
    *   **Theorem 1.23 (Ore, 1960)**: If *G* is a graph of order *n ≥ 3* and **deg(x) + deg(y) ≥ n for all pairs of nonadjacent vertices x, y**, then *G* is Hamiltonian.
    *   **Independent set of vertices**: A set of vertices that are pairwise nonadjacent.
    *   **Independence number (α(G))**: The largest size of an independent set of vertices.
    *   **Theorem 1.24 (Chvátal and Erdős, 1972)**: If **κ(G) ≥ α(G)** (connectivity is greater than or equal to independence number), then *G* is Hamiltonian.
    *   **Forbidden Subgraphs**:
        *   **H-free**: A graph *G* that does not contain *H* as an induced subgraph.
        *   **S-free**: *G* does not contain any graph in set *S* as an induced subgraph.
        *   **Theorem 1.25 (Goodman and Hedetniemi, 1974)**: If *G* is a **2-connected, {K1,3, Z1}-free graph**, then *G* is Hamiltonian.
        *   **Theorem 1.26 (Duffus, Gould, Jacobson)**: If *G* is a **{K1,3, N}-free graph**, then *G* is traceable (if connected) and Hamiltonian (if 2-connected).
        *   **K1,3 (the "claw")** is a prominent forbidden subgraph in Hamiltonicity results.
*   **Three Open Problems**:
    *   **Intersecting Detour Paths**:
        *   **Detour order (τ(G))**: The number of vertices in a longest path in *G*. A longest path is a **detour path**.
        *   **Question B**: If *G* is connected and *P1, ..., Pn* are distinct detour paths, must their intersection *∩V(Pi)* be nonempty? (Answer is "no" for *n=12* and *n=7*).
        *   **Conjecture 1**: If *G* is connected, then the intersection of any three distinct detour paths in *G* is nonempty (unknown for *n=3,4,5,6*).
    *   **Matthews and Sumner’s Conjecture**: Concerns Hamiltonicity of *k*-connected claw-free graphs. **Theorem 1.28**: If *G* is **7-connected and claw-free**, then *G* is Hamiltonian. (Open for *k=4, 5, 6*).
    *   **Path Partition Conjecture**:
        *   A graph *G* is **τ-partitionable** if it has an *(a, b)*-partition for every pair of positive integers *(a, b)* such that *a + b = τ(G)*.
        *   **Conjecture**: Every connected graph is τ-partitionable.
        *   **Theorem 1.30**: If *G* is **claw-free**, then *G* is τ-partitionable.

#### **1.5 Planarity**

This section defines planar graphs and explores properties related to their drawings in a plane.

*   **Definitions and Examples**:
    *   **Planar graph**: Can be drawn in the plane such that edges intersect only at vertices.
    *   **Nonplanar graph**: Has no such representation.
    *   **Planar representation (planar embedding)**: A drawing of a planar graph with no edge crossings.
    *   **Examples**: *K1, K2, K3, K4* are planar. *K5* and *K3,3* are nonplanar.
    *   **Region**: A maximal section of the plane in a planar representation where any two points can be joined by a curve not intersecting the graph. The unbounded region is the **exterior (outer) region**.
    *   **Bound degree (b(R))**: The number of edges that bound a region *R*.
    *   The number of regions in a planar representation is independent of the specific drawing.
*   **Euler’s Formula and Beyond**:
    *   **Theorem 1.31 (Euler’s Formula)**: For a **connected planar graph G with n vertices, q edges, and r regions, n − q + r = 2**.
    *   **Corollaries**:
        *   **Theorem 1.32**: A planar graph of order *n ≥ 3* has **at most 3n − 6 edges**. If it is maximal planar (adding any edge makes it nonplanar), it has exactly *3n-6* edges and every region is a triangle.
        *   **Theorem 1.33**: A **planar bipartite graph of order n ≥ 3 has no more than 2n − 4 edges**.
        *   **Theorem 1.35**: If *G* is a planar graph, then **G contains a vertex of degree at most five (δ(G) ≤ 5)**.
*   **Regular Polyhedra**:
    *   The skeletons of polyhedra (vertices and edges) can be viewed as planar graphs.
    *   **Theorem 1.36**: For a polyhedron with *V* vertices, *E* edges, and *F* faces, **V − E + F = 2** (directly from Euler's Formula).
    *   **Theorem 1.37**: For all polyhedra *P*, the minimum bound degree of any region *ρ(P)* satisfies **3 ≤ ρ(P) ≤ 5**.
    *   **Theorem 1.38**: **There are exactly five regular polyhedra** (Platonic solids: tetrahedron, cube, octahedron, dodecahedron, icosahedron), derived using Euler's formula and regularity conditions.
*   **Kuratowski’s Theorem**:
    *   *K3,3* and *K5* are known to be nonplanar. Any graph containing them as subgraphs is also nonplanar.
    *   **Subdivision**: A graph *H* is a subdivision of *G* if *H* can be obtained from *G* by replacing edges with paths.
    *   **Theorem 1.39**: A graph *G* is planar if and only if every subdivision of *G* is planar.
    *   **Theorem 1.40 (Kuratowski’s Theorem)**: **A graph G is planar if and only if it contains no subdivision of K3,3 or K5**.

#### **1.6 Colorings**

This section focuses on vertex colorings and the related concept of chromatic number.

*   **Definitions**:
    *   A **k-coloring** of a graph *G* assigns one of *k* colors to each vertex.
    *   A **proper k-coloring** ensures that no two adjacent vertices have the same color.
    *   **Color classes**: Sets of vertices that all receive the same color (must be independent sets).
    *   **Chromatic number (χ(G))**: The smallest integer *k* such that *G* is *k*-colorable.
    *   **Examples**: χ(Cn) is 2 if *n* is even, 3 if *n* is odd; χ(Pn) is 2 if *n ≥ 2*, 1 if *n=1*; χ(Kn) = *n*; χ(En) = 1; χ(Km,n) = 2.
    *   **k-critical graph**: χ(G) = *k* and χ(G − v) < *k* for every vertex *v*. A *k*-critical graph is connected and has *δ(G) ≥ k − 1*.
*   **Bounds on Chromatic Number**:
    *   **Greedy Algorithm**: A simple algorithm for coloring a graph, which produces a valid coloring using at most *Δ(G) + 1* colors.
    *   **Theorem 1.42**: For any graph *G*, **χ(G) ≤ Δ(G) + 1** (where *Δ(G)* is the maximum degree).
    *   **Theorem 1.43 (Brooks’s Theorem, 1941)**: If *G* is a **connected graph that is neither a complete graph nor an odd cycle, then χ(G) ≤ Δ(G)**.
    *   **Clique number (ω(G))**: The order of the largest complete graph that is a subgraph of *G*.
    *   **Theorem 1.44**: For any graph *G*, **χ(G) ≥ ω(G)**. (Note: *χ(G)* is not always equal to *ω(G)*).
    *   **Theorem 1.45**: For any graph *G* of order *n*, **n/α(G) ≤ χ(G) ≤ n + 1 − α(G)** (where *α(G)* is the independence number).
*   **The Four Color Problem**:
    *   **Conjecture**: Can every planar map be colored with at most four colors such that adjacent regions have different colors?.
    *   **Theorem 1.46 (Four Color Theorem, Appel and Haken, 1976)**: **Every planar graph is 4-colorable**. The proof involved extensive computer verification.
*   **Chromatic Polynomials**:
    *   **cG(k)**: A polynomial that represents the number of different ways to properly color the vertices of a labeled graph *G* using at most *k* colors.
    *   **Theorem 1.48 (Birkhoff–Lewis Reduction Theorem)**: For any graph *G* and any edge *e*, **cG(k) = cG−e(k) − cG/e(k)**, where *G/e* is *G* with edge *e* removed and its end vertices identified.
    *   **Theorem 1.49**: For a graph *G* of order *n*:
        1.  *cG(k)* is a polynomial in *k* of degree *n*.
        2.  The leading coefficient of *cG(k)* is 1.
        3.  The constant term of *cG(k)* is 0.
        4.  The coefficients of *cG(k)* alternate in sign.
        5.  The absolute value of the coefficient of the *k^(n−1)* term is the number of edges in *G*.

#### **1.7 Matchings**

This section explores matchings, sets of edges with no shared vertices, and related theorems.

*   **Definitions**:
    *   A **matching** in a graph is a set of independent edges (no two edges share a vertex).
    *   **M-saturated vertices**: Vertices belonging to the edges of a matching *M*.
    *   **M-unsaturated vertices**: Vertices not belonging to edges of *M*.
    *   **Perfect matching**: A matching that saturates every vertex of *G*. A graph must have an even order to have a perfect matching.
    *   **Maximum matching**: A matching with the largest possible cardinality.
    *   **Maximal matching**: A matching that cannot be enlarged by adding any edge.
*   **Hall’s Theorem and SDRs**:
    *   **Theorem 1.50 (Berge, 1957)**: A matching *M* in a graph *G* is maximum if and only if *G* contains no **M-augmenting paths** (paths starting and ending with *M*-unsaturated vertices, with alternating edges between *M* and *E(G)\M*).
    *   In a bipartite graph with partite sets *X* and *Y*, *X* can be matched into *Y* if there's a matching saturating *X*.
    *   **Theorem 1.51 (Hall’s Theorem / Hall’s Marriage Theorem, 1935)**: In a bipartite graph with partite sets *X* and *Y*, **X can be matched into Y if and only if |A| ≤ |N(A)| for every subset A of X** (where *N(A)* is the set of neighbours of *A*).
    *   **System of Distinct Representatives (SDR)**: A collection of distinct elements, one from each set in a family of sets.
    *   **Theorem 1.52**: A collection of finite, nonempty sets *S1, ..., Sk* has an SDR if and only if **for every *t ∈ {1, ..., k}*, the union of any *t* of these sets contains at least *t* elements**. (This is proven using a bipartite graph and Hall's Theorem).
*   **The König–Egerváry Theorem**:
    *   **Edge cover**: A set *C* of vertices in *G* such that every edge of *G* is incident with at least one vertex of *C*.
    *   **Theorem 1.53 (König–Egerváry Theorem, 1931)**: **In a bipartite graph, the maximum number of edges in a matching equals the minimum number of vertices in an edge cover**.
    *   **Related Theorems**:
        *   **Max Flow Min Cut Theorem (Theorem 1.55)**: In a flow network, the maximum value of total flow equals the minimum capacity of a cut.
        *   **Independent Zeros Theorem (Theorem 1.56)**: For a matrix *A*, the maximum number of independent zeros equals the minimum number of lines through rows or columns that cover all zeros.
*   **Perfect Matchings**:
    *   **Corollary 1.57**: **If G is a bipartite graph that is regular of degree k, then G contains a perfect matching**.
    *   **Theorem 1.58**: If *G* is a graph of order *2n* such that **δ(G) ≥ n**, then *G* has a perfect matching (proven using Dirac's Theorem for Hamiltonian cycles).
    *   **Theorem 1.59 (Tutte’s Theorem, 1947)**: A graph *G* has a perfect matching if and only if for every subset *S* of vertices, the number of odd components of *G − S* (denoted Ω(*G − S*)) is less than or equal to *|S|*.
    *   **Theorem 1.60 (Petersen’s Theorem, 1891)**: **Every bridgeless, 3-regular graph contains a perfect matching**.

#### **1.8 Ramsey Theory**

This section introduces Ramsey theory, which deals with finding monochromatic substructures in colored graphs.

*   **Classical Ramsey Numbers**:
    *   **2-coloring of edges**: Assigning one of two colors (e.g., red and blue) to each edge of a graph.
    *   **Ramsey number R(p, q)**: The **smallest integer n** such that every 2-coloring of the edges of *Kn* either contains a **red Kp** or a **blue Kq** as a subgraph.
    *   **Existence**: Ramsey numbers *R(p, q)* always exist (proven by Ramsey).
    *   **Known values**:
        *   *R(1, k) = 1* for any *k ≥ 1*.
        *   *R(2, 4) = 4*.
        *   **R(3, 3) = 6** (proven by showing *K5* can be 2-colored without monochromatic *K3*, and *K6* always contains one).
        *   *R(3, 4) = 9*.
    *   **Bounds**:
        *   **Theorem 1.64**: If *p ≥ 2* and *q ≥ 2*, then **R(p, q) ≤ R(p − 1, q) + R(p, q − 1)**. The inequality is strict if both terms on the right are even.
        *   **Theorem 1.65**: For every integer *q ≥ 3*, **R(3, q) ≤ (q^2 + 3)/2**.
*   **Graph Ramsey Theory**:
    *   **Graph Ramsey number R(G, H)**: The **smallest value of n** such that any 2-coloring of the edges of *Kn* contains either a **red copy of G** or a **blue copy of H**.
    *   **Theorem 1.67**: If *G* is a graph of order *p* and *H* is a graph of order *q*, then **R(G, H) ≤ R(p, q)**.
    *   **Theorem 1.68 (Chvátal and Harary)**: **R(G, H) ≥ (χ(G) − 1)(C(H) − 1) + 1**, where *χ(G)* is the chromatic number of *G* and *C(H)* is the order of the largest component of *H*.
    *   **Theorem 1.69 (Chvátal)**: If *Tm* is a tree with *m* vertices, then **R(Tm, Kn) = (m − 1)(n − 1) + 1**.

This comprehensive overview covers the essential information from Chapter 1.