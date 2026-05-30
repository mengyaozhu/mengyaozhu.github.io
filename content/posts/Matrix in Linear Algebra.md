+++
title = "Matrix in Linear Algebra"
date = 2026-05-24
math = true
tags = ["Math for AI", "Matrix in Linear Algebra", "Definition of Matrix"]
author = ["Mengyao Zhu"]
+++

### Definition of Matrix  

A matrix in linear algebra is a rectangular arrangement of numbers, symbols, or expressions organized into rows and columns. Each individual entry within this arrangement is called an element. The primary purpose of this structure is to store multiple pieces of numerical information in a way that allows simultaneous manipulation of entire sets of data.

The size of a matrix is denoted as $m \times n$, where $m$ is the number of rows and $n$ is the number of columns. 

### Square Matrix

A square matrix has the same number of rows and columns, which can be written as $A_{{n \times n}}$ or $A_{m \times n}$, where $m = n$, such as a $3\times 3$ square matrix has two rows and two columns, a $4 \times 4$ square matrix has five rows and five columns, and an $n \times n$ square matrix has n rows and $n$ columns, where $n$ can be any positive integer.

$$
A_{3 \times 3} = \begin{pmatrix} a_{11} & a_{12} & a_{13} \cr a_{21} & a_{22} & a_{23} \cr a_{31} & a_{32} & a_{33} \end{pmatrix}.
$$

$$
\text{A square matrix with three rows and three columns}
$$

$$
A_{4 \times 4} = \begin{pmatrix} a_{11} & a_{12} & a_{13} & a_{14} \cr a_{21} & a_{22} & a_{23} & a_{24} \cr a_{31} & a_{32} & a_{33} & a_{34} \cr a_{41} & a_{42} & a_{43} & a_{44} \end{pmatrix}.
$$

$$
\text{A Square matrix with four rows and four columns}
$$

$$
A_{n \times n} = \begin{pmatrix} 
a_{11} & a_{12} & \cdots & a_{1n} \cr 
a_{21} & a_{22} & \cdots & a_{2n} \cr 
\vdots & \vdots & \ddots & \vdots \cr 
a_{n1} & a_{n2} & \cdots & a_{nn} 
\end{pmatrix}.
$$

$$
\text{A square matrix with } n \text{ rows and } n \text{ columns}
$$

### Non-Square Matrix

#### Tall Matrix with More Rows than Columns

A tall matrix has more number of rows than that of the columns, which looks taller than the square matrix, such as a tall matrix $B_{6 \times 3}$ with four rows and two columns, or a tall matrix $B_{n \times 5}$ with $n$ rows and five columns.


$$
\begin{array}{cc}
C_{6 \times 3}^{(\text{tall})} = \begin{pmatrix} 
c_{11} & c_{12} & c_{13} \cr 
c_{21} & c_{22} & c_{23} \cr 
c_{31} & c_{32} & c_{33} \cr 
c_{41} & c_{42} & c_{43} \cr 
c_{51} & c_{52} & c_{53} \cr 
c_{61} & c_{62} & c_{63} 
\end{pmatrix} &
\quad \text{vs.} \quad &
A_{3 \times 3}^{\text{(square)}} = \begin{pmatrix} 
a_{11} & a_{12} & a_{13} \cr 
a_{21} & a_{22} & a_{23} \cr 
a_{31} & a_{32} & a_{33} 
\end{pmatrix}
\end{array}
$$

$$
\text{A tall matrix (left side) looks taller than the square matrix (right side)}
$$

#### A Wide Matrix with More Columns than Rows

A wide matrix has more number of columns than that of the rows, which looks wider than the square matrix, such as a wide matrix $C_{3 \times 6}$ with three rows and six columns, or a wide matrix $C_{5 \times n}$ with five rows and $n$ columns.

$$
\begin{array}{cc}
C_{3 \times 6} = \begin{pmatrix} 
c_{11} & c_{12} & c_{13} & c_{14} & c_{15} & c_{16} \cr 
c_{21} & c_{22} & c_{23} & c_{24} & c_{25} & c_{26} \cr 
c_{31} & c_{32} & c_{33} & c_{34} & c_{35} & c_{36} 
\end{pmatrix} &
\quad \text{vs.} \quad &
A_{3 \times 3} = \begin{pmatrix} 
a_{11} & a_{12} & a_{13} \cr 
a_{21} & a_{22} & a_{23} \cr 
a_{31} & a_{32} & a_{33} 
\end{pmatrix}
\end{array}
$$

$$
\text{A wide matrix (left side) looks wider than the square matrix (right side)}
$$

