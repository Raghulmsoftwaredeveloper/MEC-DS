# Linked List
A **Linked List** is a dynamic data structure used in **Data Structures and Algorithms (DSA)** and implemented using pointers in the **C Programming Language**.
Unlike arrays, linked list elements are **not stored in contiguous memory**. Instead, each element (node) contains a **pointer to the next node**.

---

# 1. What is a Linked List?

A **Linked List** is a collection of **nodes**, where each node contains:

1. **Data** – the value stored in the node
2. **Pointer (Link)** – address of the next node

### Structure of a Node

```c
struct node
{
    int data;
    struct node *next;
};
```

Here:

* `data` → stores the value
* `next` → stores the address of the next node

---

# 2. Linked List Representation

Example linked list:

```
10 → 20 → 30 → 40 → NULL
```

Memory representation:

```
[10 | 2000] → [20 | 3000] → [30 | 4000] → [40 | NULL]
```

Explanation:

* First part → data
* Second part → address of next node
* Last node points to **NULL**

---

# 3. Why Linked List is Needed

### Problems with Arrays

1. Fixed size
2. Memory wastage
3. Insertion and deletion require shifting elements

Example:

Array

```
10 20 30 40
```

Insert **25 between 20 and 30**

```
10 20 25 30 40
```

All elements must shift.

### Linked List Solution

```
10 → 20 → 25 → 30 → 40
```

Only pointer values change.

---

# 4. Types of Linked Lists

## 1. Singly Linked List

Each node contains **one pointer** to the next node.

```
10 → 20 → 30 → 40 → NULL
```

---

## 2. Doubly Linked List

Each node contains **two pointers**.

```
NULL ← 10 ⇄ 20 ⇄ 30 ⇄ 40 → NULL
```

Structure:

```c
struct node
{
    int data;
    struct node *prev;
    struct node *next;
};
```

---

## 3. Circular Linked List

The last node points back to the first node.

```
10 → 20 → 30 → 40
↑               ↓
← ← ← ← ← ← ← ←
```

---

# 4. Advantages of Linked List

1. Dynamic memory allocation
2. Efficient insertion and deletion
3. No memory wastage
4. Flexible size

---

# 5. Disadvantages of Linked List

1. Extra memory for pointers
2. Sequential access only
3. More complex than arrays
4. Slower traversal

---

# 6. Time Complexity

| Operation | Time Complexity |
| --------- | --------------- |
| Traversal | O(n)            |
| Insertion | O(1)            |
| Deletion  | O(1)            |
| Searching | O(n)            |

---

# 7. Applications of Linked List

Linked lists are used in:

* Implementing **Stacks**
* Implementing **Queues**
* Music playlists
* Browser history
* Undo/Redo operations
* Memory management

---

✅ **Important Linked List Programs in C (very common in exams)**

1. Create linked list
2. Display linked list
3. Insert at beginning
4. Insert at end
5. Insert at position
6. Delete from beginning
7. Delete from end
8. Delete specific node
9. Reverse linked list
10. Count number of nodes

