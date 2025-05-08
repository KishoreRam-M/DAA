# 🔁 Bubble Sort – Count Number of Swaps

## 📘 Problem Statement
You are given an array of integers:  
```

[8, 22, 7, 9, 31, 19, 5, 13]

```
Find how many **swaps** are required to sort the array in **ascending order** using **Bubble Sort**.

---

## 🧠 Bubble Sort Logic

Bubble Sort repeatedly compares adjacent elements and swaps them if they are in the wrong order. With each pass, the largest unsorted element "bubbles" to the end.

### 📌 Pseudocode:
```

for i = 0 to n - 1:
for j = 0 to n - i - 2:
if arr\[j] > arr\[j + 1]:
swap(arr\[j], arr\[j + 1])

````

---

## 🔍 Dry Run – Pass by Pass

Initial array: `[8, 22, 7, 9, 31, 19, 5, 13]`  
We count swaps during each pass:

| Pass | Swaps                                                                 | Swap Count |
|------|------------------------------------------------------------------------|------------|
| 1    | 22>7, 22>9, 31>19, 31>5, 31>13                                          | 5          |
| 2    | 8>7, 22>19, 22>5, 22>13                                                | 4          |
| 3    | 19>5, 19>13                                                            | 2          |
| 4    | 9>5                                                                    | 1          |
| 5    | 8>5                                                                    | 1          |
| 6    | 7>5                                                                    | 1          |
|      | ✅ Final Array: `[5, 7, 8, 9, 13, 19, 22, 31]`                          | **14**     |

---

## 💻 Java Code

```java
public class BubbleSortSwaps {
    public static void main(String[] args) {
        int[] arr = {8, 22, 7, 9, 31, 19, 5, 13};
        int swapCount = 0;

        for (int i = 0; i < arr.length - 1; i++) {
            for (int j = 0; j < arr.length - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Swap
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapCount++;
                }
            }
        }

        System.out.print("Sorted Array: ");
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println("\nTotal Swaps: " + swapCount);
    }
}
````

---

## 🧮 Output

```
Sorted Array: 5 7 8 9 13 19 22 31
Total Swaps: 14
```

---

## ⏱️ Time & Space Complexity

| Case    | Time Complexity | Explanation                       |
| ------- | --------------- | --------------------------------- |
| Best    | O(n)            | When the array is already sorted  |
| Average | O(n²)           | Nested loop comparisons & swaps   |
| Worst   | O(n²)           | Reversely sorted array            |
| Space   | O(1)            | In-place sorting, no extra memory |

---

## 🧰 Use Cases

Bubble Sort is not efficient for large datasets but useful for:

* Teaching sorting logic to beginners 👨‍🏫
* Sorting small datasets (5–10 elements)
* Detecting if an array is already sorted (with optimized version)
* Interview question to test basic sorting logic

---

## 🔄 Comparison with Other Algorithms

| Algorithm          | Time Complexity (Best / Avg / Worst) | Space    | Stable | Suitable For                 |
| ------------------ | ------------------------------------ | -------- | ------ | ---------------------------- |
| **Bubble Sort**    | O(n) / O(n²) / O(n²)                 | O(1)     | ✅ Yes  | Small data, learning         |
| **Selection Sort** | O(n²) / O(n²) / O(n²)                | O(1)     | ❌ No   | When swaps are expensive     |
| **Insertion Sort** | O(n) / O(n²) / O(n²)                 | O(1)     | ✅ Yes  | Nearly sorted data           |
| **Merge Sort**     | O(n log n) / O(n log n) / O(n log n) | O(n)     | ✅ Yes  | Large datasets               |
| **Quick Sort**     | O(n log n) / O(n log n) / O(n²)      | O(log n) | ❌ No   | Fast in practice, large data |

---

## 🎯 Final Answer: `14 swaps
