---
title: "Guide for the Text"
published: true
morea_id: reading-text-linspace
morea_summary: "Chapters 3.1 and 3.2"
morea_type: reading
morea_labels:
---

We primarily focus on the definitions of the linear spaces here. You have
to be comfortable in all the ways you can express the four fundamental 
linear spaces of a matrix. Chapter 3.2 also contains how to find all $$\bf x$$
such that $$A{\bf x}=0$$ (ie characterize all vectors of the null space).
 
Also note that Chapter 3.2 goes into what happens when you encounter
free columns in elimination, but we already know that from the
elimination module.  Rather than treat elimination piece by piece, we
learnt the entire procedure and all its cases (and you have written
code for that) in prior modules. Note that we didn't stop at the upper
triangular matrix in the Gaussian elimination module, we went on to get
to the reduced row echelon form, which is only introduced now in Chapter 3.2.

## Column and row spaces
We have been seeing matrices in terms of its rows and columns, but to really
use the power of the ideas we are developing, we have to go beyond even this.
Instead when we see a bunch of vectors, we also think of every
vector that can be formed by linear combinations of the given vectors. This
is the motivation behind why we define linear spaces.

A linear space $${\mathcal L}$$ is a set of vectors that are **closed under linear combinations**. This means that if you take any finite set of vectors $$\left\{{\bf x}_1\upto {\bf x}_n \right\}\subseteq {\mathcal L}$$, then for all numbers $$\alpha_1\upto \alpha_n$$, the linear combination

$$\alpha_1 {\bf x}_1 + \cdots + \alpha_n {\bf x}_n$$

is also in $${\mathcal L}$$. So we cannot generate an element out of the set $${\mathcal L}$$ by making linear combinations of elements from $${\mathcal L}$$.

We went over multiple examples in class. The most important are the fundamental spaces of a matrix. The first is the column space of $$A$$, which is the set of all linear combinations of the columns of $$A$$. In other words, if $$A$$ is a $$m\times n$$ matrix, 

$$ \text{col}(A) = \left\{ A{\bf w} : {\bf w} \in {\mathbb R}^n \right\}, $$

and every element of col$$(A)$$ is a vector with $$m$$ coordinates, i.e. col$$(A)\subseteq {\mathbb R}^m$$.

Why is this a linear space? Let $${\bf u}_1, \cdots {\bf u}_n$$ be $$n$$ elements of the column space. Now, any linear combination of $${\bf u}_1, \cdots {\bf u}_n$$ is

$$\begin{bmatrix} {\bf u}_1 & \cdots & {\bf u}_n \end{bmatrix} {\bf z},$$

where $$\bf z$$ is a vector with $$n$$ coordinates. But
since each vector is a linear combination of the columns of $$A$$, $${\bf u}_i = A{\bf w}_i$$ for some $${\bf w}_i\in{\mathbb R}^n$$, we have

$$\begin{bmatrix} {\bf u}_1 & \cdots & {\bf u}_n \end{bmatrix}{\bf z}
=
\begin{bmatrix} A{\bf w}_1 & \cdots & A{\bf w}_n \end{bmatrix}{\bf z}
=
A\begin{bmatrix} {\bf w}_1 & \cdots & {\bf w}_n \end{bmatrix}{\bf z}
= AW{\bf z} = A{\bf c},
$$

where $$W$$ is the matrix $$\begin{bmatrix} {\bf w}_1 & \cdots & {\bf w}_n \end{bmatrix}$$ and $$\bf c$$ is the vector $$W{\bf z}$$. But $$A{\bf c}$$ is simply a linear combination of the columns of $$A$$ again, thus it belongs to the column space of $$A$$. 

Therefore we showed that any linear combination of vectors in the column space of $$A$$ is simply another linear combination of the columsn of $$A$$, thus a member of the column space of $$A$$ again. Therefore the column space of $$A$$ is a linear space.

## Null space of $$A$$

The null space of $$A$$ borrows ideas from elimination. The idea is that every time a (free) column is a linear combination of the prior columns, we can write a vector $$\bf z$$ that is both non-zero and that satisfies $$A{\bf z}={\bf 0}$$.

Why? Suppose we have a matrix $$A$$ with 5 columns, where column 3 is free, and is the sum of the prior two columns. Then, we have (writing $${\bf c}_i$$ for column $$i$$)

$${\bf c}_3 = {\bf c}_1 + {\bf c}_2 \text{ or } {\bf c}_3 - {\bf c}_1 - {\bf c}_2 = {\bf 0}. $$

So the relation between columns just translated to a linear combination above of 5 columns that is equal to $$\bf 0$$. We know how to write linear combinations as matrix multiplications, doing so yields:

$$ A \begin{bmatrix} -1 \\ -1\\ 1\\ 0 \\ 0 \end{bmatrix} = {\bf 0}.$$

Similarly, every time anyone gives us a non-zero vector $$\bf z$$ such that $$A{\bf z} = 0$$, we can see it equivalently as a non-trivial dependency among the columns of the matrix. 

