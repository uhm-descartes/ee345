---
title: "Problems in class"
published: true
morea_id: experience-prob-inverses
morea_type: experience
morea_summary: "Inverses"
morea_start_date: "2023-09-21"
morea_labels:
---

# Problems in class

1. Suppose $$A$$ is a $$n\times m$$ matrix with $$m\ne n$$ (so not square). 

	* Show that if $$m \le n$$ ($$A$$ is tall) with pivots in every
      column, then you have a $$m\times n$$ matrix $$C$$ such that $$CA = I_m$$,
	  but there is no matrix $$B$$ such that $$AB =I_n$$. In particular, while
	  $$AC$$ exists, it is not equal to an identity matrix.

	* Guess what happens when $$n\le m$$ ($$A$$ is wide) with pivots
      in every row, and prove it.

2. From the prior problem, show that if $$A$$ is a matrix such that
   there is a matrix $$C$$ satisfying $$CA =I$$ (whose size I do not
   reveal yet) _and_ a matrix $$B$$ such that $$AB=I$$ (again, I
   do not reveal the size), then $$A$$ must be square and
   $$B=C=A^{-1}$$. From the prior problem, note that just one of the
   conditions (either $$CA=I$$ or $$AB=I$$) alone is insufficient.

3. Show that for any square $$A$$, $$(A^T)^{-1} = (A^{-1})^T$$.

4. These problems anticipate a future topic. In all problems below,
   we are only talking of square matrices $$A$$.
   * Show that if any row of $$A$$ is all zero, $$A$$ has no inverse
   * Show that if any two rows are equal in $$A$$, $$A$$ has no inverse
   * Show that if any row of $$A$$ is a linear combination of other rows
	 of $$A$$, then $$A$$ has no inverse
	 
5. Show that if $$I+XY$$ is square and has an inverse, 
   * $$I+YX$$ also has an inverse 
   * $$(I+XY)^{-1}X = X(I+YX)^{-1}$$
   * (I+Z)^{-1} = I - (I+Z)^{-1} Z
   * $$(I+XY)^{-1} = I - X(I+YX)^{-1}Y 
   
   These may seem like gymnastics, but consider the case where $$X$$
   is a column vector and $$Y$$ a row vector, both with the same
   number of coordinates. Then $$I+XY$$ is a square matrix. But $$YX$$
   is just a number and so $$I+YX$$ is just $$1+YX$$, another number,
   whose inverse is just its regular real number
   reciprocal. Therefore, we get $$(I+XY)^{-1}$$ simply as $$I -
   XY/(1+ YX)$$, a simple update that does not require a whole lot of
   calculations. 
   
   The last one, which combines the prior few identities, is the
   essence of the Woodbury-Morrison formula/matrix inversion lemma,
   and shows up everywhere in engineering (Kalman Filters, Recursive
   Least Squares, and many other places). It is usually phrased in a
   little more complicated form, but the last identity above captures
   its essence.
