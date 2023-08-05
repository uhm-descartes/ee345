---
title: "Linear independence, rank"
published: true
morea_id: experience-linind-prob
morea_type: experience
morea_summary: "Problems in Class"
morea_start_date: "2023-10-11"
morea_labels:
---

# Problems in Class

1. Let $$A$$ be a $$m\times n$$ matrix, and let us collect the pivot
columns of $$A$$ (identified by Gaussian elimination) into another matrix $$P$$.
Say there are $$k$$ pivots in $$A$$, therefore $$P$$ is a $$m\times k$$ matrix.
Factorize $$A = P W$$, where $$W$$ is a $$k\times n$$ matrix. 

2. Use your insights into linear independence to
    * Construct $$A=\begin{bmatrix}\a_1 &\a_2&\a_3&\a_4&
\a_5\end{bmatrix}$$, a $$4\times 5$$ matrix with pivots in the
first, second and fourth column. such that the matrix $$\begin{bmatrix}\a_1 &\a_3&\a_2&\a_4& \a_5\end{bmatrix}$$ has pivots in the first, second and fourth columns and
    * Construct $$B=\begin{bmatrix}\b_1 &\b_2&\b_3&\b_4&
\b_5\end{bmatrix}$$, a $$4\times 5$$ matrix with pivots in the
first, second and fourth column. such that the matrix $$\begin{bmatrix}\b_1 &\b_3&\b_2&\b_4& \b_5\end{bmatrix}$$ has pivots in the first, third and fourth columns.

   As you see, free and pivot columns need not retain their identities
   as free/pivot under a reordering of the columns. But the number of
   pivot columns does not change under any reordering of the columns.
   This is because, regardless of arrangement of columns, those marked as pivot
   columns form a maximal linearly independent set of the column space
   of the matrix. Reordering may produce a different maximal linearly
   independent set, but all maximal linearly independent sets of the
   column space of the matrix must have the same size.
   
3. **Rank of a matrix** Show that a basis in the column space of $$A$$
    and a basis in the row space of $$A$$ have the same size. In other
    words, the column space of $$A$$ and row space of $$A$$ have the
    same dimension. This number, the dimension of the column/row
    space, is called the __rank__ of $$A$$.
	
	Hint: start from Problem 1, writing a $$m\times n$$ matrix $$A$$
	with $$k$$ pivot columns as $$A=P W$$, where $$P$$ is $$m\times
	k$$. Therefore $$W$$ must have size $$k\times n$$. The column
	space has therefore dimension $$k$$. From our knowledge of matrix
	multiplication, every row of $$A$$ is a linear combination of the
	rows of $$W$$, therefore the rows of $$W$$ span the row space of
	$$A$$. This implies that the dimension of the row space $$\le k$$,
	the dimension of the column space. Applying the same argument to
	$$A^T$$, we get that the dimension of the row space $$\ge$$ the
	dimension of the column space. Thereby, concluding that both
	spaces have equal dimension.
	
4. Suppose $$U = \{ {\bf u}_1, \ldots, {\bf u}_k \}$$ and $$V = {\bf
   v}_1, \ldots {\bf v}_{n-k}\} $$ are two sets of linearly independent
   sets in $${\mathbb R}^n$$. Show that if each vector in 
   $$V$$ is orthogonal to every vector of $$U$$, then $$U$$ and $$V$$
   are disjoint (no elements in common) and $$U \cup V$$ is a basis for
   $${\mathbb R}^n$$. 

5. **Basis for the null set** We will find a basis for the right null
    set of a $$m\times n$$ matrix $$A$$. Say $$A$$ has $$k$$
    pivots. Let $$R$$ be the reduced row echelon form of $$A$$, and
    let $$R'$$ be the matrix obtained by dropping all-zero rows of
    $$R$$.  Let $$F$$ be the submatrix formed by the free columns in
    $$R'$$,
	 
     * What are the shapes of $$R$$ and $$R'$$?
	 * How is the shape of $$F$$? 
	 * Let $$N$$ be the $$n\times n-k$$ matrix constructed as follows:
	   identify the pivot columns of $$A$$. Suppose they are
	   $$i_1,\ldots, i_k$$. Fill up the $$i_1,\ldots, i_k$$'th rows of
	   $$N$$ with $$-F$$. At this point there are $$n-k$$ rows of $$N$$
	   that are not yet filled. Fill them up with the rows of $$I_{n-k}$$.
	   Show that $$RN={\bf 0}$$, and therefore that $$AN={\bf 0}$$. Thus,
	   each column of $$N$$ is in the right null space of $$A$$.
	   
	   Hint: move all the pivot columns of $$R$$ to the left to get
	   $$\begin{bmatrix} I_k & F_{k,n-k}$$ and all the corresponding
	   rows of $$N$$$ to the top to get $$\begin{bmatrix} -F_{k,n-k}\\
	   I_{n-k} \end{bmatrix}$$.  Argue that this rearrangement of columns
	   in $$R$$ simultaneously with the rows of $$N$$ does not change the
	   product $$RN$$. And to obtain the product of transformed matrices,
	   use the block matrix multiplication approach.
	   
	 * Now show that the $$n-k$$ columns of $$N$$ are linearly independent,

	 * Show that the columns of $$N$$ are a maximal linearly
	   independent set of the null space of $$A$$. To show this, use Problem 4
	   above. 
	   
	 Therefore the set of all solutions for $$A{\bf x} ={\bf 0}$$ is the column
	 space of $$N$$, ie $$ \{ N {\bf z} : {\bf z} \in {\mathbb R}^{n-k}\}$$ and
	 the dimension of the right null space is $$n-k$$.


