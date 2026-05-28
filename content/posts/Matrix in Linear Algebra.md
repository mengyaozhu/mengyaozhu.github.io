+++
title = "Matrix in Linear Algebra"
# date = 2026-05-24
math = true
tags = ["Math for AI", "Matrix in Linear Algebra", "Definition of Matrix"]
author = ["Mengyao Zhu"]
+++

A matrix in linear algebra is a rectangular arrangement of numbers, symbols, or expressions organized into rows and columns. Each individual entry within this arrangement is called an element. The size or dimension of a matrix is described by the number of rows followed by the number of columns. The primary purpose of this structure is to store multiple pieces of numerical information in a way that allows simultaneous manipulation of entire sets of data. When two matrices are of compatible sizes, operations such as addition involve adding corresponding elements, while multiplication follows a specific rule where the element in the $i$-th row and $j$-th column of the product is formed by combining the $i$-th row of the first matrix with the $j$-th column of the second.

Consider a square matrix of size $n \times n$, meaning it has the same number of rows and columns. For example, a $3 \times 3$ matrix with three rows and three columns can be written as:
$$
A_{3 \times 3} = \begin{pmatrix} a_{11} & a_{12} & a_{13} \cr a_{21} & a_{22} & a_{23} \cr a_{31} & a_{32} & a_{33} \end{pmatrix}.
$$

A $5 \times 5$ matrix with five rows and five columns can be written as:

$$
A_{5 \times 5} = \begin{pmatrix} a_{11} & a_{12} & a_{13} & a_{14} & a_{15} \cr a_{21} & a_{22} & a_{23} & a_{24} & a_{25} \cr a_{31} & a_{32} & a_{33} & a_{34} & a_{35} \cr a_{41} & a_{42} & a_{43} & a_{44} & a_{45} \cr a_{51} & a_{52} & a_{53} & a_{54} & a_{55} \end{pmatrix}.
$$

The equal number of rows and columns is significant because only square matrices can have certain properties such as being invertible. 

Next, a matrix with more rows than columns, denoted $m \times n$ where $m > n$, appears taller than it is wide. For instance, a $4 \times 2$ matrix with four rows and two columns is:
$$
B_{4 \times 2} = \begin{pmatrix} b_{11} & b_{12} \cr b_{21} & b_{22} \cr b_{31} & b_{32} \cr b_{41} & b_{42} \end{pmatrix}.
$$

Additionally, a $5 \times 3$ tall matrix, having five rows and three columns, is written as:
$$
D_{5 \times 3} = \begin{pmatrix} d_{11} & d_{12} & d_{13} \cr d_{21} & d_{22} & d_{23} \cr d_{31} & d_{32} & d_{33} \cr d_{41} & d_{42} & d_{43} \cr d_{51} & d_{52} & d_{53} \end{pmatrix}.
$$

Such a matrix typically arises when there are more equations than unknown variables in a system. 

Conversely, a matrix with more columns than rows, written $n \times m$ where $m > n$, is wider than it is tall. A $2 \times 4$ matrix with 2 rows and 4 columns is:
$$
C_{2 \times 4} = \begin{pmatrix} c_{11} & c_{12} & c_{13} & c_{14} \cr c_{21} & c_{22} & c_{23} & c_{24} \end{pmatrix}.
$$

A $3 \times 5$ wide matrix, with three rows and five columns, is:
$$
E_{3 \times 5} = \begin{pmatrix} e_{11} & e_{12} & e_{13} & e_{14} & e_{15} \cr e_{21} & e_{22} & e_{23} & e_{24} & e_{25} \cr e_{31} & e_{32} & e_{33} & e_{34} & e_{35} \end{pmatrix}.
$$

This shape often appears when there are fewer equations than unknowns, leading to multiple possible solutions.

A concrete numerical square matrix of size $2 \times 2$ is:
$$
F_{2 \times 2} = \begin{pmatrix} 4 & 7 \cr 2 & 5 \end{pmatrix}.
$$
This matrix has two rows and two columns, with each entry being a specific number rather than a variable.

A concrete numerical tall matrix of size $3 \times 2$ is:
$$
G_{3 \times 2} = \begin{pmatrix} 1 & 3 \cr 0 & -2 \cr 5 & 4 \end{pmatrix}.
$$
It contains three rows and two columns, making it taller than it is wide, with all entries given as fixed numbers.

A concrete numerical wide matrix of size $2 \times 3$ is:
$$
H_{2 \times 3} = \begin{pmatrix} -1 & 6 & 2 \cr 8 & 0 & -4 \end{pmatrix}.
$$
This matrix has two rows and three columns, so it is wider than it is tall, with each entry explicitly defined numerically.

The essential characteristics of a matrix in linear algebra include its size, the nature of its elements, and the operations defined upon it. The arrangement into rows and columns is not arbitrary; each element has a specific position identified by two indices, one for the row and one for the column. This positional structure allows the matrix to represent linear transformations, where applying the matrix to a vector produces another vector. Another characteristic is that matrices can be added only when they share the same size, and multiplication requires that the number of columns in the first matrix equals the number of rows in the second matrix. The set of all matrices of a given size forms a mathematical structure where addition is commutative and associative, and multiplication distributes over addition. Furthermore, some matrices have special patterns, such as symmetric matrices where $a_{ij} = a_{ji}$, diagonal matrices where nonzero entries appear only on the main diagonal, and identity matrices which act as the multiplicative neutral element. These characteristics collectively define how matrices behave as computational tools and as representations of linear relationships between sets of numbers.