#### Column Vector as a Special Matrix

A column vector is a special matrix with multiple rows but only one column, written as 

$$
C_{3 \times 1} = \begin{pmatrix} 
c_{11} \cr 
c_{21} \cr 
c_{31} 
\end{pmatrix}.
$$

$$
\text{A column vector with three rows and one column}
$$

$$
C_{6 \times 1} = \begin{pmatrix} 
c_{11} \cr 
c_{21} \cr 
c_{31} \cr 
c_{41} \cr 
c_{51} \cr 
c_{61} 
\end{pmatrix}.
$$

$$
\text{A column vector with six rows and one column}
$$

$$
C_{n \times 1} = \begin{pmatrix} 
c_{11} \cr 
c_{21} \cr 
\vdots \cr 
c_{n1} 
\end{pmatrix}.
$$

$$
\text{A column vector with } n \text{ rows and one column}
$$





column vector C
row vector R
tall matrix T
wide matrix W
square matrix S
scalar vector N



#### Row Vector as a Special Matrix 


$$
W_{1 \times 3} = \begin{pmatrix} w_{11} & w_{12} & w_{13} \end{pmatrix}.
$$

$$
\text{A row vector with one row and three columns}
$$

$$
W_{1 \times 6} = \begin{pmatrix} w_{11} & w_{12} & w_{13} & w_{14} & w_{15} & w_{16} \end{pmatrix}.
$$

$$
\text{A row vector with one row and six columns}
$$

$$
W_{1 \times n} = \begin{pmatrix} w_{11} & w_{12} & \cdots & w_{1n} \end{pmatrix}.
$$

$$
\text{A row vector with one row and } n \text{ columns}
$$


#### Scalar as a Special Matrix





A tall matrix has $m > n$, with more rows than columns, appearing vertically extended. A wide matrix has $m < n$, with more columns than rows, appearing horizontally extended. A column vector is a special matrix with $n = 1$, written as $m \times 1$, containing only one column. A row vector is a special matrix with $m = 1$, written as $1 \times n$, containing only one row. A scalar is a special matrix with $m = n = 1$, representing a single number, which can be thought of as a $1 \times 1$ matrix.



$$
B_{4 \times 2} = \begin{pmatrix} 
b_{11} & b_{12} \cr 
b_{21} & b_{22} \cr 
b_{31} & b_{32} \cr 
b_{41} & b_{42} 
\end{pmatrix}.
$$

$$
\text{A tall matrix with four rows and two columns}
$$

$$
C_{6 \times 3} = \begin{pmatrix} 
c_{11} & c_{12} & c_{13} \cr 
c_{21} & c_{22} & c_{23} \cr 
c_{31} & c_{32} & c_{33} \cr 
c_{41} & c_{42} & c_{43} \cr 
c_{51} & c_{52} & c_{53} \cr 
c_{61} & c_{62} & c_{63} 
\end{pmatrix}.
$$

$$
\text{A tall matrix with six rows and three columns}
$$

$$
D_{n \times 4} = \begin{pmatrix} 
d_{11} & d_{12} & d_{13} & d_{14} \cr 
d_{21} & d_{22} & d_{23} & d_{24} \cr 
\vdots & \vdots & \vdots & \vdots \cr 
d_{n1} & d_{n2} & d_{n3} & d_{n4} 
\end{pmatrix}.
$$

$$
\text{A tall matrix with } n \text{ rows and } 4 \text{ columns (where } n > 4\text{)}
$$





The entries of a matrix can take various forms, including variables such as $a, b, x, y$ (representing unknown or symbolic quantities); numerical values such as integers ($1, -5, 42$), real numbers ($3.14, -0.001$), or complex numbers ($2+3i$); and mathematical expressions such as $x^2 + 1$, $\sin(\theta)$, $e^{t}$, or $\frac{a+b}{c}$, allowing the matrix to represent functional relationships or parameterized systems.


## Matrix of Different Sizes

### Square Matrix 

#### Square Matrix with Variable Elements

Consider a square matrix of size $n \times n$, meaning it has the same number of rows and columns. For example, a $3 \times 3$ matrix with three rows and three columns can be written as:


A $4 \times 4$ matrix with five rows and five columns can be written as:




### Square Matrix with Numerical Elements

A $3 \times 3$ square matrix with numerical values, having three rows and three columns, is:
$$
N_{3 \times 3} = \begin{pmatrix} 1 & 4 & 7 \cr 2 & 5 & 8 \cr 3 & 6 & 9 \end{pmatrix}.
$$
A $4 \times 4$ square matrix with numerical values, having four rows and four columns, is:
$$
N_{4 \times 4} = \begin{pmatrix} 2 & 5 & 8 & 11 \cr 3 & 6 & 9 & 12 \cr 4 & 7 & 10 & 13 \cr 5 & 8 & 11 & 14 \end{pmatrix}.
$$





