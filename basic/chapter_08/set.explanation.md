# [⬅️ Back](./chapter_08.md) | [📖 ReadMe](./../../README.md)

## 🎒 What is a **set**?

A **set** is like a **box** where you can put things,

but it **never allows duplicates** and always keeps them **sorted** automatically.

Example 👇

You put: `5, 2, 3, 2, 5`

The set will only keep:

```
2, 3, 5
```

Because it **removes duplicates** and **sorts numbers**.

---

## ✏️ How to use it

```cpp
set<int> s;
s.insert(5);
s.insert(2);
s.insert(3);
s.insert(2); // ignored (already exists)
```

Now the set has:

```
2, 3, 5
```

---

## 👀 How to check if something is inside?

```cpp
if (s.count(3)) cout << "Found!";
else cout << "Not found!";
```

or

```cpp
if (s.find(3) != s.end()) cout << "Found!";
```

---

## ❌ How to remove something

```cpp
s.erase(3);
```

Now it has:

```
2, 5
```

---

## 🔁 How to go through all elements

```cpp
for (auto x : s)
    cout << x << " ";
```

Output:

```
2 5
```

Always sorted 🔼

---

## ⚙️ Some Useful Operations

| Operation    | Code Example                | Description               | Time     |
| ------------ | --------------------------- | ------------------------- | -------- |
| Add element  | `s.insert(x);`              | Adds if not already there | O(log n) |
| Remove       | `s.erase(x);`               | Removes if exists         | O(log n) |
| Check exists | `s.count(x)` or `s.find(x)` | Finds element             | O(log n) |
| Size         | `s.size();`                 | Number of items           | O(1)     |
| Empty        | `s.empty();`                | True if no items          | O(1)     |
| Clear        | `s.clear();`                | Remove all                | O(n)     |

---

## 🧩 When to use `set`

✅ When you want to **store unique items only**

✅ When you want items **automatically sorted**

✅ When you don’t need duplicates

Example:

```cpp
set<string> names;
names.insert("Rezaki");
names.insert("Owl");
names.insert("Rezaki"); // ignored

for (auto x : names)
    cout << x << " ";
```

Output:

```
Owl Rezaki
```

---

## ⚡ `unordered_set` (faster, not sorted)

```cpp
unordered_set<int> s;
```

- Doesn’t keep order
- Works faster (average O(1))
- Still no duplicates allowed

---

## 🧮 Example Use in CP (Competitive Programming)

✅ Store **unique numbers**

✅ Remove **duplicates** from a list

✅ Quickly check **if a number exists**

✅ Count **distinct elements**

Example:

```cpp
vector<int> a = {5, 3, 5, 2, 3};
set<int> s(a.begin(), a.end());
cout << s.size(); // 3
```

---
