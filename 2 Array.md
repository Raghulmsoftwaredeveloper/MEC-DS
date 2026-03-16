# Array
An **Array** is one of the most basic data structures in the **C Programming Language**. It stores **multiple values of the same data type in contiguous memory locations** and allows access using an **index**.

---

# 1. What is an Array?

An **array** is a collection of elements of the **same data type** stored in **continuous memory locations**.

Example:

```c
int arr[5] = {10,20,30,40,50};
```

Here:

* `arr` → array name
* `5` → size of the array
* `10,20,30,40,50` → elements

---

# 2. Array Representation

Example array:

```
Index:   0   1   2   3   4
Value:  10  20  30  40  50
```

Memory layout:

```
arr[0] → 10
arr[1] → 20
arr[2] → 30
arr[3] → 40
arr[4] → 50
```

Accessing elements:

```c
printf("%d", arr[2]);
```

Output

```
30
```

---

# 3. Types of Arrays

## 1. One-Dimensional Array (1D)

A simple list of elements.

Example:

```c
int arr[5] = {1,2,3,4,5};
```

Program Example:

```c
#include<stdio.h>

int main()
{
    int arr[5] = {10,20,30,40,50};

    for(int i=0;i<5;i++)
    {
        printf("%d ",arr[i]);
    }
}
```

Output

```
10 20 30 40 50
```

---

## 2. Two-Dimensional Array (2D)

Used to store **matrix or table data**.

Example:

```c
int arr[2][3] = {
    {1,2,3},
    {4,5,6}
};
```

Memory representation:

```
1 2 3
4 5 6
```

Program:

```c
#include<stdio.h>

int main()
{
    int arr[2][3] = {{1,2,3},{4,5,6}};

    for(int i=0;i<2;i++)
    {
        for(int j=0;j<3;j++)
        {
            printf("%d ",arr[i][j]);
        }
        printf("\n");
    }
}
```

---

## 3. Multi-Dimensional Array

More than two dimensions.

Example:

```c
int arr[2][2][2];
```

Used in:

* 3D graphics
* scientific computations

---

# 4. Array Declaration

Syntax:

```c
datatype array_name[size];
```

Example:

```c
int arr[10];
float marks[5];
char name[20];
```

---

# 5. Array Initialization

### Method 1

```c
int arr[5] = {1,2,3,4,5};
```

### Method 2

```c
int arr[] = {1,2,3,4,5};
```

Compiler automatically calculates size.

### Method 3

```c
int arr[5] = {1,2};
```

Remaining values become **0**.

Output

```
1 2 0 0 0
```

---

# 6. Array Operations

Common operations:

1. Traversal
2. Insertion
3. Deletion
4. Searching
5. Updating

---

# 7. Traversal

Accessing each element one by one.

Example:

```c
for(int i=0;i<n;i++)
{
    printf("%d",arr[i]);
}
```

Time Complexity:

```
O(n)
```

---

# 8. Insertion in Array

Example:

Initial array

```
10 20 30 40
```

Insert **25 at position 2**

Result

```
10 20 25 30 40
```

Steps:

1. Shift elements right
2. Insert new value

Program:

```c
#include<stdio.h>

int main()
{
    int arr[10] = {10,20,30,40};
    int n=4,pos=2,val=25;

    for(int i=n;i>pos;i--)
    {
        arr[i]=arr[i-1];
    }

    arr[pos]=val;
    n++;

    for(int i=0;i<n;i++)
        printf("%d ",arr[i]);
}
```

Output

```
10 20 25 30 40
```

---

# 9. Deletion in Array

Example:

```
10 20 30 40
```

Delete **20**

Result

```
10 30 40
```

Program:

```c
#include<stdio.h>

int main()
{
    int arr[5]={10,20,30,40};
    int n=4,pos=1;

    for(int i=pos;i<n-1;i++)
    {
        arr[i]=arr[i+1];
    }

    n--;

    for(int i=0;i<n;i++)
        printf("%d ",arr[i]);
}
```

---

# 10. Searching in Array

## Linear Search

Search element one by one.

Example:

```c
for(int i=0;i<n;i++)
{
    if(arr[i]==key)
    {
        printf("Found");
    }
}
```

Time Complexity

```
O(n)
```

---

## Binary Search

Works only for **sorted arrays**.

Example:

