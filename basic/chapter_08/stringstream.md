# [⬅️ Back](./other_trick.md) | [Chapter 8 ➡️](./chapter_08.md)

## 🧃 What is `stringstream`?

Think of a `stringstream` as a **tiny machine that helps you break a string into pieces** — like splitting a sentence into words or converting text numbers into real numbers.

---

## 🍪 Basic Example

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    string s = "10 20 30";
    stringstream ss(s);

    int a, b, c;
    ss >> a >> b >> c;

    cout << a + b + c; // 60
}

```

🧠 What happened here?

- We gave `stringstream` a string: `"10 20 30"`
- Then we used `>>` just like reading from `cin`
- It pulled out the numbers one by one!

---

## 🧩 Why it’s useful

Because in programming, you often get inputs like:

```
1 2 3 4 5
```

all in **one line**, and you need to **separate** them into numbers.

`stringstream` makes that super easy.

---

## 💬 Example: Split words

```cpp
string s = "Owl loves Rezaki";
stringstream ss(s);
string word;

while (ss >> word)
    cout << word << endl;
```

Output:

```
Owl
loves
Rezaki
```

👉 It automatically splits by **spaces**.

---

## 🔄 You can also build a string

You can use it like a “string builder.”

```cpp
stringstream ss;
ss << "Hello " << "World " << 2025;

string result = ss.str(); // get the final string
cout << result; // Hello World 2025
```

---

## 📦 Common uses

✅ Split strings by space

✅ Convert string → numbers easily

✅ Convert numbers → string easily

✅ Read mixed data from one line

---

## 🔥 Example 1: Convert string → number

```cpp
string s = "123";
stringstream ss(s);
int num;
ss >> num;
cout << num + 10; // 133
```

---

## 🔥 Example 2: Convert number → string

```cpp
int x = 42;
stringstream ss;
ss << x;

string str = ss.str();
cout << "Answer: " << str;
```

---

## 🧮 Example 3: Read unknown number of inputs in one line

```cpp
string line;
getline(cin, line); // input: 10 20 30 40

stringstream ss(line);
int num, sum = 0;
while (ss >> num)
    sum += num;

cout << sum; // 100
```

Super helpful in competitive programming when input comes in a single messy line 🏁

---

## 🧠 Quick summary

| What you do      | Code                           | Result                 |
| ---------------- | ------------------------------ | ---------------------- |
| Read from string | `stringstream ss("10 20 30");` | like `cin`             |
| Take values out  | `ss >> x;`                     | gives next word/number |
| Put values in    | `ss << value;`                 | build a string         |
| Get full string  | `ss.str();`                    | returns complete text  |
