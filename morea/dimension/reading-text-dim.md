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

Suppose the assertion was false. There are linearly independent sets, $$\{{\bf v}_1, \cdots , {\bf v}_n\}$$ as well as $$\{{\bf w}_1, \cdots , {\bf w}_m\}$$, both maximal in a linear space $$\mathcal L$$, and with sizes $$n\ne m$$. One of the sets is larger than another, without loss of generality, let $$n \ge m$$. 

Now let $$ V = \begin{bmatrix} {\bf v}_1 & \cdots & {\bf v}_n \end{bmatrix}$$ and $$W = \begin{bmatrix} {\bf w}_1 & \cdots & {\bf w}_m \end{bmatrix}$$. Now since $$W$$ contains a maximal linearly independent set for its columns, any vector in the linear space $$\mathcal L$$, including $${\bf v}_1, \cdots , {\bf v}_n$$ be written as a linear combination of the columsn of $$W$$. Therefore, there is a matrix $$T$$ such that

$$ V = WT$$

where $$V$$ has $$n$$ columns, $$W$$ has $$m$$ columns, so $$T$$ is $$m\times n$$. Recall $$m\le n$$, so $T$$ has more columns than rows. From our basic understanding of elimination, there is a free column in $$T$$ since no row can have more than one pivot. But this means there is a vector $$\x \ne {\bf 0}$$ with $$n$$ coordinates such that $$T\x ={\bf 0}$$. From the equation above 

$$ V \x = WT\x = W(T\x) = {\bf 0} $$

as well. Since $$\x\ne {\bf 0}$$, $$V{\bf x} = {\bf 0}$$ means that $$V$$ has free columns too, a contradiction on our assumption that the columns of $$V$$ were
linearly independent.

Therefore all maximal linearly independent sets in a linear space have the same size---this is a property of the linear space, and we call this the \emph{dimension} of the linear space. 
