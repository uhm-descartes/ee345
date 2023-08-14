---
title: "Problems in Class"
published: true
morea_id: experience-det-prob
morea_type: experience
morea_summary: "Determinants"
morea_start_date: "2023-11-14"
morea_labels:
---

# Problems in Class

1. A matrix called the _Vandermonde_ matrix, appears in a number of places from statistics, polynomial interpolation (and extensively in error control coding, Fast Fourier transforms, and signal processing). It is also a very elegant matrix from a mathematical point of view. A $$3\times 3$$ Vandermonde matrix is

	$$\begin{bmatrix} 1 & x_1 & x_1^2 \\ 1 & x_2 & x_2^2 \\ 1& x_3 & x_3^2 \end{bmatrix}$$
	
Find the determinant of the matrix above. 

2. Show that the determinant of 

	$$\begin{bmatrix} a & b & c \\ b & c & a \\ c& a & b \end{bmatrix}$$
	
	equals 0 iff $$a=b=c$$ or if $$a+b+c = 0 $$.
	
3. Let 

	$$P_1 = \begin{bmatrix} 0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0& 1 \end{bmatrix} \textrm{ and } P_2 = \begin{bmatrix}  0 & 0& 1 \\ 1 & 0 & 0 \\ 0 & 1 & 0\end{bmatrix}$$
	
	Find all values of $$\lambda$$ such that $$P_1-\lambda I_3$$ and all 
	$$\mu$$ such that $$P_2-\mu I_3$$ are singular.
	
4. **Jacobian** Let $$x = f_1(u, v)$$ and $$y = f_2(u,v)$$. We think of $$(u,v)$$ to be the coordinates in a 2-$$d$$ plane, and $$f_1$$ and $$f_2$$ are (possibly non-linear) transformations of the coordinates. Assume that the transformations map each point $$(u,v)$$ to a unique point $$(x,y)$$ to visualize this better.If $$(u,v)$$ maps to $$(x,y)$$, recall from elementary calculus that an elemental change $$(u+du, v+dv)$$ changes the mapped point to $$(x+\Delta x, y+\Delta y)$$, where:
  $$\begin{align*}
	   \Delta x = \frac{\partial f_1}{\partial u } du + \frac{\partial f_1}{\partial v} dv\\
	   \Delta y = \frac{\partial f_2}{\partial u } du + \frac{\partial f_2}{\partial v} dv.\\
   $$\end{align*}
      
   * Imagine the elemental rectangle with corners $$(u,v)$$, $$(u+ du, v)$$, $$(u, v+dv)$$ and $$(u+du, v+dv)$$. Find the point in the $$x,y$$ plane that  each corner of the rectangle above maps to. Since we are working with elemental increments, the rectangle in the $$u,v$$ plane maps in general to a parallelogram in the $$x,y$$ plane. Call this parallelogram as $$D_{x,y}$$
   
   * What is the ratio of area of the elemental parallelogram $$D_{x,y}$$ to $$du dv$$, the area of the elemental rectangle in the $$(u,v)$$plane?
   
   This ratio of areas is called the Jacobian, and you will encounter
   it again in EE342, among other topics.
   

5. *Cramer's Rule* Cramer's rule is a neat way to combine what we
   learnt about solving equations with what we know about
   determinants, at least in some cases. Suppose $$A$$ is a square
   $$n\times n$$ matrix, $${\bf b}$$ is a $$n\times 1$$ vector, and we
   are trying to solve $$A{\bf x} ={\bf b}$$. If $$A$$ is rectangular,
   Cramer's rule does not help us find solutions if any. For the
   following, you may choose to do the problems for $$3\times 3$$
   matrix $$A$$ and a $$3\times 1$$ vector $$\bf b$$, and convince
   yourself that the arguments generalize for any $$n\times n$$
   matrix.
   
   * If $$A$$ is singular, what is the determinant of $$A$$? In this
     case, $$A{\bf x}={\bf b}$$ has potentially infinite solutions or
     no solution, depending on whether $${\bf b}$$ is a linear
     combination of the columns of $$A$$ or not. We are out of luck
     here, Cramer's rule does not help us find a solution even if
     there is one.
   
   * If $$A$$ is not singular, we know the determinant of $$A$$ is
     not 0. What can you say about the solutions of $$A{\bf x} = {\bf b}$$? Why?
 
   * Suppose $$A$$ is not singular, and let $$A{\bf x}_1 ={\bf b}$$, where
	 $${\bf x}_1$$ is the unique solution of $$A{\bf x}={\bf b}$$. Let $$X_1$$
	 be a $$n\times n$$ matrix, whose first column is $${\bf x}_1$$, and the
	 remaining $$n$$ columns are the corresponding columns of $$I_n$$. What is
	 $$AX_1$$?
	 
   * Cramer's rule: Show that the determinant of $$X_1$$ is simply the
     first component of $${\bf x}_1$$. 
	 
   * Extend the above argument to obtain all other components of $${\bf x}_1$$.
   
   * Extend the above argument to find the inverse of a square,
     non-singular matrix $$A$$.
   
   
   
