+++
title = "Chapter 1 Section 1: Matrix in Linear Algebra and AI"
date = 2026-05-24
math = true
tags = ["Math for AI", "Matrix in Linear Algebra", "Definition of Matrix"]
author = ["Mengyao Zhu"]
+++

---
# 1. Definition of Matrix
---
A matrix in linear algebra is a rectangular arrangement of numbers, symbols, or expressions organized into rows and columns. Each individual entry within this arrangement is called an element (or entry). These elements are typically scalars from a field (such as real or complex numbers), but can also be symbolic expressions that evaluate to such scalars. The vertical stacks of elements are called column vectors, and the horizontal sequences are called row vectors. Together, these rows and columns give the matrix its shape: a matrix with $m$ rows and $n$ columns is said to be of size $m \times n$.

This structure allows the matrix to serve different functions. For example, a matrix can transform an input vector from one space into an output vector in another space through multiplication. It can also represent a collection of $m$ data points in an $n$-dimensional space, where each row vector represents a single data point and each column vector corresponds to a specific feature or coordinate axis. Additionally, a matrix can encode the coefficients of a system of linear equations, or act as a linear map that scales, rotates, or shears geometric objects. In all these roles, the matrix remains a unified object that organizes information in a way that makes computation and analysis systematic.

**Example 1: Table of Demographic Data** 

| | Age (Col 1) | Salary (Col 2) | Height (cm) (Col 3) | Weight (kg) (Col 4) |
| :--- | :---: | :---: | :---: | :---: |
| **Person 1 (Row 1)** | 30 | 50,000 | 175 | 70 |
| **Person 2 (Row 2)** | 25 | 45,000 | 160 | 55 |
| **Person 3 (Row 3)** | 45 | 80,000 | 180 | 85 |

In matrix form: 

$$
D = \begin{pmatrix}
30 & 50000 & 175 & 70 \cr 
25 & 45000 & 160 & 55 \cr 
45 & 80000 & 180 & 85
\end{pmatrix}
$$

In matrix form with row and column annotations:

$$
D =
\left(
\begin{array}{c|c|c|c}
30 & 50000 & 175 & 70 \cr
25 & 45000 & 160 & 55 \cr
45 & 80000 & 180 & 85 \cr
\hline
\downarrow & \downarrow & \downarrow & \downarrow \cr
\mathrm{Col\ 1} & \mathrm{Col\ 2} & \mathrm{Col\ 3} & \mathrm{Col\ 4} \cr
(\mathrm{Age}) & (\mathrm{Salary}) & (\mathrm{Height}) & (\mathrm{Weight})
\end{array}
\right)
\begin{array}{l}
\leftarrow \mathrm{Row 1\ (Person\ 1)} \cr
\leftarrow \mathrm{Row 2\ (Person\ 2)} \cr
\leftarrow \mathrm{Row 3\ (Person\ 3)} \cr
\cr
\cr
\cr
\end{array}
$$


- **Rows** (3 rows): Each row corresponds to one person (Person 1, Person 2, Person 3).  
- **Columns** (4 columns): Each column corresponds to a demographic feature (Column 1 = Age, Column 2 = Salary, Column 3 = Height, Column 4 = Weight).  
- **Entries:** Each entry is the value of a specific feature for a specific person (e.g., entry $d_{23} = 160$ means Person 2 has height 160 cm).


**Example 2: Table of Clinical Patient Data**

| | Blood Pressure (Col 1) | Heart Rate (Col 2) | Temperature (°C) (Col 3) | Cholesterol (mg/dL) (Col 4) |
| :--- | :---: | :---: | :---: | :---: |
| **Patient 1 (Row 1)** | 120/80 | 72 | 36.8 | 190 |
| **Patient 2 (Row 2)** | 135/85 | 80 | 37.1 | 210 |
| **Patient 3 (Row 3)** | 110/70 | 65 | 36.5 | 180 |

In matrix form:

$$
C = \begin{pmatrix}
120/80 & 72 & 36.8 & 190 \cr 
135/85 & 80 & 37.1 & 210 \cr 
110/70 & 65 & 36.5 & 180
\end{pmatrix}
$$

In matrix form with row and column annotations:

$$
C =
\left(
\begin{array}{c|c|c|c}
120/80 & 72 & 36.8 & 190 \cr
135/85 & 80 & 37.1 & 210 \cr
110/70 & 65 & 36.5 & 180 \cr
\hline
\downarrow & \downarrow & \downarrow & \downarrow \cr
\mathrm{Col\ 1} & \mathrm{Col\ 2} & \mathrm{Col\ 3} & \mathrm{Col\ 4} \cr
(\mathrm{Blood\ Pressure}) & (\mathrm{Heart\ Rate}) & (\mathrm{Temperature}) & (\mathrm{Cholesterol})
\end{array}
\right)
\begin{array}{l}
\leftarrow \mathrm{Row\ 1\ (Patient\ 1)} \cr
\leftarrow \mathrm{Row\ 2\ (Patient\ 2)} \cr
\leftarrow \mathrm{Row\ 3\ (Patient\ 3)} \cr
\cr
\cr
\cr
\end{array}
$$




