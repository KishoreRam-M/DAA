# ✅ Quick Sort – Full Explanation & Step-by-Step Dry Run


## 📌 Problem Description

**Problem**:
Sort the array `[5, 3, 1, 9, 8, 2, 4, 7]` using the **Quick Sort** algorithm.

**Condition**: Use the **last element** as the pivot in each recursive call (Lomuto partition scheme).

---

## 🎯 Objective

* Apply Quick Sort to sort the array.
* Show recursive partitioning steps.
* Provide a Java implementation.
* Analyze time and space complexity.
* Compare with other sorting algorithms.
* Mention real-world applications.

---

## 🔍 What is Quick Sort?

**Quick Sort** is a **Divide and Conquer** algorithm that:

* Picks a **pivot element**.
* **Partitions** the array: elements smaller than the pivot go left, larger go right.
* **Recursively sorts** the left and right subarrays.

---

## ⚙️ How It Works?

### Step-by-Step Dry Run for Array: `[5, 3, 1, 9, 8, 2, 4, 7]`

---

### 📥 Step 1: Initial Call

```
Array: [5, 3, 1, 9, 8, 2, 4, 7]
Pivot = 7 (last element)
```

Partitioning results in:

```
[5, 3, 1, 2, 4], 7, [9, 8]
```

---

### 📥 Step 2: Recurse on Left `[5, 3, 1, 2, 4]`

* Pivot = 4
  Partition result:

```
[3, 1, 2], 4, [5]
```

---

### 📥 Step 3: Recurse on `[3, 1, 2]`

* Pivot = 2
  Partition result:

```
[1], 2, [3]
```

Now all subarrays are sorted:

```
[1, 2, 3, 4, 5]
```

---

### 📥 Step 4: Recurse on Right `[9, 8]`

* Pivot = 8
  Partition result:

```
[8], 9
```

---

### ✅ Final Sorted Array:

```
[1, 2, 3, 4, 5, 7, 8, 9]
```

---

## 🧠 Algorithm Steps

```text
QuickSort(arr, low, high):
    if low < high:
        pivotIndex = partition(arr, low, high)
        QuickSort(arr, low, pivotIndex - 1)
        QuickSort(arr, pivotIndex + 1, high)

partition(arr, low, high):
    pivot = arr[high]
    i = low - 1
    for j from low to high - 1:
        if arr[j] < pivot:
            i++
            swap arr[i] and arr[j]
    swap arr[i+1] and arr[high]
    return i + 1
```

---

## 💻 Java Implementation

```java
public class QuickSort {
    static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            int pi = partition(arr, low, high);
            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }

    static int partition(int[] arr, int low, int high) {
        int pivot = arr[high];
        int i = low - 1;

        for (int j = low; j < high; j++) {
            if (arr[j] < pivot) {
                i++;
                // swap arr[i] and arr[j]
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }

        // swap arr[i + 1] and arr[high]
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;

        return i + 1;
    }

    public static void main(String[] args) {
        int[] arr = {5, 3, 1, 9, 8, 2, 4, 7};
        quickSort(arr, 0, arr.length - 1);

        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}
```

---

## 📊 Time and Space Complexity

| Case         | Time Complexity | Explanation                                   |
| ------------ | --------------- | --------------------------------------------- |
| Best Case    | O(n log n)      | Pivot divides array evenly                    |
| Average Case | O(n log n)      | Typical case with decent pivot choice         |
| Worst Case   | O(n²)           | Pivot is always max or min (unbalanced split) |

**Space Complexity**: O(log n) for recursion stack in best case; O(n) in worst case.

---

## 🎨 Visual Diagram

```
Original:        [5, 3, 1, 9, 8, 2, 4, 7]
                      |
                  pivot = 7
         ------------------------------
         |                            |
 [5, 3, 1, 2, 4]                      [9, 8]
         |                             |
     pivot = 4                     pivot = 8
     -----------                   ---------
     |         |                 [8]       [9]
[3, 1, 2]     [5]      
    |
pivot = 2
  --------
  |      |
[1]     [3]
```

---

## 🔄 Comparison with Other Algorithms

| Algorithm      | Time Complexity | Space    | Stable | Best For                                 |
| -------------- | --------------- | -------- | ------ | ---------------------------------------- |
| **Quick Sort** | O(n log n)      | O(log n) | ❌      | Best average case, fast in practice      |
| Merge Sort     | O(n log n)      | O(n)     | ✅      | Stable sort, guaranteed performance      |
| Bubble Sort    | O(n²)           | O(1)     | ✅      | Educational, small or nearly sorted data |
| Insertion Sort | O(n²)           | O(1)     | ✅      | Good for small or nearly sorted data     |

---

## 🧰 Real-World Use Cases

✅ Used in **system-level libraries** like:

* C/C++ standard library `qsort()`
* Java’s Arrays.sort() for primitive types (dual-pivot QuickSort)

✅ Used in **search engines**, **databases**, **file systems**, and **data analytics tools** for efficient sorting.

---

## 📦 Output

```text
1 2 3 4 5 7 8 9
```
