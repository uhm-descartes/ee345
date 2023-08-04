---
title: "Problems in class"
published: true
morea_id: experience-linspace-prob
morea_type: experience
morea_summary: "Fundamental Spaces of a matrix"
morea_start_date: "2021-07-15T23:00"
morea_labels:
---

# Problems in class

1. Let $$A$$ be a $$m\times n$$ matrix, and let $$P$$ be the matrix
   whose columns are the columns of $$A$$ in which Gaussian
   elimination finds a pivot. Show that col($$A$$) = col($$P$$). 

2. Suppose $$A$$ is a $$m\times n$$ matrix. 

	* If $$C$$ is a $$n\times n$$ matrix, show that the column space
      of $$AC$$ is a subset of the column space of $$A$$
	* Show that if $$C$$ is a $$n\times n$$ invertible matrix, then
      the column space of $$AC$$ equal to the column space of $$A$$?
      Give and example to show that the condition on $$C$$ is not
      always necessary
    * What is the column space of $$\begin{bmatrix} A & AC \end{bmatrix}$$?
	* Can you make statements analogous to the above about row spaces? 
    * The (row/column) space is preserved in each step of the Gaussian
      elimination procedure. (choose the correct answer, with an explanation)
	
3. **Linear Regression** This is an important result which we will
   need for linear regression in a future module. Show that the null
   space of a $$n\times p$$ matrix $$X$$ equals the null space of
   $$X^TX$$. 

4. Let $$A$$ have rref $$R_1$$, and let $$A^T$$ have rref $$R_2$$. We will
   relate the fundamental spaces of $$A$$ to those of $$R_1$$ and $$R_2$$.

    * Convince yourself that $$R_1$$ and $$R_2$$ are not transposes of
      each other in general.
	* The column space of $$A$$ equals the (row/column) space of
      ($$R_1/R_2$$)?  (choose correct answers with explanations)
    * The row space of $$A$$ equals the (row/column) space of
      ($$R_1/R_2$$)?  (choose correct answers with explanations)
	* The right null space of $$A$$ equals the (left/right) null space
      of ($$R_1/R_2$$)?  (choose correct answers with explanations)
    * The left null space of $$A$$ equals the (left/right) null space
      of ($$R_1/R_2$$)?  (choose correct answers with explanations)
	
5. These problems on stacked matrices recap the basic concepts behind
   Gaussian elimination and the linear spaces we have learnt about.
   
     * If $$A$$ is an invertible 4x4 matrix, what is the rref of
       $$\begin{bmatrix} A & A \end{bmatrix}$$ and that of
       $$\begin{bmatrix} A\\ A \end{bmatrix}$$? What about
       $$\begin{bmatrix} A & AB \end{bmatrix}$$? (You do not need to
       know $$A$$ to write the answers out, express the last part in
       terms of $$B$$).
	   
	 * Express the (right) null space of $$\begin{bmatrix} A\\ B
       \end{bmatrix}$$ in terms of the right null spaces of $$A$$ and
       $$B$$.
	 
   
	



