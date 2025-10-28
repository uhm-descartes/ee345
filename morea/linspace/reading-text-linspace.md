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
$$\newcommand{\u}{{\bf u}}$$
$$\newcommand{\v}{{\bf v}}$$
$$\newcommand{\sets}[1]{\left\{ #1 \right\}}
We have been seeing matrices in terms of its rows and columns, but to really
use the power of the ideas we are developing, we have to go beyond even this.
Instead when we see a bunch of vectors, we also think of every
vector that can be formed by linear combinations of the given vectors. This
is the motivation behind why we define linear spaces.

A linear space $${\mathcal L}$$ is a set of vectors that are **closed under linear combinations**. This means that if you take any finite set of vectors $$\left\{{\bf x}_1\upto {\bf x}_n \right\}\subseteq {\mathcal L}$$, then for all numbers $$\alpha_1\upto \alpha_n$$, the linear combination

$$\alpha_1 {\bf x}_1 + \cdots + \alpha_n {\bf x}_n$$

is also in $${\mathcal L}$$. So we cannot generate an element out of the set $${\mathcal L}$$ by making linear combinations of elements from $${\mathcal L}$$.
