# 🎯 Multiset in C++

## 📖 What is a Multiset?

A **Multiset** is an associative container in the C++ Standard Template Library (STL) that stores elements in **sorted order** and **allows duplicate elements**.

Internally, a `multiset` is implemented using a **Self-Balancing Binary Search Tree (Red-Black Tree)**.

It is defined in the `<set>` header file.

```cpp
#include <set>
```

---

# ✨ Why Use Multiset?

- ✅ Allows duplicate elements.
- ✅ Automatically stores elements in sorted order.
- ✅ Fast insertion, deletion, and searching.
- ✅ Useful when element frequency matters.
- ✅ Widely used in DSA and Competitive Programming.

---

# 🛠️ Declaration

```cpp
multiset<data_type> multiset_name;
```

### Example

```cpp
multiset<int> ms;
```

---

# 📌 Initialization

### Empty Multiset

```cpp
multiset<int> ms;
```

---

### Initialize Using List

```cpp
multiset<int> ms = {5, 2, 8, 5, 1, 2};
```

Output

```
1 2 2 5 5 8
```

> Duplicate elements are preserved.

---

# 📌 Traversing a Multiset

### Using Range-Based Loop

```cpp
for(auto x : ms)
{
    cout << x << " ";
}
```

Output

```
1 2 2 5 5 8
```

---

### Using Iterator

```cpp
for(auto it = ms.begin(); it != ms.end(); it++)
{
    cout << *it << " ";
}
```

---

# 📌 Common Functions

## insert()

Inserts an element into the multiset.

```cpp
ms.insert(10);
ms.insert(20);
ms.insert(20);
ms.insert(30);
```

Time Complexity: **O(log n)**

---

## erase(value)

Removes **all occurrences** of a value.

```cpp
ms.erase(20);
```

Example

Before

```
10 20 20 30
```

After

```
10 30
```

Time Complexity: **O(log n + count)**

---

## erase(iterator)

Removes only the element pointed to by the iterator.

```cpp
auto it = ms.find(20);

ms.erase(it);
```

Example

Before

```
10 20 20 30
```

After

```
10 20 30
```

---

## find()

Returns an iterator to the **first occurrence** of the element.

```cpp
auto it = ms.find(20);

if(it != ms.end())
    cout << "Found";
```

Time Complexity: **O(log n)**

---

## count()

Returns the number of occurrences of an element.

```cpp
cout << ms.count(20);
```

Output

```
2
```

Time Complexity: **O(log n + count)**

---

## size()

Returns the total number of elements.

```cpp
cout << ms.size();
```

Time Complexity: **O(1)**

---

## empty()

Checks whether the multiset is empty.

```cpp
if(ms.empty())
{
    cout << "Multiset is empty";
}
```

Time Complexity: **O(1)**

---

## clear()

Removes all elements.

```cpp
ms.clear();
```

Time Complexity: **O(n)**

---

## swap()

Swaps two multisets.

```cpp
multiset<int> ms1, ms2;

ms1.swap(ms2);
```

Time Complexity: **O(1)**

---

## lower_bound()

Returns an iterator to the **first element greater than or equal to** the given value.

```cpp
auto it = ms.lower_bound(20);
```

Time Complexity: **O(log n)**

---

## upper_bound()

Returns an iterator to the **first element greater than** the given value.

```cpp
auto it = ms.upper_bound(20);
```

Time Complexity: **O(log n)**

---

## equal_range()

Returns the range of all occurrences of a value.

```cpp
auto range = ms.equal_range(20);

for(auto it = range.first; it != range.second; it++)
{
    cout << *it << " ";
}
```

Output

```
20 20
```

Time Complexity: **O(log n + count)**

---

# 📌 Example Program

```cpp
#include<iostream>
#include<set>
using namespace std;

int main()
{
    multiset<int> ms;

    ms.insert(10);
    ms.insert(30);
    ms.insert(20);
    ms.insert(20);
    ms.insert(10);

    for(auto x : ms)
    {
        cout << x << " ";
    }

    return 0;
}
```

Output

```
10 10 20 20 30
```

---

# 📌 Iterators

```cpp
ms.begin()
ms.end()
ms.rbegin()
ms.rend()
ms.cbegin()
ms.cend()
```

---

# ⏱️ Time Complexity

| Operation | Complexity |
|-----------|------------|
| `insert()` | `O(log n)` |
| `erase(value)` | `O(log n + count)` |
| `erase(iterator)` | `O(1)` (amortized) |
| `find()` | `O(log n)` |
| `count()` | `O(log n + count)` |
| `lower_bound()` | `O(log n)` |
| `upper_bound()` | `O(log n)` |
| `equal_range()` | `O(log n)` |
| `size()` | `O(1)` |
| `empty()` | `O(1)` |
| `clear()` | `O(n)` |
| `swap()` | `O(1)` |

---

# 💾 Space Complexity

A multiset stores elements dynamically.

**Space Complexity:** `O(n)`

where **n** is the total number of elements (including duplicates).

---

# 🚀 Advantages

- Allows duplicate elements.
- Automatically keeps elements sorted.
- Efficient insertion, deletion, and searching.
- Useful for frequency-based problems.
- Supports range queries.

---

# ❌ Disadvantages

- Slower than `unordered_multiset` on average.
- Uses more memory due to tree structure.
- No random access or indexing.

---

# 📌 Applications of Multiset

- Frequency counting.
- Sliding Window problems.
- Maintaining sorted duplicate data.
- Median of a Data Stream.
- Competitive Programming.

---

# 📊 Set vs Multiset

| Feature | Set | Multiset |
|---------|-----|----------|
| Duplicate Elements | ❌ Not Allowed | ✅ Allowed |
| Order | Sorted | Sorted |
| Search | `O(log n)` | `O(log n)` |
| Implementation | Red-Black Tree | Red-Black Tree |

---

# 📊 Multiset vs Unordered Multiset

| Feature | Multiset | Unordered Multiset |
|---------|----------|--------------------|
| Ordering | Sorted | Unsorted |
| Duplicate Elements | ✅ Allowed | ✅ Allowed |
| Search | `O(log n)` | `O(1)` (Average) |
| Implementation | Red-Black Tree | Hash Table |

---

# 📌 Key Points

- A `multiset` stores elements in **sorted order**.
- Duplicate elements are **allowed**.
- Implemented using a **Red-Black Tree**.
- `count()` returns the number of occurrences.
- `erase(value)` removes **all** occurrences.
- `erase(iterator)` removes **only one** occurrence.
- `equal_range()` returns the range of duplicate elements.

---

# 🎯 Interview Tip

A `multiset` is frequently used when you need to maintain **sorted data with duplicates**.

You should know:
- `insert()`, `erase()`, `find()`, `count()`
- `lower_bound()`, `upper_bound()`, `equal_range()`
- Difference between **Set**, **Multiset**, and **Unordered Multiset**
- Time complexities
- Applications like **frequency counting**, **sliding window**, and **median-based problems**.
