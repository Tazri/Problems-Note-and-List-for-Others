# [⬅️ Back](./chapter_09.md) | [📖 ReadMe](./../../README.md)

# 🧮 Arithmetic Progression (AP)

## 📝 Definition

Arithmetic Series is a series where difference between two adjacent terms is always equals.

Example:

    2, 4, 6, 8, 10, ....
    Common difference is 2

    3, 10, 17, 24, .....
    Common difference is 7

**General Structure of AP :**

```sql
a, a + d, a + 2d, a + 3d, ...

a = first term
d = common difference
n = number of terms
```

### **nth Term Formula**

```sql
The nth term of an AP is:
a_n = a + (n - 1) \* d

here :
a_n = nth term
a = first term
d = common difference
n = term number
```

Example:

    AP: 3, 5, 7, 9, …

```
a = 3, d = 2
4th term: a_4 = 3 + (4-1)\*2 = 9 ✅
```

### **Sum of nth terms**

The sum of first n terms of an AP is:

Formula 1:

```ini
S_n = n/2 * (2a + (n - 1) * d)

here :
S_n = sum of nth terms
a = first term
n = number of terms
d = common difference
```

Formula 2 (alternate, using first and last term):

```ini
S_n = n/2 \* (a + l)

here :
l = last term = a_n
```

Example:

    AP: 3, 5, 7, 9, …, n=4

```sql
a = first term = 3
d = common difference = 2
l = last term


S4 = 4/2 * (2*3 + (4-1)*2) = 2 * (6 + 6) = 24

Or S4 = 4/2 * (3 + 9) = 2 * 12 = 24
```

## 📖 Special AP

### 🟠 Find the N'th Term of series

```sql
N'th term of even series
{2, 4, 6, 8, 10, 12, ....., n}
N'th term is = 2*n

N'th term of odd series
{1, 3, 5, 7, 9, ........, n}
N'th term is = 2*(n-1)
```

### 🟤 Sum of First N Numbers

```sql
Sum of N regular numbers :
1 + 2 + 3 + ... + n = n * (n + 1) / 2

Sum of squares :
1² + 2² + ... + n² = n*(n+1)*(2n+1)/6

Sum of cubes:
1³ + 2³ + ... + n³ = [n*(n+1)/2]²

Sum of Evens :
2+4+6+...+2n=n(n+1)

Sum of Odds :
1+3+5+...+(2n−1)=n²
```
