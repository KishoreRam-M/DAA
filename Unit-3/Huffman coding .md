## 🧩 **Huffman Coding Algorithm**

### ✅ **Step 1: Input Data**

| Character | Frequency |
| --------- | --------- |
| a         | 5         |
| b         | 12        |
| c         | 16        |
| d         | 13        |
| e         | 9         |
| f         | 45        |

### 🌲 **Step 2: Construct the Huffman Tree**

1. **Initial heap**: (a:5), (b:12), (c:16), (d:13), (e:9), (f:45)

#### Iteration 1:

* Pick **a (5)** and **e (9)** → merge into node (14)

#### Iteration 2:

* Pick **b (12)** and **d (13)** → merge into node (25)

#### Iteration 3:

* Pick **14** (a+e) and **c (16)** → merge into node (30)

#### Iteration 4:

* Pick **25 (b+d)** and **30 (a+e+c)** → merge into node (55)

#### Final Iteration:

* Pick **55** and **f (45)** → merge into root node (100)

---

### 🌳 **Final Huffman Tree**

```plaintext
        100
       /   \
     45(f)  55
           /   \
         25     30
        / \     / \
      b   d   14   c
                / \
               a   e
```

### 🧮 **Step 3: Assign Binary Huffman Codes**

| Character | Huffman Code |
| --------- | ------------ |
| f         | 0            |
| b         | 100          |
| d         | 101          |
| c         | 111          |
| a         | 1100         |
| e         | 1101         |

---

### 📝 **Time & Space Complexity**

#### ✅ **Time Complexity:**

* **O(n log n)** for the construction of the Huffman tree, where `n` is the number of characters. This is because we use a **min-heap** (priority queue) to merge the nodes, which takes logarithmic time.

#### ✅ **Space Complexity:**

* **O(n)**, where `n` is the number of characters. We store the Huffman tree nodes in memory, and the space is proportional to the number of characters.

---

### ✅ **Real-World Use Cases**

1. **File Compression:**

   * **ZIP files** use Huffman coding for **lossless data compression**, ensuring that files occupy less storage.
2. **Image Compression (JPEG):**

   * Huffman coding is used in image compression algorithms like **JPEG** to reduce file sizes without losing quality.
3. **Data Transmission:**

   * Huffman coding helps in **network protocols** (like **HTTP compression**) to send data more efficiently by reducing the data size.
4. **Multimedia File Formats:**

   * Formats like **MP3** and **MP4** use Huffman coding to compress audio and video files.

---

### ✅ **Comparison with Other Algorithms**

| **Algorithm**              | **Time Complexity** | **Space Complexity** | **Use Case**                                          |
| -------------------------- | ------------------- | -------------------- | ----------------------------------------------------- |
| **Huffman Coding**         | O(n log n)          | O(n)                 | Lossless data compression, file formats (JPEG, MP3)   |
| **Run-Length Encoding**    | O(n)                | O(n)                 | Simple compression for repetitive data (e.g., images) |
| **LZ77/LZ78 (Dictionary)** | O(n)                | O(n)                 | Text compression (used in **ZIP** files)              |
| **Arithmetic Coding**      | O(n)                | O(n)                 | Lossless compression for smaller data (used in JPEG)  |
