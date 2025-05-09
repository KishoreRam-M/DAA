# 🔁 Hamiltonian Cycle Problem

> 🧠 *"Find a path that visits each vertex exactly once and returns to the start."*

---

## 📌 Table of Contents

- [📖 What is a Hamiltonian Cycle?](#-what-is-a-hamiltonian-cycle)
- [🆚 Hamiltonian vs Eulerian](#-hamiltonian-vs-eulerian)
- [🌐 Real-World Applications](#-real-world-applications)
- [📅 When to Use It?](#-when-to-use-it)
- [🧠 Algorithm Logic](#-algorithm-logic)
- [🔍 Step-by-Step Explanation](#-step-by-step-explanation)
- [📊 Time and Space Complexity](#-time-and-space-complexity)
- [💡 Java Code Example](#-java-code-example)
- [✅ Advantages](#-advantages)
- [❌ Disadvantages](#-disadvantages)
- [🔄 Comparison with Other Algorithms](#-comparison-with-other-algorithms)
- [📚 Resources](#-resources)
- [🧩 Visual Representation](#-visual-representation)
- [🔚 Final Thoughts](#-final-thoughts)

---

## 📖 What is a Hamiltonian Cycle?

A **Hamiltonian cycle** in a graph is a cycle that visits **each vertex exactly once** and **returns to the starting vertex**.

> 🔁 Unlike a simple path, a Hamiltonian cycle must:
> - Visit every node **only once**
> - **Return to the start**

---

## 🆚 Hamiltonian vs Eulerian

| Feature           | Hamiltonian Cycle         | Eulerian Cycle             |
|------------------|---------------------------|----------------------------|
| Visits           | Every **vertex** once     | Every **edge** once        |
| Returns to start | ✅ Yes                     | ✅ Yes                      |
| Focus            | Vertices                  | Edges                      |
| Problem type     | NP-complete               | Polynomial time solvable   |

---

## 🌐 Real-World Applications

- 🛰️ **Traveling Salesman Problem (TSP)** – Find the shortest route that visits all cities
- 🧬 **Genome assembly** in bioinformatics
- 🛠️ **Network topology testing**
- 🧑‍💼 **Scheduling and optimization**
- 🎮 **Puzzle solving** in games like Knight's Tour

---

## 📅 When to Use It?

Use Hamiltonian Cycle approach when:
- You need to visit every node exactly once and return
- The graph is **undirected or directed**
- Brute-force would be too slow, and clever pruning is needed
- You're solving problems like TSP, Knight’s Tour, or route optimization

---

## 🧠 Algorithm Logic

We use **Backtracking** to explore all possible paths and check if a Hamiltonian cycle exists.

**Core Idea**:
1. Start from vertex 0
2. Recursively add unvisited vertices to the path
3. If all vertices are in the path and the last is connected to the first → ✅ Hamiltonian Cycle

---

## 🔍 Step-by-Step Explanation

Given a graph `G` with `V` vertices:
```text
1. Create an array `path[]` of size V, initialize all as -1
2. Put vertex 0 as the starting point (path[0] = 0)
3. For each position in path[1...V-1], try all vertices:
    a. Check if the vertex is adjacent to the previous
    b. Ensure it is not already in the path
4. If all positions are filled and the last vertex connects to the first:
    ✅ Hamiltonian Cycle found
5. Else:
    ❌ Backtrack and try next option
````

---

## 📊 Time and Space Complexity

| Type              | Complexity                                              |
| ----------------- | ------------------------------------------------------- |
| Time (Worst case) | O(N!) (factorial)                                       |
| Space             | O(N) (path + recursion)                                 |
| Optimization      | Use **pruning** with adjacency checks and visited flags |

---

## 💡 Java Code Example

```java
public class HamiltonianCycle {
    final int V = 5;
    int path[];

    boolean isSafe(int v, int[][] graph, int[] path, int pos) {
        if (graph[path[pos - 1]][v] == 0)
            return false;
        for (int i = 0; i < pos; i++)
            if (path[i] == v)
                return false;
        return true;
    }

    boolean hamCycleUtil(int[][] graph, int[] path, int pos) {
        if (pos == V) {
            return graph[path[pos - 1]][path[0]] == 1;
        }

        for (int v = 1; v < V; v++) {
            if (isSafe(v, graph, path, pos)) {
                path[pos] = v;
                if (hamCycleUtil(graph, path, pos + 1))
                    return true;
                path[pos] = -1; // Backtrack
            }
        }
        return false;
    }

    void hamCycle(int[][] graph) {
        path = new int[V];
        for (int i = 0; i < V; i++)
            path[i] = -1;

        path[0] = 0;
        if (!hamCycleUtil(graph, path, 1)) {
            System.out.println("No Hamiltonian Cycle exists");
            return;
        }

        System.out.print("Hamiltonian Cycle: ");
        for (int i = 0; i < V; i++)
            System.out.print(path[i] + " ");
        System.out.println(path[0]); // return to start
    }

    public static void main(String[] args) {
        HamiltonianCycle h = new HamiltonianCycle();
        int[][] graph1 = {
            {0, 1, 0, 1, 0},
            {1, 0, 1, 1, 1},
            {0, 1, 0, 0, 1},
            {1, 1, 0, 0, 1},
            {0, 1, 1, 1, 0},
        };
        h.hamCycle(graph1);
    }
}
```

---

## ✅ Advantages

* ✔️ Systematic way to find cycles
* ✔️ Helps in solving TSP and routing problems
* ✔️ Works for both directed/undirected graphs

---

## ❌ Disadvantages

* ❌ Very high time complexity (O(N!))
* ❌ Impractical for large graphs
* ❌ Not scalable without heuristics like **Branch and Bound** or **Dynamic Programming (Held-Karp)**

---

## 🔄 Comparison with Other Algorithms

| Algorithm         | Best For                         | Time Complexity |
| ----------------- | -------------------------------- | --------------- |
| Hamiltonian Cycle | Visit every vertex once & return | O(N!)           |
| DFS               | Explore graph paths              | O(V + E)        |
| BFS               | Shortest path (unweighted)       | O(V + E)        |
| Dijkstra          | Shortest path (weighted)         | O(E + V log V)  |
| TSP (DP)          | Min cost cycle                   | O(n^2 \* 2^n)   |

---

## 📚 Resources

* 📘 [GeeksforGeeks - Hamiltonian Cycle](https://www.geeksforgeeks.org/hamiltonian-cycle-backtracking-6/)
* 📘 [JavaTPoint - Hamiltonian Cycle](https://www.javatpoint.com/hamiltonian-cycle)
* 📘 [Wikipedia - Hamiltonian Path](https://en.wikipedia.org/wiki/Hamiltonian_path)

---

## 🧩 Visual Representation

```
Example graph:

(0)---(1)
 |   / |
 |  /  |
(3)---(2)---(4)

Hamiltonian Cycle: 0 → 1 → 2 → 4 → 3 → 0
```

---

## 🔚 Final Thoughts

Hamiltonian Cycle is a **classic NP-complete** problem—challenging, but essential in theory and applications. While it may not scale well, it forms the base of many optimization problems in logistics, biology, and AI.

> 🔁 It's not just about visiting all nodes—it's about visiting **smartly and cyclically**.

---

⭐ If you found this helpful, **star this repo** and share it with your fellow coders!
