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

### $$A$$ is $$n\times n$$ matrix with $$n$$ pivots iff there is a matrix $$B$$ such that $$AB=I$$

We only prove that if $$A$$ is a $$n\times n$$ matrix with $$n$$
pivots, there is a matrix $$B$$ such that $$AB=I$$ in this
writeup. The converse is left as an exercise. If you cannot prove the
converse yourself, I strongly recommend you come to me and learn how
to prove it.

Not all square $$n\times n$$ matrices have $$n$$ pivots. But suppose
$$A$$ is a square $$n\times n$$ matrix with $$n$$ pivots. Then when
you consider solving $$A{\bf x} = {\bf b}$$, the augmented matrix is

$$ \begin{bmatrix} A & {\bf b} \end{bmatrix}. $$

When doing elimination on the augmented matrix above, notice that
we find a pivot in each of the first $$n$$ columns because $$A$$ has
a pivot in each column, the presence of the augmented column doesn't
change the pivots we obtained for the first $$n$$ columns. At the
end of the $$n'$$th column, we have exhausted all rows, so there are
no more pivots to be found. 

Therefore the last column is a _free_ column, regardless of what $$\bf
b$$ is. Therefore $$A{\bf x}={\bf b}$$ has a solution for all $$\bf b$$.
Moreover the solution is unique since $$A$$ has no free columns. 

For $$1\le i\le n$$, let $${\bf e}_i$$ be a vector with $$n$$
coordinates, 1 in the $$i'$$th coordinate and 0 everywhere
else. Therefore, there exists unique vectors $${\bf x}_i$$, $$1\le i\le n$$
such that

$$\begin{align*} 
	A{\bf x}_1 &= {\bf e}_1\\
		\vdots\\
	A{\bf x}_i &= {\bf e}_i\\		
		\vdots\\
	A{\bf x}_n &= {\bf e}_n\\
\end{align*}$$

Therefore, there is a _unique_ matrix $$B$$

$$ B = \begin{bmatrix} {\bf x}_1 & \ldots & {\bf x}_n \end{bmatrix} $$

satisfying

$$A B = \begin{bmatrix} A {\bf x}_1 & \ldots & A{\bf x}_n \end{bmatrix} = 
\begin{bmatrix} {\bf e}_1 & \ldots & {\bf e}_n \end{bmatrix} = I_n. $$

The converse would be: if there is a matrix $$B$$ satisfying $$AB=I$$
for a $$n\times n $$ matrix $$A$$, then $$A$$ must have $$n$$ pivots.

We will not prove it in class due to time constraints, but I strongly
urge you to prove the converse. In fact, you can prove a stronger
statement than given: if there is a matrix $$B$$ satisfying $$AB=I$$
for a $$n\times n $$ matrix $$A$$, then both $$A$$ and $$B$$ must have
$$n$$ pivots each.

### For all $$n\times n$$ matrices $$A$$ with $$n$$ pivots, there is a matrix $$C$$ such that $$CA=I$$

This follows from one of the problems in the prior module. Recall that if $$A$$
is square with $$n$$ pivots, Gaussian elimination (row operations) allows us
to write

$$ U_1\cdots U_1 D L_n\cdots L_1 A =I, $$

where $$U_i$$ is the matrix that does the row operations to find and eliminate
every number above the pivot in the $$i'$$th column, $$D$$ normalizes
each of the $$n$$ pivots to 1, and $$L_j$$ finds and zeros every entry below the
pivot in the $$j'$$th column. We say "finds" because while tackling any column,
it may be necessary to perform a row permutation to bring the pivot to its place. Note also that we use $$U_i$$ and $$L_j$$, but if row permutations were used, they may not correspond to upper-triangular or lower-triangular matrix (we use
it nevertheless to indicate above/below pivot).

Let 

$$ C = U_1\cdots U_1 D L_n\cdots L_1. $$

Thus $$CA = I$$.

### Every $$n\times n$$ square $$A$$ with $$n$$ pivots has a unique inverse $$A^{-1}$$ satisfying $$AA^{-1} = A^{-1}A = I$$.

We will show that the matrices $$B$$ and $$C$$ of the prior sections must
be equal. To see this, note that

$$CAB = (CA)B = IB = B$$

but also

$$CAB = C(AB) = CI = C,$$

so that $$CAB = B = C$$, or $$B=C$$. Recall also that we observed
$$B$$ was unique, so $$C$$ must be as well. We call this unique matrix
$$B= C= A^{-1}$$ as the _inverse_ of $$A$$.




