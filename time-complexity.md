# Time Complexity Notes

## **Quick Facts (T/F Q's)**

#### Section #1
1. The time complexity of an algorithm can be represented by a deterministic Turing machine (TM).
2. Big-O notation represents the asymptotic upper bound of a function.
3. In Big-O notation, coefficients of lower order terms are not significant for large input sizes.
4. The time complexity of a Turing machine is defined as the maximum number of steps it uses on any input of length n.

#### Section #2
1. Exponential time algorithms are generally considered impractical for large input sizes.
2. Class P includes all languages decidable in polynomial time on a deterministic single-tape Turing machine.
3. Not all problems in P can be solved efficiently in real-world scenarios due to large polynomial degrees or high constants.
4. The Hamiltonian Path problem is not currently known to be in P.
5. Breadth-first search is a polynomial time algorithm for solving the PATH problem in graphs.

#### Section #3
1. Currently, no polynomial time algorithm is known for finding a Hamiltonian path in a general graph.
2. Class NP consists of problems for which a solution can be verified in polynomial time.
3. Not every problem in NP is known to be solvable in polynomial time.
4. Non-deterministic Turing Machines (NTMs) can decide NP problems by definition, but it's unknown if they can do so in polynomial time for all NP problems.
5. The CLIQUE problem is in NP because there exists a polynomial time verifier for it.

#### Section #4
1. NP-Complete problems are the most challenging problems in NP in the sense that if any of them can be solved in polynomial time, all problems in NP can be.
2. If any NP-Complete problem is solvable in polynomial time, then all problems in NP can be solved in polynomial time.
3. The 3SAT problem is polynomial time reducible to the CLIQUE problem.
4. The SAT (Satisfiability) problem is NP-Complete.
5. The Cook-Levin Theorem states that every problem in NP is polynomial time reducible to the SAT problem.

## **Notes**

### Time Complexity Part #1 (Introduction)

1. **Definition and Measurement:**
   - Time complexity measures the time an algorithm or Turing machine takes to solve a problem as a function of the input size.
   - Measured by the number of steps a Turing machine takes for an input of size `n`.

2. **Big-O Notation:**
   - A way to express the upper bound of an algorithm's running time, focusing on the worst-case scenario.
   - Important for understanding the scalability and efficiency of algorithms, especially for large inputs.
   - Edge Case: Algorithms with the same Big-O notation can have different actual running times.

3. **Deterministic vs. Nondeterministic Turing Machines:**
   - Deterministic Turing Machines (DTMs) follow a single computation path for each input.
   - Nondeterministic Turing Machines (NTMs) can have multiple computation paths.
   - Edge Case: NTMs can solve some problems more quickly than DTMs in theory, but this is not always practically achievable.

4. **Time Complexity Classes:**
   - The class `TIME(t(n))` includes all problems decidable by a Turing machine in `O(t(n))` time.
   - These classes help categorize problems based on their computational hardness.
   - Edge Case: Some problems may belong to multiple complexity classes, indicating different possible running times based on the algorithm used.

5. **Practical Examples:**
   - Turing machine `M1` that decides `{0^k1^k | k >= 0}` has a time complexity of `O(n^2)`.
   - The conversion of multitape Turing machines to single-tape models affects running time, often increasing the complexity.

6. **Multitape vs. Single-Tape Models:**
   - Multitape Turing machines can be more efficient than single-tape models.
   - The simulation of a multitape machine on a single-tape machine can lead to an increase in time complexity.

7. **Algorithm Efficiency:**
   - Comparing algorithms using time complexity helps in selecting the most efficient method for problem-solving.
   - Edge Case: Algorithms with lower complexity are not always faster for small input sizes or specific cases.

### Time Complexity 02 - Class P

1. **Polynomial vs Exponential Time:**
   - Polynomial time (e.g., `n^2`) is considered efficient and realistically solvable on computers.
   - Exponential time (e.g., `2^n`) is considered inefficient for large `n`.
   - Example: For `n = 1000`, an `n^2` algorithm takes `0.001` second, while a `2^n` algorithm takes approximately `10^284` years.

2. **Class P:**
   - Definition: Class P consists of problems decidable in polynomial time on a deterministic single-tape Turing machine.
   - Formally, `P = TIME(n^k)` for some `k`, where `TIME(n^k)` is a set of languages decidable in `O(n^k)` time.

3. **Running Time in Turing Machines:**
   - A Turing machine runs in polynomial time if each step is executed and each step takes polynomial time (i.e., `nk` for some `k`).
   - Steps in a Turing machine refer to discrete operations or configurations.

4. **Example of a Polynomial Time Problem:**
   - `PATH = { G s t | G is a directed graph with a path from s to t}`: Decidable in polynomial time.
   - Brute-Force vs Efficient Algorithms: Brute-force may take exponential time, while algorithms like breadth-first search achieve polynomial time.

5. **Breadth-First Search for PATH:**
   - An efficient way to achieve polynomial time for PATH, by marking nodes and scanning edges.
   - The algorithm runs in polynomial time, considering the number of nodes and edges in the graph.

6. **Relative Primes (RELPRIME):**
   - Two numbers are relatively prime if 1 is the largest integer that evenly divides them both
   - Brute-force algorithms may take exponential time, but Euclidean Algorithm offers a polynomial-time solution.
   - We can also use Greatest Common Divisor to find if they are relatively prime

