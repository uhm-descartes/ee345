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

$$\newcommand{\upto}{,\cdots,}
\renewcommand{\v}{{\bf v}}
\newcommand{\reals}{{\mathbb R}}$$

If you have $$n$$ linearly independent vectors $$\v_1\upto \v_n \in \reals^d$$, let

$$ V = \begin{bmatrix} \v_1 & \ldots & \v_n \end{bmatrix}$$

be the $d\times n$ matrix that places all the $$n$$ vectors as its columns. By definition of linear independence all columns are pivot columns. One of the first insights is that any reordering of the columns of $$V$$ (where all columns are pivots) still keeps all
columns to be pivot columns. Can you see (by contradiction) why this should be so?

Now this means (using our way of solving equations by putting the target as the last column of an augmented matrix) that no vector $$\v_i$$ can be written as a linear combination of the other $$n-1$$ vectors.
