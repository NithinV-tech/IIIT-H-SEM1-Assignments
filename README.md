#Sparse Matrix Implementation in C++

This README provides an overview and guide for the sparse matrix implementation in C++. The code includes two main approaches for storing and manipulating sparse matrices: one using a sparse array and the other using a linked list. Below, we will cover the details of both implementations and how to use them.

## Table of Contents

1. **Overview**
2. **Data Structures**

   * Sparse Array Class
   * Linked List Class
3. **Operations**

   * Insertion of elements
   * Displaying the matrix
   * Transposition
   * Matrix Operations (Addition, Multiplication)
4. **Usage**
5. **Compiling and Running the Code**
6. **Examples**
7. **Conclusion**

---

## 1. Overview

This program demonstrates the use of sparse matrices, which store only non-zero elements to save memory. Sparse matrices are used for efficient storage and computation in problems with large, mostly-zero matrices (such as graph representations, image processing, etc.).

The program is flexible, supporting both linked list-based and array-based sparse matrix representations. It provides the following functionalities:

* **Matrix Operations**: Addition, Multiplication, and Transposition.
* **Sorting**: Sorting matrix elements based on row and column indices.
* **Dynamic Storage**: Automatically resizes arrays when the capacity is reached.

---

## 2. Data Structures

### Sparse Array Class (`sparsearr`)

This class is used to represent a sparse matrix using a 2D array of pointers. Each element in the matrix is stored in a 3-element array that stores:

1. Row index
2. Column index
3. The non-zero value at that position

The `sparsearr` class provides methods to:

* Insert elements into the matrix.
* Display the matrix in its original form and transposed form.
* Sort the matrix elements.
* Perform matrix operations like addition, multiplication, and transposition.

### Linked List Class (`ll`)

This class represents the sparse matrix using a linked list of `Node` objects. Each node contains:

* The data value.
* The row index (`r`).
* The column index (`c`).

The `ll` class supports:

* Insertion of nodes (matrix elements).
* Displaying the matrix.
* Matrix transposition.
* Merging lists (for operations like matrix addition and multiplication).

---

## 3. Operations

### Insertion of Elements

#### Sparse Array (`sparsearr`)

You can insert a non-zero element into the sparse matrix using the `insertnodearr` method, which inserts elements with row and column indices, along with the value at that position.

#### Linked List (`ll`)

In the linked list implementation, the `insertnode` method is used to insert matrix elements, where each node contains the matrix value and its row and column indices.

### Displaying the Matrix

Both the sparse array and linked list provide methods to display the matrix. The `display` method prints the matrix in its original form, while `displaytrans` shows the transposed matrix.

### Transposition

* **Sparse Array**: Transposition is achieved by swapping the row and column indices.
* **Linked List**: A new linked list is created with the rows and columns swapped and the result is displayed.

### Matrix Operations

#### Addition

Both implementations support matrix addition. The program adds corresponding elements from two sparse matrices, creating a new matrix that holds the result.

#### Multiplication

Matrix multiplication is implemented by multiplying corresponding elements and summing them up for each position. The result is stored in a new matrix.

---

## 4. Usage

### Input Format

The program expects the following input format:

1. The number of test cases (`t`).
2. The operation to perform (`op`), which can be:

   * `1`: Matrix Addition
   * `2`: Matrix Transposition
   * `3`: Matrix Multiplication
3. The dimensions of the first matrix (`n1`, `m1`).
4. The matrix elements (row by row, where each element is space-separated).
5. If `op == 1` or `op == 3`, input the dimensions and elements for the second matrix.

### Example Usage

#### Example 1: Matrix Addition

```
Input:
1
1
3 3
1 2 3
4 5 6
7 8 9
3 3
1 1 1
1 1 1
1 1 1
```

#### Example 2: Matrix Multiplication

```
Input:
1
3
2 3
1 2 3
4 5 6
3 2
1 2
3 4
```

---

## 5. Compiling and Running the Code

To compile the C++ program, follow these steps:

1. Save the program in a file called `sparse_matrix.cpp`.
2. Use the following command to compile:

   ```
   g++ -o sparse_matrix sparse_matrix.cpp
   ```
3. Run the program with:

   ```
   ./sparse_matrix
   ```

---

## 6. Examples

### Example 1: Matrix Addition

```
Input:
1
1
3 3
1 2 3
4 5 6
7 8 9
3 3
1 1 1
1 1 1
1 1 1
```

**Output:**

```
Matrix 1:
1 2 3
4 5 6
7 8 9

Matrix 2:
1 1 1
1 1 1
1 1 1

Result of Addition:
2 3 4
5 6 7
8 9 10
```

### Example 2: Matrix Multiplication

```
Input:
1
3
2 3
1 2 3
4 5 6
3 2
1 2
3 4
```

**Output:**

```
Matrix 1:
1 2 3
4 5 6

Matrix 2:
1 2
3 4

Result of Multiplication:
14 20
32 44
```

---

## 7. Conclusion

This program offers two approaches to handling sparse matrices: one using arrays and the other using linked lists. Both approaches allow for dynamic storage, efficient matrix operations, and sorting. The flexibility to switch between array-based and linked list-based implementations allows for different trade-offs in memory usage and processing time, depending on the problem at hand.
