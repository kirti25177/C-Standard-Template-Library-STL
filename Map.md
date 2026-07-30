# 🗺️ Map in C++

## 📖 What is a Map?

A **Map** is an associative container in the C++ Standard Template Library (STL) that stores elements as **key-value pairs**.

- Each **key** is **unique**.
- Each key is associated with exactly **one value**.
- Elements are automatically stored in **ascending order of keys**.

Internally, a `map` is implemented using a **Self-Balancing Binary Search Tree (Red-Black Tree)**.

It is defined in the `<map>` header file.

```cpp
#include <map>
```

---

# ✨ Why Use Map?

- ✅ Stores data as key-value pairs.
- ✅ Keys are unique.
- ✅ Automatically sorts keys.
- ✅ Fast searching, insertion, and deletion.
- ✅ Widely used in DSA and Competitive Programming.

---

# 🛠️ Declaration

```cpp
map<key_type, value_type> map_name;
```

### Example

```cpp
map<int, string> mp;
```

---

# 📌 Inserting Elements

### Using `[]`

```cpp
map<int, string> mp;

mp[1] = "Apple";
mp[2] = "Banana";
mp[3] = "Mango";
```

---

### Using `insert()`

```cpp
mp.insert({4, "Orange"});
```

---

### Using `make_pair()`

```cpp
mp.insert(make_pair(5, "Grapes"));
```

---

# 📌 Accessing Elements

### Using `[]`

```cpp
cout << mp[1];
```

Output

```
Apple
```

---

### Using `at()`

```cpp
cout << mp.at(2);
```

Output

```
Banana
```

---

# 📌 Traversing a Map

### Using Range-Based Loop

```cpp
for(auto x : mp)
{
    cout << x.first << " -> " << x.second << endl;
}
```

Output

```
1 -> Apple
2 -> Banana
3 -> Mango
```

---

### Using Iterator

```cpp
for(auto it = mp.begin(); it != mp.end(); it++)
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
mp.insert({10, "Book"});
```

Time Complexity: **O(log n)**

---

## erase()

Removes an element by key.

```cpp
mp.erase(2);
```

Time Complexity: **O(log n)**

---

## find()

Searches for a key.

```cpp
auto it = mp.find(3);

if(it != mp.end())
    cout << "Found";
else
    cout << "Not Found";
```

Time Complexity: **O(log n)**

---

## count()

Returns `1` if the key exists, otherwise `0`.

```cpp
cout << mp.count(1);
```

Output

```
1
```

Time Complexity: **O(log n)**

---

## size()

Returns the number of key-value pairs.

```cpp
cout << mp.size();
```

Time Complexity: **O(1)**

---

## empty()

Checks whether the map is empty.

```cpp
if(mp.empty())
{
    cout << "Map is empty";
}
```

Time Complexity: **O(1)**

---

## clear()

Removes all elements.

```cpp
mp.clear();
```

Time Complexity: **O(n)**

---

## swap()

Swaps two maps.

```cpp
map<int, string> mp1, mp2;

mp1.swap(mp2);
```

Time Complexity: **O(1)**

---

## lower_bound()

Returns an iterator to the **first key greater than or equal to** the given key.

```cpp
auto it = mp.lower_bound(3);
```

Time Complexity: **O(log n)**

---

## upper_bound()

Returns an iterator to the **first key greater than** the given key.

```cpp
auto it = mp.upper_bound(3);
```

Time Complexity: **O(log n)**

---

# 📌 Example Program

```cpp
#include<iostream>
#include<map>
using namespace std;

int main()
{
    map<int, string> mp;

    mp[3] = "Mango";
    mp[1] = "Apple";
    mp[2] = "Banana";

    for(auto x : mp)
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
2 -> Banana
3 -> Mango
```

---

# 📌 Iterators

```cpp
mp.begin()
mp.end()
mp.rbegin()
mp.rend()
mp.cbegin()
mp.cend()
```

---

# ⏱️ Time Complexity

| Operation | Complexity |
|-----------|------------|
| `insert()` | `O(log n)` |
| `erase()` | `O(log n)` |
| `find()` | `O(log n)` |
| `count()` | `O(log n)` |
| `lower_bound()` | `O(log n)` |
| `upper_bound()` | `O(log n)` |
| `operator[]` | `O(log n)` |
| `at()` | `O(log n)` |
| `size()` | `O(1)` |
| `empty()` | `O(1)` |
| `clear()` | `O(n)` |
| `swap()` | `O(1)` |

---

# 💾 Space Complexity

A map stores key-value pairs dynamically.

**Space Complexity:** `O(n)`

where **n** is the number of key-value pairs.

---

# 🚀 Advantages

- Stores data in key-value pairs.
- Keys are automatically sorted.
- Fast searching, insertion, and deletion.
- No duplicate keys.
- Supports efficient range queries.

---

# ❌ Disadvantages

- Slower than `unordered_map` on average.
- Uses more memory because of the tree structure.
- No indexing like arrays or vectors.

---

# 📌 Applications of Map

- Frequency counting.
- Phone directories.
- Student records.
- Database indexing.
- Memoization.
- Graph representation.
- Competitive Programming.

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

# 📊 Map vs Set

| Feature | Map | Set |
|---------|-----|-----|
| Stores | Key-Value Pair | Only Keys |
| Keys | Unique | Unique |
| Values | Present | Not Present |
| Ordering | Sorted | Sorted |

---

# 📌 Key Points

- A `map` stores **key-value pairs**.
- Keys are always **unique**.
- Elements are automatically sorted by **key**.
- Implemented using a **Red-Black Tree**.
- Searching, insertion, and deletion take **O(log n)** time.
- Use `operator[]` or `at()` to access values.
- Supports `lower_bound()` and `upper_bound()`.

---

# 🎯 Interview Tip

`map` is one of the most important STL containers in coding interviews.

You should know:
- `insert()`, `erase()`, `find()`, `count()`
- `operator[]` vs `at()`
- `lower_bound()` and `upper_bound()`
- Difference between **Map**, **Multimap**, and **Unordered Map**
- Time complexities
- Applications like **frequency counting**, **hash maps**, **memoization**, and **graph problems**
