### [⬅️ Back To README FILE](./../../README.md)

# Chapter 03 : 🧱 Types of Loops in C++

### 1️⃣ **`for` Loop**

The `for` loop is best when the number of iterations is known.

```cpp
for (int i = 0; i < 10; i++) {
    cout << i << " ";
}
```

🔹 Components:

- Initialization → `int i = 0`
- Condition → `i < 10`
- Update → `i++`
  The loop runs **as long as the condition is true**.

---

### 2️⃣ **`while` Loop**

The `while` loop is used when the number of iterations is unknown.

```cpp
int i = 0;
while (i < 10) {
    cout << i << " ";
    i++;
}
```

Runs **only when the condition is true** from the start.

---

### 3️⃣ **`do...while` Loop**

Executes at least once, **even if the condition is false**.

```cpp
int i = 0;
do {
    cout << i << " ";
    i++;
} while (i < 10);
```

✅ Use it when the loop **must execute once no matter what**.

---

## 🎯 Key Concepts to Master

### 🔁 Loop Control Statements

### 🔸 `break`

Used to **exit the loop immediately**.

```cpp
for (int i = 1; i <= 10; i++) {
    if (i == 5) break;
    cout << i << " ";
}
```

### 🔸 `continue`

Skips the current iteration and moves to the next one.

```cpp
for (int i = 1; i <= 10; i++) {
    if (i == 5) continue;
    cout << i << " ";
}
```

---

### 🧠 Infinite Loops

Be careful not to create a loop that never ends:

```cpp
while (true) {
    // Will run forever unless broken manually
}
```

Use only with clear break conditions!

---

### 🔄 Nested Loops

A loop inside another loop.

```cpp
for (int i = 1; i <= 3; i++) {
    for (int j = 1; j <= 2; j++) {
        cout << "(" << i << "," << j << ") ";
    }
}
```

Used for grids, matrices, pairwise comparisons, etc.

⛔ Be careful: **nested loops can cause TLE (Time Limit Exceeded)** if total iterations are too large.

---

### 🧮 Loop Variable Scope

Variables declared inside a loop exist **only inside that loop**:

```cpp
for (int i = 0; i < 5; i++) {
    cout << i << " ";
}
// i is not accessible here
```

---

## 🪄 Competitive Programming Tips & Tricks

### 💡 1. **Loop Bounds Matter**

Always double-check `i <= n` vs `i < n`. An off-by-one can cause WA or TLE.

### 💡 2. **Use `-i` Instead of `i--` (Micro-optimization)**

```cpp
for (int i = n; i >= 1; --i) // slightly faster
```

This is a micro-optimization. Rarely needed, but fun fact.

### 💡 3. **Speed Up Loops with Bit Shifting**

Instead of `i *= 2`:

```cpp
for (int i = 1; i <= n; i <<= 1)
```

Faster and cleaner! Works great when iterating over powers of 2.

### 💡 4. **Avoid Unnecessary Conditions Inside Loop**

If possible, **move `if` logic outside the loop** or redesign loop bounds to skip unnecessary checks.

### 💡 5. **Break Early in Searching**

If you're looking for something in a loop (like a minimum or a match), don’t scan the whole thing if not needed—break as soon as found.

### 💡 6. **Avoid Nested Loops for Large `n`**

If `n` is 10^5+, avoid nested loops. They cause TLE. Instead, try prefix sums, maps, or math tricks.

---

## 🎉 Summary

| Concept                      | Learn & Master                     |
| ---------------------------- | ---------------------------------- |
| `for`, `while`, `do...while` | When and how to use                |
| `break`, `continue`          | Control loop execution             |
| Loop bounds                  | `i < n`, `i <= n`, `i--`, etc.     |
| Nested loops                 | Watch total iterations             |
| Infinite loops               | Use only with clear exit (`break`) |
