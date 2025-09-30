### [⬅️ Back To README FILE](./../../README.md)

# 🧠 What is a Multidimensional Array?

A **multidimensional array** is basically an array of arrays. Think of a **2D array** as a grid, like a chessboard. It helps store data in a row-column format.

In competitive programming, the most common use is for:

- **Grids** (maps, boards, matrices),
- **DP tables**, or
- **Adjacency matrices** for graphs.

---

## 📐 Declaration

```cpp
type array_name[rows][columns];
```

### Example:

```cpp
int grid[100][100]; // 2D array of 100 rows and 100 columns
```

Fun Fact 🧩: A 2D array like `grid[3][4]` has 3 rows and 4 columns = 12 total elements.

---

## 🧮 Accessing and Modifying Elements

You access an element using `grid[row][col]`.

```cpp
grid[0][1] = 5;
cout << grid[0][1]; // Outputs 5
```

⚠️ Remember: Indexing starts at 0!

---

## 🌀 Common Use Cases

### 1. **Input/Output for a Grid**

```cpp
nt n, m;
cin >> n >> m;
int grid[n][m]; // ❌ Not allowed in old compilers! Use constant size.

const int MAX = 1005;
int grid[MAX][MAX];

for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
        cin >> grid[i][j];
    }
}
```

### 2. **Printing a Grid**

```cpp
for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
        cout << grid[i][j] << " ";
    }
    cout << "\n";
}
```

---

## ⚔️ Competitive Programming Tips

### ✅ Tip 1: Use constant sizes

In contests, avoid:

```cpp
int n;
cin >> n;
int arr[n]; // ❌ Not safe or portable
```

Use:

```cpp
const int N = 1005;
int arr[N][N];
```

---

### ✅ Tip 2: Initialize safely

Use `memset` only for 0 or -1 (byte-wise set):

```cpp
memset(arr, 0, sizeof arr);   // Set all to 0
memset(arr, -1, sizeof arr);  // Set all to -1
```

⚠️ Don’t use `memset` to set other values!

---

### ✅ Tip 3: Direction Arrays for Grids

Useful for moving up/down/left/right:

```cpp
cpp
CopyEdit
int dx[4] = {-1, 1, 0, 0};
int dy[4] = {0, 0, -1, 1};

for (int dir = 0; dir < 4; dir++) {
    int nx = x + dx[dir];
    int ny = y + dy[dir];
    // check bounds, then access grid[nx][ny]
}
```

---

### ✅ Tip 4: Use 3D arrays wisely

Sometimes, 2D is not enough.

```cpp
int dp[100][100][2]; // e.g. store extra state like turn, parity, etc.
```

---

## ❌ Common Mistakes

- ❗ Using `int arr[n][m];` without knowing if n, m are too big.
- ❗ Using wrong dimensions. `arr[rows][cols]` — double-check which index is row vs col!
- ❗ Forgetting to reset array between test cases in multi-case problems.

---

## 🧠 Mini Summary

| Concept     | Syntax                        | Notes                    |
| ----------- | ----------------------------- | ------------------------ |
| Declaration | `int arr[100][100];`          | Fixed size only          |
| Access      | `arr[i][j]`                   | 0-based indexing         |
| Initialize  | `memset(arr, 0, sizeof arr);` | Only for 0/-1            |
| Grid Moves  | `dx[], dy[]`                  | For 4-direction movement |
| 3D Arrays   | `arr[x][y][state];`           | Advanced usage           |
