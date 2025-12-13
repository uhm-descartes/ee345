---
title: "Guide for the Text"
published: true
morea_id: reading-text-dim
morea_summary: "Chapters 3.5"
morea_type: reading
morea_labels:
---

This continues our study of linear independence. The text goes a
little into abstract spaces where the elements are not vectors, but
functions. There is a little bit about solving differential equations
in general, namely casting a general solution as the sum of a
particular solution and the null space, analogous to what we did in
class for matrix solutions. In EE 213, and in differential equations
in general, you would pick one among all possible solutions
using boundary conditions. In the lab, you will see how in machine
learning, we pick one among all possible solutions using _regularization_,
in an effort to buy generalizability. 


## Dimension

We showed in class that all maximal linearly independent sets have the same shape using elimination ideas. We prove this by a proof by contradiction.

Suppose the assertion was false. There are linearly independent sets, {$${\bf v}_1, \cdots , {\bf v}_n$$} as well as {$${\bf w}_1, \cdots , {\bf w}_m$$}, both maximal in a linear space $$\mathcal L$$, and with sizes $$n\ne m$$. One of the sets is larger than another, without loss of generality, let $$n \ge m$$. 

Now let $$V = \begin{bmatrix} {\bf v}_1 & \cdots & {\bf v}_n \end{bmatrix}$$ and $$W = \begin{bmatrix} {\bf w}_1 & \cdots & {\bf w}_m \end{bmatrix}$$. Now since $$W$$ contains a maximal linearly independent set in $$\mathcal L$$ for its columns, any vector in the linear space $$\mathcal L$$, including the vectors $${\bf v}_1, \cdots , {\bf v}_n$$, be written as linear combinations of the columsn of $$W$$. Therefore, there is a matrix $$T$$ such that

$$V = WT$$

where $$V$$ has $$n$$ columns, $$W$$ has $$m$$ columns, so $$T$$ is $$m\times n$$. Recall $$m\le n$$, so $$T$$ has more columns than rows. From our basic understanding of elimination, there is a free column in $$T$$ since no row can have more than one pivot. But this means there is a vector $${\bf x} \ne {\bf 0}$$ with $$n$$ coordinates such that $$T{\bf x} ={\bf 0}$$. From the equation above 

$$ V {\bf x} = WT{\bf x} = W(T{\bf x}) = {\bf 0} $$

as well. Since $${\bf x}\ne {\bf 0}$$, $$V{\bf x} = {\bf 0}$$ means that $$V$$ has free columns too, a contradiction on our assumption that the columns of $$V$$ were
linearly independent.

Therefore all maximal linearly independent sets in a linear space have the same size---this is a property of the linear space, and we call this the \emph{dimension} of the linear space. 


## Dimension of fundamental spaces

If a matrix $$A$$ has $$k$$ pivots, we saw that the $$k$$ pivot
columns form a maximal linearly independent set in $$A$$. No matter
how you rearrange the columsn, the number of pivot columns cannot change because all maximal linear independent sets have the same size.

Therefore from our notes on bases for the column and row spaces of $$A$$, the 
pivot columns of $$A$$ are a basis for the column space of $$A$$. So the dimensino of the column space of $$A$$ is the number of pivots in $$A$$, equal to $$k$$. The basis for the row space of $$A$$ are the non-zero rows of the rref, and the number of non-zero rows in the rref equals the number of pivots (one pivot per non-zero row, every row below them is zeroed out). So the row space also has dimension equal to $$k$$, the number of pivots in $$A$$.

There is a "cool" proof of the above result too. If $$P$$ is a matrix whose columns are the pivot columns of $$A$$, we have

$$A = PC$$

