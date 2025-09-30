### [⬅️ Back To README FILE](./../../README.md)

# 🧱 Basics of Array in C++

### 🧪 Declaration

```cpp
int a[10];          // Declares array of size 10 (index: 0 to 9)
int a[5] = {1, 2, 3, 4, 5};  // Initializes first 5 values
```

### 🧪 Accessing Elements

```cpp
a[0] = 10;
cout << a[0];  // Outputs: 10
```

Indexing starts from **0**, and **out-of-bound access = UB (undefined behavior)**.

---

## 🚀 Key Topics You MUST Master

### 1️⃣ **Input/Output Efficiently**

```cpp
int n;
cin >> n;
int a[n];  // Not standard C++, but allowed in many CP platforms like Codeforces
for (int i = 0; i < n; i++){
	cin >> a[i];
}
```

---

### 2️⃣ **Bounds and Limits**

### 🔹 Array Sizes

```cpp
int a[1000000]; // 1e6 → OK globally
```

| Scope        | Max Size |
| ------------ | -------- |
| Global array | ~1e7     |
| Local array  | ~1e5     |

✅ Use global scope (outside main) for big arrays.

---

### 3️⃣ **Multi-dimensional Arrays**

```cpp
int grid[100][100];
grid[0][1] = 5;
```

Common for matrix problems, DP grids, graphs.

---

### 4️⃣ **Looping Tricks**

### Forward:

```cpp
for(int i = 0; i < n; i++) ...
```

### Backward:

```cpp
for (int i = n - 1; i >= 0; i--) ...
```

### 6️⃣ Sorting And Reverse Functions

```cpp
sort(a, a + n); // sorts array a[0] to a[n-1] in ascending order
reverse(a, a + n); // reverses array a[0] to a[n-1]
```

---

# 🧰 Some Array Technique.

### 1️⃣ Search The Element in The Array

⚒️ Method 1: Brute Force (Linear Search)

```cpp
bool found = false;
for (int i = 0; i < n; i++) {
    if (a[i] == x) {
        found = true;
        break;
    }
}
```

✅ Works on **unsorted arrays**

🕐 Time: **O(n)**

📦 Space: **O(1)**

⚒️ Method 2: Use `count()` from `<algorithm>`

```cpp
bool found = count(a, a + n, x) > 0;
```

✅ Clean and short

🕐 Time: **O(n)**

📦 Space: **O(1)**

⚠️ Still linear — don’t use for large arrays repeatedly!

---

## 2️⃣ Find Maximum and Minimum Value in The Array

### ⚒️ Method 1: Manual Way (Classic CP Style)

```cpp
int mx = a[0], mn = a[0];
for (int i = 1; i < n; i++) {
    mx = max(mx, a[i]);
    mn = min(mn, a[i]);
}
```

✅ Fast, simple, pure C++

🕐 Time: **O(n)**

📦 Space: **O(1)**

💡 Works with `int`, `long long`, `double`, etc.

### ⚒️ Method 2: Using `max_element` and `min_element`

```cpp
#include <algorithm>

int mx = *max_element(a, a + n);
int mn = *min_element(a, a + n);
```

✅ Short and sweet

🕐 Time: **O(n)**

📦 Space: **O(1)**

🔥 Cleaner than writing your own loop in contests

---

### 3️⃣ Frequency Count

📝 Example 1: Count Frequency of Elements from 1 to 100

```cpp
int freq[101] = {0};
for (int i = 0; i < n; i++) {
    freq[a[i]]++;
}
```

🧠 Now:

- `freq[5]` → number of times `5` appears
- `freq> 0` → element `x` exists
- `freq== 2` → `x` appeared twice

---

### 4️⃣ Basic Prefix Sum

## 🛠️ Prefix Sum Build

```cpp
int a[n]; // original array
int prefix[n + 1]; // prefix[0] = 0

prefix[0] = 0;
for (int i = 1; i <= n; i++) {
    prefix[i] = prefix[i - 1] + a[i - 1];
}
```

🧠 Now:

```cpp
// sum from index l to r (0-based):
int sum = prefix[r + 1] - prefix[l];
```

💡 `prefix[i]` stores sum of first `i` elements (0-based logic)

---

## ⚔️ Competitive Programming Tips & Tricks

### 💡 1. **Always Initialize Carefully**

Uninitialized arrays = garbage data = WA/TLE.

Use:

```cpp
int a[100] = {0}; // fills with 0
```

Or `memset` for small values:

```cpp
memset(a, -1, sizeof(a));  // sets all bytes to -1 (only for -1 or 0)
```

---

### 💡 2. **Handle Index Carefully**

❌ `a[n] = x;` when `a` is size `n` → **TLE/RE**

✅ Always validate:

```cpp
if (i >= 0 && i < n) a[i] = x;
```

---

### 💡 4. **Sentinels for Border Handling**

You can pad arrays with extra space to avoid index out of bounds.

```cpp
int a[n + 2] = {0}; // extra padding on both sides
```

Helpful for problems with `a[i-1]`, `a[i+1]` access.

---

### 💡 5. **Avoid Nested Loops on Large Arrays**

For `n >= 10^5`, nested loops like:

```cpp
cpp
CopyEdit
for (int i = 0; i < n; i++){
    for (int j = i+1; j < n; j++){
	    // avoid this if n >= 10^5
	  }
}
```

💣 Will cause TLE.

✅ Instead, try:

- Prefix sums
- Hashing
- Sliding window
- Two pointers

---

### 💡 6. **Watch for `int` Overflows**

Sum of 10^5 values each up to 10^9?

Use `long long`:

```cpp
long long sum = 0;
for (...) sum += a[i];
```

---

## 🔥 Must-Know Snippets

✅ **Reverse an array**

```cpp
for (int i = 0; i < n / 2; i++)
    swap(a[i], a[n - i - 1]);
```

✅ **Find max element**

```cpp
int mx = a[0];
for (int i = 1; i < n; i++)
    mx = max(mx, a[i]);
```

✅ **Count occurrences of value `x`**

```cpp
int count = 0;
for (int i = 0; i < n; i++)
    if (a[i] == x) count++;
```

---

## 🧠 Summary Table

| Concept         | Importance                    |
| --------------- | ----------------------------- |
| Input/output    | Fast scan of `n` elements     |
| Prefix sum      | Range queries in O(1)         |
| Frequency array | Count occurrences efficiently |
| Loop styles     | Forward/reverse logic         |
| Memory limits   | Prevent RE and TLE            |
