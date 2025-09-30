### [⬅️ Back To README FILE](./../../README.md)

# Chapter 01 : Data Types, Variables & Operators

### 0️⃣ **Output and Basic Structure**

```cpp
#include <bits/stdc++.h>

using namespace std;

int main(){
	cout << "Hello, World!" << endl;
	return 0;
}
```

⚡ Tip: Use `ios::sync_with_stdio(false); cin.tie(0);` for **fast I/O** in CP!

---

### 1️⃣ **Basic Data Types**

- `int` – Integers (e.g., `1, -3, 42`)
- `long long` – Bigger integers (usually 64-bit, e.g., `1e18`)
- `float` – Decimal numbers (single precision)
- `double` – More precise decimals (use in CP for average, percentages)
- `char` – Single characters (like `'a'`, `'Z'`)
- `bool` – Boolean values (`true` or `false`)

👉 Use `long long` in CP by default to avoid overflow in large calculations.

---

### 2️⃣ **Data Type Limits**

```cpp
#include <climits>
#include <cfloat>
cout << INT_MAX; // 2147483647
cout << LLONG_MAX; // 9223372036854775807

```

⚠️ _Overflow/underflow bugs are real monsters in contests!_

---

### 3️⃣ **Variable Declaration & Initialization**

```cpp
int x;         // Declaration
int y = 5;     // Declaration + Initialization
long long z = 1e18;
```

👉 Always initialize your variables. Uninitialized variables = unpredictable bugs 🐞💣

---

### 4️⃣ **Constants**

```cpp
const int MOD = 1e9 + 7;
```

🛡️ Used for values that never change (e.g., modulo bases in CP)

### 5️⃣ **Type Modifiers**

- `unsigned int` → Only positive numbers (bigger max value)
- `short`, `long`, `long long`
- `signed` vs `unsigned`

💡 Use `unsigned` _carefully_ in loops, as it may cause infinite loops if you're not careful with negative conditions.

---

### 6️⃣ **Typecasting**

```cpp
int x = 5;
double y = (double)x / 2; // 2.5
```

🎯 Use it to get precise divisions, especially when computing averages!

---

### 7️⃣ **Operators**

### 👉 Arithmetic Operators:

```cpp
+ - * / %
```

- `%` is **modulus** – only works with integers.
- `/` does **integer division** for `int`s (`5/2 = 2`), but **floating division** for `double`s.

### 👉 Assignment Operators:

```cpp
=, +=, -=, *=, /=, %=
```

### 👉 Comparison Operators:

```cpp
==, !=, <, >, <=, >=
```

Used in `if`, `while`, etc.

### 👉 Logical Operators:

```cpp
&& (AND), || (OR), ! (NOT)
```

Used heavily in conditional statements.

---

### 8️⃣ **Input / Output variable**

```cpp
int a, b;
cin >> a >> b;
cout << a + b << endl;
```

⚡ Tip: Use `ios::sync_with_stdio(false); cin.tie(0);` for **fast I/O** in CP!

---

### 🔟 **Best Practices in CP**

- Use `long long` when you expect values > `10^9`
- Always initialize variables
- Avoid float unless absolutely needed (use `double`)
- Use `const` for global constants like MOD or INF
- Prefer `scanf/printf` or fast I/O for large inputs

🥇 **Bonus: Data Type Ranges (Common in CP)**

| Type        | Size | Range                               |
| ----------- | ---- | ----------------------------------- |
| `int`       | 4B   | −2,147,483,648 to 2,147,483,647     |
| `long long` | 8B   | −9,223,372,036,854,775,808 to +9e18 |
| `double`    | 8B   | ±1.7e±308                           |
| `char`      | 1B   | -128 to 127 or 0 to 255 (ASCII)     |
| `bool`      | 1B   | 0 or 1                              |

## 🧠 Tips & Tricks: Data Types, Variables & Operators for Competitive Programming (C++)

---

### 🔹 1. **Ceil Division without `ceil()` or condition**

**Problem:** You want to compute ⌈a / b⌉

**Trick:**

```cpp
int result = (a + b - 1) / b;
```

💡 Works for positive integers. No need for slow `ceil()` or messy `if`s!

🧪 Example:

```cpp
int a = 7, b = 3;
cout << (a + b - 1) / b; // 3
```

---

### 🔹 2. **Fast Input / Output (Don’t TLE in Big Input Problems)**

```cpp
ios::sync_with_stdio(false);
cin.tie(0);
```

Place this **at the start of `main()`** to _turbo boost_ I/O 🚀

---

### 🔹 3. **Avoid Integer Overflow with `long long`**

Use:

```cpp
long long a = 1e9, b = 1e9;
long long prod = a * b; // Use LL or you'll overflow
```

🔪 NEVER do:

```cpp
int a = 1e9;
long long b = a * a; // ❌ WRONG! a*a happens as int first!
```

✅ Do:

```cpp
long long b = 1LL * a * a;
```

---

### 🔹 4. **Use `1LL` to Force Long Long Arithmetic**

```cpp
long long x = 1LL * a * b % MOD;
```

📌 Essential in modulo arithmetic to avoid **intermediate overflow**

---

### 🔹 5. **Bit Tricks for Power of 2**

```cpp
bool isPowerOf2 = (n & (n - 1)) == 0;
```

✅ Works if `n > 0`. Fastest way to check if `n` is power of 2.

---

### 🔹 6. **Swap without Temp**

```cpp
a ^= b;
b ^= a;
a ^= b;
```

modern compilers optimize `swap(a,b)` well. so use swap function is better.

---

### 🔹 7. **Use `__builtin_popcount()` to Count Set Bits**

```cpp
int x = 7;
cout << __builtin_popcount(x); // 3 → since 7 = 111 in binary
```

⚠️ Works with `int` → For `long long`, use `__builtin_popcountll(x)`

📌 Useful for Hamming distance, subset problems, etc.

---

### 🔹 8. **Modulo Always Non-Negative**

```cpp
int mod(int a, int m) {
    return ((a % m) + m) % m;
}
```

✅ Ensures result is always non-negative. Important in hash problems, cycles, etc.

---

### 🔹 9. **Using `bool` for Flags is Better Than `int`**

```cpp
bool visited[MAX];
```

✅ Saves memory, more readable, helps clarity in graph/DFS/BFS/DP.

---

### 🔹 🔟 Use `#define` for Constants & Shortcuts (but don’t abuse)

```cpp
#define MOD 1000000007
#define INF 1e18
#define pb push_back
```

But don’t go overboard like:

```cpp
#define int long long // ❌ BAD IDEA, creates bugs in corner cases
```

---

### 🔹 11. **Declare Global Arrays Carefully**

📛 `int arr[1e6];` inside `main()` = stack overflow.

✅ Use:

```cpp
int arr[(int)1e6 + 5]; // Global or static allocation
```

---

### 🔹 12. **Avoid Mixing `scanf/printf` with `cin/cout`**

It can cause weird delays. Stick to one style.
