### [⬅️ Back To README FILE](./../../README.md)

# 🧩 Chapter 02: **Conditions** (C++ Edition – Competitive Programming Focus)

---

### 1️⃣ **Basic Conditional Statements**

```cpp
if (condition1) {
    // Code runs if condition1 is true
} else if (condition1) {
    // Code runs if condition2 is true
} else {
    // Default action
}

```

💡 Every `if` runs one by one, top to bottom.

---

### 2️⃣ **Comparison Operators (Used in Conditions)**

| Operator | Meaning               | Example  |
| -------- | --------------------- | -------- |
| `==`     | Equal                 | `x == y` |
| `!=`     | Not Equal             | `x != y` |
| `<`      | Less Than             | `x < y`  |
| `<=`     | Less Than or Equal    | `x <= y` |
| `>`      | Greater Than          | `x > y`  |
| `>=`     | Greater Than or Equal | `x >= y` |

---

### 3️⃣ **Logical Operators (Combine Multiple Conditions)**

| Operator | Name | Example            | Meaning                               |
| -------- | ---- | ------------------ | ------------------------------------- |
| `&&`     | AND  | `a > 0 && b < 5`   | Both must be true                     |
| `\|\|`   | OR   | `a > 0 \|\| b < 5` | One of them must true                 |
| `!`      | NOT  | `!visited[i]`      | Opposite of condition (false ➡️ true) |

---

### 4️⃣ **Short if (Ternary Operator)**

```cpp
int max = (a > b) ? a : b;
```

🧠 Equivalent to:

```cpp
if (a > b) max = a;
else max = b;
```

Used in one-liners and inline logic. Great for **readable max/min logic.**

---

### 5️⃣ **Nesting Conditions**

```cpp
if (x > 0) {
    if (y > 0) {
        cout << "nested";
    }
}
```

🧱 Like building condition pyramids! Be careful—too deep = spaghetti 🍝

---

### 6️⃣ **Switch Case (Not Common in CP, but Useful)**

```cpp
switch (value) {
    case 1: cout << "One"; break;
    case 2: cout << "Two"; break;
    default: cout << "Other";
}
```

📛 Avoid in CP unless you're handling small fixed value cases.

---

## 🎯 CP Tips & Tricks for Conditions

---

### 🔥 1. **Avoid Redundant Conditions**

```cpp
if (x == true) // ❌
if (x)         // ✅ Better
```

Or:

```cpp
if (x == false) // ❌
if (!x)         // ✅
```

Clean code is fast code 🧼💨

---

### 🔥 2. **Short-Circuit Evaluation**

```cpp
if (x != 0 && y / x > 5) {...}
```

✅ C++ stops checking once it knows the result. So this prevents division by zero

---

### 🔥 3. **Avoid `else` when `if` already returns**

```cpp
if (x == 0) return;
else doSomething(); // ❌ useless
```

✅ Just do:

```cpp
if (x == 0) return;
doSomething(); // Cleaner
```

---

### 🔥 4. **Use Binary Conditions in Greedy/Math Problems**

For example:

```cpp
if (n % 2 == 0) {
    // Even case
} else {
    // Odd case
}
```

📌 CP problems often split cases into binary decisions. Structure code accordingly.

---

### 🔥 5. **Inline `min()` and `max()`**

```cpp
min(a, b); // returns minimum
max(x, y); // returns maximum
```

Use them instead of long if-else for choosing best.

---

### 🔥 6. **Don't Be Scared of Multiple Conditions**

```cpp
if ((a % 2 == 0 && b % 2 == 0) || (a == b)) {
    // Legit logic. Just write cleanly.
}
```

✅ Use parentheses to group logic and avoid mistakes.

---

### 🔥 7. **Avoid Floating Point in Conditions**

```cpp
if (a / b == 0.3333) // ❌ BAD
```

---

### 🔥 8. **Write Conditions Like English Sentences**

Instead of:

```cpp
if (!(x > 0 && y > 0)) // ❌ confusing
```

Do:

```cpp
if (x <= 0 || y <= 0) // ✅ More readable
```
