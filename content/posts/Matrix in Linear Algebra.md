+++
title = "Matrix in Linear Algebra"
date = 2026-05-24
math = true
tags = ["Neural Networks", "Large Language Model", "Embeddings", "Similarity"]
author = ["Mengyao Zhu"]
+++






A matrix in linear algebra is a rectangular arrangement of numbers, symbols, or expressions organized into rows and columns. Each individual entry within this arrangement is called an element. The size or dimension of a matrix is described by the number of rows followed by the number of columns. The primary purpose of this structure is to store multiple pieces of numerical information in a way that allows simultaneous manipulation of entire sets of data. When two matrices are of compatible sizes, operations such as addition involve adding corresponding elements, while multiplication follows a specific rule where the element in the $i$-th row and $j$-th column of the product is formed by combining the $i$-th row of the first matrix with the $j$-th column of the second.

Consider a square matrix of size $n \times n$, meaning it has the same number of rows and columns. For example, a $3 \times 3$ matrix can be written as:
$$
A_{3 \times 3} = \begin{pmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33} \end{pmatrix}.
$$
The equal number of rows and columns is significant because only square matrices can have certain properties such as being invertible. Next, a matrix with more rows than columns, denoted $m \times n$ where $m > n$, appears taller than it is wide. For instance, a $4 \times 2$ matrix is:
$$
B_{4 \times 2} = \begin{pmatrix} b_{11} & b_{12} \\ b_{21} & b_{22} \\ b_{31} & b_{32} \\ b_{41} & b_{42} \end{pmatrix}.
$$
Such a matrix typically arises when there are more equations than unknown variables in a system. Conversely, a matrix with more columns than rows, written $n \times m$ where $m > n$, is wider than it is tall. A $2 \times 4$ matrix example is:
$$
C_{2 \times 4} = \begin{pmatrix} c_{11} & c_{12} & c_{13} & c_{14} \\ c_{21} & c_{22} & c_{23} & c_{24} \end{pmatrix}.
$$
This shape often appears when there are fewer equations than unknowns, leading to multiple possible solutions.

The essential characteristics of a matrix in linear algebra include its size, the nature of its elements, and the operations defined upon it. The arrangement into rows and columns is not arbitrary; each element has a specific position identified by two indices, one for the row and one for the column. This positional structure allows the matrix to represent linear transformations, where applying the matrix to a vector produces another vector. Another characteristic is that matrices can be added only when they share the same size, and multiplication requires that the number of columns in the first matrix equals the number of rows in the second matrix. The set of all matrices of a given size forms a mathematical structure where addition is commutative and associative, and multiplication distributes over addition. Furthermore, some matrices have special patterns, such as symmetric matrices where $a_{ij} = a_{ji}$, diagonal matrices where nonzero entries appear only on the main diagonal, and identity matrices which act as the multiplicative neutral element. These characteristics collectively define how matrices behave as computational tools and as representations of linear relationships between sets of numbers.



$$
\begin{bmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{bmatrix}
$$




$$\begin{bmatrix}
a_{11} & a_{12} & a_{13} \
a_{21} & a_{22} & a_{23} \
a_{31} & a_{32} & a_{33}
\end{bmatrix}$$

