# ⚡ Unordered Map in C++

## 📖 What is an Unordered Map?

An **Unordered Map** is an associative container in the C++ Standard Template Library (STL) that stores elements as **key-value pairs**.

- Each **key is unique**.
- Each key is associated with exactly **one value**.
- Elements are stored in **no particular order**.

Internally, an `unordered_map` is implemented using a **Hash Table**, which provides very fast searching, insertion, and deletion on average.

It is defined in the `<unordered_map>` header file.

```cpp
#include <unordered_map>
```

---

# ✨ Why Use Unordered Map?

- ✅ Stores data as key-value pairs.
- ✅ Keys are unique.
- ✅ Very fast searching, insertion, and deletion.
- ✅ Average time complexity is **O(1)**.
- ✅ Widely used in DSA and Competitive Programming.

---

# 🛠️ Declaration

```cpp
unordered_map<key_type, value_type> um;
```

### Example

```cpp
unordered_map<int, string> um;
```

---

# 📌 Inserting Elements

### Using `[]`

```cpp
unordered_map<int, string> um;

um[1] = "Apple";
um[2] = "Banana";
um[3] = "Mango";
```

---

### Using `insert()`

```cpp
um.insert({4, "Orange"});
```

---

### Using `make_pair()`

```cpp
um.insert(make_pair(5, "Grapes"));
```

---

# 📌 Accessing Elements

### Using `[]`

```cpp
cout << um[1];
```

Output

```
Apple
```

---

### Using `at()`

```cpp
cout << um.at(2);
```

Output

```
Banana
```

---

# 📌 Traversing an Unordered Map

### Using Range-Based Loop

```cpp
for(auto x : um)
{
    cout << x.first << " -> " << x.second << endl;
}
```

Possible Output

```
3 -> Mango
1 -> Apple
2 -> Banana
```

> **Note:** The order is **not guaranteed**.

---

### Using Iterator

```cpp
for(auto it = um.begin(); it != um.end(); it++)
{
    cout << it->first << " -> "
         << it->second << endl;
}
```

---

# 📌 Common Functions

## insert()

Inserts a key-value pair.

```cpp
um.insert({10, "Book"});
```

Time Complexity: **O(1)** (Average)

---

## erase()

Removes an element by key.

```cpp
um.erase(2);
```

Time Complexity: **O(1)** (Average)

---

## find()

Searches for a key.

```cpp
auto it = um.find(3);

if(it != um.end())
    cout << "Found";
else
    cout << "Not Found";
```

Time Complexity: **O(1)** (Average)

---

## count()

Returns `1` if the key exists, otherwise `0`.

```cpp
cout << um.count(1);
```

Output

```
1
```

Time Complexity: **O(1)** (Average)

---

## size()

Returns the number of key-value pairs.

```cpp
cout << um.size();
```

Time Complexity: **O(1)**

---

## empty()

Checks whether the unordered map is empty.

```cpp
if(um.empty())
{
    cout << "Unordered Map is empty";
}
```

Time Complexity: **O(1)**

---

## clear()

Removes all elements.

```cpp
um.clear();
```

Time Complexity: **O(n)**

---

## swap()

Swaps two unordered maps.

```cpp
unordered_map<int, string> um1, um2;

um1.swap(um2);
```

Time Complexity: **O(1)**

---

# 📌 Example Program

```cpp
#include<iostream>
#include<unordered_map>
using namespace std;

int main()
{
    unordered_map<int, string> um;

    um[3] = "Mango";
    um[1] = "Apple";
    um[2] = "Banana";

    for(auto x : um)
    {
        cout << x.first << " -> "
             << x.second << endl;
    }

    return 0;
}
```

Possible Output

```
2 -> Banana
3 -> Mango
1 -> Apple
```

---

# 📌 Iterators

```cpp
um.begin()
um.end()
um.cbegin()
um.cend()
```

> **Note:** Reverse iterators (`rbegin()` and `rend()`) are **not available** because elements are not stored in sorted order.

---

# ⏱️ Time Complexity

| Operation | Average Case | Worst Case |
|-----------|--------------|------------|
| `insert()` | `O(1)` | `O(n)` |
| `erase()` | `O(1)` | `O(n)` |
| `find()` | `O(1)` | `O(n)` |
| `count()` | `O(1)` | `O(n)` |
| `operator[]` | `O(1)` | `O(n)` |
| `at()` | `O(1)` | `O(n)` |
| `size()` | `O(1)` | `O(1)` |
| `empty()` | `O(1)` | `O(1)` |
| `clear()` | `O(n)` | `O(n)` |
| `swap()` | `O(1)` | `O(1)` |

---

# 💾 Space Complexity

An unordered map stores key-value pairs using a hash table.

**Space Complexity:** `O(n)`

where **n** is the number of key-value pairs.

---

# 🚀 Advantages

- Very fast average-case searching.
- Very fast insertion and deletion.
- Stores unique keys.
- Excellent for frequency counting.
- Preferred when ordering is not required.

---

# ❌ Disadvantages

- Elements are **not sorted**.
- Worst-case complexity can become **O(n)** due to hash collisions.
- `lower_bound()` and `upper_bound()` are **not supported**.
- Slightly higher memory usage because of the hash table.

---

# 📌 Applications of Unordered Map

- Frequency Counting
- Hashing Problems
- Memoization (Dynamic Programming)
- Graph Algorithms
- Caching
- Database Indexing
- Competitive Programming

---

# 📊 Map vs Unordered Map

| Feature | Map | Unordered Map |
|---------|-----|---------------|
| Ordering | Sorted by Key | Unsorted |
| Duplicate Keys | ❌ No | ❌ No |
| Implementation | Red-Black Tree | Hash Table |
| Search | `O(log n)` | `O(1)` (Average) |
| Insert | `O(log n)` | `O(1)` (Average) |
| Erase | `O(log n)` | `O(1)` (Average) |
| `lower_bound()` | ✅ Yes | ❌ No |
| `upper_bound()` | ✅ Yes | ❌ No |

---

# 📊 Map vs Unordered Map vs Multimap

| Feature | Map | Unordered Map | Multimap |
|---------|-----|---------------|----------|
| Duplicate Keys | ❌ No | ❌ No | ✅ Yes |
| Ordering | Sorted | Unsorted | Sorted |
| Implementation | Red-Black Tree | Hash Table | Red-Black Tree |
| Search | `O(log n)` | `O(1)` (Average) | `O(log n)` |

---

# 📌 Key Points

- `unordered_map` stores **key-value pairs**.
- Keys are **unique**.
- Elements are stored in **no specific order**.
- Implemented using a **Hash Table**.
- Average time complexity for `insert()`, `erase()`, and `find()` is **O(1)**.
- `lower_bound()` and `upper_bound()` are **not available**.
- Best choice when **fast lookup** is more important than maintaining sorted order.

---

# 🎯 Interview Tip

`unordered_map` is one of the **most frequently used STL containers** in coding interviews.

You should know:
- `insert()`, `erase()`, `find()`, `count()`
- `operator[]` vs `at()`
- Average vs Worst-case time complexity
- Hash Table implementation
- Difference between **Map**, **Unordered Map**, and **Multimap**
- Applications like **frequency counting**, **memoization**, **graph algorithms**, **Two Sum**, **Longest Subarray with Sum K**, and many other hashing-based problems.
