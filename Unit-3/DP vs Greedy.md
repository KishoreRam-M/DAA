# 📊 **Dynamic Programming (DP) vs Greedy Algorithm** 🧠⚡

## ✅ **Comparison Table: Dynamic Programming vs Greedy Techniques**

| 🔍 **Aspect**          | 🧠 **Dynamic Programming (DP)**                                                                                    | ⚡ **Greedy Algorithm**                                                                                          |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------- |
| **What is it?**        | A method to solve problems by **breaking them down** into **overlapping subproblems** and storing solutions.       | A method to build up a solution by choosing the **locally optimal** choice at each step.                        |
| **Strategy**           | Solve all subproblems and combine results (**Bottom-Up** or **Top-Down with Memoization**).                        | Make the best decision at each step, hoping to reach the global optimum.                                        |
| **Used when**          | Subproblems **overlap** and **optimal substructure** exists.                                                       | A greedy choice at each step leads to the **globally optimal solution**.                                        |
| **Solution Build-Up**  | **Explore all paths**, store and reuse previous results (optimal for all subproblems).                             | **One-pass selection**; never reconsider past choices.                                                          |
| **Time Complexity**    | Often higher (but optimized with memoization), e.g., O(n²), O(n\*k)                                                | Usually lower, e.g., O(n log n), O(n)                                                                           |
| **Space Complexity**   | More space (to store subproblem solutions)                                                                         | Less space (only variables for current state)                                                                   |
| **Nature of Problems** | Optimization with overlapping subproblems (Fibonacci, Knapsack)                                                    | Optimization without overlapping subproblems (Activity Selection, Coin Change with greedy)                      |
| **Result**             | **Always optimal** (if problem fits DP structure)                                                                  | **May or may not be optimal**                                                                                   |
| **Programming Style**  | Recursive + Memoization or Iterative with Table (Tabulation)                                                       | Iterative + Greedy decision making                                                                              |
| **Examples**           | 🔹 **0/1 Knapsack**<br>🔹 **Fibonacci**<br>🔹 **Matrix Chain Multiplication**<br>🔹 **Longest Common Subsequence** | 🔹 **Activity Selection**<br>🔹 **Fractional Knapsack**<br>🔹 **Huffman Coding**<br>🔹 **Dijkstra’s Algorithm** |

---

## 🧪 **Real-World Example: Knapsack Problem** 🎒

### **Problem:**

Given a set of items with weights and values, find the most valuable subset that fits in a bag of limited capacity.

### **Comparison of Approaches:**

| 💡 **Feature**          | **0/1 Knapsack (Dynamic Programming)**                        | **Fractional Knapsack (Greedy)**                              |
| ----------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| **Can Take Fractions?** | ❌ **No**, items are whole only                                | ✅ **Yes**, can take partial items                             |
| **Approach**            | Consider all combinations using DP table (Weight vs Value)    | Sort by value/weight ratio and pick items greedily            |
| **Time Complexity**     | O(nW), where `n` = items, `W` = capacity                      | O(n log n), because of sorting by ratio                       |
| **Optimal Result**      | ✔️ **Always gives the correct best value**                    | ❌ **May miss the best** if full items are needed              |
| **When to Use?**        | When **fractions are not allowed** (like carrying full items) | When **fractions are allowed** (like gold dust, petrol, etc.) |

---

## 🎯 **Summary of Key Differences** ✨

| **Criteria**              | **Dynamic Programming**                   | **Greedy Algorithm**                        |
| ------------------------- | ----------------------------------------- | ------------------------------------------- |
| **Always Optimal?**       | ✅ **Yes** (for DP-suitable problems)      | ❌ **Not always**                            |
| **Subproblem Overlap?**   | ✅ **Yes**                                 | ❌ **No**                                    |
| **Local Decisions Only?** | ❌ **No**                                  | ✅ **Yes**                                   |
| **Time Complexity**       | ❌ **Slower**                              | ✅ **Faster**                                |
| **Space Complexity**      | ❌ **More memory**                         | ✅ **Less memory**                           |
| **Example Problems**      | **Longest Subsequence**, **0/1 Knapsack** | **Huffman Coding**, **Fractional Knapsack** |

---

## 🧩 **Text Diagram Comparison (Knapsack Problem)**

### **0/1 Knapsack (Dynamic Programming)**

```plaintext
Given: Weights: [1, 2, 3, 8, 7], Values: [20, 5, 10, 40, 15], Capacity: 10

Step 1: Build a DP table (rows = items, columns = capacities).
      Example: DP[3][10] will tell max value for 3 items with capacity 10.

Step 2: For each item and capacity, consider:
  - Include or exclude each item.
  - Reuse already computed results (subproblems).
      Table:
        [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
        [0, 20, 20, 20, 20, 20, 20, 20, 20, 20, 20]
        [0, 20, 20, 20, 20, 25, 25, 25, 25, 25, 25]
        [0, 20, 20, 20, 20, 25, 25, 25, 25, 30, 30]
        [0, 20, 20, 20, 20, 25, 25, 25, 25, 30, 35]

Result: Maximum Value = 35
```

### **Fractional Knapsack (Greedy Algorithm)**

```plaintext
Given: Weights: [1, 2, 3, 8, 7], Values: [20, 5, 10, 40, 15], Capacity: 10

Step 1: Calculate value-to-weight ratios: [20, 2.5, 3.33, 5, 2.14]
Step 2: Sort items based on ratios in descending order: [40 (item 3), 20 (item 1), 10 (item 2), 15 (item 5), 5 (item 4)].
Step 3: Take items greedily based on the ratio until capacity is reached:
  - Take item 3 fully (weight 3, value 40).
  - Take item 1 fully (weight 1, value 20).
  - Take item 2 fully (weight 2, value 10).
  - Remaining capacity: 10 - 6 = 4.
Step 4: Fractionally take item 5, with weight 4, to fill the remaining capacity.

Result: Maximum Value = 40 + 20 + 10 + (4/7)*15 ≈ 75.14
```

---

## 🔥 **Time and Space Complexity**

| **Metric**                       | **Dynamic Programming** | **Greedy Algorithm** |
| -------------------------------- | ----------------------- | -------------------- |
| **Best Case Time Complexity**    | O(nW)                   | O(n log n)           |
| **Average Case Time Complexity** | O(nW)                   | O(n log n)           |
| **Worst Case Time Complexity**   | O(nW)                   | O(n log n)           |
| **Space Complexity**             | O(nW)                   | O(n)                 |
| **Auxiliary Space**              | O(nW)                   | O(1)                 |

---

## ✅ **Real-World Use Cases** 🌍

### **Dynamic Programming:**

* **Knapsack Problem** (0/1 and Fractional)
* **Longest Common Subsequence**
* **Matrix Chain Multiplication**
* **Fibonacci Sequence**

### **Greedy Algorithms:**

* **Huffman Coding** (for efficient data compression)
* **Activity Selection Problem** (selecting maximum number of activities without conflict)
* **Prim’s Algorithm** (for Minimum Spanning Tree)
* **Dijkstra's Algorithm** (for shortest path)
