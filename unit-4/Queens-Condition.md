# ♛ N-Queens Problem: Constraints & Step-by-Step Placement

## ✅ Constraints for Placing Queens

In the **N-Queens problem**, you must place N queens on an N×N chessboard such that **no two queens attack each other**. The constraints are:

### 1. Row Constraint

> Only one queen per row.
> **Why?** Two queens in the same row can attack each other.

### 2. Column Constraint

> Only one queen per column.
> **Why?** Queens in the same column can attack each other.

### 3. Diagonal Constraint (↘ Main Diagonal)

> No two queens should lie on the same diagonal (top-left to bottom-right).
> **Check:** `r1 - c1 ≠ r2 - c2`

### 4. Anti-diagonal Constraint (↙ Anti-Diagonal)

> No two queens should lie on the same anti-diagonal (top-right to bottom-left).
> **Check:** `r1 + c1 ≠ r2 + c2`

---

## 🔢 Step-by-Step Placement (4×4 Example)

### 🔹 Step 1: Place First Queen in Row 0

We start at the top-left and place the first queen in **column 0** of **row 0**.

```txt
Q . . .
. . . .
. . . .
. . . .
```

---

### 🔹 Step 2: Try Placing Queen in Row 1

We try each column in row 1 from left to right:

* Column 0 ❌ (same column as first queen)
* Column 1 ❌ (same diagonal as first queen)
* Column 2 ✅ (safe → place queen)

```txt
Q . . .
. . Q .
. . . .
. . . .
```

---

## 🧠 Visualizing Constraints — Example

For a queen at **(1, 2)**:

```txt
. . * .     ← Anti-diagonal attack
. . Q .     ← Queen at (1,2)
* * * *     ← Row and column attack
. * . *     ← Diagonal attack
```

> `*` = attacked position
> `Q` = queen
> `.` = safe/empty
