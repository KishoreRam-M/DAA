# 📊 Time Complexity: Finding Minimum and Maximum using Divide and Conquer

---

## 🧠 Problem Statement

Given an array of `n` elements, find both the **minimum** and **maximum** elements using the **Divide and Conquer** technique.

---

## ⚙️ Algorithm Steps

1. **Divide**:
   Split the array into two halves of size `n/2`.

2. **Conquer**:
   Recursively find the **minimum** and **maximum** in each half.

3. **Combine**:
   Use **2 comparisons** to determine the final `min` and `max`:

   * Compare the two mins → get overall min.
   * Compare the two maxs → get overall max.

---

## ⏱️ Time Complexity Derivation

Let `T(n)` be the time to find min and max of `n` elements.

### 🧮 Recurrence Relation:

$$
T(n) = 2T\left(\frac{n}{2}\right) + 2
$$

* `2T(n/2)` → recursive calls on the two halves
* `+2` → to compare the two mins and the two maxs

---

## 🧾 Base Cases

* If `n = 1`:
  → `T(1) = 0` (no comparisons needed)

* If `n = 2`:
  → `T(2) = 1` (1 comparison between the two elements)

---

## 📐 Solve Using Master Theorem

General form:

$$
T(n) = aT\left(\frac{n}{b}\right) + O(n^d)
$$

Here:

* `a = 2`, `b = 2`, `d = 0`
* $n^{\log_b a} = n^{\log_2 2} = n^1$

Since `d = 0 < 1`, this matches **Case 1** of the Master Theorem:

> **Result**:
>
> $$
> T(n) = O(n)
> $$

---

## ✅ Final Answer

| Method               | Time Complexity | Comparisons  |
| -------------------- | --------------- | ------------ |
| Divide & Conquer     | `O(n)`          | ≈ `1.5n - 2` |
| Brute Force (linear) | `O(n)`          | `2n - 2`     |

> 🔍 **Conclusion**:
> Divide and Conquer uses fewer comparisons than brute-force and is optimal in terms of comparison count.
