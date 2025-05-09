# 🔁 Dynamic Programming vs Divide-and-Conquer

## 🧩 What They Have in Common

| **Aspect**               | **Dynamic Programming (DP)**                                    | **Divide-and-Conquer (D\&C)**                    |
| ------------------------ | --------------------------------------------------------------- | ------------------------------------------------ |
| **Problem Division**     | Breaks problem into smaller subproblems                         | Breaks problem into smaller subproblems          |
| **Recursive Approach**   | Solves subproblems recursively                                  | Solves subproblems recursively                   |
| **Optimal Substructure** | Uses solutions of subproblems to build optimal overall solution | Same — solves and combines subproblems optimally |
| **Subproblem Overlap**   | ✅ Yes — stores and reuses overlapping subproblem results        | ❌ No — subproblems are usually independent       |

### 🔑 Key Difference:

* **DP** solves **overlapping** subproblems and **reuses** results.
* **D\&C** solves **independent** subproblems and **does not reuse** results.

---

# 📐 Principle of Optimality

> The **Principle of Optimality** states:
> **“An optimal solution to a problem contains optimal solutions to its subproblems.”**
> This is the foundation of **dynamic programming**.

---

# 🧠 Characteristics of Dynamic Programming

| **Characteristic**          | **Description**                                                             |
| --------------------------- | --------------------------------------------------------------------------- |
| **Optimal Substructure**    | Solution to the main problem is built from optimal solutions to subproblems |
| **Overlapping Subproblems** | Same subproblems occur multiple times and are reused                        |
| **Memoization**             | Top-down approach: store computed subproblem results to avoid recomputation |
| **Tabulation**              | Bottom-up approach: solve small subproblems first and build up the solution |
| **Optimal Solution**        | Guarantees the best solution by exploring all possibilities                 |
| **State Space**             | Problem can be represented using states, each corresponding to a subproblem |

---

# 🛠️ Steps to Design a Dynamic Programming Solution

1. **Characterize the Structure**

   * Break the problem into smaller subproblems.
   * Find how their solutions can form the final result.

2. **Define the State**

   * Choose a state that captures essential information needed for subproblems.

3. **Formulate the Recurrence**

   * Write a recursive formula that relates the current state to smaller subproblems.

4. **Determine Base Cases**

   * Define trivial or smallest inputs with known answers.

5. **Choose Memoization or Tabulation**

   * **Memoization**: Recursively compute with caching (Top-down).
   * **Tabulation**: Iteratively fill a table (Bottom-up).

6. **Compute the Solution**

   * Use the recurrence and state transitions to compute the final result.

---

# 📚 Applications of Dynamic Programming

| **Problem**                          | **Description**                                              |
| ------------------------------------ | ------------------------------------------------------------ |
| **Fibonacci Sequence**               | Efficient calculation using memoization or tabulation        |
| **Knapsack Problem**                 | Maximize value under weight constraint                       |
| **Shortest Path (Bellman-Ford)**     | Find shortest paths in graphs with possible negative weights |
| **Longest Common Subsequence (LCS)** | Find the longest subsequence present in two sequences        |
| **Matrix Chain Multiplication**      | Minimize the number of operations to multiply matrices       |
| **Coin Change Problem**              | Find the minimum coins needed to make a given value          |
| **Edit Distance / String Matching**  | Measure how different two strings are                        |
| **Subset Sum Problem**               | Determine if a subset exists that adds up to a target sum    |