```c
while(low<=high)
{
    mid=(low+high)/2;

    if(arr[mid]==key)
        return mid;
    else if(arr[mid]<key)
        low=mid+1;
    else
        high=mid-1;
}
```

Time Complexity

```
O(log n)
```

---

# 11. Advantages of Array

1. Fast access using index
2. Easy to implement
3. Efficient memory usage
4. Useful for matrices and tables

---

# 12. Disadvantages of Array

1. Fixed size
2. Insertion and deletion costly
3. Memory wastage
4. Cannot store different data types

---

# 13. Time Complexity of Array Operations

| Operation | Complexity |
| --------- | ---------- |
| Access    | O(1)       |
| Traversal | O(n)       |
| Insertion | O(n)       |
| Deletion  | O(n)       |
| Searching | O(n)       |

---

# 14. Applications of Arrays

Arrays are used in:

* Matrix operations
* Image processing
* Sorting algorithms
* Searching algorithms
* Implementing stacks and queues

---

# 15. How Arrays are Stored in Memory

In C, array elements are stored in **contiguous memory locations** (one after another).

Example:

```c
int arr[5] = {10,20,30,40,50};
```

Memory layout (assuming integer size = **4 bytes**):

```
Index    Value    Address
arr[0]    10      1000
arr[1]    20      1004
arr[2]    30      1008
arr[3]    40      1012
arr[4]    50      1016
```

Here:

* Base Address = **1000**
* Each element takes **4 bytes**

So every next element increases by **4 bytes**.

---

# 16. Address Calculation Formula (1D Array)

Formula:

```
Address of arr[i] = Base Address + (i × size of data type)
```

Where:

* **Base Address** = address of first element
* **i** = index
* **size of data type** = memory size of element

---

# 17. Example Problem

Array:

```
int arr[5]
```

Given:

```
Base Address = 2000
Size of int = 4 bytes
Find address of arr[3]
```

Using formula:

```
Address = Base + (i × size)
```

Calculation:

```
Address = 2000 + (3 × 4)
Address = 2000 + 12
Address = 2012
```

Final answer:

```
Address of arr[3] = 2012
```

---

# 18. Pointer View of Arrays

In C:

```
arr[i] = *(arr + i)
```

Example:

```c
printf("%d", *(arr+2));
```

Output:

```
30
```

Because:

```
*(arr+2) = arr[2]
```

---

# 19. Address Using Pointer Arithmetic

Example program:

```c
#include<stdio.h>

int main()
{
    int arr[5] = {10,20,30,40,50};

    for(int i=0;i<5;i++)
    {
        printf("%p\n",&arr[i]);
    }
}
```

Example Output:

```
1000
1004
1008
1012
1016
```

Addresses increase by **4 bytes**.

---

# 20. Address Formula for 2D Array

A **2D array** is stored in **row-major order** in C.

Example:

```
int arr[3][3]
```

Matrix:

```
1 2 3
4 5 6
7 8 9
```

Memory storage:

```
1 2 3 4 5 6 7 8 9
```

---

# 21. Address Calculation Formula for 2D Array

Row-major order formula:

```
Address(arr[i][j]) =
Base Address + ((i × number_of_columns + j) × size)
```

Where:

* **i** = row number
* **j** = column number
* **size** = size of data type

---

# 22. Example of 2D Address Calculation

Given:

```
int arr[3][3]
Base Address = 1000
Size of int = 4 bytes
Find address of arr[2][1]
```

Step 1

```
i = 2
j = 1
columns = 3
```

Step 2

```
Address = 1000 + ((2 × 3 + 1) × 4)
```

Step 3

```
Address = 1000 + ((6 + 1) × 4)
Address = 1000 + (7 × 4)
Address = 1000 + 28
Address = 1028
```

Final Answer

```
Address of arr[2][1] = 1028
```

---

# 23. Important Points for Exams

1. Arrays are stored in **contiguous memory locations**
2. **Base address = address of first element**
3. Address increases by **size of data type**
4. **2D arrays use row-major order in C**
5. `arr[i]` is equal to `*(arr+i)`

---

# 24. Common Viva Questions

**Q1:** What is base address?
Answer: Address of first element of array.

**Q2:** Why arrays are fast?
Answer: Because elements are stored in contiguous memory.

**Q3:** What does `arr` represent?
Answer: Address of the first element.

**Q4:** What is `*(arr+3)`?
Answer:

```
arr[3]
```

---
