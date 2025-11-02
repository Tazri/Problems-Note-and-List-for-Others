# [⬅️ Back](./chapter_09.md) | [📖 ReadMe](./../../README.md)

# 📘 GCD in Competitive Programming

---

## ⚡ 1. Definition

**GCD (Greatest Common Divisor)** of two integers `a` and `b` is the **largest integer** that divides both of them.

**Example:**

- gcd(12, 18) = 6
- gcd(7, 13) = 1
- gcd(8, 0) = 8

---

## 🧠 2. Fundamental Properties

Let’s gather the most useful facts that you’ll use all the time in CP 👇

| Property                                 | Formula / Meaning                |
| ---------------------------------------- | -------------------------------- |
| 1️⃣ Commutative                           | gcd(a, b) = gcd(b, a)            |
| 2️⃣ Associative                           | gcd(a, b, c) = gcd(gcd(a, b), c) |
| 3️⃣ If b divides a                        | gcd(a, b) = b                    |
| 4️⃣ gcd(a, 0)                             | a                                |
| 5️⃣ gcd(a, b) = gcd(a−b, b)               | (Subtraction property)           |
| 6️⃣ gcd(k·a, k·b) = k·gcd(a, b)           | (Scaling property)               |
| 7️⃣ gcd(a, b) divides (a + b) and (a − b) | always true                      |

---

## 🧮 3. The Euclidean Algorithm

The **Euclidean Algorithm** is the fastest way to compute gcd.

```cpp
int gcd(int a, int b) {
    if (b == 0) return a;
    return gcd(b, a % b);
}

```

🌀 **Time complexity:** `O(log(min(a, b)))`

💡 It’s super efficient — even for numbers up to 10¹⁸.

**Example trace:**

```
gcd(48, 18)
→ gcd(18, 48 % 18 = 12)
→ gcd(12, 18 % 12 = 6)
→ gcd(6, 12 % 6 = 0)
→ gcd = 6 ✅

```

---

## 🧩 4. Relationship with LCM

They’re like yin and yang ☯️

```cpp
lcm(a,b)×gcd(a,b)=a×b
```

Hence:

```cpp
long long lcm = (a / gcd(a, b)) * b;
```

⚠️ Be careful with overflow — divide before multiply!

---

## ⚙️ 5. GCD in Arrays

To compute gcd of multiple numbers:

```cpp
int g = a[0];
for (int i = 1; i < n; i++)
    g = gcd(g, a[i]);

```

**Property:**

If all numbers share gcd `g`, then dividing all by `g` makes them **coprime**.

---

## 🧨 6. Coprime Numbers

Two numbers `a` and `b` are **coprime** (or **relatively prime**) if:

```cpp
gcd(a,b) = 1
```

Examples:

- (4, 9) → coprime ✅
- (6, 9) → not coprime ❌

#### Another important rules :

Any two **consecutive integers** are coprime:

```cpp
gcd(n,n+1) = 1
```

Example :

- (4,5) = 1
- (9,10) = 1

## 💣 7. Common Mistakes

❌ Using `a*b/gcd(a,b)` without dividing first → overflow!

❌ Forgetting that `gcd(0, 0)` is undefined (handle separately).

❌ Mixing up lcm & gcd in modular formulas.

❌ Assuming gcd(a, b) = gcd(a % b, b) works for negative numbers (use abs).
