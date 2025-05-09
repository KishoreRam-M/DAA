# 🎨 Graph Coloring using Backtracking

> 🧠 *"Assign colors to graph vertices such that no two adjacent vertices share the same color."*

---

## 📚 Table of Contents

- [📖 What is Graph Coloring?](#-what-is-graph-coloring)
- [🌍 Real-World Applications](#-real-world-applications)
- [📅 When to Use It?](#-when-to-use-it)
- [⚙️ Problem Statement](#-problem-statement)
- [💡 Backtracking Approach](#-backtracking-approach)
- [🔍 Step-by-Step Logic](#-step-by-step-logic)
- [🧑‍💻 Java Implementation](#-java-implementation)
- [📊 Time and Space Complexity](#-time-and-space-complexity)
- [✅ Advantages](#-advantages)
- [❌ Disadvantages](#-disadvantages)
- [🔄 Comparison with Other Approaches](#-comparison-with-other-approaches)
- [🧩 Visual Example](#-visual-example)
- [📚 Resources](#-resources)
- [📌 Final Thoughts](#-final-thoughts)

---

## 📖 What is Graph Coloring?

**Graph Coloring** is the process of assigning **colors to vertices** of a graph such that **no two adjacent vertices share the same color**.

> 🎯 The goal: Minimize the number of colors while satisfying the constraint.

---

## 🌍 Real-World Applications

- 🗓️ **Timetable Scheduling**: No two classes at the same time in the same room
- 📡 **Register Allocation in Compilers**
- 🛰️ **Frequency Assignment** in mobile towers
- 🎮 **Map Coloring**: Adjacent regions with different colors
- 🧮 **Sudoku solving**

---

## 📅 When to Use It?

Use Graph Coloring when:
- Adjacency conflicts must be avoided (e.g., in scheduling, resource allocation)
- Graph structure is known and moderate in size
- Optimal or feasible solutions are needed via backtracking

---

## ⚙️ Problem Statement

Given a graph `G(V, E)` and an integer `M`, determine if the graph can be colored using at most `M` colors such that **no two adjacent vertices** have the same color.

---

## 💡 Backtracking Approach

> Try assigning colors one vertex at a time and **backtrack** if any assignment violates the constraint.

**Steps:**
1. Start from vertex 0.
2. Try all colors from 1 to M.
3. Check if the color is safe (not used by adjacent vertex).
4. If safe, assign and move to next vertex.
5. If no color is valid, backtrack.

---

## 🔍 Step-by-Step Logic

```text
1. Create a colors[] array to store color of each vertex
2. Start from vertex 0
3. For each color from 1 to M:
    a. If color is not used by any adjacent vertex
        → Assign it
        → Recurse for next vertex
4. If all vertices are colored
    ✅ Return true
5. Else
    ❌ Backtrack and try next color
````

---

## 🧑‍💻 Java Implementation

```java
public class GraphColoring {
    final int V = 4;

    boolean isSafe(int v, int[][] graph, int[] color, int c) {
        for (int i = 0; i < V; i++)
            if (graph[v][i] == 1 && color[i] == c)
                return false;
        return true;
    }

    boolean graphColoringUtil(int[][] graph, int m, int[] color, int v) {
        if (v == V)
            return true;

        for (int c = 1; c <= m; c++) {
            if (isSafe(v, graph, color, c)) {
                color[v] = c;
                if (graphColoringUtil(graph, m, color, v + 1))
                    return true;
                color[v] = 0; // Backtrack
            }
        }
        return false;
    }

    boolean graphColoring(int[][] graph, int m) {
        int[] color = new int[V];
        if (!graphColoringUtil(graph, m, color, 0)) {
            System.out.println("Solution does not exist.");
            return false;
        }

        System.out.println("Solution Exists: Following are the assigned colors");
        for (int i = 0; i < V; i++)
            System.out.print(color[i] + " ");
        return true;
    }

    public static void main(String[] args) {
        GraphColoring g = new GraphColoring();
        int[][] graph = {
            {0, 1, 1, 1},
            {1, 0, 1, 0},
            {1, 1, 0, 1},
            {1, 0, 1, 0}
        };
        int m = 3; // Number of colors
        g.graphColoring(graph, m);
    }
}
```

---

## 📊 Time and Space Complexity

| Metric           | Value                  |
| ---------------- | ---------------------- |
| Time Complexity  | O(M^V) — Exponential   |
| Space Complexity | O(V) — For color array |

> ⚠️ Exponential time — only feasible for small graphs (V ≤ 20)

---

## ✅ Advantages

* ✔️ Simple and intuitive
* ✔️ Ensures valid coloring
* ✔️ Good for small graphs or testing feasibility

---

## ❌ Disadvantages

* ❌ Not efficient for large graphs
* ❌ No guarantee for minimal colors
* ❌ Exponential time

---

## 🔄 Comparison with Other Approaches

| Approach         | Use Case                     | Time Complexity | Optimality           |
| ---------------- | ---------------------------- | --------------- | -------------------- |
| Backtracking     | Small graphs, feasibility    | O(M^V)          | ✅ Valid, ❌ Optimal   |
| Greedy Coloring  | Large graphs, fast           | O(V + E)        | ❌ Not always optimal |
| DSatur Algorithm | Better heuristic than greedy | O(V^2)          | ✅ Better optimality  |

---

## 🧩 Visual Example

```text
Graph:
(0)---(1)
 |   / |
 |  /  |
(3)---(2)

Using 3 colors:
Vertex 0 → Color 1
Vertex 1 → Color 2
Vertex 2 → Color 3
Vertex 3 → Color 2
```

---

## 📚 Resources

* 📘 [GeeksforGeeks - Graph Coloring](https://www.geeksforgeeks.org/m-coloring-problem-backtracking-5/)
* 📘 [JavaTPoint - Graph Coloring](https://www.javatpoint.com/graph-coloring)
* 📘 [Wikipedia - Graph Coloring](https://en.wikipedia.org/wiki/Graph_coloring)

---

## 📌 Final Thoughts

Graph Coloring using Backtracking is a **powerful tool** when solving constraint satisfaction problems. While not efficient for large-scale graphs, it's ideal for:

* Small input spaces
* Combinatorial problem solving
* Educational and interview use

> 🎨 *"Graph coloring isn't just about colors—it's about conflict-free logic!"*

---

⭐ Star this repository if you found this helpful!
