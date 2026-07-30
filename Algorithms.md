# 🛠️ Algorithms in C++

## 📖 What are STL Algorithms?

The **C++ Standard Template Library (STL)** provides a collection of **built-in algorithms** that perform common operations like searching, sorting, counting, reversing, and more.

These algorithms work with **iterators**, making them compatible with most STL containers such as:

- `vector`
- `deque`
- `list`
- `set`
- `map`
- `unordered_set`
- `unordered_map`

Most STL algorithms are defined in the `<algorithm>` header file.

```cpp
#include <algorithm>
```

Some numeric algorithms are defined in:

```cpp
#include <numeric>
```

---

# ✨ Why Use STL Algorithms?

- ✅ Reduces code length.
- ✅ Optimized and efficient.
- ✅ Easy to read and maintain.
- ✅ Less chance of bugs.
- ✅ Widely used in coding interviews and competitive programming.

---

# 🛠️ Basic Syntax

Most STL algorithms follow this format:

```cpp
algorithm_name(start_iterator, end_iterator);
```

Example:

```cpp
sort(v.begin(), v.end());
```

Here,

- `v.begin()` → First element
- `v.end()` → One position after the last element

---

# 📌 Categories of STL Algorithms

STL algorithms are mainly divided into the following categories:

### 1️⃣ Sorting Algorithms

Used to arrange elements in ascending or descending order.

Examples:

- `sort()`
- `stable_sort()`
- `partial_sort()`

---

### 2️⃣ Searching Algorithms

Used to search for elements.

Examples:

- `find()`
- `binary_search()`
- `lower_bound()`
- `upper_bound()`

---

### 3️⃣ Counting Algorithms

Used to count elements.

Examples:

- `count()`
- `count_if()`

---

### 4️⃣ Modifying Algorithms

Used to modify container elements.

Examples:

- `copy()`
- `fill()`
- `replace()`
- `remove()`
- `reverse()`
- `rotate()`

---

### 5️⃣ Numeric Algorithms

Defined in `<numeric>`.

Examples:

- `accumulate()`
- `iota()`
- `partial_sum()`

---

### 6️⃣ Heap Algorithms

Used with heaps.

Examples:

- `make_heap()`
- `push_heap()`
- `pop_heap()`
- `sort_heap()`

---

### 7️⃣ Permutation Algorithms

Used to generate permutations.

Examples:

- `next_permutation()`
- `prev_permutation()`

---

### 8️⃣ Set Algorithms

Used on sorted ranges.

Examples:

- `set_union()`
- `set_intersection()`
- `set_difference()`

---

# 📌 Iterators Used in Algorithms

Algorithms work with iterators instead of indexes.

```cpp
v.begin()
v.end()
v.rbegin()
v.rend()
```

Example

```cpp
sort(v.begin(), v.end());
```

---

# 📌 Example Program

```cpp
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;

int main()
{
    vector<int> v = {5,2,8,1,3};

    sort(v.begin(), v.end());

    for(int x : v)
    {
        cout << x << " ";
    }

    return 0;
}
```

Output

```
1 2 3 5 8
```

---

# 📌 Most Frequently Used STL Algorithms

| Algorithm | Purpose |
|-----------|---------|
| `sort()` | Sort elements |
| `reverse()` | Reverse elements |
| `find()` | Search an element |
| `count()` | Count occurrences |
| `binary_search()` | Binary search |
| `lower_bound()` | First element ≥ value |
| `upper_bound()` | First element > value |
| `max_element()` | Largest element |
| `min_element()` | Smallest element |
| `accumulate()` | Sum of elements |
| `swap()` | Swap two values |
| `rotate()` | Rotate elements |
| `unique()` | Remove consecutive duplicates |
| `fill()` | Fill with a value |

---

# ⏱️ Common Time Complexities

| Algorithm | Time Complexity |
|-----------|-----------------|
| `sort()` | `O(n log n)` |
| `find()` | `O(n)` |
| `count()` | `O(n)` |
| `reverse()` | `O(n)` |
| `binary_search()` | `O(log n)` |
| `lower_bound()` | `O(log n)` |
| `upper_bound()` | `O(log n)` |
| `accumulate()` | `O(n)` |
| `max_element()` | `O(n)` |
| `min_element()` | `O(n)` |

---

# 💾 Space Complexity

Most STL algorithms use:

**Space Complexity:** `O(1)` (Auxiliary Space)

Some algorithms (like `stable_sort()`) may require additional memory.

---

# 📌 Advantages

- Optimized implementations.
- Easy to use.
- Reduces coding effort.
- Works with most STL containers.
- Improves code readability.
- Frequently used in interviews.

---

# ❌ Limitations

- Some algorithms require sorted data.
- Not all algorithms work with every container.
- Certain algorithms require specific iterator types.

---

# 📌 Header Files

| Header File | Algorithms |
|-------------|------------|
| `<algorithm>` | Most STL algorithms |
| `<numeric>` | Numeric algorithms |

---

# 📌 Key Points

- STL algorithms are predefined functions.
- Most algorithms are available in `<algorithm>`.
- Numeric algorithms are available in `<numeric>`.
- Algorithms work using **iterators**.
- They are optimized and efficient.
- Learning STL algorithms can significantly reduce coding time in interviews and competitive programming.

---

# 🎯 Interview Tip

The most commonly asked STL algorithms in coding interviews are:

- `sort()`
- `find()`
- `reverse()`
- `binary_search()`
- `lower_bound()`
- `upper_bound()`
- `count()`
- `max_element()`
- `min_element()`
- `accumulate()`
- `next_permutation()`
- `unique()`

Master these algorithms first before exploring the advanced STL algorithms.
