# 📘 Max-Min Algorithm using Divide and Conquer

## 📝 Problem Description

Given an array `A = [5, 7, 3, 4, 9, 12, 6, 2]`, the task is to find the **maximum** and **minimum** elements from the array using the **Divide and Conquer** approach.

### 🧠 Divide and Conquer Approach:
- **Divide** the array into two halves.
- **Recurse** to find the max and min for each half.
- **Combine** the results to get the overall maximum and minimum.

---

## 📊 Example Breakdown

### 🏷️ Initial Array:
```

A = \[5, 7, 3, 4, 9, 12, 6, 2]

````
- Split the array into two halves:

  Left: `[5, 7, 3, 4]`  
  Right: `[9, 12, 6, 2]`

### 🌳 Divide & Conquer Tree:

```plaintext
                              [5, 7, 3, 4, 9, 12, 6, 2]
                               /                     \
                     [5, 7, 3, 4]                    [9, 12, 6, 2]
                      /        \                     /         \
                [5, 7]      [3, 4]              [9, 12]      [6, 2]
                  ↓           ↓                   ↓             ↓
          Max=7, Min=5   Max=4, Min=3      Max=12, Min=9   Max=6, Min=2
                  \           /                   \             /
           Max=7, Min=3 (left half)         Max=12, Min=2 (right half)
                         \                          /
                🔚 Final Result: Max = 12, Min = 2
````

* **Left half**: Max = 7, Min = 3
* **Right half**: Max = 12, Min = 2

### ✅ Final Result:

* **Maximum** = 12
* **Minimum** = 2

---

## 🧑‍💻 **Algorithm for Max-Min using Divide and Conquer**

### **Algorithm Explanation:**

The algorithm uses the Divide and Conquer strategy to find the maximum and minimum elements in an array efficiently.

1. **Base Case:**

   * If the array has only one element, it is both the maximum and the minimum.
   * If the array has two elements, compare them directly to determine the maximum and minimum.

2. **Recursive Case:**

   * Divide the array into two halves.
   * Recursively find the maximum and minimum in both halves.
   * Combine the results from both halves to get the final maximum and minimum.

### **Pseudocode:**

```plaintext
Function FindMaxMin(arr, low, high):
    If low == high:
        Return arr[low], arr[low]   // one element, both max and min

    If high == low + 1:
        If arr[low] > arr[high]:
            Return arr[low], arr[high]   // arr[low] is max, arr[high] is min
        Else:
            Return arr[high], arr[low]   // arr[high] is max, arr[low] is min

    mid = (low + high) // 2
    (max1, min1) = FindMaxMin(arr, low, mid)    // recursive call for left half
    (max2, min2) = FindMaxMin(arr, mid + 1, high) // recursive call for right half

    Return max(max1, max2), min(min1, min2)  // Combine the results
```

---

## 💻 Java Code Implementation

```java
public class MaxMinDivideAndConquer {

    // Function to find the maximum and minimum using Divide and Conquer
    public static int[] findMaxMin(int[] arr, int low, int high) {
        // Base case: Only one element
        if (low == high) {
            return new int[] {arr[low], arr[low]}; // (max, min)
        }
        
        // Base case: Two elements
        if (high == low + 1) {
            if (arr[low] > arr[high]) {
                return new int[] {arr[low], arr[high]}; // (max, min)
            } else {
                return new int[] {arr[high], arr[low]}; // (max, min)
            }
        }

        // Recursive case: Divide the array
        int mid = (low + high) / 2;
        int[] left = findMaxMin(arr, low, mid);
        int[] right = findMaxMin(arr, mid + 1, high);
        
        // Combine results
        int max = Math.max(left[0], right[0]);
        int min = Math.min(left[1], right[1]);

        return new int[] {max, min};
    }

    public static void main(String[] args) {
        int[] arr = {5, 7, 3, 4, 9, 12, 6, 2};
        int n = arr.length;
        
        // Find max and min
        int[] result = findMaxMin(arr, 0, n - 1);

        // Output the result
        System.out.println("Maximum = " + result[0]);
        System.out.println("Minimum = " + result[1]);
    }
}
```

---

## ⏱️ Time & Space Complexity

| Complexity       | Time Complexity                                                                                        | Space Complexity |
| ---------------- | ------------------------------------------------------------------------------------------------------ | ---------------- |
| **Best Case**    | O(n)                                                                                                   | O(log n)         |
| **Average Case** | O(n)                                                                                                   | O(log n)         |
| **Worst Case**   | O(n)                                                                                                   | O(log n)         |
| **Explanation**  | The array is divided recursively until base case (log n), and at each level, comparisons are made (n). |                  |

---

## 🧰 Real-World Use Cases

* **Small datasets**: When the dataset is small and you need an efficient way to compute both max and min.
* **Optimization Problems**: Reduce the number of comparisons, especially in competitive programming.
* **Divide & Conquer Strategy**: Commonly used in problem-solving techniques like searching, sorting, and dynamic programming.

---

## 🔄 Comparison with Other Algorithms

| Algorithm                      | Time Complexity (Best / Avg / Worst) | Space    | Stable | Use Case                         |
| ------------------------------ | ------------------------------------ | -------- | ------ | -------------------------------- |
| **Bubble Sort**                | O(n) / O(n²) / O(n²)                 | O(1)     | ✅ Yes  | Simple, small datasets           |
| **Merge Sort**                 | O(n log n) / O(n log n) / O(n log n) | O(n)     | ✅ Yes  | Large datasets, stable sort      |
| **Quick Sort**                 | O(n log n) / O(n log n) / O(n²)      | O(log n) | ❌ No   | Fast for large datasets          |
| **Max-Min (Divide & Conquer)** | O(n)                                 | O(log n) | ✅ Yes  | Efficient, minimizes comparisons |

---

## ✅ Final Answer

For the array `A = [5, 7, 3, 4, 9, 12, 6, 2]`:

* **Maximum** = 12
* **Minimum** = 2

---

## 🏁 Conclusion

* **Divide and Conquer** is a powerful technique to reduce the number of comparisons when finding both the maximum and minimum elements.
* The algorithm is efficient for large datasets and can be applied to many real-world problems where optimization is required.

