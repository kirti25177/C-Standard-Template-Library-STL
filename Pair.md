# 👥 Pair in C++

## 📖 What is a Pair?

A **pair** is a container provided by the C++ Standard Template Library (STL) that allows you to store **two values together** as a single unit.

The two values can be of:
- The **same data type**, or
- **Different data types**

It is defined in the `<utility>` header file.

```cpp
#include <utility>
```

---

# 🛠️ Syntax

```cpp
pair<data_type1, data_type2> pair_name;
```

### Example

```cpp
pair<int, string> student;
```

---

# ✨ Creating a Pair

```cpp
#include <iostream>
#include <utility>
using namespace std;

int main() {

    pair<int, string> p;

    p.first = 101;
    p.second = "Kirti";

    cout << p.first << " " << p.second;

    return 0;
}
```

### Output

```
101 Kirti
```

---

# 📌 Using `make_pair()`

Instead of assigning values separately, we can use `make_pair()`.

```cpp
pair<int, string> p = make_pair(101, "Kirti");
```

---

# 📌 Direct Initialization

```cpp
pair<int, string> p = {101, "Kirti"};
```

or

```cpp
pair<int, string> p(101, "Kirti");
```

---

# 📌 Accessing Elements

```cpp
cout << p.first << endl;
cout << p.second << endl;
```

### Output

```
101
Kirti
```

---

# 📌 Pair with Same Data Type

```cpp
pair<int, int> p = {10, 20};

cout << p.first << " " << p.second;
```

Output

```
10 20
```

---

# 📌 Pair with Different Data Types

```cpp
pair<string, double> product = {"Laptop", 69999.99};

cout << product.first << endl;
cout << product.second;
```

Output

```
Laptop
69999.99
```

---

# 📌 Nested Pair

A pair can contain another pair.

```cpp
pair<int, pair<int, int>> p = {1, {2, 3}};

cout << p.first << endl;
cout << p.second.first << endl;
cout << p.second.second << endl;
```

Output

```
1
2
3
```

---

# 📌 Array of Pairs

```cpp
pair<int, string> students[3] = {
    {101, "Alice"},
    {102, "Bob"},
    {103, "Charlie"}
};

for(int i = 0; i < 3; i++)
{
    cout << students[i].first << " "
         << students[i].second << endl;
}
```

Output

```
101 Alice
102 Bob
103 Charlie
```

---

# 📌 Swapping Two Pairs

```cpp
pair<int, int> p1 = {10, 20};
pair<int, int> p2 = {30, 40};

swap(p1, p2);

cout << p1.first << " " << p1.second << endl;
cout << p2.first << " " << p2.second;
```

Output

```
30 40
10 20
```

---

# 📌 Comparing Pairs

Pairs are compared **lexicographically**.

- Compare `first`
- If `first` is equal, compare `second`

```cpp
pair<int,int> p1 = {1,2};
pair<int,int> p2 = {1,3};

if(p1 < p2)
    cout << "True";
else
    cout << "False";
```

Output

```
True
```

---

# ⏱️ Time Complexity

| Operation | Time Complexity |
|------------|-----------------|
| Access `first` | `O(1)` |
| Access `second` | `O(1)` |
| Create Pair | `O(1)` |
| Copy Pair | `O(1)` |
| Swap | `O(1)` |
| Compare | `O(1)` |

---

# 💾 Space Complexity

A pair stores exactly **two values**.

**Space Complexity:** `O(1)`

---

# 🚀 Common Use Cases

- Returning multiple values from a function.
- Storing `(key, value)` pairs.
- Representing coordinates `(x, y)`.
- Storing `(node, distance)` in Graph algorithms.
- Competitive Programming.

---

# 📌 Key Points

- A pair stores **exactly two values**.
- Access elements using `.first` and `.second`.
- Values can have **same or different data types**.
- Nested pairs are allowed.
- Arrays, vectors, maps, and other STL containers can store pairs.
- Pair comparison is **lexicographical**.

---

# 🎯 Interview Tip

`pair` is one of the most frequently used STL components in DSA. It is commonly used in:
- Graph Algorithms
- Binary Trees
- Priority Queues
- Maps
- Competitive Programming
