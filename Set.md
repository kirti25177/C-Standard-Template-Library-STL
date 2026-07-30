# 🎯 Set in C++

## 📖 What is a Set?

A **Set** is an associative container in the C++ Standard Template Library (STL) that stores **unique elements in sorted order**.

Internally, a `set` is implemented using a **Self-Balancing Binary Search Tree (Red-Black Tree)**.

It is defined in the `<set>` header file.

```cpp
#include <set>
```

---

# ✨ Why Use Set?

- ✅ Stores only unique elements.
- ✅ Automatically sorts elements in ascending order.
- ✅ Fast searching, insertion, and deletion.
- ✅ No need to sort manually.
- ✅ Widely used in DSA and Competitive Programming.

---

# 🛠️ Declaration

```cpp
set<data_type> set_name;
```

### Example

```cpp
set<int> st;
```

---

# 📌 Initialization

### Empty Set

```cpp
set<int> st;
```

---

### Initialize Using List

```cpp
set<int> st = {5, 2, 8, 1, 5, 2};
```

Output

```
1 2 5 8
```

> Duplicate elements are automatically removed.

---

# 📌 Traversing a Set

### Using Range-Based Loop

```cpp
for(auto x : st)
{
    cout << x << " ";
}
```

Output

```
1 2 5 8
```

---

### Using Iterator

```cpp
for(auto it = st.begin(); it != st.end(); it++)
{
    cout << *it << " ";
}
```

---

# 📌 Common Functions

## insert()

Inserts an element into the set.

```cpp
st.insert(10);
st.insert(20);
st.insert(30);
```

Time Complexity: **O(log n)**

---

## erase()

Removes an element.

```cpp
st.erase(20);
```

Time Complexity: **O(log n)**

---

## find()

Searches for an element.

```cpp
auto it = st.find(10);

if(it != st.end())
    cout << "Found";
else
    cout << "Not Found";
```

Time Complexity: **O(log n)**

---

## count()

Returns `1` if the element exists, otherwise `0`.

```cpp
cout << st.count(10);
```

Output

```
1
```

Time Complexity: **O(log n)**

---

## size()

Returns the number of elements.

```cpp
cout << st.size();
```

Time Complexity: **O(1)**

---

## empty()

Checks whether the set is empty.

```cpp
if(st.empty())
{
    cout << "Set is empty";
}
```

Time Complexity: **O(1)**

---

## clear()

Removes all elements.

```cpp
st.clear();
```

Time Complexity: **O(n)**

---

## swap()

Swaps two sets.

```cpp
set<int> st1, st2;

st1.swap(st2);
```

Time Complexity: **O(1)**

---

## lower_bound()

Returns an iterator to the **first element greater than or equal to** the given value.

```cpp
auto it = st.lower_bound(15);

cout << *it;
```

---

## upper_bound()

Returns an iterator to the **first element greater than** the given value.

```cpp
auto it = st.upper_bound(20);

cout << *it;
```

---

# 📌 Example Program

```cpp
#include<iostream>
#include<set>
using namespace std;

int main()
{
    set<int> st;

    st.insert(30);
    st.insert(10);
    st.insert(20);
    st.insert(10);

    for(auto x : st)
    {
        cout << x << " ";
    }

    return 0;
}
```

Output

```
10 20 30
```

---

# 📌 Iterators

```cpp
st.begin()
st.end()
st.rbegin()
st.rend()
st.cbegin()
st.cend()
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
| `size()` | `O(1)` |
| `empty()` | `O(1)` |
| `clear()` | `O(n)` |
| `swap()` | `O(1)` |

---

# 💾 Space Complexity

A set stores unique elements dynamically.

**Space Complexity:** `O(n)`

where **n** is the number of unique elements.

---

# 🚀 Advantages

- Stores only unique elements.
- Automatically keeps elements sorted.
- Fast searching, insertion, and deletion.
- No need to sort manually.
- Supports efficient range queries using `lower_bound()` and `upper_bound()`.

---

# ❌ Disadvantages

- Duplicate elements are not allowed.
- Slower than `unordered_set` on average.
- More memory usage due to tree structure.
- No indexing (`st[0]` is invalid).

---

# 📌 Applications of Set

- Removing duplicate elements.
- Maintaining sorted unique data.
- Searching efficiently.
- Competitive Programming.
- Range-based queries.
- Mathematical set operations.

---

# 📊 Vector vs Set

| Feature | Vector | Set |
|---------|--------|-----|
| Duplicate Elements | ✅ Allowed | ❌ Not Allowed |
| Order | Insertion Order | Sorted Order |
| Random Access | ✅ Yes | ❌ No |
| Search | `O(n)` | `O(log n)` |
| Insert | `O(1)` (at end) | `O(log n)` |

---

# 📊 Set vs Unordered Set

| Feature | Set | Unordered Set |
|---------|-----|---------------|
| Ordering | Sorted | Unsorted |
| Implementation | Red-Black Tree | Hash Table |
| Search | `O(log n)` | `O(1)` (Average) |
| Duplicate Elements | ❌ No | ❌ No |

---

# 📌 Key Points

- A `set` stores **unique elements**.
- Elements are **automatically sorted** in ascending order.
- Implemented using a **Red-Black Tree**.
- Searching, insertion, and deletion take **O(log n)** time.
- Does not support indexing.
- Supports `lower_bound()` and `upper_bound()`.

---

# 🎯 Interview Tip

`set` is one of the most commonly used STL containers in coding interviews.

You should know:
- `insert()`, `erase()`, `find()`, `count()`
- `lower_bound()` and `upper_bound()`
- Difference between **Set**, **Multiset**, and **Unordered Set**
- Time complexities
- Applications like **removing duplicates**, **sorted storage**, and **efficient searching**.
