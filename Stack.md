# 📚 Stack in C++

## 📖 What is a Stack?

A **Stack** is a container adapter in the C++ Standard Template Library (STL) that follows the **LIFO (Last In, First Out)** principle.

This means the **last element inserted is the first one to be removed**.

A stack allows insertion and deletion only from the **top**.

It is defined in the `<stack>` header file.

```cpp
#include <stack>
```

---

# ✨ Why Use Stack?

- ✅ Follows the LIFO principle.
- ✅ Fast insertion and deletion.
- ✅ Simple and efficient.
- ✅ Used in recursion, expression evaluation, and backtracking.

---

# 🛠️ Declaration

```cpp
stack<data_type> stack_name;
```

### Example

```cpp
stack<int> st;
```

---

# 📌 Working of a Stack

```
Push(30)

Top
 ↓
+-----+
| 30  |
+-----+
| 20  |
+-----+
| 10  |
+-----+

Pop()

Top
 ↓
+-----+
| 20  |
+-----+
| 10  |
+-----+
```

---

# 📌 Common Functions

## push()

Adds an element to the top of the stack.

```cpp
st.push(10);
st.push(20);
st.push(30);
```

Time Complexity: **O(1)**

---

## pop()

Removes the top element.

```cpp
st.pop();
```

Time Complexity: **O(1)**

---

## top()

Returns the top element.

```cpp
cout << st.top();
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
cout << st.size();
```

Time Complexity: **O(1)**

---

## empty()

Checks whether the stack is empty.

```cpp
if(st.empty())
{
    cout << "Stack is empty";
}
```

Time Complexity: **O(1)**

---

## swap()

Swaps two stacks.

```cpp
stack<int> st1, st2;

st1.swap(st2);
```

Time Complexity: **O(1)**

---

# 📌 Example Program

```cpp
#include<iostream>
#include<stack>
using namespace std;

int main()
{
    stack<int> st;

    st.push(10);
    st.push(20);
    st.push(30);

    cout << "Top Element: " << st.top() << endl;

    st.pop();

    cout << "Top Element after Pop: " << st.top();

    return 0;
}
```

Output

```
Top Element: 30
Top Element after Pop: 20
```

---

# 📌 Traversing a Stack

A stack **cannot be traversed directly** because it does not provide iterators.

To print all elements, create a copy of the stack.

```cpp
stack<int> temp = st;

while(!temp.empty())
{
    cout << temp.top() << " ";
    temp.pop();
}
```

Output

```
30 20 10
```

---

# 📌 Important Notes

- ❌ No indexing (`st[0]` is invalid).
- ❌ No iterators (`begin()` and `end()` are not available).
- ❌ Elements cannot be accessed except the top element.
- ✅ Only the top element can be inserted, removed, or accessed.

---

# ⏱️ Time Complexity

| Operation | Complexity |
|-----------|------------|
| `push()` | `O(1)` |
| `pop()` | `O(1)` |
| `top()` | `O(1)` |
| `size()` | `O(1)` |
| `empty()` | `O(1)` |
| `swap()` | `O(1)` |

---

# 💾 Space Complexity

A stack stores elements dynamically.

**Space Complexity:** `O(n)`

where **n** is the number of elements stored.

---

# 🚀 Advantages

- Simple implementation.
- Fast insertion and deletion.
- Efficient memory usage.
- Ideal for LIFO operations.
- Frequently used in DSA.

---

# ❌ Disadvantages

- No random access.
- Cannot access middle elements.
- Cannot traverse directly.
- Only the top element is accessible.

---

# 📌 Applications of Stack

- Function call management (Call Stack)
- Recursion
- Expression Evaluation
- Parentheses Matching
- Undo/Redo Operations
- Browser History
- Backtracking Algorithms
- Depth First Search (DFS)

---

# 📊 Stack vs Queue

| Feature | Stack | Queue |
|---------|-------|-------|
| Principle | LIFO | FIFO |
| Insertion | Top | Rear |
| Deletion | Top | Front |
| Accessible Element | Top | Front & Rear |

---

# 📌 Key Points

- Stack follows the **Last In, First Out (LIFO)** principle.
- Insertion and deletion occur only at the **top**.
- `push()` inserts an element.
- `pop()` removes the top element.
- `top()` accesses the top element.
- Stack does not support indexing or iterators.
- Most operations take **O(1)** time.

---

# 🎯 Interview Tip

A **stack** is one of the most commonly used data structures in coding interviews.

You should know:
- LIFO principle
- `push()`, `pop()`, `top()`
- Time complexities
- Applications like **DFS**, **Recursion**, **Balanced Parentheses**, **Next Greater Element**, **Largest Rectangle in Histogram**, and **Undo/Redo** functionality.
