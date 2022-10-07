Let $A$ is $N \times D$ matrix, $B$ is $D \times M$ matrix, $f: C \rightarrow \R$ is some scalar function of matrix argument $C$, where $C = AB$. We also know  $\frac{\partial y}{\partial C}$. Derive $\frac{\partial f}{\partial A}$, $\frac{\partial f}{\partial B}$.  
Let's make a simple example: $N = D = M = 2$. Then 
$
A = 
\begin{bmatrix} 
a_0 & a_1 \\
a_2 & a_3 \\
\end{bmatrix}
$,
$
B = 
\begin{bmatrix} 
b_0 & b_1 \\
b_2 & b_3 \\
\end{bmatrix}
$.  
Let's find $\frac{\partial y}{\partial A}$.
1. Let's consider first row of $A = a$ and first column of $B = b$.  
Then $c = a \cdot b = a_0b_0 + a_1b_1$ is a scalar.  
$
\frac{\partial y}{\partial a_0} = 
\frac{\partial y}{\partial c} \frac{\partial c}{\partial a_0} = 
\frac{\partial y}{\partial c} b_0
$
2. Let's consider first row of $A = a$ and full matrix $B$.  
Then $
c = aB = 
\begin{bmatrix}c_0 & c_1\end{bmatrix} =
\begin{bmatrix}a_0b_0 + a_1b_1 & a_0b_1 + a_1b_3\end{bmatrix} = 
$ is a row vector.  
$
\frac{\partial y}{\partial a_0} = 
\frac{\partial y}{\partial c} \frac{\partial c}{\partial a_0} = 
\begin{bmatrix}
\frac{\partial y}{\partial c_0} & \frac{\partial y}{\partial c_1}
\end{bmatrix} 
\begin{bmatrix} 
b_0 \\ b_1
\end{bmatrix}
$  
Note that:
* left operand is i-th row in $\frac{\partial y}{\partial C}$, $0 \le i < N$
* right operand is j-th row in $B$, $0 \le j < D$  
So, $\frac{\partial y}{\partial A} = \frac{\partial y}{\partial C} B^\top$

Let's find $\frac{\partial y}{\partial B}$.
1. Let's consider first row of $A = a$ and first column of $B = b$.  
Then $c = a \cdot b = a_0b_0 + a_1b_1$ is a scalar.  
$
\frac{\partial y}{\partial b_0} = 
\frac{\partial y}{\partial c} \frac{\partial c}{\partial b_0} = 
\frac{\partial y}{\partial c} a_0
$
2. Let's consider full matrix $A$ and first column of $B = b$.  
Then $
c = Ab = 
\begin{bmatrix}c_0 \\ c_1\end{bmatrix} =
\begin{bmatrix}a_0b_0 + a_1b_1 \\ a_2b_0 + a_3b_1\end{bmatrix}
$ is a column vector.  
$
\frac{\partial y}{\partial b_0} = 
\frac{\partial y}{\partial c} \frac{\partial c}{\partial b_0} = 
\begin{bmatrix} 
a_0 & a_2
\end{bmatrix}
\begin{bmatrix}
\frac{\partial y}{\partial c_0} \\ \frac{\partial y}{\partial c_1}
\end{bmatrix} 
$  
Note that:
* left operand is i-th column in $A$, $0 \le i < D$  
* right operand is j-th column in $\frac{\partial y}{\partial C}$, $0 \le j < M$  
So, $\frac{\partial y}{\partial B} = A^\top \frac{\partial y}{\partial C}$