# [⬅️ Back](./chapter_08.md) | [📖 ReadMe](./../../README.md)

## 🗺️ Map

### **Basic**

👉 Each key is **unique**, and the map automatically **sorts** the keys in **ascending order** (by default, using `<`).

**Declare :**

```cpp
// declare
map<keyType,valueType> mp;

// add value
mp[key] = value;

// access
cout << mp[key] << endl;

// if access not exist key, it by default give 0 for int type value
cout << mp[notExistKey] <<endl;
```

**Example :**

```cpp
map<string, int> score;
score["Rezaki"] = 100;
score["Owl"] = 999;
cout << score["Rezaki"] << endl; // 100
cout<<score["Sirius"] << endl; // 0
```

Another Example:

```cpp
map<int, string> mp;
mp[1] = "Rezaki";
mp[3] = "Owls";
mp[2] = "Void";
```

🌟 Automatically sorted by key → 1, 2, 3

---

## 🧠 **Important Operations**

| Operation         | Code Example                                     | Complexity | Description                                 |
| ----------------- | ------------------------------------------------ | ---------- | ------------------------------------------- |
| Insert element    | `mp.insert({key, value});` or `mp[key] = value;` | O(log n)   | Adds key–value pair                         |
| Access element    | `mp[key]`                                        | O(log n)   | Finds or creates entry                      |
| Erase by key      | `mp.erase(key);`                                 | O(log n)   | Removes a key                               |
| Erase by iterator | `mp.erase(it);`                                  | O(1)       | Removes using iterator                      |
| Find              | `auto it = mp.find(key);`                        | O(log n)   | Returns iterator or `mp.end()` if not found |
| Size              | `mp.size();`                                     | O(1)       | Count of pairs                              |
| Clear             | `mp.clear();`                                    | O(n)       | Remove all                                  |
| Empty             | `mp.empty();`                                    | O(1)       | Check if empty                              |
| Count             | `mp.count(key);`                                 | O(log n)   | 1 if exists, 0 otherwise                    |

---

## 🧭 **Traversal**

```cpp
for (auto it = mp.begin(); it != mp.end(); ++it)
    cout << it->first << " " << it->second << "\n";

```

```cpp
for (auto [k, v] : mp)
    cout << k << " => " << v << "\n";
```

## 🎯 Perfect for frequency counting, sorting automatically by key.

## 🚀 **Important Notes for CP**

### 1️⃣ Map is **ordered**

- Uses **Red-Black Tree** internally.
- Keeps keys sorted automatically.
- Useful when you need both **searching + sorting**.

### 2️⃣ For **faster** operations, use:

- `unordered_map` (uses **hash table**)
  Average: O(1), Worst: O(n)

  ```cpp
  unordered_map<int, string> mp;
  // other thing are similar with map
  ```

  ⚠️ But **keys are not sorted**!

### 3️⃣ Map auto-inserts zero values when accessed:

```cpp
mp["x"];  // creates key "x" with default value 0 if "x" not exist in mp

```

To avoid that, use `find()` before using `[]`.

---

## 🧮 **When to Use Map in CP**

✅ Counting frequencies (like counting numbers, words, characters).

✅ Storing key–value relationships (like indexes, parent-child mappings).

✅ Problems needing **sorted** keys automatically.

✅ When array index can’t be used (like big keys or negative numbers).

---

## ⚔️ **Common CP Mistakes**

🚫 Using map when you only need array (O(1) vs O(log n))

🚫 Forgetting that `[]` inserts keys (can bloat your map)

🚫 Comparing performance of `map` vs `unordered_map` — they behave differently!

---

## 🌈 **Quick Comparison**

| Feature                            | `map`           | `unordered_map` |
| ---------------------------------- | --------------- | --------------- |
| Order                              | Sorted (by key) | Unordered       |
| Internal structure                 | Red-Black Tree  | Hash Table      |
| Search                             | O(log n)        | Avg O(1)        |
| Worst case                         | O(log n)        | O(n)            |
| Allow duplicate keys?              | ❌              | ❌              |
| Supports lower_bound / upper_bound | ✅              | ❌              |
