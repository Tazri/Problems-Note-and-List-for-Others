# [⬅️ Back](./chapter_08.md) | [📖 ReadMe](./../../README.md)

# ⚙️ Other Tricks

## 🧩 Separate Words from Sentence

If you want to know about stringstream then go :

### [StringStream](./stringstream.md)

**Using `stringstream` (Easiest & Most Popular Way)**

The classic method — clean, short, and powerful 🔥

```cpp
string sentence;
getline(cin, sentence); // take sentece
stringstream ss(sentence);  // create a stream from the sentence
string word;

while (ss >> word) {        // extract words one by one
    cout << word << '\n';
}
```

🧠 _How it works:_

`stringstream` automatically breaks by **spaces or newlines**.

You can also change the separator manually if needed.

✅ Best for: **Normal space-separated words**

⚠️ Limitation: Doesn’t handle punctuation automatically (`"cool!"` stays `"cool!"`)

## ✒️ Reversing String

```cpp
string s = "owls are awesome";
reverse(s.begin(), s.end());
```

## 📊 Track Frequencies Using Map

```cpp
vector<int> nums = {1, 2, 1, 3, 2, 1, 4};
map<int, int> freq; // key = number, value = count

for (int x : nums)
    freq[x]++; // auto-creates and increments

for (auto [num, count] : freq)
    cout << num << " appears " << count << " times\n";

```

## 🗒️ Counting Words in Sentence

```cpp
string s = "owl owl is wise and owl is cute";
stringstream ss(s);
map<string, int> freq;
string word;

while (ss >> word)
    freq[word]++;

for (auto [w, c] : freq)
    cout << w << " -> " << c << '\n';
```

## 🖊️ Marking using set

```cpp
vector<int> a = {1, 2, 2, 3, 1};
set<int> visited;

for (int x : a) {
    if (visited.find(x) == visited.end()) {
        cout << x << " first time\n";
        visited.insert(x); // mark it
    }
}
```

## 🗑️ Remove Duplicate

```cpp
vector<int> a = {1, 2, 2, 3, 4, 1, 5};
set<int> s(a.begin(), a.end()); // auto removes duplicates
vector<int> filter;

for (int x : s)
    filter.push_back(x);
```

## 📓 Preserve Original Order + Distinct Values

```cpp
vector<int> a = {4, 1, 2, 2, 3, 4, 1, 5};
set<int> seen;
vector<int> distinct;

for (int x : a) {
    if (!seen.count(x)) {   // first time
        seen.insert(x);
        distinct.push_back(x);
    }
}

for (int x : distinct) cout << x << " ";
```

---

## 📚 Find All Divisors in O(√n)

```cpp
long long n;
cin >> n;

vector<long long> divisors;

// here i*i , that why it run sqrt(n)
for (long long i = 1; i * i <= n; i++) {
    if (n % i == 0) {
        divisors.push_back(i);
        if (i != n / i)
            divisors.push_back(n / i);
    }
}

// sort divisors
sort(divisors.begin(), divisors.end());

for (auto d : divisors)
    cout << d << " ";
cout << "\n";
```

### ⚙️ How It Works

Let’s say you want all divisors of n.

> If i divides n, then n / i is also a divisor.

👉 So for each divisor i ≤ √n, we get two divisors at once:
i and n / i.

💡 Example:

```
n = 36
i = 1 → 1 x 36
i = 2 → 2 x 18
i = 3 → 3 x 12
i = 4 → 4 x 9
i = 5 → no
i = 6 → 6 x 6 (same, only take once)
```

✅ Divisors = [1, 2, 3, 4, 6, 9, 12, 18, 36]
