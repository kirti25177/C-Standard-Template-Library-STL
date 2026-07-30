# 🔁 Iterators in C++

## 📖 What is an Iterator?

An **iterator** is an object that acts like a **pointer** and is used to traverse elements of STL containers such as `vector`, `list`, `set`, `map`, etc.

Instead of accessing elements using indices, iterators provide a generic way to access elements in any STL container.

---

# ✨ Why Use Iterators?

- ✅ Traverse STL containers efficiently.
- ✅ Work with all STL algorithms.
- ✅ Provide a uniform way to access container elements.
- ✅ Required for containers like `set` and `map` (which do not support indexing).

---

# 🛠️ Syntax

```cpp
container<data_type>::iterator iterator_name;
```

### Example

```cpp
vector<int>::iterator it;
```

Using `auto` (Recommended)

```cpp
auto it = v.begin();
```

---

# 📌 begin()

Returns an iterator pointing to the **first element**.

```cpp
vector<int> v = {10,20,30};

auto it = v.begin();

cout << *it;
```

Output

```
10
```

---

# 📌 end()

Returns an iterator pointing **one position after the last element**.

```cpp
auto it = v.end();
```

> **Note:** `end()` does **not** point to the last element.

```cpp
cout << *(v.end()-1);
```

Output

```
30
```

---

# 📌 rbegin()

Returns a reverse iterator pointing to the **last element**.

```cpp
auto it = v.rbegin();

cout << *it;
```

Output

```
30
```

---

# 📌 rend()

Returns a reverse iterator pointing **before the first element**.

```cpp
auto it = v.rend();
```

Used while traversing in reverse.

---

# 📌 Traversing Using Iterators

```cpp
vector<int> v = {10,20,30,40};

for(auto it = v.begin(); it != v.end(); it++)
{
    cout << *it << " ";
}
```

Output

```
10 20 30 40
```

---

# 📌 Reverse Traversal

```cpp
for(auto it = v.rbegin(); it != v.rend(); it++)
{
    cout << *it << " ";
}
```

Output

```
40 30 20 10
```

---

# 📌 Iterator Arithmetic

```cpp
vector<int> v = {10,20,30,40};

auto it = v.begin();

cout << *it << endl;

it++;

cout << *it << endl;

it += 2;

cout << *it;
```

Output

```
10
20
40
```

---

# 📌 Accessing Elements

```cpp
cout << *it;
```

The `*` operator is called the **dereference operator**.

It accesses the value stored at the iterator's position.

---

# 📌 const_iterator

A constant iterator cannot modify elements.

```cpp
vector<int>::const_iterator it = v.begin();
```

or

```cpp
auto it = v.cbegin();
```

---

# 📌 cbegin() and cend()

```cpp
auto it = v.cbegin();
auto last = v.cend();
```

These return constant iterators.

---

# 📌 Iterator with List

```cpp
list<int> l = {10,20,30};

for(auto it = l.begin(); it != l.end(); it++)
{
    cout << *it << " ";
}
```

---

# 📌 Iterator with Set

```cpp
set<int> s = {5,2,8};

for(auto it = s.begin(); it != s.end(); it++)
{
    cout << *it << " ";
}
```

Output

```
2 5 8
```

---

# 📌 Iterator with Map

```cpp
map<int,string> mp;

mp[1] = "One";
mp[2] = "Two";

for(auto it = mp.begin(); it != mp.end(); it++)
{
    cout << it->first << " "
         << it->second << endl;
}
```

Output

```
1 One
2 Two
```

---

# 📌 Types of Iterators

| Iterator | Description |
|----------|-------------|
| `begin()` | First element |
| `end()` | One past the last element |
| `rbegin()` | Last element |
| `rend()` | Before the first element |
| `cbegin()` | Constant iterator to first element |
| `cend()` | Constant iterator to one past the last element |

---

# ⏱️ Time Complexity

| Operation | Complexity |
|-----------|------------|
| `begin()` | `O(1)` |
| `end()` | `O(1)` |
| `rbegin()` | `O(1)` |
| `rend()` | `O(1)` |
| Increment (`++it`) | `O(1)` |
| Dereference (`*it`) | `O(1)` |

---

# 💾 Space Complexity

Using an iterator requires only constant extra memory.

**Space Complexity:** `O(1)`

---

# 🚀 Advantages

- Works with all STL containers.
- Simplifies traversal.
- Compatible with STL algorithms.
- Safer and more flexible than indexing.

---

# ❌ Limitations

- Not all iterators support random access.
- Containers like `list`, `set`, and `map` do not allow indexing.
- Some operations (e.g., `it + 1`) are only valid for random access iterators like `vector`.

---

# 📌 Key Points

- An iterator behaves like a pointer.
- Use `*it` to access the value.
- Use `it->member` to access members of objects or pairs.
- `begin()` points to the first element.
- `end()` points one position after the last element.
- `rbegin()` and `rend()` are used for reverse traversal.
- Prefer `auto` to declare iterators.

---

# 🎯 Interview Tip

You should know:
- `begin()` vs `end()`
- `rbegin()` vs `rend()`
- `cbegin()` vs `begin()`
- `*it` vs `it->first`
- Iterator traversal for `vector`, `set`, and `map`
- Which containers support random access iterators (`vector`, `deque`) and which do not (`list`, `set`, `map`)
