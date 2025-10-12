# [⬅️ Back](./../../README.md)

# 📖 Implemantation & Bruteforce

## Before

- [Map](./map.md)
- [Set](./set.md)
- [Others Tricks](./other_trick.md)

# Bruteforces

## ⚙️ The Idea

> Brute force = Generate all possibilities + Check each one

**🧠 Logic steps:**

1. Generate all combinations / permutations / subsets / possibilities.
1. For each, check if it satisfies the condition.
1. Keep track of the best/valid result.

“If you can’t think cleverly... just think completely!”

## 🧮 **When to Use Brute Force**

✅ Small input size (usually n ≤ 10⁵ only if O(1) per step, else ≤ 20–25).

✅ You can **enumerate all cases** without time limit explosion.

✅ When you are **not sure of optimization yet** — brute force first, then optimize!

---

## ⏳ **Time Complexity Intuition**

| n   | n! (permutations) | 2ⁿ (subsets)  | n²  | n³    |
| --- | ----------------- | ------------- | --- | ----- |
| 10  | 3,628,800         | 1024          | 100 | 1000  |
| 15  | 1.3e12 ❌         | 32768 ✅      | 225 | 3375  |
| 20  | 🚫 DEAD           | 1,048,576 ✅  | 400 | 8000  |
| 25  | 💀💀💀            | 33,554,432 ⚠️ | 625 | 15625 |

So usually:

- Up to **n = 10–12** for permutations is fine
- Up to **n = 20–25** for subsets is fine
- Up to **n = 1e3–1e5** for O(n²) or O(n log n)

⚠️ Always check constraints before brute-forcing

---

# 🧩 Implementation

“Implementation problems” are those where the **logic is not very hard**, but the **real challenge is writing correct code** that follows all the details of the problem statement.

👉 In short:

> “You know what to do — but can you code it without making a single mistake?” 😏

These problems test your **carefulness**, **simulation ability**, and **attention to edge cases**.

---

## ⚙️ Types of Implementation Problems

### 1️⃣ **Simulation**

You’re asked to simulate a real-world or described process.

Examples:

- Moving a robot based on commands (U, D, L, R)
- Simulating a game (like tic-tac-toe or snakes and ladders)
- Processing a sequence of operations on an array or string

🧠 _Tip:_ Always keep track of “state” carefully — positions, direction, etc.

---

### 2️⃣ **String Implementation**

Work with strings carefully — often with tricky conditions.

Examples:

- Replacing substrings
- Checking palindromes
- Reordering characters

🧠 _Tip:_ Learn to use:

```cpp
string, substr(), find(), erase(), push_back(), stoi(), to_string()
```

---

### 3️⃣ **Math-based Implementation**

Sometimes you already know the formula or algorithm, but need to code it precisely.

Examples:

- Finding factorial without overflow
- Converting number systems
- Handling big numbers manually

---

### 4️⃣ **Array / Grid Implementation**

You’re asked to implement logic on 2D or 1D arrays.

Examples:

- Matrix rotation, transposition
- Counting adjacent cells
- Tracking elements after swaps

---

### 5️⃣ **Ad-hoc Problems**

No fixed category. You just have to carefully implement some unique logic.

Example:

> Given a list of names and scores, output the second-highest unique score.

---

## 🧠 Key Skills You Must Master

### 🧩 1. Reading Carefully

Implementation problems _love_ to hide small conditions —

like “if there are multiple answers, print the smallest one.”

💀 One missed line = Wrong Answer.

### ⚙️ 2. Breaking Down Steps

Don’t code the whole thing at once.
Instead:

1. Write down the logic step-by-step.
2. Implement one small part.
3. Print intermediate results (for debugging).

### 🔢 3. Edge Cases

Always think:

- What if array size = 1?
- What if all numbers are same?
- What if negative / zero values appear?

### 🧾 4. Clean Input Handling

In CP, input can be tricky. Learn:

```cpp
getline(cin, s);
cin >> n >> a >> b;
```

and mixing them carefully.

### 🧮 5. Use STL smartly

Know when to use:

- `vector`, `set`, `map`
- `sort()`, `unique()`
- `pair`,
- `auto`

### 💬 6. Debugging Skills

Use:

```cpp
cerr << "debug: " << var << endl;
```

Or print intermediate states to find bugs faster.

---

## 🦉 Common Mistakes by Beginners

❌ Forgetting to reset arrays or variables

❌ Confusing `n` vs `n-1` loops

❌ Mixing `int` and `long long`

❌ Ignoring special cases

❌ Copy-paste errors in simulation

---

## 🧭 Strategy to Solve Implementation Problems

1️⃣ **Read the problem twice** (first for story, second for details)

2️⃣ **Write steps in plain English**

3️⃣ **Simulate manually on sample input**

4️⃣ **Implement step by step**

5️⃣ **Test on hidden cases**

6️⃣ **Refactor to cleaner code**
