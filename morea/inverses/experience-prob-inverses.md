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

1. Suppose $$A$$ is a $$m\times n$$ matrix with $$m\ne n$$ (so not square). 

	* Show that if $$n < m$$ ($$A$$ is tall) with pivots in every
      column, then there is a $$n\times m$$ matrix $$C$$ such that
      $$CA = I_n$$, but there can be no matrix $$B$$ such that $$AB
      =I_n$$. In particular, while $$AC$$ exists, it is not equal to
      an identity matrix.

	* Guess what happens when $$n < m$$ ($$A$$ is wide) with pivots
      in every row, and prove it.

2. Show that if $$A$$ is a $$m\times n$$ matrix (we do not know if
   $$m=n$$ or not) such that there exists $$C$$ satisfying $$CA =I_n$$
   _and_ a matrix $$B$$ such that $$AB=I_m$$, then $$A$$ must be
   square (ie $$m=n$$) and $$B=C=A^{-1}$$. Comparing with the prior
   problem, note that just one of the conditions (either $$CA=I$$ or
   $$AB=I$$) alone is insufficient if we do not know that $$A$$ is
   square. What if we knew $$m=n$$ from the get go?

3. Show that for any square $$A$$, $$(A^T)^{-1} = (A^{-1})^T$$.

4. **Determinants** These problems anticipate a future topic,
   determinants. In all problems below, we are only talking of square
   matrices $$A$$.
   * Show that if any row of $$A$$ is all zero, $$A$$ has no inverse
   * Show that if any two rows are equal in $$A$$, $$A$$ has no inverse
   * Show that if any row of $$A$$ is a linear combination of other rows
	 of $$A$$, then $$A$$ has no inverse
	 
5. **Matrix Inversion Lemma** Show that if $$I+XY$$ is square and has an inverse, 
   * $$I+YX$$ also has an inverse 
   * Show that $$(I+XY)^{-1}X = X(I+YX)^{-1}$$
   * Show that $$(I+Z)^{-1} = I - (I+Z)^{-1} Z$$
   * Using the above, show that
   
      $$(I+XY)^{-1} = I - X(I+YX)^{-1}Y $$
   
   Consider the case where $$X$$ is a column vector and $$Y$$ a row
   vector, both with the same number of coordinates. Then $$I+XY$$ is
   a square matrix. But $$YX$$ is just a number and so $$I+YX$$ is
   just $$1+YX$$, another number, whose inverse is just its regular
   real number reciprocal (if $$1+YX\ne 0$$). Therefore, if $$YX\ne
   -1$$, we know that $$I+XY$$ is invertible (from first part), and
   that 
   
   $$(I+XY)^{-1} = I - \frac{XY}{1+ YX},$$ 
   
   a simple update that does not require computing any matrix inverse
   explicitly!
   
   The last identity is the essence of the Woodbury-Morrison
   formula/matrix inversion lemma (though it is usually phrased in a
   more complex form).  All of the above may seem like pointless
   gymnastics at this point. But the matrix-inversion lemma is
   surprisingly useful and shows up from
    * Kernel methods (a powerful but computationally intensive state
   of the art machine learning approach) to
    * Traditional algorithms you use all the time such as the Kalman
   filter (well you may not know you used it, but if you have used GPS
   to navigate, you have used Kalman filters). You know the first time
   Kalman filters were used? On the Apollo Guidance computer for the
   moon landings. 
   
