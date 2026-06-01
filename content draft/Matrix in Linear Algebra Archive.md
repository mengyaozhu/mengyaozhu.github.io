+++
title = "Matrix in Linear Algebra Archive"
# date = 2026-05-24
math = true
tags = ["Math for AI", "Matrix in Linear Algebra", "Definition of Matrix"]
author = ["Mengyao Zhu"]
+++


A matrix in linear algebra is a rectangular arrangement of numbers, symbols, or expressions organized into rows and columns. Each individual entry within this arrangement is called an element (or entry). These elements are typically scalars from a field (such as real or complex numbers), but can also be symbolic expressions that evaluate to such scalars. The vertical stacks of elements are called column vectors, and the horizontal sequences are called row vectors. Together, these rows and columns give the matrix its shape: a matrix with $m$ rows and $n$ columns is said to be of size $m \times n$.

This structure allows the matrix to serve different functions. For example, a matrix can transform an input vector from one space into an output vector in another space through multiplication. It can also represent a collection of $m$ data points in an $n$-dimensional space, where each row vector represents a single data point and each column vector corresponds to a specific feature or coordinate axis. Additionally, a matrix can encode the coefficients of a system of linear equations, or act as a linear map that scales, rotates, or shears geometric objects. In all these roles, the matrix remains a unified object that organizes information in a way that makes computation and analysis systematic.





In the study of matrices, there are two distinct interpretive perspectives for row vectors and column vectors: the conventional linear algebra perspective and the data science perspective. While the mathematical structure of the matrix remains identical, the semantic role assigned to its rows and columns differs significantly between these fields, influencing how operations and data relationships are conceptualized.

| Feature | **Conventional Linear Algebra Perspective** | **Data Science / Programming Perspective** |
| :--- | :--- | :--- |
| **Primary Orientation** | **Column-centric.** Vectors are typically defined as $n \times 1$ matrices (columns). | **Row-centric.** Datasets are typically stored as tables where each record is a row. |
| **Row Vector Interpretation** | Often viewed as a **linear functional** or a covector. In matrix multiplication $Ax$, rows of $A$ compute the dot product with the input vector to produce a single scalar output component. | Represents a single **data point** (sample, observation, or instance). For an $m \times n$ matrix, there are $m$ row vectors, each living in an $n$-dimensional feature space. |
| **Column Vector Interpretation** | Represents a **geometric vector** in space, a basis vector, or the image of a basis element under a linear map. The columns of a matrix span the **Column Space** (Range). | Represents a **feature** (variable, attribute, or coordinate axis). For an $m \times n$ matrix, there are $n$ column vectors, each containing $m$ values across all data points. |
| **Matrix-Vector Multiplication** | $A\mathbf{x}$: The result is a **linear combination of the columns** of $A$. The input $\mathbf{x}$ is a column vector. | $\mathbf{x}A$ or $A^T\mathbf{x}$: Often, operations are designed to process rows. However, standard libraries (like scikit-learn) still use column-major math internally but present data as rows. |
| **Geometric Meaning** | Columns define the **transformation** (where the basis vectors land). Rows define the **constraints** (equations in a system $Ax=b$). | Columns define the **dimensions** of the space (e.g., "Age axis," "Salary axis"). Rows define the **position** of specific entities within that space. |
| **Notation Standard** | $\mathbf{v} \in \mathbb{R}^{n \times 1}$ (Default vector is a column). | $\mathbf{x} \in \mathbb{R}^{1 \times n}$ (Default data record is a row). |

Both interpretive perspectives are mathematically correct and valid within their respective domains. However, if you are focusing on data science fundamentals, the interpretation where **rows represent data points** and **columns represent features** should be the primary focus. This convention aligns with standard dataset structures, statistical analysis methods, and machine learning libraries, ensuring clarity when organizing, processing, and modeling real-world data.


$$
S_{3 \times 3} = \begin{pmatrix} s_{11} & s_{12} & s_{13} \cr s_{21} & s_{22} & s_{23} \cr s_{31} & s_{32} & s_{33} \end{pmatrix}.
$$

$$
\text{A square matrix with three rows and three columns}
$$

