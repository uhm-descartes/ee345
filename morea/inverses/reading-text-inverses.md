---
title: "Guide for the Text"
published: true
morea_id: reading-text-inverses
morea_summary: "Chapter 2.5"
morea_type: reading
morea_labels:
---

The solution of $$A{\bf x}={\bf b}$$ is unique if and only if (i)
$$\bf b$$ is a linear combination of the columns of $$A$$, and (ii)
$$A$$ has no free columns. $$A$$ itself could be square or
tall-rectangular (it can never be wide-rectangular, why?). The case
where $$A$$ is square is special. If $$A$$ is a square $$n\times n$$ matrix,
then the fact that $$A$$ has no free columns implies it has $$n$$ pivot
columns, ie, that it has $$n$$ pivots. 

Chapter 2.5 examines the case when $$A$$ is a square matrix with $$n$$
pivots. In that case, the primary insight is that the action of $$A$$
can be undone elegantly, by means of what is called the _inverse_ of
$$A$$, denoted by $$A^{-1}$$.

## Textbook approach
In the text, you will find a prophetic and mysterious definition of
the inverse in the beginning of Section 2.5. But why should there be
such a matrix? What if only $$AA^{-1}=I$$ and not $$A^{-1}A$$ (or the
other way around)? What is the point of such a matrix? Where does it
come from? Only the last subsection (Singular and Invertible) resolves
the mysteries. Instead, in class, we let inverses follow naturally
from our previous module, Elimination.


## Class approach
There is no reason for a detective novel approach. The idea of an
inverse follows naturally from Elimination, as do its properties. Here
is how we approached this in class.


### If $$A$$ is $$n\times n$$ matrix with $$n$$ pivots, there is a matrix $$B$$ such that $$BA=I$$

If $$A$$ has $$n$$ pivots, all columns are pivot columns. Therefore

$$\text{rref}(A) = I.$$

Now we perform a series of reversible row operations to get $$A$$ into the rref forms, and as we understood in the elimination module, each such reversible row operation is a **matrix multiplication on the left**. 

Let the operations we perform correspond to $$R_1, R_2, \ldots R_k$$ in sequence (meaning we perform row operation $$R_1$$ first, $$R_k$$ last). Then the process of transforming $$A$$ into its reduced row echelon form is 

$$ R_k R_{k-1} \cdots R_1 A = I.\tag{1}$$

Letting 

$$B \stackrel{\text{def}}{=} R_k R_{k-1} \cdots R_1, \tag{2}$$ 

we have $$BA=I$$. The converse is true too, but we will show it after the next step.


### If $$A$$ is $$n\times n$$ matrix with $$n$$ pivots, if there is a matrix $$B$$ such that $$AB=I$$

We will actually show that the same matrix $$B$$ from Equation~{(2)} will satisfy $$AB=I$$. Start from Equation~(1). Note that each row operation we perform is reversible by another row operation (for example, add 2 $$\times$$ row 1 to row 2 is reversed by subtract 2 $$\times$$ row 1 from row2), and denote the reversal of operation $$R_i$$ by $$R_i^{-1}$$. In matrix form, the reversal is another multiplication on the left, so we have for all $$i$$,

$$R_i^{-1} R_i =I.$$ 

Then (note that you have to undo the last operation first---if you wear socks and shoes, you have to remove shoes first then socks):

$$ A = R_1^{-1} \cdots R_{k}^{-1}. $$

Now it is simple to verify that using Equation~(2) and the associative
law of multiplication (if you have a series of matrices you are
multiplying, you can multiply any two adjacent matrices first and
replace them with their product, as long as you do not mess up the
order of matrices):

$$ AB = (R_1^{-1} \cdots R_{k}^{-1}) (R_k R_{k-1} \cdots R_1) = I $$

The matrix $$B$$ above is called the **inverse** of $$A$$ and is denoted
by $$A^{-1}$$.

### If for any square $$n\times n$$ matrix $$A$$, there is another matrix $$B$$ such that $$AB=I$$, then $$A$$ has $$n$$ pivots.

This is a result that follows from combining ideas in elimination and
matrix multiplication. Because $$AB=I$$, every column of $$I$$ is a
linear combination of the columns of $$A$$. Furthermore any vector
$${\bf b}$$ is a linear combination of the columns of the identity matrix.

Therefore, consider elimination of the following matrix

$$\begin{bmatrix} A & I & {\bf b} \end{bmatrix}$$

Where are the pivots? Since every column of $$I$$ is known to be a linear
combination of the columns of $$A$$, they are all free. 

The last column cannot be a pivot column no matter how we choose $$\bf
b$$, since they are definitely a linear combination of the columns of
$$I$$ (to note that $$\bf b$$ will be a free columns, we really don't
need to care at this point if they are linear combinations of the
columns of $$A$$!).

So no matter how we choose the vector $$\bf b$$, we cannot have a pivot in
that column. The only way this can happen is if all $$n$$ __rows__ of the augmented matrix above have pivots before we come to the final column. Since the pivots were not in the columns of $$I$$, they must have been in $$A$$. Therefore $$A$$ has $$n$$ pivots.

### Another operational way to find inverses
Not all square $$n\times n$$ matrices have $$n$$ pivots. But suppose
$$A$$ is a square $$n\times n$$ matrix with $$n$$ pivots. Then we saw
there is a matrix $$A^{-1}$$ such that $$AA^{-1}=I$$. The form of the 
above equation is also a simple recipe to find $$A^{-1}$$.

For $$1\le i\le n$$, let $${\bf e}_i$$ be the $$i'$$th column of the
identity matrix $$I$$, a vector with $$n$$
coordinates, 1 in the $$i'$$th coordinate and 0 everywhere
else. So we are seeing $$AA^{-1}=I$ as

$$\begin{bmatrix} {\bf e}_1 & \cdots & {\bf e}_n \end{bmatrix}
= I = AA^{-1} = A\begin{bmatrix} {\bf x}_1 &\cdots & {\bf x}_n \end{bmatrix},$$

where we think of the $$n$$ columns of $$A^{-1}$$ as 
$${\bf x}_1, \cdots, {\bf x}_n$$ respectively. Then we immediately see that the
columns of $$A^{-1}$$ are respectively solutions of the equations 
$$\begin{align*} 
	A{\bf x}_1 &= {\bf e}_1\\
		\vdots\\
	A{\bf x}_i &= {\bf e}_i\\		
		\vdots\\
	A{\bf x}_n &= {\bf e}_n\\
\end{align*}$$

Each equation above has a unique solution since $$A$$ has no free columns.
Therefore, we get for free that $$A^{-1}$$ must be unique.

### Every $$n\times n$$ square $$A$$ with $$n$$ pivots has a unique inverse $$A^{-1}$$ satisfying $$AA^{-1} = A^{-1}A = I$$.

We will show that the matrices $$B$$ and $$C$$ of the prior sections must
be equal. To see this, note that

$$CAB = (CA)B = IB = B$$

but also

$$CAB = C(AB) = CI = C,$$

so that $$CAB = B = C$$, or $$B=C$$. Recall also that we observed
$$B$$ was unique, so $$C$$ must be as well. We call this unique matrix
$$B= C= A^{-1}$$ as the _inverse_ of $$A$$.




