# ⚙️ Functors in C++

## 📖 What are Functors?

A **Functor** (also called a **Function Object**) is an object that behaves like a function.

In C++, a class or structure becomes a functor when it **overloads the `operator()`**.

Functors are widely used in the C++ Standard Template Library (STL) with algorithms such as `sort()`, `find_if()`, `count_if()`, and containers like `priority_queue`.

It is defined in the `<functional>` header file.

```cpp
#include <functional>
```

---

# ✨ Why Use Functors?

- ✅ Can behave like normal functions.
- ✅ Can store data (state).
- ✅ Faster than function pointers in many cases.
- ✅ Widely used with STL algorithms.
- ✅ Improves code reusability.

---

# 🛠️ Basic Syntax

```cpp
class FunctorName
{
public:
    return_type operator()(parameters)
    {
        // code
    }
};
```

---

# 📌 Example 1: Simple Functor

```cpp
#include<iostream>
using namespace std;

class Square
{
public:
    int operator()(int x)
    {
        return x * x;
    }
};

int main()
{
    Square sq;

    cout << sq(5);

    return 0;
}
```

Output

```
25
```

Here, `sq(5)` internally calls:

```cpp
sq.operator()(5);
```

---

# 📌 Example 2: Functor with Two Parameters

```cpp
#include<iostream>
using namespace std;

class Add
{
public:
    int operator()(int a, int b)
    {
        return a + b;
    }
};

int main()
{
    Add sum;

    cout << sum(10,20);

    return 0;
}
```

Output

```
30
```

---

# 📌 Predefined STL Functors

The STL provides many built-in functors in the `<functional>` header.

| Functor | Description |
|----------|-------------|
| `greater<int>()` | Greater than |
| `less<int>()` | Less than |
| `plus<int>()` | Addition |
| `minus<int>()` | Subtraction |
| `multiplies<int>()` | Multiplication |
| `divides<int>()` | Division |
| `modulus<int>()` | Modulus |
| `equal_to<int>()` | Equality |
| `not_equal_to<int>()` | Not Equal |
| `logical_and<bool>()` | Logical AND |
| `logical_or<bool>()` | Logical OR |
| `logical_not<bool>()` | Logical NOT |

---

# 📌 Using `greater<int>()`

Sort in descending order.

```cpp
#include<iostream>
#include<vector>
#include<algorithm>
#include<functional>
using namespace std;

int main()
{
    vector<int> v = {5,2,8,1,3};

    sort(v.begin(), v.end(), greater<int>());

    for(int x : v)
        cout << x << " ";

    return 0;
}
```

Output

```
8 5 3 2 1
```

---

# 📌 Using `less<int>()`

Sort in ascending order.

```cpp
sort(v.begin(), v.end(), less<int>());
```

Output

```
1 2 3 5 8
```

---

# 📌 Using Functors with Priority Queue

### Max Heap (Default)

```cpp
priority_queue<int> pq;
```

---

### Min Heap

```cpp
priority_queue<int,
               vector<int>,
               greater<int>> pq;
```

---

# 📌 Custom Functor

```cpp
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;

class Descending
{
public:
    bool operator()(int a, int b)
    {
        return a > b;
    }
};

int main()
{
    vector<int> v = {4,1,8,2,5};

    sort(v.begin(), v.end(), Descending());

    for(int x : v)
        cout << x << " ";

    return 0;
}
```

Output

```
8 5 4 2 1
```

---

# 📌 Functors vs Functions

| Feature | Function | Functor |
|----------|----------|----------|
| Stores Data | ❌ No | ✅ Yes |
| Can Maintain State | ❌ No | ✅ Yes |
| Overloads `()` | ❌ No | ✅ Yes |
| STL Compatible | ✅ Yes | ✅ Yes |
| Performance | Good | Better in many cases |

---

# 📌 Common STL Algorithms Using Functors

```cpp
sort()
stable_sort()
find_if()
count_if()
remove_if()
for_each()
transform()
```

Example

```cpp
sort(v.begin(), v.end(), greater<int>());
```

---

# 📌 Common Predefined Functors

| Category | Functors |
|----------|----------|
| Comparison | `greater`, `less`, `equal_to`, `not_equal_to` |
| Arithmetic | `plus`, `minus`, `multiplies`, `divides`, `modulus` |
| Logical | `logical_and`, `logical_or`, `logical_not` |

---

# ⏱️ Time Complexity

Functors themselves do **not** have a fixed time complexity.

Their complexity depends on the STL algorithm using them.

Examples:

| Algorithm | Complexity |
|-----------|------------|
| `sort()` | `O(n log n)` |
| `find_if()` | `O(n)` |
| `count_if()` | `O(n)` |
| `remove_if()` | `O(n)` |

---

# 💾 Space Complexity

A functor object usually requires:

**Space Complexity:** `O(1)`

unless it stores additional data members.

---

# 🚀 Advantages

- Faster than function pointers.
- Can maintain internal state.
- Easy to reuse.
- Works seamlessly with STL.
- Improves performance and readability.

---

# ❌ Disadvantages

- Slightly more code than normal functions.
- Can be harder to understand for beginners.

---

# 📌 Applications of Functors

- Sorting with custom order.
- Custom comparators.
- Priority Queues.
- Searching with conditions.
- Counting based on conditions.
- Competitive Programming.
- Generic Programming.

---

# 📊 Function vs Functor vs Lambda

| Feature | Function | Functor | Lambda |
|---------|----------|----------|---------|
| Reusable | ✅ Yes | ✅ Yes | Limited |
| Stores State | ❌ No | ✅ Yes | ✅ Yes |
| Syntax | Simple | Medium | Short |
| Performance | Good | Excellent | Excellent |
| STL Support | ✅ Yes | ✅ Yes | ✅ Yes |

---

# 📌 Key Points

- A **Functor** is an object that behaves like a function.
- It is created by overloading the `operator()`.
- Functors are defined in the `<functional>` header.
- STL provides predefined functors such as `greater`, `less`, and `plus`.
- Functors are commonly used with `sort()`, `priority_queue`, and other STL algorithms.
- They can store data and maintain state, unlike normal functions.

---

# 🎯 Interview Tip

Functors are frequently asked in STL interviews.

You should know:
- What a functor is
- `operator()`
- `greater<int>()` and `less<int>()`
- Custom comparators
- Difference between **Functions**, **Functors**, and **Lambdas**
- Usage with **sort()**, **priority_queue**, and **STL algorithms**
