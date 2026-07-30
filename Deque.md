# ↔️ Deque in C++

## 📖 What is a Deque?

A **Deque (Double Ended Queue)** is a sequence container in the C++ Standard Template Library (STL) that allows insertion and deletion of elements from **both the front and the back** efficiently.

Unlike a vector, a deque does **not** store elements in a single contiguous block of memory. Instead, it uses multiple memory blocks internally while still providing fast random access.

It is defined in the `<deque>` header file.

```cpp
#include <deque>
```

---

# ✨ Why Use Deque?

- ✅ Dynamic size
- ✅ Fast insertion and deletion at both ends
- ✅ Random access using indexing
- ✅ More flexible than a vector for front operations
- ✅ Commonly used to implement queues and sliding window algorithms

---

# 🛠️ Declaration

```cpp
deque<data_type> deque_name;
```

### Example

```cpp
deque<int> dq;
```

---

# 📌 Initialization

### Empty Deque

```cpp
deque<int> dq;
```

---

### Deque with Size

```cpp
deque<int> dq(5);
```

Output

```
0 0 0 0 0
```

---

### Deque with Initial Value

```cpp
deque<int> dq(5, 10);
```

Output

```
10 10 10 10 10
```

---

### Initialize using List

```cpp
deque<int> dq = {1,2,3,4,5};
```

---

### Copy a Deque

```cpp
deque<int> dq1 = {1,2,3};

deque<int> dq2(dq1);
```

---

# 📌 Accessing Elements

```cpp
deque<int> dq = {10,20,30};

cout << dq[0] << endl;
cout << dq.at(1) << endl;
cout << dq.front() << endl;
cout << dq.back() << endl;
```

Output

```
10
20
10
30
```

---

# 📌 Traversing a Deque

### Using Index

```cpp
for(int i = 0; i < dq.size(); i++)
{
    cout << dq[i] << " ";
}
```

---

### Using Range-Based Loop

```cpp
for(auto x : dq)
{
    cout << x << " ";
}
```

---

### Using Iterator

```cpp
for(auto it = dq.begin(); it != dq.end(); it++)
{
    cout << *it << " ";
}
```

---

# 📌 Common Functions

## push_back()

Adds an element at the end.

```cpp
dq.push_back(10);
```

Time Complexity: **O(1)**

---

## push_front()

Adds an element at the beginning.

```cpp
dq.push_front(5);
```

Time Complexity: **O(1)**

---

## pop_back()

Removes the last element.

```cpp
dq.pop_back();
```

Time Complexity: **O(1)**

---

## pop_front()

Removes the first element.

```cpp
dq.pop_front();
```

Time Complexity: **O(1)**

---

## front()

Returns the first element.

```cpp
cout << dq.front();
```

Time Complexity: **O(1)**

---

## back()

Returns the last element.

```cpp
cout << dq.back();
```

Time Complexity: **O(1)**

---

## at()

Accesses an element with bounds checking.

```cpp
cout << dq.at(2);
```

Time Complexity: **O(1)**

---

## size()

Returns the number of elements.

```cpp
cout << dq.size();
```

Time Complexity: **O(1)**

---

## empty()

Checks whether the deque is empty.

```cpp
if(dq.empty())
{
    cout << "Deque is empty";
}
```

Time Complexity: **O(1)**

---

## clear()

Removes all elements.

```cpp
dq.clear();
```

Time Complexity: **O(n)**

---

## insert()

Inserts an element at a specified position.

```cpp
dq.insert(dq.begin() + 2, 100);
```

Time Complexity: **O(n)**

---

## erase()

Removes an element from a specified position.

```cpp
dq.erase(dq.begin() + 1);
```

Time Complexity: **O(n)**

---

## resize()

Changes the size of the deque.

```cpp
dq.resize(10);
```

Time Complexity: **O(n)**

---

## swap()

Swaps two deques.

```cpp
dq1.swap(dq2);
```

Time Complexity: **O(1)**

---

# 📌 Capacity Functions

## size()

Returns the current number of elements.

```cpp
cout << dq.size();
```

---

## max_size()

Returns the maximum number of elements the deque can hold.

```cpp
cout << dq.max_size();
```

---

# 📌 Iterators

```cpp
dq.begin()
dq.end()
dq.rbegin()
dq.rend()
dq.cbegin()
dq.cend()
```

---

# 📌 Example Program

```cpp
#include<iostream>
#include<deque>
using namespace std;

int main()
{
    deque<int> dq;

    dq.push_back(20);
    dq.push_back(30);
    dq.push_front(10);

    for(auto x : dq)
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

# ⏱️ Time Complexity

| Operation | Complexity |
|-----------|------------|
| Access (`[]`, `at()`) | `O(1)` |
| `front()` | `O(1)` |
| `back()` | `O(1)` |
| `push_front()` | `O(1)` |
| `push_back()` | `O(1)` |
| `pop_front()` | `O(1)` |
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

A deque stores elements dynamically.

**Space Complexity:** `O(n)`

where **n** is the number of elements stored.

---

# 🚀 Advantages

- Dynamic size
- Fast insertion and deletion at both ends
- Supports random access
- More efficient than a vector for front operations
- No need to shift elements when inserting or deleting at the front

---

# ❌ Disadvantages

- Uses more memory than a vector
- Elements are not stored in a single contiguous memory block
- Slightly slower random access than a vector

---

# 📊 Vector vs Deque

| Feature | Vector | Deque |
|---------|--------|-------|
| Dynamic Size | ✅ | ✅ |
| Random Access | ✅ | ✅ |
| `push_back()` | `O(1)` | `O(1)` |
| `push_front()` | `O(n)` | `O(1)` |
| `pop_back()` | `O(1)` | `O(1)` |
| `pop_front()` | `O(n)` | `O(1)` |
| Memory | Contiguous | Non-contiguous |

---

# 📌 Key Points

- A deque stands for **Double Ended Queue**.
- Supports insertion and deletion from **both ends**.
- Provides **constant-time random access**.
- Use `front()` and `back()` to access the first and last elements.
- Ideal when both front and back operations are frequent.

---

# 🎯 Interview Tip

Use a **deque** when your algorithm requires:
- Frequent insertion and deletion from both ends.
- Sliding Window problems.
- Monotonic Queue problems.
- Implementing queues with efficient front and back operations.

A **vector** is generally preferred when most operations occur at the end, while a **deque** is the better choice when operations are needed at both the front and the back.
