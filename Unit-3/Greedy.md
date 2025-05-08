# 🚦 **Dijkstra’s Algorithm**

### ✅ **What is it?**

Dijkstra’s Algorithm is a **graph-based greedy algorithm** used to find the **shortest path** from a starting node (source) to all other nodes in a **weighted graph with non-negative edge weights**.

---

### ❓ **Why is it used?**

It efficiently calculates the **minimum distance** from a source to every other vertex, which is essential in:

* **Navigation systems** (like Google Maps)
* **Network routing protocols** (like OSPF)
* **Pathfinding in games**

---

### ⏱️ **When is it used?**

Use Dijkstra’s Algorithm when:

* The graph is **weighted** (edges have costs).
* Edge weights are **non-negative**.
* You need **shortest paths** from one source to many nodes.

---

### 🌍 **Where is it used?**

* **Transportation networks** (shortest travel route)
* **Internet routing** (data packet paths)
* **Robotics** (finding optimal movement paths)

---

### ⚙️ **How does it work?**

1. **Initialize distances** from the source to all vertices as **infinity**, and distance to the source itself as **0**.
2. Use a **priority queue (min-heap)** to pick the vertex with the **minimum distance**.
3. For the selected vertex, **relax all adjacent edges**:

   * If the new calculated distance to a neighbor is less, update it.
4. **Repeat** until all nodes are visited or distances finalized.

---

### 💡 **Example:**

Graph:

```
      (2)
   A ----- B
   |       |
 (1)|     (3)
   |       |
   C ----- D
      (1)
```

Start from **A**.

| Step | Current Node | Distance from A | Notes                 |
| ---- | ------------ | --------------- | --------------------- |
| 1    | A            | A=0, B=2, C=1   | Initialized distances |
| 2    | C            | D=2             | From C to D (1)       |
| 3    | B            |                 | Already at distance 2 |
| 4    | D            | Done            | All nodes visited     |

✅ **Shortest paths** from A:

* A to A: 0
* A to B: 2
* A to C: 1
* A to D: 2

---

### ⏳ **Time Complexity:**

* Using Min Heap (Priority Queue): **O((V + E) log V)**

  * V = vertices, E = edges

---

### 🖼️ **Diagram:**

```plaintext
A --2-- B
|      |
1      3
|      |
C --1-- D
```

---

### ✅ **Summary:**

| Aspect          | Dijkstra’s Algorithm            |
| --------------- | ------------------------------- |
| Type            | Greedy algorithm                |
| Purpose         | Find shortest paths from source |
| Edge Weights    | Must be non-negative            |
| Data Structure  | Priority Queue (Min-Heap)       |
| Time Complexity | O((V + E) log V)                |
| Real-World Use  | Maps, routing, AI pathfinding   |
