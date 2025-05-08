## 🎯 Chessboard Representation

```
Row →     0  1  2  3  4  5  6  7
         ------------------------
Row 0  →  Q  .  .  .  .  .  .  .   → Queen at (0, 0)
Row 1  →  .  .  .  .  Q  .  .  .   → Queen at (1, 4)
Row 2  →  .  .  .  .  .  .  .  Q   → Queen at (2, 7)
Row 3  →  .  .  .  .  .  Q  .  .   → Queen at (3, 5)
Row 4  →  .  .  Q  .  .  .  .  .   → Queen at (4, 2)
Row 5  →  .  .  .  .  .  .  Q  .   → Queen at (5, 6)
Row 6  →  .  Q  .  .  .  .  .  .   → Queen at (6, 1)
Row 7  →  .  .  .  Q  .  .  .  .   → Queen at (7, 3)
```

---

## 🧠 Step-by-Step Backtracking Explanation

We try placing queens **row by row**:

### ✅ **Step 1: Row 0**

Try columns from 0 to 7.

* (0,0): ✅ Safe → Place Queen
  `board = [0, _, _, _, _, _, _, _]`

---

### ✅ **Step 2: Row 1**

Try columns:

* (1,0): ❌ same column as (0,0)
* (1,1): ❌ same diagonal as (0,0)
* (1,2): ❌ same diagonal
* (1,3): ❌ same diagonal
* (1,4): ✅ Safe → Place Queen
  `board = [0, 4, _, _, _, _, _, _]`

---

### ✅ **Step 3: Row 2**

Try columns:

* (2,0) → ❌ column clash
* (2,1) → ❌ diagonal clash
* (2,2) → ❌ diagonal
* ...
* (2,7): ✅ Safe → Place Queen
  `board = [0, 4, 7, _, _, _, _, _]`

---

### ✅ **Step 4: Row 3**

Try columns:

* (3,0) to (3,4) → ❌ conflicts
* (3,5): ✅ Safe → Place Queen
  `board = [0, 4, 7, 5, _, _, _, _]`

---

### ✅ **Step 5: Row 4**

Try columns:

* (4,0) → ❌ column clash
* ...
* (4,2): ✅ Safe → Place Queen
  `board = [0, 4, 7, 5, 2, _, _, _]`

---

### ✅ **Step 6: Row 5**

Try columns:

* (5,0) to (5,5) → ❌ conflicts
* (5,6): ✅ Safe → Place Queen
  `board = [0, 4, 7, 5, 2, 6, _, _]`

---

### ✅ **Step 7: Row 6**

Try columns:

* (6,0) → ❌ conflict
* (6,1): ✅ Safe → Place Queen
  `board = [0, 4, 7, 5, 2, 6, 1, _]`

---

### ✅ **Step 8: Row 7**

Try columns:

* (7,0) to (7,2) → ❌ conflict
* (7,3): ✅ Safe → Place Queen
  `board = [0, 4, 7, 5, 2, 6, 1, 3]`

---

## 🎉 Success! All 8 queens placed without attack!

---

## 🧠 Final Board: Visual Understanding

```plaintext
 Q  .  .  .  .  .  .  .   ← (0,0)
 .  .  .  .  Q  .  .  .   ← (1,4)
 .  .  .  .  .  .  .  Q   ← (2,7)
 .  .  .  .  .  Q  .  .   ← (3,5)
 .  .  Q  .  .  .  .  .   ← (4,2)
 .  .  .  .  .  .  Q  .   ← (5,6)
 .  Q  .  .  .  .  .  .   ← (6,1)
 .  .  .  Q  .  .  .  .   ← (7,3)
