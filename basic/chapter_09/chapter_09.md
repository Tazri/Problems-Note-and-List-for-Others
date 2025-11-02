# [⬅️ Back](./../../README.md)

## 🧩 **Chapter 09: Functions, Math & Observation**

---

### 🧱 Part 1: ⚙️ Functions

### ✨ Structure of a Function in C++

```cpp
return_type function_name(parameter1_type parameter1, parameter2_type parameter2, ...) {
    // function body
    // logic or operations
    return value; // optional if return_type is void
}

```

**Example:**

```cpp
int add(int a, int b) {   // function definition
    return a + b;
}

int main() {
    int x = 5, y = 7;
    cout << add(x, y);    // function call
    return 0;
}

```

---

### 💡 Function Components

| Part             | Description                         | Example                         |
| ---------------- | ----------------------------------- | ------------------------------- |
| Return Type      | What data type the function returns | `int`, `double`, `bool`, `void` |
| Function Name    | Name of the function                | `add`, `maxValue`               |
| Parameters       | Inputs to the function              | `(int a, int b)`                |
| Return Statement | Gives result back                   | `return a + b;`                 |

---

### 🧩 Function Types:

1. **No parameter, no return:**

   ```cpp
   void sayHi() { cout << "Hello Owl!"; }
   ```

2. **Parameter, no return:**

   ```cpp
   void printSum(int a, int b) { cout << a + b; }
   ```

3. **Parameter and return:**

   ```cpp
   int multiply(int a, int b) { return a * b; }
   ```

4. **No parameter but return:**

   ```cpp
   int giveMe42() { return 42; }
   ```

---

### ⚡ Common Built-in Functions in C++ for CP

### 📊 **Math functions (from `<cmath>`)**

| Function                                                                                    | Description             | Example           |
| ------------------------------------------------------------------------------------------- | ----------------------- | ----------------- |
| `abs(x)`                                                                                    | Absolute value          | `abs(-7)` → 7     |
| `sqrt(x)`                                                                                   | Square root             | `sqrt(9)` → 3     |
| `pow(a,b)`                                                                                  | Power                   | `pow(2,3)` → 8    |
| `ceil(x)` (Suggest not use it for `a / b`, it gives wrong for big numbers). Use `(a+b-1)/b` | Round up                | `ceil(4.2)` → 5   |
| `floor(x)` (Suggest not use it for `a/b`, it gives wrong for big numbers.)                  | Round down              | `floor(4.8)` → 4  |
| `round(x)`                                                                                  | Nearest integer         | `round(3.6)` → 4  |
| `max(a,b)` / `min(a,b)`                                                                     | Max or min              | `max(3,5)` → 5    |
| `hypot(a,b)`                                                                                | √(a² + b²)              | `hypot(3,4)` → 5  |
| `__gcd(a,b)`                                                                                | Greatest common divisor | `__gcd(8,12)` → 4 |

---

### 🔠 **Character-related (from `<cctype>`)**

| Function      | Description          | Example       |
| ------------- | -------------------- | ------------- |
| `isalpha(ch)` | Is alphabet          | `'a'` → true  |
| `isdigit(ch)` | Is digit             | `'5'` → true  |
| `islower(ch)` | Is lowercase         | `'a'` → true  |
| `isupper(ch)` | Is uppercase         | `'A'` → true  |
| `tolower(ch)` | Convert to lowercase | `'A'` → `'a'` |
| `toupper(ch)` | Convert to uppercase | `'a'` → `'A'` |

---

### 🧮 **Useful <algorithm> functions**

| Function                               | Description                       |
| -------------------------------------- | --------------------------------- |
| `sort(v.begin(), v.end())`             | Sort ascending                    |
| `reverse(v.begin(), v.end())`          | Reverse elements                  |
| `count(v.begin(), v.end(), x)`         | Count occurrences                 |
| `accumulate(v.begin(), v.end(), 0)`    | Sum of elements                   |
| `unique(v.begin(), v.end())`           | Remove duplicates (adjacent only) |
| `next_permutation(v.begin(), v.end())` | Next lexicographical order        |

---

## 🧮 Part 2: Basic Math in Competitive Programming

## - [🧮 Arithematic Progression](./arithmetic_series.md)

## - [🍰 Divisibility & Remainder](./divisiblity_remaider.md)

## - [📉 Coordinate, Number Line & Manhattan Distance – CP Basics](./Coordinate_Numberline.md)

## - [⚖️ Parity in Competitive Programming](./parity.md)

## - [📘 GCD in Competitive Programming](./gcd.md)