### Square Matrix with Expression Elements

A $3 \times 3$ square matrix with math expressions, having three rows and three columns, is:
$$
E_{3 \times 3} = \begin{pmatrix} x+1 & 2y & z-3 \cr 2x & y+1 & 3z \cr x-2 & y+2 & z+4 \end{pmatrix}.
$$
A $4 \times 4$ square matrix with simple expressions, having four rows and four columns, is:
$$
E_{4 \times 4} = \begin{pmatrix} x+1 & 2y & z-3 & t+5 \cr 2x & y+1 & 3z & t-1 \cr x-2 & y+2 & z+4 & 2t \cr x+y & y+z & z+t & t+x \end{pmatrix}.
$$

## Tall Matrix 

A $4 \times 2$ tall matrix with symbols as elements, having four rows and two columns, is:
$$
T_{4 \times 2}^{(var)} = \begin{pmatrix} t_{11} & t_{12} \cr t_{21} & t_{22} \cr t_{31} & t_{32} \cr t_{41} & t_{42} \end{pmatrix}.
$$
A $4 \times 3$ tall matrix with symbols as elements, having four rows and three columns, is:
$$
T_{4 \times 3}^{(var)} = \begin{pmatrix} t_{11} & t_{12} & t_{13} \cr t_{21} & t_{22} & t_{23} \cr t_{31} & t_{32} & t_{33} \cr t_{41} & t_{42} & t_{43} \end{pmatrix}.
$$

A $4 \times 2$ tall matrix with numerical values as elements, having four rows and two columns, is:
$$
T_{4 \times 2}^{(num)} = \begin{pmatrix} 3 & 8 \cr 5 & 1 \cr 7 & 4 \cr 2 & 6 \end{pmatrix}.
$$
A $4 \times 3$ tall matrix with numerical values as elements, having four rows and three columns, is:
$$
T_{4 \times 3}^{(num)} = \begin{pmatrix} 1 & 4 & 7 \cr 2 & 5 & 8 \cr 3 & 6 & 9 \cr 4 & 7 & 10 \end{pmatrix}.
$$

A $4 \times 2$ tall matrix with simple expressions as elements, having four rows and two columns, is:
$$
T_{4 \times 2}^{(exp)} = \begin{pmatrix} x+1 & 2y \cr z-3 & t+5 \cr 2x & y+1 \cr 3z & t-1 \end{pmatrix}.
$$
A $4 \times 3$ tall matrix with simple expressions as elements, having four rows and three columns, is:
$$
T_{4 \times 3}^{(exp)} = \begin{pmatrix} x+1 & 2y & z-3 \cr t+5 & 2x & y+1 \cr 3z & t-1 & x-2 \cr y+2 & z+4 & 2t \end{pmatrix}.
$$

Next, a matrix with more rows than columns, denoted $m \times n$ where $m > n$, appears taller than it is wide. For instance, a $4 \times 2$ matrix with four rows and two columns is:
$$
B_{4 \times 2} = \begin{pmatrix} b_{11} & b_{12} \cr b_{21} & b_{22} \cr b_{31} & b_{32} \cr b_{41} & b_{42} \end{pmatrix}.
$$

Additionally, a $5 \times 3$ tall matrix, having five rows and three columns, is written as:
$$
D_{5 \times 3} = \begin{pmatrix} d_{11} & d_{12} & d_{13} \cr d_{21} & d_{22} & d_{23} \cr d_{31} & d_{32} & d_{33} \cr d_{41} & d_{42} & d_{43} \cr d_{51} & d_{52} & d_{53} \end{pmatrix}.
$$

Such a matrix typically arises when there are more equations than unknown variables in a system. 

## Wide Matrix 

Conversely, a matrix with more columns than rows, written $n \times m$ where $m > n$, is wider than it is tall. A $2 \times 4$ matrix with 2 rows and 4 columns is:
$$
C_{2 \times 4} = \begin{pmatrix} c_{11} & c_{12} & c_{13} & c_{14} \cr c_{21} & c_{22} & c_{23} & c_{24} \end{pmatrix}.
$$

A $3 \times 5$ wide matrix, with three rows and five columns, is:
$$
E_{3 \times 5} = \begin{pmatrix} e_{11} & e_{12} & e_{13} & e_{14} & e_{15} \cr e_{21} & e_{22} & e_{23} & e_{24} & e_{25} \cr e_{31} & e_{32} & e_{33} & e_{34} & e_{35} \end{pmatrix}.
$$