since every column of $$A$$ is a linear combination of the pivot columns. If $$A$$ is $$m\times n$$, $$P$$ is $$m\times k$$ and therefore $$C$$ is $$k\times n$$. But this also means that every row of $$A$$ is a linear combination of the $$k$$ rows of $$C$$. Since we don't know if the rows of $$C$$ are linearly independent, we can conclude that the set of linearly independent rows of $$C$$ can represent every row of $$A$$ and therefore every vector in the row space of $$A$$ as well. So the row space of $$A$$ has dimension $$\le $$ dimension of the column space of $$A$$.

Using this exact argument for $$A^T$$, we have the row space of $$A^T$$ has dimension $$\le$$ dimension of the column space of $$A^T$$. But row space of $$A^T$$ is the column space of $$A$$ and the column space of $$A^T$$ is the row space of $$A$$. So the column space of $$A$$ has dimension $$\le$$ dimension of the row space of $$A$$.

Put the two together, the column and row spaces have the same dimension.

## Dimension of null spaces

We can write for each free column in $$A$$ a relation that expresses that free column as a linear combination of the prior pivot columns. Each time we get an expression that expresses a column in terms of others, we get a non-zero vector in the null space of $$A$$ as we saw in class.

Now note that every vector in the null space is in $${\mathbb R}^n$$. As is every vector in the row space of $$A$$.

If $$A$$ is $$m\times n$$ and has $$k$$ pivot columns, it means $$A$$ has $$n-k$$ free columns. So counting one non-zero vector for each free column, we can build a set with $$n-k$$ linearly independent vectors in the null space of $$A$$. Call this set $$N$$. 

Are there more? The answer is no. The reason comes from noting that the null space of $$A$$ and the row space of $$A$$ are orthogonal spaces, meaning for each $${\bf v}\in \text{null}(A)$$ and each $${\bf w} \in \text{row}(A)$$, $${\bf v}^T{\bf w} =0$$. 

Let us pool together the basis for the row space of $$A$$ and these $$n-k$$ linearly independent vectors in the null space, $$N$$, that we constructed above. Any basis for the row space of $$A$$ has $$k$$ vectors, call one such set $$R$$. 

Now $$R \cup N$$ (the union of the sets) has $$k + (n-k) =n$$ vectors. They are all linearly independent (why?). But the basis for the set of all vectors in $${\mathbb R}^n$$ must have only $$n$$ vectors, so $$R\cup N$$ is a basis for $${\mathbb R}^n$$. Therefore $$R\cup N$$ is maximal, meaning $$N$$ must be maximal in the null space of $$A$$ as well!

This means the dimension of the null space of $$A$$ is _exactly_ $$n-k$$. Similarly the dimension of the null space of $$A^T$$ is $$m-k$$, by applying the abbove arguments to $$A^T$$.

We call the row space of $$A$$ and the null space of $$A$$ to be _orthogonal complements_. They are orthogonal spaces, that together provide a complete basis for $${\mathbb R}^n$$. Note however that their union is _not_ $${\mathbb R}^n$$ (only that every element in $${\mathbb R}^n$$ is a sum of one vector in the row space of $$A$$ and one vector in the null space of $$A$$). Similarly, the row space of $$A^T$$ (ie column space of $$A$$) and the null space of $$A^T$$ are also orthogonal complements by using the same arguments above for the matrix $$A^T$$.

## Preview of linear regression

Given that $$R\cup N$$ is a basis for $${\mathbb R}^n$$, we notice that every vector $${\bf x} \in {\mathbb R}^n$$ can be written 

$${\bf x} = {\bf r} + {\bf n},$$

where $$\bf r$$ is the component built from the basis vectors in $$R$$, namely a vector in row($$A$$) and a vector $$\bf n$$ is the component built from basis vectors in $$N$$, a vector in the null space of $$A$$. So one vector in the row space and one vector in the null space.

Similarly any vector $${\bf y} \in {\mathbb R}^m$$ can be written as 

$${\bf y} = {\bf c} + {\bf e},$$

where $$\bf c$$ is a vector in the row space of $$A^T$$ (so column space of $$A$$) and $$\bf e$$ is in the null space of $$A^T$$. This is the picture we will develop in the next module as linear regression.
