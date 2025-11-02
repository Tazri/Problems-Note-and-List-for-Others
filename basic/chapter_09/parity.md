# [⬅️ Back](./chapter_09.md) | [📖 ReadMe](./../../README.md)

# ⚖️ Parity in Competitive Programming

---

## 🎯 1. What is Parity?

**Parity** refers to whether a number is **even** or **odd**.

Formally:

- A number **n** is **even** if `n % 2 == 0`
- A number **n** is **odd** if `n % 2 == 1`

We say:

| Number     | Parity |
| ---------- | ------ |
| 2, 4, 6, 8 | Even   |
| 1, 3, 5, 7 | Odd    |

This simple concept shows up **EVERYWHERE** in CP — from bit manipulation to graph coloring, number theory, and dynamic programming.

---

## 💡 2. Fundamental Properties

### 🧮 a) Addition & Subtraction

| Operation   | Rule | Example    |
| ----------- | ---- | ---------- |
| even + even | even | 2 + 4 = 6  |
| odd + odd   | even | 3 + 5 = 8  |
| even + odd  | odd  | 4 + 3 = 7  |
| odd - odd   | even | 9 - 3 = 6  |
| even - even | even | 10 - 4 = 6 |
| even - odd  | odd  | 8 - 5 = 3  |

👉 **Parity of sum/difference depends only on parity of operands**, not their values.

---

### ✖️ b) Multiplication

| Operation       | Rule | Example  |
| --------------- | ---- | -------- |
| even × anything | even | 2×7 = 14 |
| odd × odd       | odd  | 3×5 = 15 |

👉 Multiplying by an even number always yields an even result.

---

### 🧠 c) Power Rules

- odd ^ anything = odd
- even ^ anything (>0) = even
- (anything)^0 = 1 (odd)

---

### ⚡ d) XOR & Parity (Bit Magic)

In binary:

- `1` represents odd parity
- `0` represents even parity

The **XOR (⊕)** of bits acts like addition modulo 2:

- 0 ⊕ 0 = 0 (even)
- 1 ⊕ 1 = 0 (even)
- 1 ⊕ 0 = 1 (odd)

👉 Hence, **XOR is addition mod 2**.

That’s why parity often connects with XOR logic in bit problems!

---

## 🔍 3. Parity in Common CP Contexts

---

### ⚙️ a) Number Line / Distances

The **distance** between two integers `a` and `b` is `|a - b|`.

- If both `a` and `b` have **same parity**, distance is **even**.
- If parities differ, distance is **odd**.

**Example:**

```sql
a = 3, b = 7 → same parity (odd, odd)
|a - b| = 4 → even
```

**Application:**

Problems like _“Can we reach from x to y in k moves?”_ often depend on **distance parity**.

> 🚀 Trick: If the move changes position by 1 each time, then parity flips each move.
>
> So, you can only reach positions with the same parity after even moves!

---

### 🧩 b) Arrays and Sum Parity

If an array’s **sum** is even/odd, you can reason about element parities:

- Even sum ⇒ either all even, or even number of odd elements
- Odd sum ⇒ odd number of odd elements

**Example Problem:**

> Can we make the array sum even by removing one element?

✅ Yes, if there’s at least one odd and one even — removing an odd flips the parity.

---

### 🕹️ c) Chessboard / Grid Parity

On a chessboard, cells can be **colored** by `(x + y) % 2`:

- Even ⇒ one color (say white)
- Odd ⇒ another (say black)

**Fun property:**

The parity of `(x + y)` alternates with every move that changes one coordinate by 1.

That’s how knight/bishop movement logic in CP is often based on parity:

- Bishop stays on same color → `(x + y)` parity stays same
- Knight flips parity → because it moves (2,1)
- Kings change parity in every move.

---

## 🧰 4. Quick Tricks and Patterns

| Pattern                                | Meaning |
| -------------------------------------- | ------- |
| Same parity numbers → even difference  |         |
| Different parity → odd difference      |         |
| Even count of odds → even sum          |         |
| Odd count of odds → odd sum            |         |
| XOR of all parities = parity of sum    |         |
| Movement that adds 1 flips parity      |         |
| Movement that adds 2 keeps parity same |         |

---

## 🧩 5. Common Mistakes

❌ Forgetting that subtraction keeps same parity as addition.

❌ Assuming parity is about value, not index (in many problems, index parity matters too!).

❌ Ignoring that parity flips every time you move one step.

❌ Confusing XOR parity with number parity.