This shape often appears when there are fewer equations than unknowns, leading to multiple possible solutions.

## Matrix in Neural Network Modeling

In neural network modeling, particularly for Transformer-based models, matrices serve as the fundamental data structure for representing all learnable parameters and intermediate computations. Each token, obtained by splitting the raw input text into smaller units such as words or subwords during tokenization, is then embedded as a vector through an embedding lookup matrix. For example, a token embedding vector of size $1 \times d$ (or $d \times 1$) is:

$$
\text{Token vector}\_{1 \times d} = \begin{pmatrix} v\_1 & v_2 & \dots & v_d \end{pmatrix} \quad \text{or} \quad \text{Token vector}\_{d \times 1} = \begin{pmatrix} v\_1 \cr v\_2 \cr \vdots \cr v\_d \end{pmatrix}.
$$

The entire sequence of $n$ tokens is packed into a matrix where rows correspond to tokens and columns to embedding dimensions:

$$
\text{Input matrix}\_{n \times d} = \begin{pmatrix} 
\text{token}\_1 \cr 
\text{token}\_2 \cr 
\vdots \cr 
\text{token}\_n 
\end{pmatrix}
= \begin{pmatrix}
v\_{11} & v\_{12} & \dots & v\_{1d} \cr
v\_{21} & v\_{22} & \dots & v\_{2d} \cr
\vdots & \vdots & \ddots & \vdots \cr
v\_{n1} & v\_{n2} & \dots & v\_{nd}
\end{pmatrix}.
$$

The self-attention mechanism, the core of Transformers, computes three matrices from the input: queries, keys, and values, each obtained by multiplying the input matrix with distinct weight matrices:

$$
\text{Queries}\_{n \times d\_k} = \text{Input}\_{n \times d} \cdot W^Q\_{d \times d_k}.
$$


$$
\text{Keys}\_{n \times d\_k} = \text{Input}\_{n \times d} \cdot W^K\_{d \times d\_k}.
$$

$$
\text{Values}\_{n \times d\_v} = \text{Input}\_{n \times d} \cdot W^V\_{d \times d_v}.
$$



The attention scores themselves form a square matrix of size sequence length times sequence length, capturing pairwise relationships between all tokens:

$$
\text{Attention scores}\_{n \times n} = \text{Queries}\_{n \times d\_k} \cdot \text{Keys}^{\top}\_{d\_k \times n} = \begin{pmatrix}
s\_{11} & s\_{12} & \dots & s\_{1n} \cr
s\_{21} & s\_{22} & \dots & s\_{2n} \cr
\vdots & \vdots & \ddots & \vdots \cr
s\_{n1} & s\_{n2} & \dots & s\_{nn}
\end{pmatrix}.
$$




All feed-forward layers are matrix multiplications, and the output of each transformer block is again a matrix. Without matrices, parallel processing of sequences would be impossible, and the efficiency of training on graphics processing units, which are optimized for matrix operations, would collapse. Thus, the matrix is not merely a notational convenience but the computational backbone that enables Transformers to scale to billions of parameters and process long sequences.



## Essential Characteristics of Matrix

The essential characteristics of a matrix in linear algebra include its size, the nature of its elements, and the operations defined upon it. The arrangement into rows and columns is not arbitrary; each element has a specific position identified by two indices, one for the row and one for the column. This positional structure allows the matrix to represent linear transformations, where applying the matrix to a vector produces another vector. Another characteristic is that matrices can be added only when they share the same size, and multiplication requires that the number of columns in the first matrix equals the number of rows in the second matrix. The set of all matrices of a given size forms a mathematical structure where addition is commutative and associative, and multiplication distributes over addition. Furthermore, some matrices have special patterns, such as symmetric matrices where $a_{ij} = a_{ji}$, diagonal matrices where nonzero entries appear only on the main diagonal, and identity matrices which act as the multiplicative neutral element. These characteristics collectively define how matrices behave as computational tools and as representations of linear relationships between sets of numbers.



### Trial

$$
\text{Attention scores}\_{n \times n} = \text{Queries}\_{n \times d\_k} \cdot \text{Keys}^{\top}\_{d\_k \times n}
$$

$$
= \begin{pmatrix}
s_{11} & s_{12} & \dots & s_{1n} \cr
s_{21} & s_{22} & \dots & s_{2n} \cr
\vdots & \vdots & \ddots & \vdots \cr
s_{n1} & s_{n2} & \dots & s_{nn}
\end{pmatrix}.
$$



