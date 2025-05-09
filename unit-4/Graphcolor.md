# 🎨 Graph Coloring Approaches — Time and Space Complexity

**Graph Coloring** assigns colors to graph vertices such that no two adjacent vertices share the same color.

---

## 📘 1. Brute Force Approach

**Description**: Try all possible combinations of color assignments.

* **Time Complexity**: `O(kⁿ)`
* **Space Complexity**: `O(n)` (for color array)

> ⚠️ **Use Case**: Only theoretical; infeasible for large graphs.

---

## 📘 2. Backtracking Approach

**Description**: Recursive coloring with constraint checks. Backtrack if a conflict occurs.

* **Time Complexity**: `O(kⁿ)` worst-case
* **Space Complexity**: `O(n)` (recursion + color array)

> ✅ **Use Case**: Practical for **small/medium** graphs; exact solutions with early pruning.

---

## 📘 3. Greedy Coloring

**Description**: Assign the **smallest available color** to each vertex sequentially.

* **Time Complexity**: `O(V + E)`
* **Space Complexity**: `O(V)`

> ⚡ **Use Case**: Fast; widely used but **not always optimal**.

---

## 📘 4. DSATUR (Degree of Saturation)

**Description**: Choose the uncolored vertex with the **highest number of differently colored neighbors**.

* **Time Complexity**:

  * `O(V²)` (naive)
  * `O(V log V + E)` with heaps/sets
* **Space Complexity**: `O(V + E)`

> 🤖 **Use Case**: Better results than greedy in **real-world scenarios**.

---

## 📘 5. Dynamic Programming on Trees (Tree DP)

**Description**: Specialized for tree or forest structures. Use DP to compute colorings from leaves to root.

* **Time Complexity**: `O(n·k²)`
* **Space Complexity**: `O(n·k)`

> 🌲 **Use Case**: Most **efficient for trees** or acyclic graphs.

---

## 📊 Summary Table

| Approach         | Time Complexity  | Space Complexity | Notes                        |
| ---------------- | ---------------- | ---------------- | ---------------------------- |
| **Brute Force**  | `O(kⁿ)`          | `O(n)`           | Impractical for large graphs |
| **Backtracking** | `O(kⁿ)` (pruned) | `O(n)`           | Exact solution with pruning  |
| **Greedy**       | `O(V + E)`       | `O(V)`           | Fast but may use more colors |
| **DSATUR**       | `O(V²)` / better | `O(V + E)`       | Efficient heuristic          |
| **Tree DP**      | `O(n·k²)`        | `O(n·k)`         | Ideal for trees/forests      |

---

Would you like a flowchart or visual example showing how each approach colors a sample graph?
