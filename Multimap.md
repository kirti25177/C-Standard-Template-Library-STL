# 🗺️ Multimap in C++

## 📖 What is a Multimap?

A **Multimap** is an associative container in the C++ Standard Template Library (STL) that stores elements as **key-value pairs**.

Unlike a `map`, a **multimap allows multiple values to have the same key**.

Elements are automatically stored in **ascending order of keys**.

Internally, a `multimap` is implemented using a **Self-Balancing Binary Search Tree (Red-Black Tree)**.

It is defined in the `<map>` header file.

```cpp
#include <map>
```

---

# ✨ Why Use Multimap?

- ✅ Stores key-value pairs.
- ✅ Allows duplicate keys.
- ✅ Automatically sorts keys.
- ✅ Efficient insertion, deletion, and searching.
- ✅ Useful when one key is associated with multiple values.

---

# 🛠️ Declaration

```cpp
multimap<key_type, value_type> mmap;
```

### Example

```cpp
multimap<int, string> mmap;
```

---

# 📌 Inserting Elements

### Using `insert()`

```cpp
multimap<int, string> mmap;

mmap.insert({1, "Apple"});
mmap.insert({2, "Banana"});
mmap.insert({1, "Orange"});
```

Output

```
1 -> Apple
1 -> Orange
2 -> Banana
```

> **Note:** `multimap` does **not** support `operator[]`.

---

### Using `make_pair()`

```cpp
mmap.insert(make_pair(3, "Mango"));
```

---

# 📌 Accessing Elements

Since duplicate keys are allowed, you **cannot** use:

```cpp
mmap[1];   // ❌ Invalid
```

Instead, use `find()`, `equal_range()`, or iterate through the container.

---

# 📌 Traversing a Multimap

### Using Range-Based Loop

```cpp
for(auto x : mmap)
{
    cout << x.first << " -> " << x.second << endl;
}
```

---

### Using Iterator

```cpp
for(auto it = mmap.begin(); it != mmap.end(); it++)
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
mmap.insert({10, "Book"});
```

Time Complexity: **O(log n)**

---

## erase(key)

Removes **all** elements having the specified key.

```cpp
mmap.erase(1);
```

Time Complexity: **O(log n + count)**

---

## erase(iterator)

Removes only the element pointed to by the iterator.

```cpp
auto it = mmap.find(1);

mmap.erase(it);
```

Time Complexity: **O(1)** (Amortized)

---

## find()

Returns an iterator to the **first occurrence** of the given key.

```cpp
auto it = mmap.find(2);

if(it != mmap.end())
    cout << "Found";
```

Time Complexity: **O(log n)**

---

## count()

Returns the number of elements with the specified key.

```cpp
cout << mmap.count(1);
```

Output

```
2
```

Time Complexity: **O(log n + count)**

---

## equal_range()

Returns the range of all elements with the specified key.

```cpp
auto range = mmap.equal_range(1);

for(auto it = range.first; it != range.second; it++)
{
    cout << it->first << " -> "
         << it->second << endl;
}
```

Output

```
1 -> Apple
1 -> Orange
```

Time Complexity: **O(log n + count)**

---

## lower_bound()

Returns an iterator to the first element whose key is **greater than or equal to** the given key.

```cpp
auto it = mmap.lower_bound(2);
```

Time Complexity: **O(log n)**

---

## upper_bound()

Returns an iterator to the first element whose key is **greater than** the given key.

```cpp
auto it = mmap.upper_bound(2);
```

Time Complexity: **O(log n)**

---

## size()

Returns the total number of key-value pairs.

```cpp
cout << mmap.size();
```

Time Complexity: **O(1)**

---

## empty()

Checks whether the multimap is empty.

```cpp
if(mmap.empty())
{
    cout << "Multimap is empty";
}
```

Time Complexity: **O(1)**

---

## clear()

Removes all elements.

```cpp
mmap.clear();
```

Time Complexity: **O(n)**

---

## swap()

Swaps two multimaps.

```cpp
multimap<int, string> m1, m2;

m1.swap(m2);
```

Time Complexity: **O(1)**

---

# 📌 Example Program

```cpp
#include<iostream>
#include<map>
using namespace std;

int main()
{
    multimap<int, string> mmap;

    mmap.insert({1, "Apple"});
    mmap.insert({2, "Banana"});
    mmap.insert({1, "Orange"});
    mmap.insert({3, "Mango"});

    for(auto x : mmap)
    {
        cout << x.first << " -> "
             << x.second << endl;
    }

    return 0;
}
```

Output

```
1 -> Apple
1 -> Orange
2 -> Banana
3 -> Mango
```

---

# 📌 Iterators

```cpp
mmap.begin()
mmap.end()
mmap.rbegin()
mmap.rend()
mmap.cbegin()
mmap.cend()
```

---

# ⏱️ Time Complexity

| Operation | Complexity |
|-----------|------------|
| `insert()` | `O(log n)` |
| `erase(key)` | `O(log n + count)` |
| `erase(iterator)` | `O(1)` (Amortized) |
| `find()` | `O(log n)` |
| `count()` | `O(log n + count)` |
| `equal_range()` | `O(log n + count)` |
| `lower_bound()` | `O(log n)` |
| `upper_bound()` | `O(log n)` |
| `size()` | `O(1)` |
| `empty()` | `O(1)` |
| `clear()` | `O(n)` |
| `swap()` | `O(1)` |

---

# 💾 Space Complexity

A multimap stores key-value pairs dynamically.

**Space Complexity:** `O(n)`

where **n** is the total number of key-value pairs.

---

# 🚀 Advantages

- Allows duplicate keys.
- Automatically keeps keys sorted.
- Efficient searching and insertion.
- Useful when one key maps to multiple values.
- Supports range queries.

---

# ❌ Disadvantages

- Does not support `operator[]`.
- Slower than `unordered_multimap` on average.
- Uses more memory due to tree implementation.
- No random access.

---

# 📌 Applications of Multimap

- Student records with the same marks.
- Employee records by department.
- Library management systems.
- Event scheduling.
- Database indexing.
- Competitive Programming.

---

# 📊 Map vs Multimap

| Feature | Map | Multimap |
|---------|-----|----------|
| Duplicate Keys | ❌ No | ✅ Yes |
| Ordering | Sorted | Sorted |
| `operator[]` | ✅ Supported | ❌ Not Supported |
| `find()` | Returns one element | Returns first matching element |
| `equal_range()` | Rarely needed | Frequently used |

---

# 📊 Multimap vs Unordered Multimap

| Feature | Multimap | Unordered Multimap |
|---------|----------|--------------------|
| Ordering | Sorted | Unsorted |
| Duplicate Keys | ✅ Yes | ✅ Yes |
| Implementation | Red-Black Tree | Hash Table |
| Search | `O(log n)` | `O(1)` (Average) |

---

# 📌 Key Points

- A `multimap` stores **key-value pairs**.
- **Duplicate keys are allowed**.
- Keys are automatically sorted.
- Implemented using a **Red-Black Tree**.
- `operator[]` is **not supported**.
- Use `equal_range()` to access all values of the same key.
- Searching, insertion, and deletion take **O(log n)** time.

---

# 🎯 Interview Tip

A `multimap` is useful when **multiple values share the same key**.

You should know:
- `insert()`, `erase()`, `find()`, `count()`
- `equal_range()`
- `lower_bound()` and `upper_bound()`
- Why `operator[]` is not available
- Difference between **Map**, **Multimap**, and **Unordered Multimap**
- Common use cases in **database indexing**, **grouping data**, and **competitive programming**
