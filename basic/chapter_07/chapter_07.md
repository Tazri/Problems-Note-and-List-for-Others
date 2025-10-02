### [⬅️ Back To README FILE](./../../README.md)

# Chapter 07: 📚 Vectors

### 1️⃣ What is a `vector`?

**Syntax:**

```cpp
#include <bits/stdc++.h>
using namespace std;

vector<int> v; // empty vector of int
vector<int> v2(5); // size 5, all 0
vector<int> v3(5, 10); // size 5, all values = 10
vecotr<int> v4 = {1,2,3} // vector with size 3 and valuse 1, 2, 3
```

---

### 2️⃣ Common Operations

### 🔹 Input Elements

```cpp

vector<int> v(n); // n is here size

for(int i = 0;i < n;i++){
    cin >> v[i];
}

// using reference loop
for(int &vi:v){
    cin >> vi;
}
```

### 🔹 Add elements

```cpp

v.push_back(7);  // add 7 to end
v.emplace_back(7); // faster than push_back (directly constructs)
```

💡 **Tip:** Use `emplace_back()` in contests — it’s slightly faster.

---

### 🔹 Use of Assign

📖 Fill the vector with n copies of a value

```cpp
vector<int> v;
v.assign(5, 100);
// Now v = {100, 100, 100, 100, 100}
```

📖 Assign from another range (iterators)

```cpp
vector<int> v1 = {1, 2, 3, 4};
vector<int> v2;
v2.assign(v1.begin(), v1.end());
// Now v2 = {1, 2, 3, 4}
```

📖 Assign from initializer list (C++11+)

```cpp
vector<int> v;
v.assign({10, 20, 30, 40});
// Now v = {10, 20, 30, 40}
```

### 🔹 Remove elements

```cpp
v.pop_back(); // removes last element
```

💡 **Tip:** `pop_back()` does NOT return the removed value. Store it first if needed.

---

### 🔹 Access elements

```cpp
int x = v[0];     // no bound checking, it print garbage if out of index
int y = v.at(0);  // bound checking (slower) it throw error if out of index
```

💡 **Tip:** Use `[]` in contests — faster, but be sure index is valid.

---

### 🔹 Begin Pointer and End Pointer

```cpp
vector<int> v = {3,4,5}; // simple vector

vector<int>::iterator it = v.begin(); // it point first value of vector
auto it1 = v.begin(); // here auto mean vector<int>::iterator
vector<int>::iterator end_it = v.end(); // it point last value of vector
auto end_it1 = v.end(); // here auto mean vector<int>::iterator

cout << it << endl; // should throw error
cout << *it << endl; // print the value which is point by it
```

### 🔹 Iterator Math

```cpp
vector<int> v = {0,1,2,3,4,5};
auto it = v.begin();

it = it + 3; // it will point index 3
cout << *it << endl; // print 3

it = it - 1; // now it point index 2
cout << *it << endl; // print 2
```

### 🔹 Get size and check if empty

```cpp
int n = v.size();
bool empty = v.empty();
```

💡 **Tip:** `empty()` is **O(1)** — safe to use in loops.

---

### 🔹 Clear the vector

```cpp
v.clear(); // removes all elements
```

💡 **Warning:** `clear()` only removes elements, it does not shrink capacity.

---

### 🔹 Insert & erase

```cpp
v.insert(v.begin() + 2, 99);    // insert 99 at index 2
v.erase(v.begin() + 3);         // erase element at index 3
v.erase(v.begin() + 1, v.begin() + 4); // erase a range 1 to 3.
```

💡 **Tip:** `insert` and `erase` are **O(n)** — avoid in huge vectors during contests unless necessary.

---

### 🔹 Swap two vectors

```cpp
vector<int> a = {1,2,3};
vector<int> b = {4,5};
a.swap(b);
```

💡 **Tip:** Swapping is **O(1)**, useful for memory efficiency tricks.

---

### 🔹 Sort

```cpp
sort(v.begin(), v.end()); // ascending
sort(v.rbegin(), v.rend()); // descending
```

💡 **Tip:** For `vector<pair<int,int>>`, sorting automatically compares `.first` then `.second`.

---

### 🔹 Remove duplicates (unique trick)

```cpp
sort(v.begin(), v.end());
v.erase(unique(v.begin(), v.end()), v.end());
```

💡 **Tip:** In CP, this is the standard way to remove duplicates in **O(n log n)**.

---

### 🔹 Find element

```cpp
auto it = find(v.begin(), v.end(), 5); // return iterator. if not found then it return v.end()
int index = it - v.begin(); // find the index
if (it != v.end()) cout << "Found!";
// before binary search must sort the vector
sort(v.begin(),v.end());
bool isFound = binary_search(v.begin(), v.end(), 2);
```

💡 **Tip:** For sorted vectors, use `binary_search()` (O(log n)) instead of `find()` (O(n)).

---

### 3️⃣ Must-Know Vector Methods for CP 🚀

| Method                           | Usage                                                                                                                                           |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| `push_back()` / `emplace_back()` | Add elements to end                                                                                                                             |
| `pop_back()`                     | Remove last element                                                                                                                             |
| `size()` / `empty()`             | Get size, check empty                                                                                                                           |
| `clear()`                        | Reset vector length 0                                                                                                                           |
| `swap()`                         | O(1) memory trick                                                                                                                               |
| `insert()` / `erase()`           | Modify at position                                                                                                                              |
| `sort()` / `reverse()`           | Fast ordering                                                                                                                                   |
| `unique()`                       | Remove duplicates                                                                                                                               |
| `binary_search()`                | Fast search, but vector must be sorted                                                                                                          |
| `assign()`                       | Fill the vector with certian amount of value, or fill the vector with another vector range using iterator and fill the vector by another vector |

4️⃣ `next_permutation` to generate permutation of vector element.

```cpp
vector<int> v = {1,2,3,4};
next_permutation(v.begin(), v.end()); // change the vector to next permute
next_permutation(v.begin(), v.end()); // anotehr permuation
// it genrate permuation in lexcographical order
// if not found then it return false
```

5️⃣ Kadane Algorithm

Kadane’s Algorithm finds the **m**aximum subarray sum \*\*\*\*in `O(n)` time.

Basically: Given an array (can have negatives), find the contiguous subarray with the largest possible sum.

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    vector<int> arr = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
    int best = arr[0], sum = 0;

    for (int x : arr) {
        sum = max(x, sum + x); // either start new subarray or extend
        best = max(best, sum); // update answer
    }

    cout << "Max subarray sum = " << best << "\n";
}
```

---

### 🏁 Competitive Programming Tips 🏆

### ✅ Tip 1: Use `vector` instead of raw arrays unless you need extreme speed.

Dynamic resizing and safer syntax save debugging time.

### ✅ Tip 2: Use `reserve(n)` when you know the size in advance

```cpp
v.reserve(1000000); // reserve the size. first prevent multiple reallocation
```

Prevents multiple reallocations — saves time in big input problems.

### ✅ Tip 3: Clearing a vector of vectors quickly

Instead of `adj.clear()`, do:

```cpp
adj.assign(n, {});
```

This resets all sub-vectors at once.

### ✅ Tip 4: Avoid `vector<bool>`

It’s memory optimized but slow. Use `vector<char>` or `vector<int>` instead if see strict memory limit and time limit.

### ✅ Tip 5: Shrink to save memory

```cpp
v.shrink_to_fit(); // after clear .. the memory not be free.. so use it for save memory... use it if see strict memory limit.
```

Rarely needed, but can help in memory limit problems.

---
