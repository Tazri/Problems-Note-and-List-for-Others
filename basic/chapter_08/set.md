# [⬅️ Back](./chapter_08.md) | [📖 ReadMe](./../../README.md)

# 🎯 Set

### 🧩 **Basic**

A **set** in C++ is an **ordered container** that stores **unique elements** (no duplicates!) and keeps them **automatically sorted** (ascending by default).

```cpp
set<Type> name;
name.insert(value);
```

Example:

```cpp
set<int> s;
s.insert(3);
s.insert(1);
s.insert(2);
```

## 🧠 **Important Operations**

| Operation         | Code Example           | Complexity | Description                                            |
| ----------------- | ---------------------- | ---------- | ------------------------------------------------------ |
| Insert            | `s.insert(x);`         | O(log n)   | Adds `x` if not already present                        |
| Erase by value    | `s.erase(x);`          | O(log n)   | Removes `x`                                            |
| Erase by iterator | `s.erase(it);`         | O(1)       | Removes via iterator                                   |
| Find              | `auto it = s.find(x);` | O(log n)   | Returns iterator or `s.end()` if `x` is not exist in s |
| Size              | `s.size();`            | O(1)       | Returns count of elements                              |
| Empty             | `s.empty();`           | O(1)       | Checks if empty                                        |
| Clear             | `s.clear();`           | O(n)       | Removes all                                            |
| Count             | `s.count(x);`          | O(log n)   | 1 if present, 0 if not                                 |
| Lower bound       | `s.lower_bound(x);`    | O(log n)   | First element ≥ x                                      |
| Upper bound       | `s.upper_bound(x);`    | O(log n)   | First element > x                                      |
| Begin and End     | `s.begin()` `s.end()`  | O(1)       | Give begin pointer and end pointer of set              |

---

## 🧭 **Traversal**

```cpp
for (auto x : s)
    cout << x << " ";

```

Or:

```cpp
for (auto it = s.begin(); it != s.end(); ++it)
    cout << *it << " ";

```

## 🧮 **When to Use `set` in CP**

✅ Need **unique elements only**

✅ Need elements **sorted automatically**

✅ Need to **search**, **insert**, **erase** efficiently (O(log n))

✅ Need to find **next/previous element** with `lower_bound` or `upper_bound`

✅ Use it as a **simple version of map** when you only need keys, not key-value pairs.

---

## ⚙️ **Set Variants**

### 1️⃣ **`set`**

- Stores **unique** elements
- Ordered
- Internally a **balanced BST (Red-Black Tree)**

### 2️⃣ **`multiset`**

- Like set but allows **duplicate** elements
- Still sorted

```cpp
multiset<int> ms = {1,1,2,2,2,3};
ms.erase(ms.find(2));  // removes only one '2'
ms.erase(2); // remove all 2
```

### 3️⃣ **`unordered_set`**

- Uses **hash table** (like `unordered_map`)
- Not sorted, but much faster on average
  Average: O(1), Worst: O(n)

```cpp
unordered_set<int> us = {5, 3, 1, 2};
```

---

## ⚔️ **When Not to Use `set`**

🚫 When order doesn’t matter → use `unordered_set` (faster).

🚫 When duplicates matter → use `multiset`.

🚫 When you can just use `vector + sort + unique`.

🚫 When you need random access (set doesn’t support indexing!).

## 🦉 **Quick Comparison**

| Feature                          | `set`          | `multiset`     | `unordered_set` |
| -------------------------------- | -------------- | -------------- | --------------- |
| Duplicates                       | ❌             | ✅             | ❌              |
| Order                            | Sorted         | Sorted         | Unordered       |
| Structure                        | Red-Black Tree | Red-Black Tree | Hash Table      |
| Search                           | O(log n)       | O(log n)       | Avg O(1)        |
| Insert                           | O(log n)       | O(log n)       | Avg O(1)        |
| Allows lower_bound / upper_bound | ✅             | ✅             | ❌              |

---
