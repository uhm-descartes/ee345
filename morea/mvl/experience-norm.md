---
title: "Norms and Dot Products"
published: true
morea_id: experience-norm
morea_type: experience
morea_summary: "The many ways to measure"
morea_start_date: "2023-08-24"
morea_labels:
---

# Norms 
This material is advanced, and if you are seeing vectors for the first
time, please read this _only_ with my help. 

We have seen that the length of a vector $${\bf x}=\begin{bmatrix} x_1\\\vdots\\ x_n \end{bmatrix}$$ is 

$$ || {\bf x}||^2 = {\bf x} \cdot {\bf x} = {\bf x}^T {\bf x} = \sum_{i=1}^n x_i^2. $$

This is usually called the Euclidean length, or $$\ell_2$$ norm. But this is
not the only way to measure a vector. There are many others we commonly use in
machine learning, prominent among them being the $$\ell_1$$ norm:

$$ ||{\bf x}||_1 = \sum_{i=1}^n |x_i|, $$

and in general for $$p\ge 1$$ the $$\ell_p$$ norm (of which the above two are special cases):

$$ ||{\bf x}||_p = \Biggl(\sum_{i=1}^n |x_i|^p\Biggr)^{1/p}. $$

We also define the $$\ell_\infty$$ norm as 

$$ ||{\bf x}||_\infty = \max_{1\le i \le n} x_i, $$

and you can convince yourself that $$\lim_{p\to\infty} ||{\bf x}||_p = ||{\bf x}||_\infty$$. These need not be the only way to measure vectors either. We can use any 
non-negative function of vectors (which we will call a _norm_) to measure them---as long as the norm function satisfies the axioms. 

* Only the $$\bf 0$$ vector has norm 0
* The norm of $$\lambda {\bf x}$$ is $$|\lambda|$$ times the norm of $${\bf x}$$
* For any vectors $${\bf x}$$ and $${\bf y}
$$, the norm of $${\bf x}+{\bf y}
$$ is $$\le$$ the norm of $${\bf x}$$ plus the norm of $${\bf y}
$$.

If you are wondering why we don't have a $$\ell_p$$ norm for $$p<1$$, the answer
is because for $$0< p < 1$$, the function $$\Biggl(\sum_{i=1}^n |x_i|^p\Biggr)^{1/p}$$ will not satisfy the third axiom above.

# .. and Dot Products

If we have an axiomatic development for norms, perhaps we have
something like that for dot products too? Indeed we have. Any real
valued function of two real vectors is an __inner__ product if it satisfies
the following axioms:

* It is symmetric in its two arguments (if we allow complex vectors, we need to relax this).
* It should be linear in the first argument when the second argument is held fixed (and by symmetry, it is automatically linear in the second if the first is held fixed).
* The inner product of a non-zero vector with itself must be non-zero.

The inner product we saw in class, the regular dot product $${\bf x}^T {\bf y}
 $$ is not
the only one we can define. In fact, machine learning uses a different kind of
dot product to move from linearity to non-linearity. You will see more of this
in EE 445. 

Notice how we defined the $$\ell_p$$ norm for $$p \ge 1$$. But only for $$p=2$$,
we wrote

$$||{\bf x}||_2^2 = {\bf x}^T{\bf x}. $$

So here, we say the $$\ell_2$$ norm is derived from the dot
product. This dot product gives rise to the geometry we are so
familiar with. What about other norms? In fact, you can prove that no
other $$\ell_p$$ norm can be derived from any dot product---$$\ell_2$$
is special among all the $$\ell_p$$ norms. 

To see this, first note that 

* the Parallelogram Law (which we proved in the Problem Set) is a
necessary consequence of the inner product axioms. Therefore any norm
derived from a dot product must satisfy the parallelogram law

* only the $$\ell_2$$ norm satisfies the parallelogram law among all
the $$\ell_p$$ norms.

So from this perspective, if you started with $$\sum |x_i|$$ as the length of a vector $$\bf x$$, you wouldn't be able to come up with a dot product (hence no question of angles or geometry as we know it). The only way to make geometry 
happen among these $\ell_p$$ norms is to use the Euclidean length as we know it!

