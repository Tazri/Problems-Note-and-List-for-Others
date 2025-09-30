### [⬅️ Back To README FILE](./../../README.md)

# Chapter 06: 📘 String

---

### 🔹 Chapter 1: Basics of C-style Strings (`char array`)

- What is a C-style string?
- Null terminator `\0`
- Declaration and Initialization
  ```cpp
  char str[10] = "hello";
  char str[] = {'h', 'e', 'l', 'l', 'o', '\0'};
  ```
- Input and Output (`cin`, `cin.getline`, `gets`, `puts`)
- Common functions from `<cstring>`:
  - `strlen`, `strcpy`, `strcat`, `strcmp`, `strchr`, `strstr`

🧠 **Tips**:

- Avoid `gets()` – it's unsafe.
- Always ensure space for the null character (`\0`).

---

### 🔹 Chapter 2: STL `string`

- Declaration and Initialization:
  ```cpp
  string s = "hello";
  string s2("world");
  string s3(5, 'x');  // "xxxxx"
  ```
- Input and Output:
  ```cpp
  getline(cin, s); // take a line
  cin >> s; // take a words
  ```
- Basic Operations:

| **Method / Operator**         | **Purpose**                                 | **Example Usage**                               |
| ----------------------------- | ------------------------------------------- | ----------------------------------------------- |
| `s.size()` / `s.length()`     | Get length of the string                    | `int n = s.size();`                             |
| `s.empty()`                   | Check if string is empty                    | `if (s.empty()) continue;`                      |
| `s[i]` or `s.at(i)`           | Access character at index `i`               | `char c = s[i];`                                |
| `s.front()` / `s.back()`      | Get first / last character                  | `if (s.back() == ')')`                          |
| `s += "abc"` / `s + s2`       | Concatenate strings                         | `s = s + "123";`                                |
| `s.push_back(c)`              | Append a character                          | `s.push_back('z');`                             |
| `s.pop_back()`                | Remove last character                       | `s.pop_back();`                                 |
| `s.substr(pos, len)`          | Get substring                               | `string sub = s.substr(2, 4);`                  |
| `s.find(str)`                 | Find first occurrence of `str`              | `if (s.find("abc") != string::npos)`            |
| `s.rfind(str)`                | Find last occurrence of `str`               | `s.rfind("abc");`                               |
| `s.erase(pos, len)`           | Erase part of string                        | `s.erase(3, 2);`                                |
| `s.insert(pos, str)`          | Insert string at position                   | `s.insert(2, "x");`                             |
| `s.clear()`                   | Clear string                                | `s.clear();`                                    |
| `s.compare(str)`              | Lexicographic comparison                    | `if (s.compare(t) < 0)`                         |
| `sort(s.begin(), s.end())`    | Sort string characters                      | `sort(s.begin(), s.end());`                     |
| `reverse(s.begin(), s.end())` | Reverse string                              | `reverse(s.begin(), s.end());`                  |
| `unique()` + `erase()`        | Remove consecutive duplicates               | `s.erase(unique(s.begin(), s.end()), s.end());` |
| `s.c_str()`                   | Convert to C-style string (for printf etc.) | `printf("%s", s.c_str());`                      |

🧠 **Tips**:

- Use `getline(cin, s)` after `cin` carefully — clear newline buffer using `cin.ignore()`.
- Use `.find()` for fast pattern matching; returns `string::npos` if not found.
- Comparing substrings is cheaper with `.compare()` than slicing + `==`.

---

### 🔹 Chapter 3: String and Character Conversion

- `stoi()`, `stol()`, `stoll()`, `stod()` – from `<string>`
- `to_string()`
- Manual conversion using `stringstream` or ASCII math:
  ```cpp
  int digit = s[i] - '0';
  char ch = d + '0';  // digit to cha
  ```

🧠 **Tip**: Use `isdigit(c)`, `isalpha(c)` from `<cctype>` to safely process characters.

---

### 🔹 Chapter 4: Iterating Strings

- Range-based loop:
  ```cpp
  for (char c : s)
  ```
- Traditional index loop
- Using iterators:
  ```cpp
  for (auto it = s.begin(); it != s.end(); ++it)
  ```

🧠 **Tip**: Avoid using `.at(i)` inside loops—it checks bounds and slows down.

---

### 🔹 Chapter 5: Sorting and Reversing

- `sort(s.begin(), s.end())`
- `reverse(s.begin(), s.end())`
- `next_permutation(s.begin(), s.end())`

💡 **Trick**: Use `sort()` to easily detect anagrams or lexicographical order.

---

### 🔹 Chapter 6: Advanced String Tricks for CP

✅ **Palindrome Check**:

```cpp

bool isPalindrome(string s) {
    int l = 0, r = s.size() - 1;
    while (l < r) if (s[l++] != s[r--]) return false;
    return true;
}
```

✅ **Frequency Count**:

```cpp
vector<int> freq(26);
for (char c : s) freq[c - 'a']++;

// or
vector<int> freq(256);
for(char c:s) freq[c]++;
```

✅ **Custom Comparator (e.g., for sorting strings)**:

```cpp
bool cmp(string a, string b) {
    return a + b > b + a;  // for forming largest number
}
```

✅ **Two Pointers on Strings**: For substring problems, sliding window, etc.

---

## 💣 Bonus String Hacks for CP

💥 **Use macros for char-index math**:

```cpp

#define idx(c) (c - 'a')
```

💥 **Avoid TLE in big string input**:

Use:

```cpp
ios::sync_with_stdio(0); cin.tie(0);
```

💥 **Remove spaces from string**:

```cpp
s.erase(remove(s.begin(), s.end(), ' '), s.end()); **Use prefix sum of characters** (for substring frequency matching):
```

💥**Case Conversion Tips (CP Super Useful!)**

| **Task**                          | **Code**                                               |
| --------------------------------- | ------------------------------------------------------ |
| Convert whole string to lowercase | `transform(s.begin(), s.end(), s.begin(), ::tolower);` |
| Convert whole string to uppercase | `transform(s.begin(), s.end(), s.begin(), ::toupper);` |
| Convert single char to lowercase  | `char lc = tolower(c);`                                |
| Convert single char to uppercase  | `char uc = toupper(c);`                                |

✅ Requires header: `#include <algorithm>` and `#include <cctype>`
