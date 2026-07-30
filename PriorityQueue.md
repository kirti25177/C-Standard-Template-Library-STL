# ⭐ Priority Queue in C++

## 📖 What is a Priority Queue?

A **Priority Queue** is a container adapter in the C++ Standard Template Library (STL) that stores elements based on their **priority** instead of the order in which they are inserted.

By default, a priority queue is implemented as a **Max Heap**, where the **largest element always remains at the top**.

It is defined in the `<queue>` header file.

```cpp
#include <queue>
```

---

# ✨ Why Use Priority Queue?

- ✅ Fast access to the highest (or lowest) priority element.
- ✅ Efficient insertion and deletion.
- ✅ Implemented using a Binary Heap.
- ✅ Widely used in DSA and Competitive Programming.

---

# 🏗️ Types of Priority Queue

## 1. Max Heap (Default)

The **largest element** has the highest priority.

```cpp
priority_queue<int> pq;
```

Example

```cpp
pq.push(10);
pq.push(50);
pq.push(20);

cout << pq.top();
```

Output

```
50
```

---

## 2. Min Heap

The **smallest element** has the highest priority.

```cpp
priority_queue<int, vector<int>, greater<int>> pq;
```

Example

```cpp
pq.push(10);
pq.push(50);
pq.push(20);

cout << pq.top();
```

Output

```
10
```

---

# 🛠️ Declaration

### Max Heap

```cpp
priority_queue<int> pq;
```

### Min Heap

```cpp
priority_queue<int, vector<int>, greater<int>> pq;
```

---

# 📌 Common Functions

## push()

Inserts an element into the priority queue.

```cpp
pq.push(30);
pq.push(10);
pq.push(50);
```

Time Complexity: **O(log n)**

---

## pop()

Removes the top element.

```cpp
pq.pop();
```

Time Complexity: **O(log n)**

---

## top()

Returns the highest priority element.

```cpp
cout << pq.top();
```

Time Complexity: **O(1)**

---

## size()

Returns the number of elements.

```cpp
cout << pq.size();
```

Time Complexity: **O(1)**

---

## empty()

Checks whether the priority queue is empty.

```cpp
if(pq.empty())
{
    cout << "Priority Queue is empty";
}
```

Time Complexity: **O(1)**

---

## swap()

Swaps two priority queues.

```cpp
priority_queue<int> pq1, pq2;

pq1.swap(pq2);
```

Time Complexity: **O(1)**

---

# 📌 Example Program (Max Heap)

```cpp
#include<iostream>
#include<queue>
using namespace std;

int main()
{
    priority_queue<int> pq;

    pq.push(20);
    pq.push(50);
    pq.push(10);
    pq.push(40);

    cout << "Top Element: " << pq.top() << endl;

    pq.pop();

    cout << "Top Element after Pop: " << pq.top();

    return 0;
}
```

Output

```
Top Element: 50
Top Element after Pop: 40
```

---

# 📌 Example Program (Min Heap)

```cpp
#include<iostream>
#include<queue>
using namespace std;

int main()
{
    priority_queue<int, vector<int>, greater<int>> pq;

    pq.push(20);
    pq.push(50);
    pq.push(10);
    pq.push(40);

    while(!pq.empty())
    {
        cout << pq.top() << " ";
        pq.pop();
    }

    return 0;
}
```

Output

```
10 20 40 50
```

---

# 📌 Traversing a Priority Queue

A priority queue **cannot be traversed directly** because it does not provide iterators.

To print all elements, create a copy.

```cpp
priority_queue<int> temp = pq;

while(!temp.empty())
{
    cout << temp.top() << " ";
    temp.pop();
}
```

Output

```
50 40 20 10
```

---

# 📌 Important Notes

- ✅ Default Priority Queue is a **Max Heap**.
- ✅ Use `greater<int>` to create a **Min Heap**.
- ❌ No indexing.
- ❌ No iterators.
- ❌ Only the top element is accessible.

---

# ⏱️ Time Complexity

| Operation | Complexity |
|-----------|------------|
| `push()` | `O(log n)` |
| `pop()` | `O(log n)` |
| `top()` | `O(1)` |
| `size()` | `O(1)` |
| `empty()` | `O(1)` |
| `swap()` | `O(1)` |

---

# 💾 Space Complexity

A priority queue stores elements dynamically.

**Space Complexity:** `O(n)`

where **n** is the number of elements stored.

---

# 🚀 Advantages

- Fast access to the highest or lowest priority element.
- Efficient insertion and deletion.
- Implemented using a Binary Heap.
- Frequently used in optimization problems.

---

# ❌ Disadvantages

- No random access.
- Cannot access middle elements.
- Cannot traverse directly.
- Insertion is slower than a normal queue (`O(log n)`).

---

# 📌 Applications of Priority Queue

- Dijkstra's Algorithm
- Prim's Algorithm
- Huffman Coding
- Heap Sort
- Task Scheduling
- CPU Scheduling
- Event Simulation
- K Largest / K Smallest Elements
- Merge K Sorted Lists

---

# 📊 Queue vs Priority Queue

| Feature | Queue | Priority Queue |
|---------|-------|----------------|
| Principle | FIFO | Priority Based |
| Top Element | First Inserted | Highest (or Lowest) Priority |
| `push()` | `O(1)` | `O(log n)` |
| `pop()` | `O(1)` | `O(log n)` |
| `top()` / `front()` | `O(1)` | `O(1)` |
| Implementation | Queue | Binary Heap |

---

# 📊 Max Heap vs Min Heap

| Feature | Max Heap | Min Heap |
|---------|----------|----------|
| Top Element | Largest | Smallest |
| Declaration | `priority_queue<int>` | `priority_queue<int, vector<int>, greater<int>>` |
| Use Case | Maximum element | Minimum element |

---

# 📌 Key Points

- A Priority Queue stores elements according to **priority**, not insertion order.
- By default, it behaves as a **Max Heap**.
- Use `greater<int>` to create a **Min Heap**.
- `top()` returns the highest priority element.
- `push()` and `pop()` take `O(log n)` time.
- Does not support indexing or iterators.

---

# 🎯 Interview Tip

Priority Queue is one of the **most important STL containers** for coding interviews.

You should know:
- Max Heap vs Min Heap
- `push()`, `pop()`, `top()`
- Time complexities
- Heap property
- Applications in **Dijkstra's Algorithm**, **Prim's Algorithm**, **Kth Largest Element**, **Merge K Sorted Lists**, and **Top K Frequent Elements**.
