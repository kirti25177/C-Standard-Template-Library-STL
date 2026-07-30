# 📦 Vector in C++

## 📖 What is a Vector?

A **vector** is a dynamic array provided by the C++ Standard Template Library (STL). Unlike normal arrays, a vector can **grow** and **shrink** automatically during runtime.

It stores elements in **contiguous memory locations**, allowing fast random access.

**Header File**

```cpp
#include <vector>
```

---

# ✨ Why Use Vector?

- ✅ Dynamic size
- ✅ Fast random access (`O(1)`)
- ✅ Easy insertion and deletion
- ✅ Rich set of built-in functions
- ✅ Widely used in DSA and Competitive Programming

---

# 🛠️ Declaration

```cpp
vector<data_type> vector_name;
```

### Example

```cpp
vector<int> v;
```

---

# 📌 Initialization

### Empty Vector

```cpp
vector<int> v;
```

### Vector with Size

```cpp
vector<int> v(5);
```

Output

```
0 0 0 0 0
```

---

### Vector with Initial Value

```cpp
vector<int> v(5, 10);
```

Output

```
10 10 10 10 10
```

---

### Initialize using List

```cpp
vector<int> v = {1,2,3,4,5};
```

---

### Copy a Vector

```cpp
vector<int> v1 = {1,2,3};

vector<int> v2(v1);
```

---

# 📌 Accessing Elements

```cpp
vector<int> v = {10,20,30};

cout << v[0] << endl;
cout << v.at(1) << endl;
cout << v.front() << endl;
cout << v.back() << endl;
```

Output

```
10
20
10
30
```

---

# 📌 Traversing a Vector

### Using Index

```cpp
for(int i=0;i<v.size();i++)
{
    cout<<v[i]<<" ";
}
```

---

### Using Range-Based Loop

```cpp
for(auto x : v)
{
    cout<<x<<" ";
}
```

---

### Using Iterator

```cpp
for(auto it=v.begin(); it!=v.end(); it++)
{
    cout<<*it<<" ";
}
```

---

# 📌 Common Functions

## push_back()

Adds an element at the end.

```cpp
v.push_back(10);
```

Time Complexity: **O(1)** (Amortized)

---

## pop_back()

Removes the last element.

```cpp
v.pop_back();
```

Time Complexity: **O(1)**

---

## size()

Returns the number of elements.

```cpp
cout<<v.size();
```

Time Complexity: **O(1)**

---

## empty()

Checks whether the vector is empty.

```cpp
if(v.empty())
```

Time Complexity: **O(1)**

---

## clear()

Removes all elements.

```cpp
v.clear();
```

Time Complexity: **O(n)**

---

## insert()

Inserts an element at a specific position.

```cpp
v.insert(v.begin()+2,100);
```

Time Complexity: **O(n)**

---

## erase()

Removes an element.

```cpp
v.erase(v.begin()+1);
```

Time Complexity: **O(n)**

Remove a range

```cpp
v.erase(v.begin()+2, v.begin()+5);
```

---

## resize()

Changes the size of the vector.

```cpp
v.resize(10);
```

Time Complexity: **O(n)**

---

## swap()

Swaps two vectors.

```cpp
v1.swap(v2);
```

Time Complexity: **O(1)**

---

## assign()

Assigns new values.

```cpp
v.assign(5,100);
```

Output

```
100 100 100 100 100
```

---

# 📌 Capacity Functions

## capacity()

Returns the current allocated capacity.

```cpp
cout<<v.capacity();
```

---

## reserve()

Allocates memory in advance.

```cpp
v.reserve(100);
```

---

## shrink_to_fit()

Reduces capacity to fit the current size.

```cpp
v.shrink_to_fit();
```

---

# 📌 Iterators

```cpp
v.begin()
v.end()
v.rbegin()
v.rend()
```

---

# 📌 Example Program

```cpp
#include<iostream>
#include<vector>
using namespace std;

int main()
{
    vector<int> v;

    v.push_back(10);
    v.push_back(20);
    v.push_back(30);

    for(auto x:v)
    {
        cout<<x<<" ";
    }

    return 0;
}
```

Output

```
10 20 30
```

---

# ⏱️ Time Complexity

| Operation | Complexity |
|-----------|------------|
| Access (`[]`, `at()`) | `O(1)` |
| `front()` | `O(1)` |
| `back()` | `O(1)` |
| `push_back()` | `O(1)` (Amortized) |
| `pop_back()` | `O(1)` |
| `insert()` | `O(n)` |
| `erase()` | `O(n)` |
| `clear()` | `O(n)` |
| `size()` | `O(1)` |
| `empty()` | `O(1)` |
| `resize()` | `O(n)` |
| `swap()` | `O(1)` |

---

# 💾 Space Complexity

A vector stores elements dynamically.

**Space Complexity:** `O(n)`

where **n** is the number of elements stored.

---

# 🚀 Advantages

- Dynamic size
- Contiguous memory
- Fast random access
- Easy insertion at the end
- Rich STL functions
- Cache friendly

---

# ❌ Disadvantages

- Insertion/deletion in the middle is slow (`O(n)`).
- Reallocation may occur when capacity is exceeded.
- Slightly more memory overhead than arrays.

---

# 📌 Key Points

- `vector` is a **dynamic array**.
- Elements are stored in **contiguous memory**.
- Size changes automatically.
- `push_back()` inserts at the end.
- `pop_back()` removes the last element.
- Access elements using `[]` or `at()`.
- `begin()` and `end()` return iterators.
- Preferred over arrays in most DSA problems.

---

# 🎯 Interview Tip

`vector` is the **most frequently used STL container** in DSA and coding interviews. Be comfortable with:
- Declaration
- Traversal
- Iterators
- `push_back()`
- `pop_back()`
- `insert()`
- `erase()`
- `resize()`
- `capacity()`
- Time complexities of all major operations
