---
title: "Problems in class"
published: true
morea_id: problems-eq
morea_summary: "Gaussian Elimination"
morea_type: experience
morea_start_date: "2023-09-08"
morea_labels:
---

# Problems in class

1. Write a $$3\times 5$$ matrix such that
   * the first, second and fifth columns are pivot columns, rest free, call this $$A$$
   * the first, third and fifth columns are pivot columns, rest free, call this $$B$$
   * You cannot always get an answer to the second part above by swapping the second and third columns of $$A$$. Why?



2. Let $$M = \begin{bmatrix} I_m & A \\ B & I_n \end{bmatrix}$$, where
   $$I_m$$ is a $$m\times m$$ identity matrix, $$A$$ is a $$m\times
   n$$ matrix, $$B$$ is a $$n\times m$$ matrix and $$I_n$$ is the
   $$n\times n$$ identity matrix.
	* If you perform elimination on $$M$$, what are the first $$m$$
pivots?
	* What is the matrix you have after you have worked through the first $$m$$ columns, just before you start looking for the $$m+1$$'th pivot?



3. Find one $$4\times 3$$ matrix $$C$$ (the same matrix must be used
   for all relevant parts below), and two vectors $$\bf b$$ and $$\bf w$$ such that
    * $$C{\bf x} = {\bf b}$$ has a unique solution;
    * $$C{\bf x} = {\bf w}$$ has no solutions
    * For the matrix $$C$$ satisfying the parts above, it possible to find a vector $$\bf z$$ such that $$C{\bf x} = {\bf z}$$ has infinite solutions?
	* Can you find a different matrix $$D$$ such that both equations $$D{\bf x} = {\bf b}$$ and $$D{\bf x}={\bf w}$$ have infinite solutions?



4. Let $$A$$ be a $$n\times k$$ matrix with $$r$$ pivots (to
   anticipate a future topic, we will call the number of pivots in
   $$A$$ to be is rank). Let $$P$$ be the $$n\times r$$ matrix whose
   columns are the pivot columns of $$A$$. Let $$R$$ be the reduced
   row echelon form of $$A$$, and let $${\tilde R}$$ be the $$r\times
   k$$ matrix obtained from $$R$$ by dropping its all-zero rows.

   * Show that $$A= P{\tilde R}$$. Thus a rank $$r$$ matrix $$A$$ with size $$n\times k$$ can
     be written as a $$n\times r$$ matrix multiplied by a $$r\times k$$ matrix.
   * Show that if a $$n\times k$$ matrix $$B$$ is a product of 
	 a $$n\times r$$ matrix and a $$r\times k$$ matrix, then the number
	 of pivots in $$B$$ is $$\le r$$ (equivalently we could also say rank of $$B$$
	 is $$\le r$$).
   * (Follows from prior parts, but maybe a little subtle) Show that
     $$A^T$$ has the same number of pivots as $$A$$. Remember that $$(AB)^T = B^TA^T$$.
   
   The observation that $$A = P{\tilde R}$$ captures the information
   the reduced row echelon form provides: 
     * it tells you which columns are pivot columns, and 
	 * how to get the free columns from the pivot columns as linear
   combinations. 
   
   Writing $$A = P{\tilde R}$$ is an example of matrix factorization.
   Suppose $$A$$ is a matrix with only non-negative entries. Many
   applications, in astronomy, computer vision, bioinformatics,
   recommender systems, signal processing and natural language
   processing, require factors of $$A$$ whose entries are also all
   non-negative, and in addition with as small a rank as possible.
   The above factorization into rank $$r$$ matrices will not cut it,
   since the entries of $$\tilde R$$ can be negative even if all the
   entries of $$A$$ are non-negative. But $$r$$ remains a lower bound
   on the rank of the factors for exact non-negative factorization.


3. Pick $$\bf v$$ to be a vector with 3 coordinates. Perform
   elimination on $$I_3 + {\bf v}{\bf v}^T$$, and multiply all the
   pivots. You will find three pivots. Find the product of all the
   pivots, and verify the product equals $$1 + ||{\bf v}||^2$$. The
   equality holds no matter what $$\bf v$$ you take. In fact, the
   equality can be generalized to vectors with any shape. 
   
   
   As you can see from the problems above, you can think far deeper into the Gaussian Elimination algorithm than is apparent.
      
   
