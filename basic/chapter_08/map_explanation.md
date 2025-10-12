# [⬅️ Back](./chapter_08.md) | [📖 ReadMe](./../../README.md)

# 🗺️ Maps

### 1️⃣ **What is a Map?**

Think of a **map** as a **dictionary in real life**:

- **Key** → the word
- **Value** → the meaning

Example:

| Word     | Meaning              |
| -------- | -------------------- |
| "apple"  | 5 (number of apples) |
| "banana" | 3                    |
| "orange" | 10                   |

In C++:

```cpp
map<string, int> fruits;
fruits["apple"] = 5;
fruits["banana"] = 3;
fruits["orange"] = 10;
```

> The key must be unique (you cannot have two “apple” keys).

---

### 2️⃣ **Map automatically sorts keys**

Maps **always keep keys in order**:

```cpp
map<int, string> mp;
mp[3] = "C";
mp[1] = "A";
mp[2] = "B";

for (auto [k,v] : mp)
    cout << k << " => " << v << "\n";
```

**Output**:

```
1 => A
2 => B
3 => C
```

📝 Even if you inserted in weird order, the map **automatically sorts by key**.

---

### 3️⃣ **Accessing a value**

```cpp
cout << fruits["apple"] << endl; // 5
```

⚠️ **Important**: If key doesn’t exist:

```cpp
cout << fruits["mango"] << endl; // 0
```

It **automatically creates the key with value 0**.

> If you don’t want that, use find() first:

```cpp
if(fruits.find("mango") != fruits.end())
    cout << fruits["mango"];
else
    cout << "Key not found!";
```

---

### 4️⃣ **Insert / Delete / Find**

| Action      | Example                                      |
| ----------- | -------------------------------------------- |
| Insert      | `mp["Rezaki"] = 100;`                        |
| Delete key  | `mp.erase("Rezaki");`                        |
| Find key    | `auto it = mp.find("Rezaki");`               |
| Delete iter | `auto it = mp.find("Rezaki"); mp.erase(it);` |
| Check key   | `mp.count("Rezaki")` → 1 if exists, 0 if not |

> Complexity: Map uses a Red-Black Tree, so search/insert/delete is O(log n), not O(1).

---

### 5️⃣ **When to Use Map**

Maps are amazing when:

- You want **sorted keys** automatically.
- You want **frequencies** (counting numbers, letters, words).
- Your keys are **not simple array indices** (like -100, 50, 999999).

**Example: Counting letters in a word**

```cpp
string s = "rezaki";
map<char,int> freq;

for(char c : s) freq[c]++;

for(auto [k,v] : freq)
    cout << k << " appears " << v << " times\n";
```

**Output:**

```
a appears 1 times
e appears 1 times
i appears 1 times
k appears 1 times
r appears 1 times
z appears 1 times
```

Notice: Automatically **sorted letters**!