- **Rows** (3 rows): Each row corresponds to one patient (Patient 1, Patient 2, Patient 3).  
- **Columns** (4 columns): Each column corresponds to a clinical measurement (Column 1 = Blood Pressure, Column 2 = Heart Rate, Column 3 = Temperature, Column 4 = Cholesterol).  
- **Entries:** Each entry is the clinical value for a specific patient (e.g., entry $c_{31} = 110/70$ means Patient 3 has blood pressure 110/70).



**Example 3: System of Linear Equations**

$$
\begin{cases}
2x_1 - x_2 + x_3 = 8 \cr
-3x_1 + 2x_2 + 2x_3 = -11 \cr
x_1 + x_2 - x_3 = 0
\end{cases}
\qquad 
\begin{array}{l}
\leftarrow \mathrm{Linear\ Equation\ Eq.\ 1} \cr
\leftarrow \mathrm{Linear\ Equation\ Eq.\ 2} \cr
\leftarrow \mathrm{Linear\ Equation\ Eq.\ 3}
\end{array}
$$

The above system is written in its conventional form, where coefficients equal to 1 are omitted. For matrix construction, the equivalent system below displays all coefficients explicitly. Note that the sign of each term, whether positive or negative, is an integral part of the corresponding coefficient and must be included when constructing the matrix.

$$  
\begin{cases}  
\mathbf{2}x_1 + (\mathbf{-1})x_2 + \mathbf{1}x_3 = \mathbf{8} \cr  
(\mathbf{-3})x_1 + \mathbf{2}x_2 + \mathbf{2}x_3 = \mathbf{-11} \cr  
\mathbf{1}x_1 + \mathbf{1}x_2 + (\mathbf{-1})x_3 = \mathbf{0}  
\end{cases}  
\qquad  
\begin{array}{l}  
\leftarrow \mathrm{Linear\ Equation\ Eq.\ 1} \cr  
\leftarrow \mathrm{Linear\ Equation\ Eq.\ 2} \cr  
\leftarrow \mathrm{Linear\ Equation\ Eq.\ 3}  
\end{array}  
$$

We can now construct the corresponding augmented matrix:

$$
A = \left(\begin{array}{ccc|c}
2 & -1 & 1 & 8 \cr 
-3 & 2 & 2 & -11 \cr  
1 & 1 & -1 & 0
\end{array}\right)
$$

The following annotations show how the rows and columns correspond to the equations, variables, and constants.

$$
A =
\left(
\begin{array}{ccc|c}
2 & -1 & 1 & 8 \cr
-3 & 2 & 2 & -11 \cr
1 & 1 & -1 & 0 \cr
\hline
\downarrow & \downarrow & \downarrow & \downarrow \cr
\mathrm{Col\ 1} & \mathrm{Col\ 2} & \mathrm{Col\ 3} & \mathrm{Col\ 4} \cr
(x_1) & (x_2) & (x_3) & (\mathrm{const})
\end{array}
\right)
\begin{array}{l}
\leftarrow \mathrm{Row\ 1\ (Eq.\ 1:\ }2x_1-x_2+x_3=8\mathrm{)} \cr
\leftarrow \mathrm{Row\ 2\ (Eq.\ 2:\ }-3x_1+2x_2+2x_3=-11\mathrm{)} \cr
\leftarrow \mathrm{Row\ 3\ (Eq.\ 3:\ }x_1+x_2-x_3=0\mathrm{)} \cr
\cr
\cr
\cr
\end{array}
$$



- **Rows** (3 rows): Each row corresponds to one linear equation (Equation 1, Equation 2, Equation 3).  
- **Columns** (4 columns): Each column corresponds to coefficients of variables and the constant term, with the vertical line separating the coefficient matrix (Columns 1–3) from the constant vector (Column 4). Column 1 = Coefficient of $x_1$, Column 2 = Coefficient of $x_2$, Column 3 = Coefficient of $x_3$, Column 4 = Constant term.  
- **Entries:** Each entry is a coefficient or constant from a specific equation (e.g., entry $a_{12} = -1$ means Equation 1 has coefficient $-1$ for $x_2$).
- **Variables, Coefficients and Constants:** The variables $x_1, x_2, x_3$ are unknown quantities to be solved for. The coefficients (Columns 1–3) multiply these variables in each equation. The constants (Column 4) are fixed numbers on the right-hand side of each equation. Together, the augmented matrix compactly represents the entire system without rewriting the variables and equality signs.



