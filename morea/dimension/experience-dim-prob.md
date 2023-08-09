---
title: "Problems in Class"
published: true
morea_id: experience-dim-prob
morea_type: experience
morea_summary: "Basis and Dimension"
morea_start_date: "2021-07-15T23:00"
morea_labels:
---

# Problems in Class

1. Let $$X$$ be a $$n\times p$$ matrix with $$k$$ pivots. 
    * What are the four fundamental spaces of $$X^TX$$ in terms of the spaces of $$X$$?
	* Dimensions of the four fundamental spaces of $$X^TX$$?
	* Repeat the above two problems for $$XX^T$$
	
2. Let $$\{ {\bf v}_1 ,\ldots, {\bf v}_n \}$$ be a collection of $$n$$ mutually
   orthogonal vectors, each vector in $${\mathbb R}^m$$ and let $$V =
   \begin{bmatrix} {\bf v}_1 & \cdots & {\bf v}_n \end{bmatrix}$$. Clearly $$m\ge n$$,
   assume $$m > n$$.
    * What is $$V^TV$$? Is $$VV^T$$ equal to an identity matrix?
	* What are the dimension of the four fundamental spaces of
      $$VV^T$$? (Use prior problem)
	
3. Suppose $$A$$ and $$B$$ are any two matrix with $$m$$ rows. Let
$$A\wedge B$$ be the matrix obtained by using a basis of the space $$\textrm{col}(A)\cap \textrm{col}(B)$$ as its columns and let $$A\vee B$$ be the matrix 
formed the union of columns from $$A$$ and $$B$$. Show that 

	$$ \textrm{rank}(A) + \textrm{rank}(B) = \textrm{rank}(A\wedge B) + \textrm{rank}(A\vee B).$$

4. **Linear Regression** Let $$X$$ be any $$n\times p$$ matrix. 
    * Show that any $$n\times 1$$ vector $${\bf y}$$ can be written
	uniquely as a sum of a vector in the column space and a vector in
	the left null space, namely as $${\bf x}+{\bf e}$$, where $${\bf
	x}\in\textrm{col}(X)$$ and $${\bf e} \in \textrm{null}(X^T)$$
    * Show that any $$p\times 1$$ vector $${\bf z}$$ can be written uniquely as
	$${\bf w}+{\bf e}$$, where $${\bf w}\in\textrm{col}(X^T)$$ and $${\bf e} \in \textrm{null}(X)$$

5. **$$t-$$statistics** Let $$X$$ be a $$n\times p$$ vector with $$p$$ pivots, and let
   $${\bf x}_1$$ be the first column of $$X$$. The set of vectors $${\mathcal L}_1 = \{
   \alpha {\bf x}_1 : \alpha \in {\mathbb R} \}$$ is a linear space within
   the column space of $$X$$. 
   
     * Show that $$X^TX$$ has an inverse
	 * Show that $$(X^TX)^{-1} = \bigl((X^TX)^{-1}\bigr)^T$$
	 * Show that the first column of $$X(X^TX)^{-1}$$ is in the column space of $$X$$
	 * Show that the first column of $$X(X^TX)^{-1}$$ is in the column space of $$X$$ is orthogonal to $${\bf x}_1$$, the first column of $$X$$ (and therefore
to the linear space $${\mathcal L}_1$$ as well).
	 
 In the lab, the last insight is an ingredient that goes into
 computing the $$t-$$statistic, which in turn estimates the
 significance of coefficients of a linear model.  To fully appreciate
 the $$t-$$statistic, you need to know a little about normal
 distributions from EE 342 as well.
