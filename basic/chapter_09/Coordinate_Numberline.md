# [⬅️ Back](./chapter_09.md) | [📖 ReadMe](./../../README.md)

# 📉 Coordinate, Number Line & Manhattan Distance – CP Basics

---

## 🔹 **Number Line Basics**

- A **number line** is a straight line where each point represents a number.
- **Distance between two points** `a` and `b` on a number line:

```
Distance = |a - b|
```

**Example:**

- a = 3, b = 10 → distance = |3 - 10| = 7 ✅
- a = -2, b = 5 → distance = |-2 - 5| = 7 ✅

---

## 🔹 **2D Coordinates**

- A **point in 2D** is represented as `(x, y)` where `x` is horizontal and `y` is vertical.
- **Distance between two points (Euclidean distance):**

```sql
Distance = sqrt( (x2 - x1)^2 + (y2 - y1)^2 )
```

- Often, CP uses **squared distance** to avoid `sqrt` for speed:

```sql
Distance^2 = (x2 - x1)^2 + (y2 - y1)^2
```

---

## 🔹 **Manhattan Distance**

- **Manhattan distance** = distance if you can only move **vertically or horizontally**, like streets in Manhattan 🏙️

```sql
Manhattan distance = |x2 - x1| + |y2 - y1|
```

**Example:**

- Point A (1,2), Point B (4,6)

```sql
dx = |4-1| = 3
dy = |6-2| = 4
Manhattan distance = 3 + 4 = 7
```

💡 **CP tip:**

- Manhattan distance is widely used in **grid problems**.
- Avoid sqrt, just use **abs differences**.

---

## ♟️ Chessboard / King Moves Variant

Imagine a **chessboard grid**:

- You can move **horizontally, vertically, or diagonally** in **one step**.
- This is exactly how the **King moves** in chess.

---

### 🔹 How to calculate distance

If you are at point `A(x1, y1)` and want to move to `B(x2, y2)`:

- Let:

```
dx = |x2 - x1|  // horizontal distance
dy = |y2 - y1|  // vertical distance

```

- **Minimum number of steps to reach B from A** (King moves allowed):

```
Chessboard distance = max(dx, dy)
```

---

### 🔹 Why max(dx, dy)?

1. In one **diagonal step**, you can move **1 unit horizontally AND 1 unit vertically** at the same time.
2. After making min(dx, dy) diagonal steps, one coordinate will reach its target.
3. The remaining steps will be **straight moves** along the other coordinate.
4. Total steps = `max(dx, dy)` ✅

---

### 🔹 Summary Table

| Concept             | Formula                   | Notes                          |
| ------------------- | ------------------------- | ------------------------------ |
| 1D distance         | \|a-b\|                   | abs(a - b)                     |
| Euclidean distance  | sqrt((x2-x1)² + (y2-y1)²) | Classic distance in 2D         |
| Squared distance    | (x2-x1)² + (y2-y1)²       | Avoid sqrt in CP               |
| Manhattan distance  | \|x1-x2\|+\|y1-y2\|       | abs(x1-x2)+abs(y1-y2)          |
| Chessboard distance | max(dx, dy)               | dx = \|x1-x2\|, dy = \|y1-y2\| |

---