---
# 2. Matrix Variations
---
## 2.1. Square Matrix
---
A square matrix has the same number of rows and columns, which can be written as $A_{{n \times n}}$ or $A_{m \times n}$, where $m = n$, such as a $3\times 3$ square matrix has three rows and three columns, a $4 \times 4$ square matrix has four rows and four columns, and an $n \times n$ square matrix has $n$ rows and $n$ columns, where $n$ can be any positive integer.

$$
S_{3 \times 3} = \begin{pmatrix} s_{11} & s_{12} & s_{13} \cr s_{21} & s_{22} & s_{23} \cr s_{31} & s_{32} & s_{33} \end{pmatrix} = \begin{pmatrix} 8 & 3 & 6 \cr 1 & 5 & 9 \cr 4 & 7 & 2 \end{pmatrix}.
$$

<center>
A square matrix with three rows and three columns.
</center>


$$
S_{4 \times 4} = \begin{pmatrix} s_{11} & s_{12} & s_{13} & s_{14} \cr s_{21} & s_{22} & s_{23} & s_{24} \cr s_{31} & s_{32} & s_{33} & s_{34} \cr s_{41} & s_{42} & s_{43} & s_{44} \end{pmatrix} = \begin{pmatrix} 5 & 9 & 2 & 7 \cr 3 & 8 & 1 & 6 \cr 4 & 0 & 9 & 3 \cr 2 & 5 & 7 & 4 \end{pmatrix}.
$$

<center>
A square matrix with four rows and four columns.
</center>


$$
S_{n \times n} = \begin{pmatrix} 
s_{11} & s_{12} & \cdots & s_{1n} \cr 
s_{21} & s_{22} & \cdots & s_{2n} \cr 
\vdots & \vdots & \ddots & \vdots \cr 
s_{n1} & s_{n2} & \cdots & s_{nn} 
\end{pmatrix}.
$$

<center>
A square matrix with $n$ rows and $n$ columns.
</center>


---
## 2.2. Non-Square Matrix
---
### 2.2.1. Tall Matrix with More Rows than Columns
---
A tall matrix has more number of rows than that of the columns, which looks taller than the square matrix, such as a tall matrix $B_{6 \times 3}$ with four rows and two columns, or a tall matrix $B_{n \times 5}$ with $n$ rows and five columns.

$$
\begin{array}{cc}
T_{6 \times 3}^{(\text{tall})} = \begin{pmatrix} 
t_{11} & t_{12} & t_{13} \cr 
t_{21} & t_{22} & t_{23} \cr 
t_{31} & t_{32} & t_{33} \cr 
t_{41} & t_{42} & t_{43} \cr 
t_{51} & t_{52} & t_{53} \cr 
t_{61} & t_{62} & t_{63} 
\end{pmatrix} &
\quad \text{vs.} \quad &
S_{3 \times 3}^{\text{(square)}} = \begin{pmatrix} 
s_{11} & s_{12} & s_{13} \cr 
s_{21} & s_{22} & s_{23} \cr 
s_{31} & s_{32} & s_{33} 
\end{pmatrix}
\end{array}
$$

<center>
A tall matrix (left side) looks taller than the square matrix (right side)
</center>

---
### 2.2.2. Wide Matrix with Less Rows than Columns
---
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

<center>
A wide matrix (left side) looks wider than the square matrix (right side)
</center>


---
## 2.3. Special Matrices
---
### 2.3.1. Column Vector as a Special Matrix
---
A column vector is a special matrix with multiple rows but only one column, written as 

$$
C_{3 \times 1} = \begin{pmatrix} 
c_{11} \cr 
c_{21} \cr 
c_{31} 
\end{pmatrix}.
$$

<center>
A column vector with three rows and one column
</center>

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

<center>
A column vector with six rows and one column
</center>

$$
C_{n \times 1} = \begin{pmatrix} 
c_{11} \cr 
c_{21} \cr 
\vdots \cr 
c_{n1} 
\end{pmatrix}.
$$