7. **Hamiltonian Path Problem (HAMPATH):**
   - Defined as finding a path in a graph that visits each node exactly once.
   - Current brute-force solutions require exponential time, and no polynomial-time solution is known yet.

8. **PATH vs HAMPATH:**
   - PATH can be decided in polynomial time, but HAMPATH cannot be (as of now).
   - Highlights the difference in complexity between seemingly similar problems.

9.  **COMPOSITES:**
   - Problem of determining if a number is a product of two non-trivial factors.
   - Currently requires exponential time and forms the basis of RSA encryption.

### Time Complexity 03 - Verifier, Class NP, NTM, and CLIQUE

1. **Hamiltonian Path (HAMPATH):**
   - A Hamiltonian path in a directed graph is a path that visits each node exactly once.
   - Formal Definition: `HAMPATH = { G s t | G is a directed graph with a Hamiltonian path from s to t}`.
   - Important for understanding complex graph problems.

2. **Verifier Concept:**
   - A verifier can check if a given solution (certificate) to a problem is correct in polynomial time.
   - Example: Verifying a Hamiltonian path in a graph or a factor of a number can be done in polynomial time.
   - Verifying is easier than finding; some problems need exponential time to solve but can be verified quickly.

3. **COMPOSITES Problem:**
   - Defined as `COMPOSITES = { x | x is divisible by c for some natural number c > 1}`.
   - A Turing Machine (TM) can verify if a number is composite in polynomial time.
   - Illustrates the concept of polynomial verifiability.

4. **Class NP:**
   - Definition: NP is the class of languages that have polynomial-time verifiers.
   - NP comes from Nondeterministic Polynomial time.
   - Theorem: A language is in NP if it is decided by some nondeterministic polynomial-time Turing machine.
   - NP includes problems that are verifiable in polynomial time, not necessarily solvable in polynomial time.

5. **Nondeterministic Turing Machines (NTMs):**
   - NTMs can make multiple computation choices simultaneously.
   - They are suitable for describing brute-force algorithms.
   - Example: An NTM can generate all possible strings over a given alphabet of a certain length in polynomial time.

6. **NTM for HAMPATH:**
   - An NTM can decide HAMPATH by generating all permutations of nodes and checking for a valid Hamiltonian path.
   - Runs in polynomial time but would take exponential time on a single-tape deterministic Turing machine.

7. **Polynomial Time Verifier to NTM Conversion:**
   - If a language has a polynomial-time verifier, it can be converted to an equivalent NTM.
   - The NTM nondeterministically selects a certificate and runs the verifier on it.

8. **Languages in NP:**
   - NTIME(t(n)) is the set of languages decided by an O(t(n)) time nondeterministic Turing machine.
   - NP is equivalent to NTIME(n^k) for some k.

9. **Examples of NP Problems:**
   - **CLIQUE Problem**: Deciding if an undirected graph contains a clique of a certain size.
   - **SUBSET-SUM Problem**: Deciding if there is a subset of numbers that sums to a target number.
   - Both problems are in NP and can be verified or decided in polynomial time by NTMs.

### Time Complexity 04 -  NP Complete, Polynomial Time Reducibility, SAT, and 3SAT

1. **NP-Completeness:**
   - A class of problems where if one can be solved in polynomial time, then all can be solved in polynomial time.
   - Important for understanding the computational complexity of different problems.

2. **Polynomial Time Reducibility (≤p):**
   - A language A is polynomial time reducible to B (A ≤p B) if there exists a polynomial time computable function f where w ∈ A ↔ f(w) ∈ B.
   - This concept is crucial for proving NP-completeness.

3. **Theorem 7.31:**
   - If A ≤p B and B is in P (polynomial time), then A is also in P.
   - This theorem is fundamental in the study of problem reductions and algorithmic efficiency.

4. **SAT (Satisfiability Problem):**
   - SAT = {φ | φ is a satisfiable Boolean formula}.
   - Central to the study of NP-completeness; involves determining if a Boolean formula can be satisfied.

5. **3SAT Problem:**
   - A specific case of SAT where each clause in the formula has exactly three literals.
   - Known to be NP-complete, making it a key problem in computational complexity.

6. **Reduction from 3SAT to CLIQUE:**
   - Demonstrates the concept of polynomial time reducibility.
   - If 3SAT is polynomial time reducible to CLIQUE, solving CLIQUE in polynomial time implies solving 3SAT in polynomial time.

7. **NP-Complete Problems:**
   - A language B is NP-Complete if it is in NP and every language A in NP is polynomial time reducible to B.
   - Examples: CLIQUE, VERTEX-COVER, HAMPATH, SUBSET-SUM.
   - These problems are central to understanding the limits of what can be efficiently computed.

8. **Proving NP-Completeness:**
   - To prove B is NP-Complete: Show B is in NP and every language A in NP is polynomial time reducible to B.
   - Involves creating a polynomial time verifier or showing a polynomial time reduction.

9. **Additional NP-Complete Problems:**
   - CLIQUE: Deciding if an undirected graph contains a k-clique.
   - VERTEX-COVER: Finding a k-node vertex cover in a graph.
   - HAMPATH: Finding a Hamiltonian path in a graph.
   - SUBSET-SUM: Determining if a subset of numbers sums to a target number.
