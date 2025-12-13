---
title: "Linear Independence"
published: true
morea_id: reading-text-linind
morea_summary: "Chapters 3.3 and 3.5"
morea_type: reading
morea_labels:
---

Chapter 3.3 works with the pivots of a matrix. Some content from
Chapter 3.3 is defined only in Chapter 3.5, and most of Chapter 3.3
is better understood in the context of Chapter 3.5.

The very first definition in Chapter 3.3 says "the rank of $$A$$ is
the number of pivots". The narrow interpretation is that this is a
definition that is based on how we define Gaussian elimination, but
the reality, as you learn later is that it is not. It does not matter
how you reorder the columns, whether you modify Gaussian elimination
(in a sane way) or more. Chapter 3.3 states: "The rank is the
dimension of the column space of $$A$$", but at this point in the
text, the term/concept "dimension" is not yet defined, and you have to
wait till Chapter 3.5 to know what is meant. Also, as we showed in
class, a minor miracle is that the row space of $$A$$ has the same
dimension.

The development in class goes from Chapter 3.5 $$\to$$ Chapter 3.3. A lot
of insights in Chapter 3.3 must be familiar to you even before you get
here (for eg. Every free column is a combination of earlier pivot
columns).  In fact, you also know how to get the exact linear
combination of the prior columns that yields that particular free
column (from the rref).

## Additional insights

$$\newcommand{\upto}{,\cdots,}$$
If you have $$n$$ linearly independent vectors $${\bf v}_1\upto {\bf v}_n \in {\mathbb R}^d$$, let



$$ V = \begin{bmatrix} {\bf v}_1 & \cdots & {\bf v}_n \end{bmatrix}$$

be the $d\times n$ matrix that places all the $$n$$ vectors as its columns. By definition of linear independence all columns are pivot columns. One of the first insights is that any reordering of the columns of $$V$$ (where all columns are pivots) still keeps all
columns to be pivot columns. Can you see (by contradiction) why this should be so?

Now this means (using our way of solving equations by putting the
target as the last column of an augmented matrix) that no vector
$${\bf v}_i$$ can be written as a linear combination of the other $$n-1$$
vectors. 

As we discussed in class, in every linear space $$\mathcal L$$, a set
of linearly independent vectors $${\bf v}_1\upto {\bf v}_n$$ is \emph{maximal}
if we cannot expand this set using any other vector $${\bf x} \in
\mathcal L$$ and still preserve the linear independence
property. Specifically, this can only happen if for all $${\bf x} \in
\mathcal L$$,

$$ \begin{bmatrix} {\bf v}_1 & \cdots & {\bf v}_n & {\bf x} \end{bmatrix}$$

has a free column. The only way the matrix above can have a free column is
if the last column is free (since we know the matrix $$V$$ above does not have
free columns by definition of linear independence of $${\bf v}_1,\cdots, {\bf v}_n$$. But
this means that $$\bf x$$ is the free column above, and therefore that $$\bf x$$ is a linear combination of $${\bf v}_1,\cdots, {\bf v}_n$$!

So if $${\bf v}_1,\cdots, {\bf v}_n$$ is a maximal set of linearly independent vectors
in $$\mathcal L$$, every vector $${\bf x}\in \mathcal L$$ is a linear combination
of $${\bf v}_1,\cdots, {\bf v}_n$$. 


Conversely, if every vecotr $$\bf x$$ in a linear space can be written as a linear combination of a set of linearly independent vectors $${\bf v}_1,\cdots, {\bf v}_n$$, then 
the set is maximal by definition. 


## Column and row spaces

The above discussion implies that if $$A$$ is a matrix with rref $$R$$, the pivot columns of $$A$$ are a maximal linearly independent set in the column space of $$A$$. In general, the pivot columns of $$R$$, the rref of $$A$$, are not necessarily a maximal linearly independent in the column space of $$A$$ (in fact, they may not even be in the column space of $$A$$). Can you see this?

Similarly the non-zero rows of $$R$$, the rref of $$A$$, will be a maximal linearly independent set in the row space of $$A$$. 

Looking at the transpose of $$A$$, $$A^T$$. Let the rref of $$A^T$$ be $$R_1$$. Now $$R_1$$ and $$R$$ are not transposes of each other in general. Using the above observations, the pivot columsn of $$A^T$$ is a maximal linearly independent set for the column space of $$A^T$$, ie., the row space of $$A$$. Similarly the non-zero rows of $$R_1$$, the rref of $$A^T$$, will be a maximal linearly independent set in the row space of $$A^T$$, ie the column space of $$A$$.

We have another name for maximal linearly independent sets in the linear space $$\mathcal L$$: a basis for $$\mathcal L$$.