<center>
A column vector with } n \text{ rows and one column
</center>


---
### 2.3.2. Row Vector as a Special Matrix
---
Below are some examples of row vectors with different number of entries. We can call a row vector with three entries as a 3-dimensional (row) vector, a row vector with six entries as a 6-dimensional (row) vector, and a row vector with $n$ entries as a n-dimensional (row) vector.
$$
W_{1 \times 3} = \begin{pmatrix} w_{11} & w_{12} & w_{13} \end{pmatrix}.
$$

<center>
A row vector with one row and three columns
</center>

$$
W_{1 \times 6} = \begin{pmatrix} w_{11} & w_{12} & w_{13} & w_{14} & w_{15} & w_{16} \end{pmatrix}.
$$

<center>
A row vector with one row and six columns
</center>

$$
W_{1 \times n} = \begin{pmatrix} w_{11} & w_{12} & \cdots & w_{1n} \end{pmatrix}.
$$

<center>
A row vector with one row and } n \text{ columns
</center>

---
### 2.3.3. Scalar as a $1 \times 1$ Matrix
---


---
### 2.3.4. Entries of the Matrix

The entries of a matrix can take various forms, including variables such as $a, b, x, y$ (representing unknown or symbolic quantities); numerical values such as integers ($1, -5, 42$), real numbers ($3.14, -0.001$), or complex numbers ($2+3i$); and mathematical expressions such as $x^2 + 1$, $\sin(\theta)$, $e^{t}$, or $\frac{a+b}{c}$, allowing the matrix to represent functional relationships or parameterized systems.

Consider a square matrix of size $n \times n$, meaning it has the same number of rows and columns. For example, a $3 \times 3$ matrix with three rows and three columns can be written as:

A $3 \times 3$ square matrix with numerical values, having three rows and three columns, is:
$$
N_{3 \times 3} = \begin{pmatrix} 1 & 4 & 7 \cr 2 & 5 & 8 \cr 3 & 6 & 9 \end{pmatrix}.
$$
A $4 \times 4$ square matrix with numerical values, having four rows and four columns, is:
$$
N_{4 \times 4} = \begin{pmatrix} 2 & 5 & 8 & 11 \cr 3 & 6 & 9 & 12 \cr 4 & 7 & 10 & 13 \cr 5 & 8 & 11 & 14 \end{pmatrix}.
$$
A $3 \times 3$ square matrix with math expressions, having three rows and three columns, is:
$$
E_{3 \times 3} = \begin{pmatrix} x+1 & 2y & z-3 \cr 2x & y+1 & 3z \cr x-2 & y+2 & z+4 \end{pmatrix}.
$$
A $4 \times 4$ square matrix with simple expressions, having four rows and four columns, is:
$$
E_{4 \times 4} = \begin{pmatrix} x+1 & 2y & z-3 & t+5 \cr 2x & y+1 & 3z & t-1 \cr x-2 & y+2 & z+4 & 2t \cr x+y & y+z & z+t & t+x \end{pmatrix}.
$$



## 2.4. Matrix in Neural Network Modeling

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



## 2.5. Essential Characteristics of Matrix

The essential characteristics of a matrix in linear algebra include its size, the nature of its elements, and the operations defined upon it. The arrangement into rows and columns is not arbitrary; each element has a specific position identified by two indices, one for the row and one for the column. This positional structure allows the matrix to represent linear transformations, where applying the matrix to a vector produces another vector. Another characteristic is that matrices can be added only when they share the same size, and multiplication requires that the number of columns in the first matrix equals the number of rows in the second matrix. The set of all matrices of a given size forms a mathematical structure where addition is commutative and associative, and multiplication distributes over addition. Furthermore, some matrices have special patterns, such as symmetric matrices where $a_{ij} = a_{ji}$, diagonal matrices where nonzero entries appear only on the main diagonal, and identity matrices which act as the multiplicative neutral element. These characteristics collectively define how matrices behave as computational tools and as representations of linear relationships between sets of numbers.



### Trial 


$$
A =
\left(
\begin{array}{ccc|c}
2 & -1 & 1 & 8 \cr
-3 & 2 & 2 & -11 \cr
1 & 1 & -1 & 0
\end{array}
\right)
\begin{array}{l}
\leftarrow \mathrm{Row\ 1} \cr
\leftarrow \mathrm{Row\ 2} \cr
\leftarrow \mathrm{Row\ 3}
\end{array}
$$




$$
A =
\left(
\begin{array}{ccc|c}
2 & -1 & 1 & 8 \cr
-3 & 2 & 2 & -11 \cr
1 & 1 & -1 & 0 \cr
\hline
\downarrow & \downarrow & \downarrow & \downarrow \cr
\mathrm{Col\ 1} & \mathrm{Col\ 2} & \mathrm{Col\ 3} & \mathrm{Col\ 4} \cr
(x_1) & (x_2) & (x_3) & (\mathrm{const})
\end{array}
\right)
\begin{array}{l}
\leftarrow \mathrm{Row\ 1} \cr
\leftarrow \mathrm{Row\ 2} \cr
\leftarrow \mathrm{Row\ 3} \cr
\cr
\cr
\cr
\end{array}
$$



