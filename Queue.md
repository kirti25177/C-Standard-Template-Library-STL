# 🚶 Queue in C++

## 📖 What is a Queue?

A **Queue** is a container adapter in the C++ Standard Template Library (STL) that follows the **FIFO (First In, First Out)** principle.

This means the **first element inserted is the first one to be removed**.

A queue allows insertion only from the **rear (back)** and deletion only from the **front**.

It is defined in the `<queue>` header file.

```cpp
#include <queue>
```

---

# ✨ Why Use Queue?

- ✅ Follows the FIFO principle.
- ✅ Fast insertion and deletion.
- ✅ Efficient for sequential processing.
- ✅ Widely used in scheduling and graph algorithms.

---

# 🛠️ Declaration

```cpp
queue<data_type> queue_name;
```

### Example

```cpp
queue<int> q;
```

---

# 📌 Working of a Queue

```
push(10)
push(20)
push(30)

Front                 Rear
  ↓                    ↓
+-----+-----+-----+
| 10  | 20  | 30  |
+-----+-----+-----+

pop()

Front          Rear
  ↓             ↓
+-----+-----+
| 20  | 30  |
+-----+-----+
```

---

# 📌 Common Functions

## push()

Adds an element at the rear of the queue.

```cpp
q.push(10);
q.push(20);
q.push(30);
```

Time Complexity: **O(1)**

---

## pop()

Removes the front element.

```cpp
q.pop();
```

Time Complexity: **O(1)**

---

## front()

Returns the front element.

```cpp
cout << q.front();
```

Output

```
10
```

Time Complexity: **O(1)**

---

## back()

Returns the rear element.

```cpp
cout << q.back();
```

Output

```
30
```

Time Complexity: **O(1)**

---

## size()

Returns the number of elements.

```cpp
cout << q.size();
```

Time Complexity: **O(1)**

---

## empty()

Checks whether the queue is empty.

```cpp
if(q.empty())
{
    cout << "Queue is empty";
}
```

Time Complexity: **O(1)**

---

## swap()

Swaps two queues.

```cpp
queue<int> q1, q2;

q1.swap(q2);
```

Time Complexity: **O(1)**

---

# 📌 Example Program

```cpp
#include<iostream>
#include<queue>
using namespace std;

int main()
{
    queue<int> q;

    q.push(10);
    q.push(20);
    q.push(30);

    cout << "Front Element: " << q.front() << endl;
    cout << "Rear Element: " << q.back() << endl;

    q.pop();

    cout << "Front Element after Pop: " << q.front();

    return 0;
}
```

Output

```
Front Element: 10
Rear Element: 30
Front Element after Pop: 20
```

---

# 📌 Traversing a Queue

A queue **cannot be traversed directly** because it does not provide iterators.

To print all elements, create a copy of the queue.

```cpp
queue<int> temp = q;

while(!temp.empty())
{
    cout << temp.front() << " ";
    temp.pop();
}
```

Output

```
10 20 30
```

---

# 📌 Important Notes

- ❌ No indexing (`q[0]` is invalid).
- ❌ No iterators (`begin()` and `end()` are not available).
- ❌ Middle elements cannot be accessed directly.
- ✅ Only the front and rear elements are accessible.

---

# ⏱️ Time Complexity

| Operation | Complexity |
|-----------|------------|
| `push()` | `O(1)` |
| `pop()` | `O(1)` |
| `front()` | `O(1)` |
| `back()` | `O(1)` |
| `size()` | `O(1)` |
| `empty()` | `O(1)` |
| `swap()` | `O(1)` |

---

# 💾 Space Complexity

A queue stores elements dynamically.

**Space Complexity:** `O(n)`

where **n** is the number of elements stored.

---

# 🚀 Advantages

- Simple implementation.
- Fast insertion and deletion.
- Efficient for FIFO operations.
- Widely used in scheduling and buffering.
- Frequently used in graph algorithms.

---

# ❌ Disadvantages

- No random access.
- Cannot access middle elements.
- Cannot traverse directly.
- Only the front and rear elements are accessible.

---

# 📌 Applications of Queue

- Breadth First Search (BFS)
- CPU Scheduling
- Printer Queue
- Task Scheduling
- Buffer Management
- Request Processing
- Call Center Systems
- Simulation Problems

---

# 📊 Queue vs Stack

| Feature | Queue | Stack |
|---------|-------|-------|
| Principle | FIFO | LIFO |
| Insertion | Rear | Top |
| Deletion | Front | Top |
| Accessible Element | Front & Rear | Top |

---

# 📌 Key Points

- Queue follows the **First In, First Out (FIFO)** principle.
- Insertion occurs at the **rear** using `push()`.
- Deletion occurs at the **front** using `pop()`.
- `front()` returns the first element.
- `back()` returns the last element.
- Queue does not support indexing or iterators.
- Most operations take **O(1)** time.

---

# 🎯 Interview Tip

A **queue** is one of the most commonly used data structures in coding interviews.

You should know:
- FIFO principle
- `push()`, `pop()`, `front()`, `back()`
- Time complexities
- Applications like **BFS**, **Level Order Traversal of Trees**, **Task Scheduling**, **Producer-Consumer Problems**, and **Simulation Problems**.
