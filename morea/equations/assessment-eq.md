---
title: "Problems in class"
published: true
morea_id: assessment-eq
morea_summary: "Gaussian Elimination"
morea_outcomes_assessed:
 # - outcome-CHANGE-ME
morea_type: assessment
morea_start_date: "2021-07-16T09:00"
morea_labels:
---

# Problems in class

1. Write a $$5x3$$ matrix with all non-zero entries, such that
   * the first, second and fifth columns are pivot columns, rest free, call this $$A$$
   * the first, third and fifth columns are pivot columns, rest free, call this $$B$$
   * You cannot always get an answer to the second part above by swapping the second and third columns. Why?

2. Let $$M = \begin{bmatrix} I_m & A \\ B & I_n \end{bmatrix}$$, where
   $$I_m$$ is a $$m\times m$$ identity matrix, $$A$$ is a $$m\times
   n$$ matrix, $$B$$ is a $$n\times m$$ matrix and $$I_n$$ is the
   $$n\times n$$ identity matrix.
	* If you perform elimination on $$M$$, what are the first $$m$$
pivots?
	* What is the matrix you have after you have worked through the first $$m$$ columns, just before you start looking for the $$m+1$$'th pivot?

3. Pick $$\bf v$$ to be a vector with 3 coordinates. Perform
   elimination on $$I_3 + {\bf v}{\bf v}^T$$, and multiply all the
   pivots. Find the product of all the pivots, and verify the product
   equals $$1 + ||{\bf v}||^2$$. No matter what $$\bf v$$ you take,
   and the result remains true when you look at vectors with any
   number $$k$$ of coordinates (and the identity matrix will then be
   $$I_k$$).
   
   One reason we have this problem is to show you that you can think
   far deeper into the elimination algorithm than is apparent. It is a
   simple procedure no doubt, but with stunningly deep ramifications.
   
4. Write a $$3\times 3$$ matrix $$C$$ such that 
   
   
