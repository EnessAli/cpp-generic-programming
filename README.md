# C++ Generic Programming

Templates, function template specialization, and the `iter` algorithm — writing type-agnostic code that works uniformly across any type satisfying the required interface.

## Concepts Covered

### Function Templates
```cpp
template <typename T>
T max(T a, T b) { return (a > b) ? a : b; }

max(3, 7);         // T = int
max(3.14, 2.71);   // T = double
max(a, z);     // T = char
```

### Class Templates
```cpp
template <typename T>
class Array {
private:
    T      *_data;
    size_t  _size;
public:
    T       &operator[](size_t i);
    size_t   size() const;
};
```
Bounds-checked `operator[]` throws `std::exception` on out-of-range access.

### iter Algorithm
```cpp
template <typename T, typename F>
void iter(T *array, size_t len, F func);

// Usage
int arr[] = {1, 2, 3, 4, 5};
iter(arr, 5, [](int &x){ x *= 2; });
```

### Template Specialization
Full and partial specialization to handle edge cases (e.g., `void*`, `char*`).

## Build

```bash
make && ./ex02
```

## Tech Stack

`C++98` `Templates` `Generic Programming` `Template Specialization` `Makefile`

