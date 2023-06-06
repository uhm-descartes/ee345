---
title: "Complex Numbers"
published: true
morea_id: experience-complex
morea_type: experience
morea_summary: "Where do they come from?"
morea_start_date: "2023-08-24"
morea_labels:
---

# Complex Numbers

This material is advanced, and if you are seeing either matrices or 
complex numbers for the first time, please read this _only_ with my help.
It is dangerous. Reading this could get you banned in Florida.

Think of vectors in $${\mathbb R}^2$$, that is vectors with 2
coordinates.  We saw the inner and outer products of these vectors (in
class and labs).  Specifically, the inner product takes two vectors in
$${\mathbb R}^2$$ and outputs a real number, the outer product takes
two vectors in $${\mathbb R}^2$$ and outputs a $$2\times 2$$ matrix.

But could we define a "algebraic product" more aligned with our notion
of product of real numbers? What do we mean by it? Well, let us list
out what properties we would like such a "algebraic product" to have:

The "algebraic product" should take any two vectors $${\bf x} \in
{\mathbb R}^2$$, and $${\bf y}\in {\mathbb R}^2$$ (the vectors could
possibly be equal) and output another vector $${\bf z} \in {\mathbb
R}^2$$ with 2 coordinates (just like the product of two real numbers
is also a real number). 

1. The "algebraic product" must be commutative, that is $${\bf x} {\bf y} = {\bf y}
   {\bf x}$$ for all $${\bf x}$$ and $${\bf y}$$.
2. The "algebraic product" is linear in each factor, namely
   $$({\bf x}_1+{\bf x}_2){\bf y} = {\bf x}_1 {\bf y} + {\bf x}_2 {\bf y}$$ and $${\bf x} ({\bf y}_1+{\bf y}_2) = {\bf x}{\bf y}_1
   +{\bf x}{\bf y}_2$, as well as for any real $$c$$, $$(c{\bf x}){\bf y} = c({\bf x}{\bf y})$$ and
   $${\bf x}(c{\bf y})=c({\bf x}{\bf y})$$.
3. The "algebraic product" is associative, that is $${\bf x}({\bf y}{\bf z}) = ({\bf x}{\bf y}){\bf z}$$ (so
   even though the product was a binary operator, we can actually
   write expressions like $${\bf x}{\bf y}{\bf z}$$ with no ambiguity).
4. If $${\bf x}\ne 0$$ and $${\bf y}\ne 0$$, the "algebraic product" $${\bf x}{\bf y} \ne 0$$.

Note that real multiplication satisfies all these. The dot product
doesn't output a vector (so point 3 is meaningless), and does not
satisfy 4 (the dot product of non-zero orthogonal vectors is 0. The
outer product again doesn't output a vector (so point 3 is again
meaningless), but satisfies 1, 2, and 4.

So what form can this "algebraic product" take? First it turns out
that the 4 axioms above imply (proof withheld but accessible) there
will be a unique identity vector $${\bf e}$$, which satisfies for all
$${\bf x}\in{\mathbb R}^2$$,

$${\bf x}{\bf e} = {\bf e}{\bf x} = {\bf x}.$$


Then it turns out the 4 axioms above also imply that (proof withheld,
but much harder) that there will be a vector $${\bf i}$$ such that

$${\bf i}{\bf i} = (-{\bf i})(-{\bf i}) = -{\bf e}.$$

These vectors $${\bf e}$$ and $${\bf i}$$ will not be scalings of each other
(since if $${\bf i} = c {\bf e}$$, then $${\bf i}{\bf i} = c^2 {\bf e}$$ and can never equal
$$-{\bf e}$$ for any real $$c$$. Therefore, the set of all linear
combinations of $${\bf e}$$ and $${\bf i}$$ is the entire plane $${\mathbb R}^2$$ of
all vectors with 2 coordinates. We can therefore represent any vector
$${\bf x} as x_1 {\bf e} + x_2 {\bf i}$$. Say $${\bf y}=y_1{\bf e} +y_2{\bf i}$$ in the same coordinate
system. Then the 4 axioms imply that the product must assign (this you
can prove if you believe the narrative till now):

$${\bf x}{\bf y} = (x_1y_1 -x_2y_2 ){\bf e} + (x_2y_1+x_1y_2){\bf i}.$$

If you are familiar with complex numbers, the above is the exact
analog of the development of complex numbers, a proof of the existence
of $\sqrt{-1}$, and the development of the complex product. Now you
know why we represent complex numbers in the Argand/Gauss
plane---another way to see complex numbers is to think about how to
introduce an algebraic product on vectors with two coordinates.

If you ask, well what about real vectors with 3 or more coordinates?
On vectors with 3 coordinates such a product is impossible no matter
what we do. The _cross product_ you have seen in physics comes close
however (but the cross product is neither associative nor
commutative).

Turns out there is a remarkable theorem called the **Frobenius
theorem** that states that only $${\mathbb R}$$, $${\mathbb R}^2$$
satisfy the 4 properties above. If we compromise on commutativity,
then $${\mathbb R}^4$$ (vectors with 4 coordinates) have an "algebraic
product" satisfying all but the commutative property. Just like
$${\mathbb R}^2$$ are called complex numbers, $${\mathbb R}^4$$ are
called quaternions.  Just as complex numbers are all over electrical
engineering, quaternions are all over computer vision, 3-d graphics,
not to mention the equations of Einstein's General Relativity.
