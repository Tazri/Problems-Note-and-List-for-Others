# [⬅️ Back](./chapter_09.md) | [📖 ReadMe](./../../README.md)

# 🍰 Divisibility & Remainders – CP Tricks & Formulas

---

## 📝 **Divisibility Rules (Quick Reference)**

| Divisor | Rule & Explanation                                                                                                                                                                                                       |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **2**   | A number is divisible by 2 if its **last digit** is even (0, 2, 4, 6, 8). <br>**Example:** 124 → last digit 4 → divisible by 2 ✅                                                                                        |
| **3**   | A number is divisible by 3 if the **sum of all its digits** is divisible by 3. <br>**Example:** 123 → 1+2+3=6 → 6 % 3 = 0 ✅                                                                                             |
| **4**   | A number is divisible by 4 if its **last two digits** form a number divisible by 4. <br>**Example:** 312 → last two digits 12 → 12 % 4 = 0 ✅                                                                            |
| **5**   | A number is divisible by 5 if its **last digit** is 0 or 5. <br>**Example:** 135 → last digit 5 → divisible ✅                                                                                                           |
| **6**   | A number is divisible by 6 if it is divisible by **both 2 and 3**. <br>**Example:** 114 → divisible by 2 (last digit 4) and sum of digits 1+1+4=6 → divisible by 3 → divisible by 6 ✅                                   |
| **7**   | Optional for CP (rare): **Double the last digit and subtract it from the rest**; if result divisible by 7, original number is divisible. <br>**Example:** 203 → 20 - 2\*3=20-6=14 → 14 divisible by 7 ✅                 |
| **8**   | A number is divisible by 8 if its **last three digits** form a number divisible by 8. <br>**Example:** 1,024 → last three digits 024 → 24 % 8 = 0 ✅                                                                     |
| **9**   | A number is divisible by 9 if the **sum of digits** is divisible by 9. <br>**Example:** 729 → 7+2+9=18 → 18 % 9 = 0 ✅                                                                                                   |
| **10**  | A number is divisible by 10 if its **last digit is 0**. <br>**Example:** 230 → last digit 0 ✅                                                                                                                           |
| **11**  | A number is divisible by 11 if the **difference between the sum of digits in odd positions and sum of digits in even positions** is divisible by 11. <br>**Example:** 2728 → (2+2) - (7+8)=4-15=-11 → divisible by 11 ✅ |
| **12**  | A number is divisible by 12 if it is divisible by **both 3 and 4**. <br>**Example:** 144 → divisible by 3 (1+4+4=9) and divisible by 4 (last two digits 44) ✅                                                           |

### 🔹 Tips for CP

1. Most of the time, you only need **2, 3, 5, 7, 10**.
2. For large numbers (like strings), you can compute sum of digits modulo 3 or 9 for divisibility.
3. Divisibility by 11 is common in some string/number problems, always check **alternate sum method**.

---

## ⌛ **Remainder (Modulo) Tricks**

### a) Basic property

```
(a + b) % m = ((a % m) + (b % m)) % m
(a - b) % m = ((a % m) - (b % m) + m) % m
(a * b) % m = ((a % m) * (b % m)) % m
```

### b) Large powers

```
(a^b) % m = ((a % m)^b) % m
```

### c) Negative numbers modulo

```
(-x) % m = (m - (x % m)) % m
```

### d) Division trick (only if m is prime)

- For `(a / b) % m`, multiply by modular inverse:

```
(a / b) % m = (a * modInverse(b, m)) % m

```

- Only works if gcd(b,m) = 1 (or m prime).
