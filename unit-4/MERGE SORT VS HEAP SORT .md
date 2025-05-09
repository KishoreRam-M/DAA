# 🔄 Merge Sort vs Heap Sort – Efficiency Comparison

| **Aspect**                  | **Merge Sort**                                                                | **Heap Sort**                                                            |
| --------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| **Time Complexity**         | Best, Average, and Worst Case: `O(n log n)`                                   | Best, Average, and Worst Case: `O(n log n)`                              |
| **Space Complexity**        | `O(n)` (extra space needed for merging sublists)                              | `O(1)` (in-place sorting; minimal extra space required)                  |
| **Stability**               | ✅ Stable (preserves the order of equal elements)                              | ❌ Not Stable (equal elements may reorder)                                |
| **Internal vs External**    | Best for **external sorting** (works with large datasets on external devices) | Suitable for **internal sorting** (works best entirely in memory)        |
| **Use of Memory**           | Needs additional `O(n)` space for temporary arrays                            | In-place; does not require extra memory besides the heap                 |
| **Sorting Type**            | Divide and Conquer strategy                                                   | Comparison-based, in-place approach                                      |
| **Linked List Performance** | ✅ Very efficient (no need for random access)                                  | ❌ Less efficient (requires random access)                                |
| **Efficiency in Practice**  | Performs well on large datasets but consumes more memory                      | Space-efficient but slower due to cache-unfriendly memory access         |
| **Key Feature**             | Divides list → sorts sublists → merges in sorted order                        | Builds a binary heap → repeatedly extracts max/min                       |
| **Applications**            | Used in sorting **linked lists**, **external sorting**, large datasets        | Preferred where **memory is limited** or **space efficiency** is crucial |

---

## 📝 Summary

* **Merge Sort** is **stable**, great for **linked lists** and **external sorting**, but uses more memory.
* **Heap Sort** is **in-place**, **space-efficient**, and suited for **internal sorting**, but is not stable and less efficient on linked structures.

> ✅ Use **Merge Sort** when stability and external sorting are needed.
> ✅ Use **Heap Sort** when memory efficiency is a top priority