$$
S_{4 \times 4} = \begin{pmatrix} s_{11} & s_{12} & s_{13} & s_{14} \cr s_{21} & s_{22} & s_{23} & s_{24} \cr s_{31} & s_{32} & s_{33} & s_{34} \cr s_{41} & s_{42} & s_{43} & s_{44} \end{pmatrix}.
$$

$$
\text{A Square matrix with four rows and four columns}
$$






---
# 3. Previous Content



<center>
\text{A tall matrix with four rows and two columns}
</center>

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





## 2.4. Tall Matrix

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

## 2.5. Wide Matrix

Conversely, a matrix with more columns than rows, written $n \times m$ where $m > n$, is wider than it is tall. A $2 \times 4$ matrix with 2 rows and 4 columns is:
$$
C_{2 \times 4} = \begin{pmatrix} c_{11} & c_{12} & c_{13} & c_{14} \cr c_{21} & c_{22} & c_{23} & c_{24} \end{pmatrix}.
$$

A $3 \times 5$ wide matrix, with three rows and five columns, is:
$$
E_{3 \times 5} = \begin{pmatrix} e_{11} & e_{12} & e_{13} & e_{14} & e_{15} \cr e_{21} & e_{22} & e_{23} & e_{24} & e_{25} \cr e_{31} & e_{32} & e_{33} & e_{34} & e_{35} \end{pmatrix}.
$$

This shape often appears when there are fewer equations than unknowns, leading to multiple possible solutions.



$$
D =
\begin{pmatrix}
30 & 50000 & 175 & 70 \cr
25 & 45000 & 160 & 55 \cr
45 & 80000 & 180 & 85
\end{pmatrix}
\begin{array}{l}
\leftarrow \mathrm{Person\ 1\ (Row\ 1)} \cr
\leftarrow \mathrm{Person\ 2\ (Row\ 2)} \cr
\leftarrow \mathrm{Person\ 3\ (Row\ 3)}
\end{array}
$$


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
$$



### Next 


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
$$



### Matrix of System of Linear Equations 

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
$$


### System of Linear Equations with Annotations


$$
\begin{cases}
2x_1 - x_2 + x_3 = 8 \cr
-3x_1 + 2x_2 + 2x_3 = -11 \cr
x_1 + x_2 - x_3 = 0
\end{cases}
\qquad 
\begin{array}{l}
\leftarrow \mathrm{Linear\ Equation\ 1} \cr
\leftarrow \mathrm{Linear\ Equation\ 2} \cr
\leftarrow \mathrm{Linear\ Equation\ 3}
\end{array}
$$



### System of Linear Equations without Annotations 

$$
\begin{cases}
2x_1 - x_2 + x_3 = 8 \cr 
-3x_1 + 2x_2 + 2x_3 = -11 \cr 
x_1 + x_2 - x_3 = 0
\end{cases}
$$



### System of Linear Equations with Row and Column Annotations 


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




### Numerical Values in System of Linear Equations in Bold 


$$
\begin{cases}
\mathbf{2}x_1 - \mathbf{1}x_2 + \mathbf{1}x_3 = \mathbf{8} \cr
-\mathbf{3}x_1 + \mathbf{2}x_2 + \mathbf{2}x_3 = \mathbf{-11} \cr
\mathbf{1}x_1 + \mathbf{1}x_2 - \mathbf{1}x_3 = \mathbf{0}
\end{cases}
\qquad 
\begin{array}{l}
\leftarrow \mathrm{Linear\ Equation\ Eq.\ 1} \cr
\leftarrow \mathrm{Linear\ Equation\ Eq.\ 2} \cr
\leftarrow \mathrm{Linear\ Equation\ Eq.\ 3}
\end{array}
$$



### System of Linear Equations 


$$
\begin{cases}
2x_1 - 1x_2 + 1x_3 = 8 \cr
-3x_1 + 2x_2 + 2x_3 = -11 \cr
1x_1 + 1x_2 - 1x_3 = 0
\end{cases}
\qquad 
\begin{array}{l}
\leftarrow \mathrm{Linear\ Equation\ Eq.\ 1} \cr
\leftarrow \mathrm{Linear\ Equation\ Eq.\ 2} \cr
\leftarrow \mathrm{Linear\ Equation\ Eq.\ 3}
\end{array}
$$





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



\