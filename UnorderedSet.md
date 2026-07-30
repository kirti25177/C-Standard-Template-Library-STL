# ⚡ Unordered Set in C++

## 📖 What is an Unordered Set?

An **Unordered Set** is an associative container in the C++ Standard Template Library (STL) that stores **unique elements** in **no particular order**.

Unlike a `set`, an `unordered_set` is implemented using a **Hash Table**, making searching, insertion, and deletion **very fast on average**.

It is defined in the `<unordered_set>` header file.

```cpp
#include <unordered_set>
```

---

# ✨ Why Use Unordered Set?

- ✅ Stores only unique elements.
- ✅ Very fast insertion, deletion, and searching.
- ✅ Average time complexity of **O(1)**.
- ✅ Ideal when ordering is not required.
- ✅ Widely used in DSA and Competitive Programming.

---

# 🛠️ Declaration

```cpp
unordered_set<data_type> us;
```

### Example

```cpp
unordered_set<int> us;
```

---

# 📌 Initialization

### Empty Unordered Set

```cpp
unordered_set<int> us;
```

---

### Initialize Using List

```cpp
unordered_set<int> us = {5, 2, 8, 5, 1, 2};
```

Possible Output

```
8 2 1 5
```

> **Note:** The output order is not guaranteed because an unordered set does not maintain sorted order.

---

# 📌 Traversing an Unordered Set

### Using Range-Based Loop

```cpp
for(auto x : us)
{
    cout << x << " ";
}
```

---

### Using Iterator

```cpp
for(auto it = us.begin(); it != us.end(); it++)
{
    cout << *it << " ";
}
```

---

# 📌 Common Functions

## insert()

Inserts an element into the unordered set.

```cpp
us.insert(10);
us.insert(20);
us.insert(30);
```

Time Complexity: **O(1)** (Average)

---

## erase()

Removes an element.

```cpp
us.erase(20);
```

Time Complexity: **O(1)** (Average)

---

## find()

Searches for an element.

```cpp
auto it = us.find(10);

if(it != us.end())
    cout << "Found";
else
    cout << "Not Found";
```

Time Complexity: **O(1)** (Average)

---

## count()

Returns `1` if the element exists, otherwise `0`.

```cpp
cout << us.count(10);
```

Output

```
1
```

Time Complexity: **O(1)** (Average)

---

## size()

Returns the number of elements.

```cpp
cout << us.size();
```

Time Complexity: **O(1)**

---

## empty()

Checks whether the unordered set is empty.

```cpp
if(us.empty())
{
    cout << "Unordered Set is empty";
}
```

Time Complexity: **O(1)**

---

## clear()

Removes all elements.

```cpp
us.clear();
```

Time Complexity: **O(n)**

---

## swap()

Swaps two unordered sets.

```cpp
unordered_set<int> us1, us2;

us1.swap(us2);
```

Time Complexity: **O(1)**

---

# 📌 Example Program

```cpp
#include<iostream>
#include<unordered_set>
using namespace std;

int main()
{
    unordered_set<int> us;

    us.insert(30);
    us.insert(10);
    us.insert(20);
    us.insert(10);

    for(auto x : us)
    {
        cout << x << " ";
    }

    return 0;
}
```

Possible Output

```
20 10 30
```

---

# 📌 Iterators

```cpp
us.begin()
us.end()
us.cbegin()
us.cend()
```

> **Note:** Reverse iterators (`rbegin()` and `rend()`) are **not available** because the elements are not stored in any order.

---

# ⏱️ Time Complexity

| Operation | Average Case | Worst Case |
|-----------|--------------|------------|
| `insert()` | `O(1)` | `O(n)` |
| `erase()` | `O(1)` | `O(n)` |
| `find()` | `O(1)` | `O(n)` |
| `count()` | `O(1)` | `O(n)` |
| `size()` | `O(1)` | `O(1)` |
| `empty()` | `O(1)` | `O(1)` |
| `clear()` | `O(n)` | `O(n)` |
| `swap()` | `O(1)` | `O(1)` |

---

# 💾 Space Complexity

An unordered set stores unique elements using a hash table.

**Space Complexity:** `O(n)`

where **n** is the number of unique elements.

---

# 🚀 Advantages

- Very fast average-case searching.
- Very fast average-case insertion and deletion.
- Stores only unique elements.
- Ideal when sorting is not required.
- Better performance than `set` for many applications.

---

# ❌ Disadvantages

- Elements are **not sorted**.
- No indexing.
- `lower_bound()` and `upper_bound()` are **not supported**.
- Worst-case complexity can degrade to **O(n)** because of hash collisions.

---

# 📌 Applications of Unordered Set

- Removing duplicate elements.
- Fast lookups.
- Hashing problems.
- Cycle detection.
- Graph algorithms.
- Competitive Programming.

---

# 📊 Set vs Unordered Set

| Feature | Set | Unordered Set |
|---------|-----|---------------|
| Ordering | Sorted | Unsorted |
| Duplicate Elements | ❌ No | ❌ No |
| Implementation | Red-Black Tree | Hash Table |
| Search | `O(log n)` | `O(1)` (Average) |
| Insert | `O(log n)` | `O(1)` (Average) |
| Erase | `O(log n)` | `O(1)` (Average) |
| `lower_bound()` | ✅ Yes | ❌ No |
| `upper_bound()` | ✅ Yes | ❌ No |

---

# 📊 Set vs Multiset vs Unordered Set

| Feature | Set | Multiset | Unordered Set |
|---------|-----|----------|---------------|
| Duplicate Elements | ❌ No | ✅ Yes | ❌ No |
| Ordering | Sorted | Sorted | Unsorted |
| Implementation | Red-Black Tree | Red-Black Tree | Hash Table |
| Search | `O(log n)` | `O(log n)` | `O(1)` (Average) |

---

# 📌 Key Points

- `unordered_set` stores **unique elements**.
- Elements are stored in **no specific order**.
- Implemented using a **Hash Table**.
- Average time complexity for `insert()`, `erase()`, and `find()` is **O(1)**.
- Does not support `lower_bound()` or `upper_bound()`.
- Does not support indexing.

---

# 🎯 Interview Tip

`unordered_set` is preferred when you need **fast lookups** and **sorting is not required**.

You should know:
- `insert()`, `erase()`, `find()`, `count()`
- Average vs worst-case time complexities
- Difference between **Set**, **Multiset**, and **Unordered Set**
- Hash table implementation
- Applications like **duplicate removal**, **hashing problems**, and **graph algorithms**
