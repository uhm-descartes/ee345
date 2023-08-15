---
title: "Problems in Class"
published: true
morea_id: experience-spectral-prob
morea_type: experience
morea_summary: "Eigenvalues/vectors Spectral Decomposition"
morea_start_date: "2023-11-15"
morea_labels:
---

# Problems in Class

1. If $$A$$ is a symmetric $$n\times n$$ matrix and $${\bf v}_1,\ldots, {\bf v}_n$$ are an orthonormal basis formed by eigenvectors with eigenvalues $$\lambda_1\ge \cdots \ge \lambda_n$$,
   * Show that $$A = \sum_{i=1}^n \lambda_i {\bf v}_i {\bf v}_i^T. $$
   * Show that for any unit vector $${\bf z}$$, $${\bf z}{\bf z}^T$$
     is the projection operator onto the linear space spanned by $$\bf
     z$$. Therefore interpret the expression for $$A$$ above
   * Let $$m< n$$, and let $$V_m =\begin{bmatrix} {\bf v}_1 & \cdots
     &{\bf v}_m \end{bmatrix}$$. Show that the projection operator
     into the linear space spanned by the first $$m$$ eigenvectors is
     $$V_m V_m^T$$. (Quick test: what is $$V_m^T V_m$$?)
   * Show that 
   
	   $$\arg\max_{ {\bf x}: ||{\bf x}||=1} {\bf x}^T A {\bf x} = {\bf v}_1$$
	   
     and that
	 
       $$\arg\min_{ {\bf x}: ||{\bf x}||=1} {\bf x}^T A {\bf x} = {\bf v}_n$$

	  Why do we only consider unit vectors in the above max/minimization?
	  
2. For all parts below, $$A$$ is a symmetric matrix such that all its
   eigenvalues are $$> 0$$.
	* Show that $${\bf x}^T A {\bf x} >0 $$ for all vectors $$\bf
	  x$$. For this reason, such a matrix $$A$$ is called _positive
	  definite_ (or simply _positive_ in some usages). This is the
	  matrix analog of positive numbers.
    * Show using examples that a matrix with all positive entries need
      not be positive definite, and positive definite matrices can
      have negative entries. So positivity of matrices is a more
      subtle concept than simply putting positive numbers in all
      entries.
	* If $$B$$ is any other matrix such that $$B^T A B$$ exists, then
	   that $$B^T A B$$ is _positive semi-definite_ (ie all its
	   eigenvalues are $$\ge 0$$---not strictly greater than zero, but
	   greater than or equal to zero).
	  
3. In the following, let $$X$$ be a $$n\times p$$ matrix with $$p$$ pivots.
	 Let $${\bf x}_1 ,\ldots, {\bf x}_n$$ be the $$n$$ rows of $$X$$.
	  * Show that $$X^TX$$ is positive definite. 
	  * Find best one dimensional linear space that best represents
        the rows of $$X$$ in a mean square sense. Specifically, if
        $$\mathcal L$$ is a linear space and $${\bf x}^{\mathcal L}$$
        is the projection of $$\bf x$$ into $$\mathcal L$$, then find
				
	   $$\arg\min_{\mathcal L} || {\bf x}_i - {\bf x}_i^{\mathcal L} ||^2.$$
	   
	  * Generalize the above for $$k-$$dimensional linear spaces that
        best represent the rows of $$X$$ in a mean square sense.
	  
	  * Write the analogs of the above observations for the columns of $$X$$.
	  
	  
4. If $$A$$ is a symmetric matrix, prove the _Cayley Hamilton_ Theorem: 
	 $$A$$ satisfies its own characteristic equation. Specifically, let 
	 $$p(\lambda) = | A- \lambda I |$$ be the characteristic equation of $$A$$.
	 Show that $$p(A)={\bf 0}$$. 
	 
	 For example, the characteristic of $$A=\begin{bmatrix} 1 & 2 \\ 2
     & 1 \end{bmatrix}$$ is $$\lambda^2 - 2\lambda -3$$, and sure
     enough, $$A^2= AA = \begin{bmatrix} 5 & 4\\4& 5\end{bmatrix}$$,
     so that $$A^2 - 2A -3I =0$$. You should of course prove it in
     general for all symmetric matrices, not a specific example.
      
     The Cayley-Hamilton Theorem holds for _all_ square matrices, not
     just symmetric matrices. The general proof is too involved for
     our course. But the symmetric case is easy to prove using the
     spectral decomposition theorem and elementary observations.
	 
5. Let $$A$$ be a symmetric matrix. How would you find $$A^100$$? What
   about $$A^{1/2}$$? From the above, can you define $$e^A$$ and
   $$f(A)$$ in general?



