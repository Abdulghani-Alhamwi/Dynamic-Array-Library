# 🗃️ Dynamic Array Library

A **type-safe**, heap-allocated dynamic array container built from scratch in C++ using class templates — no STL, no shortcuts.

![C++](https://img.shields.io/badge/C++-blue?logo=cplusplus&logoColor=white)
![Project Template](https://img.shields.io/badge/Project%20Template-Ready-purple)
---

## ✨ Features :

| # | Feature | Detail |
|---|---------|--------|
| 🔁 | Dynamic Resizing | Grow or shrink the array at runtime |
| 🔃 | In-place Reversal | Reverse all elements without a second container |
| 🎯 | Index-based Access | Get and set any element by index |
| ✚ | Flexible Insertion | Insert at start, end, before or after any index |
| − | Targeted Deletion | Delete by index, by value, first, or last |
| 🔍 | Linear Search | Find the index of any value |
| 🧹 | Clear | Reset the array to zero elements |
| 📋 | Print | Dump all elements to stdout |
---
## 🚀 Getting Started :

This is a **header-only** library. Just drop the file into your project and include it.

```cpp
#include "clsDynamicArray.h"
```

---

## 🧩 Usage Examples :

### Create & Populate :

```cpp
clsDynamicArray<int> arr(5);

arr.SetItem(0, 10);
arr.SetItem(1, 20);
arr.SetItem(2, 30);
arr.SetItem(3, 40);
arr.SetItem(4, 50);

arr.PrintList(); // 10 20 30 40 50
```

### ✚ Insert Elements :

```cpp
arr.InsertAtBeginning(0);   // Insert 0 at index 0
arr.InsertAtEnd(60);         // Append 60
arr.InsertAt(3, 99);         // Insert 99 at index 3
arr.InsertAfter(2, 77);      // Insert 77 after index 2
arr.InsertBefore(1, 55);     // Insert 55 before index 1
```

### − Delete Elements :

```cpp
arr.DeleteFirstItem();       // Remove first element
arr.DeleteLastItem();        // Remove last element
arr.DeleteItemAt(2);         // Remove element at index 2
arr.DeleteItem(99);          // Remove first occurrence of value 99
```

### 🔍 Search & Retrieve :

```cpp
int idx = arr.Find(30);      // Returns index of 30, or -1
int val = arr.GetItem(2);    // Returns element at index 2
```

### 🔁 Resize & Reverse :

```cpp
arr.Resize(10);              // Expand to 10 slots
arr.Reverse();               // Reverse the array in place
```

### 📊 Utility ;

```cpp
cout << arr.Size();          // Number of elements
cout << arr.IsEmpty();       // true / false
arr.Clear();                 // Reset to empty

// Element access
T       GetItem(int index);
bool    SetItem(int index, T value);
int     Size();
bool    IsEmpty();

// Insertion
bool    InsertAt(int index, T value);
void    InsertAtBeginning(int value);
bool    InsertAtEnd(T value);
bool    InsertBefore(int index, T value);
bool    InsertAfter(int index, T value);

// Deletion
bool    DeleteItemAt(int index);
void    DeleteFirstItem();
void    DeleteLastItem();
bool    DeleteItem(T value);

// Utilities
int     Find(T value);
void    Resize(int newSize);
void    Reverse();
void    Clear();
void    PrintList();
```

---

## ⚙️ Design Notes :

- ♻️ **Memory is managed manually** — `new` and `delete[]` are used explicitly; the destructor frees the array on scope exit.
- 🔒 **Bounds-checked** — `SetItem`, `DeleteItemAt`, and `InsertAt` return `false` on out-of-range indices instead of causing undefined behaviour.
- 🧬 **Template-generic** — Works with any copyable type: `int`, `double`, `std::string`, custom structs.
- 📦 **Header-only** — Zero build configuration required.

---
