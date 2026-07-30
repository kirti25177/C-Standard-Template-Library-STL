# 📋 List in C++

## 📖 What is a List?

A **list** is a sequence container in the C++ Standard Template Library (STL) that stores elements in a **doubly linked list**.

Unlike a vector, elements are **not stored in contiguous memory**. Each element contains pointers to both its previous and next elements.

It is defined in the `<list>` header file.

```cpp
#include <list>
```

---

# ✨ Why Use List?

- ✅ Fast insertion and deletion at any position.
- ✅ Dynamic size.
- ✅ Efficient front and back operations.
- ✅ No reallocation when elements are inserted.

---

# 🛠️ Declaration

```cpp
list<data_type> list_name;
```

### Example

```cpp
list<int> l;
```

---

# 📌 Initialization

### Empty List

```cpp
list<int> l;
```

---

### List with Size

```cpp
list<int> l(5);
```

Output

```
0 0 0 0 0
```

---

### List with Initial Value

```cpp
list<int> l(5, 10);
```

Output

```
10 10 10 10 10
```

---

### Initialize using List

```cpp
list<int> l = {1,2,3,4,5};
```

---

# 📌 Traversing a List

```cpp
list<int> l = {10,20,30,40};

for(auto x : l)
{
    cout << x << " ";
}
```

Output

```
10 20 30 40
```

---

### Using Iterator

```cpp
for(auto it = l.begin(); it != l.end(); it++)
{
    cout << *it << " ";
}
```

---

# 📌 Common Functions

## push_back()

Adds an element at the end.

```cpp
l.push_back(50);
```

Time Complexity: **O(1)**

---

## push_front()

Adds an element at the beginning.

```cpp
l.push_front(5);
```

Time Complexity: **O(1)**

---

## pop_back()

Removes the last element.

```cpp
l.pop_back();
```

Time Complexity: **O(1)**

---

## pop_front()

Removes the first element.

```cpp
l.pop_front();
```

Time Complexity: **O(1)**

---

## front()

Returns the first element.

```cpp
cout << l.front();
```

Time Complexity: **O(1)**

---

## back()

Returns the last element.

```cpp
cout << l.back();
```

Time Complexity: **O(1)**

---

## size()

Returns the number of elements.

```cpp
cout << l.size();
```

Time Complexity: **O(1)**

---

## empty()

Checks whether the list is empty.

```cpp
if(l.empty())
```

Time Complexity: **O(1)**

---

## clear()

Removes all elements.

```cpp
l.clear();
```

Time Complexity: **O(n)**

---

## insert()

Inserts an element before a given iterator.

```cpp
auto it = l.begin();
advance(it, 2);

l.insert(it, 100);
```

Time Complexity: **O(1)** (after reaching the iterator)

---

## erase()

Removes an element.

```cpp
auto it = l.begin();
advance(it, 1);

l.erase(it);
```

Time Complexity: **O(1)** (after reaching the iterator)

---

## remove()

Removes all occurrences of a value.

```cpp
l.remove(10);
```

Time Complexity: **O(n)**

---

## reverse()

Reverses the list.

```cpp
l.reverse();
```

Time Complexity: **O(n)**

---

## sort()

Sorts the list.

```cpp
l.sort();
```

Time Complexity: **O(n log n)**

---

## unique()

Removes consecutive duplicate elements.

```cpp
l.unique();
```

Time Complexity: **O(n)**

---

# 📌 Iterators

```cpp
l.begin()
l.end()
l.rbegin()
l.rend()
```

---

# 📌 Example Program

```cpp
#include<iostream>
#include<list>
using namespace std;

int main()
{
    list<int> l;

    l.push_back(10);
    l.push_back(20);
    l.push_front(5);

    for(auto x : l)
    {
        cout << x << " ";
    }

    return 0;
}
```

Output

```
5 10 20
```

---

# ⏱️ Time Complexity

| Operation | Complexity |
|-----------|------------|
| `push_front()` | `O(1)` |
| `push_back()` | `O(1)` |
| `pop_front()` | `O(1)` |
| `pop_back()` | `O(1)` |
| `front()` | `O(1)` |
| `back()` | `O(1)` |
| `insert()` | `O(1)` (after iterator) |
| `erase()` | `O(1)` (after iterator) |
| `remove()` | `O(n)` |
| `reverse()` | `O(n)` |
| `sort()` | `O(n log n)` |
| `unique()` | `O(n)` |
| `size()` | `O(1)` |
| `clear()` | `O(n)` |

---

# 💾 Space Complexity

A list stores each element along with two pointers (previous and next).

**Space Complexity:** `O(n)`

---

# 🚀 Advantages

- Fast insertion and deletion.
- Dynamic size.
- No memory reallocation.
- Efficient front and back operations.

---

# ❌ Disadvantages

- No random access.
- Cannot use indexing (`l[0]` is invalid).
- Uses more memory than a vector because of extra pointers.
- Poor cache performance compared to vectors.

---

# 📌 Vector vs List

| Feature | Vector | List |
|---------|--------|------|
| Memory Layout | Contiguous | Non-contiguous |
| Random Access | ✅ Yes | ❌ No |
| Insertion at End | `O(1)` | `O(1)` |
| Insertion in Middle | `O(n)` | `O(1)` (after iterator) |
| Deletion in Middle | `O(n)` | `O(1)` (after iterator) |
| Cache Friendly | ✅ Yes | ❌ No |

---

# 📌 Key Points

- `list` is implemented as a **doubly linked list**.
- Supports fast insertion and deletion.
- Does not support indexing.
- Use iterators to traverse a list.
- Best suited when frequent insertions and deletions are required.

---

# 🎯 Interview Tip

Use a **vector** when you need **fast random access**.

Use a **list** when your program performs **frequent insertions and deletions**, especially in the middle of the container.
