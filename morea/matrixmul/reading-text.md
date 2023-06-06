---
title: "Guide to Text"
published: true
morea_id: reading-text-matmul
morea_summary: "Section 2.4"
morea_type: reading
morea_labels:
---

Go through Section 2.4 of the Textbook. As you can see, we are not
strictly following the order in the text. This is because this course
has a companion lab, and it allows us to use class time in more
effective ways. In class we will streamline the treatment of linear
equations, and in the lab you will see linear equations in lot more
detail. The text is encyclopedic, but focus on the following amidst
the mechanics of matrix mulitplication:

* the ability to identify which linear combinations are happening
* in the subsection "Rows and Columns of $$AB$$", note that each
  column of $$AB$$ is $$A{\bf b}_i$$, hence a linear combination of the
  columns of $$A$$
* similarly, each row of $$AB$$ is a linear combination of the rows of
  $$B$$.
* $$AB \ne BA$$ in general for matrix multiplication. Make sure you
  remember this when you use the associative law: when you compute
  $$ABC$$, you can do it either as $$(AB)C$$ or $$A(BC)$$, but not as
  $$(BA)C$$ or $$A(CB)$$ or any other permutations. In fact, some of
  the products $$BA$$ or $$CB$$ may not even be defined. Students
  often mess this around.
* Note in particular that for matrices $$A$$ and a real number $$c$$,
  $$Ac = cA$$ multiplies every entry of $$A$$ by the number
  $$c$$. Therefore, $$A(cB) = (Ac)B$$ and in this special case, it
  happens that $$(Ac)B = cAB$$. Read the prior note again to recall
  that this is special when $$c$$ happens to be a real number, and not
  true if $$C$$ were a matrix in general.

For now, you can downplay the subsection "Block Matrices and Block
Multiplication", as well as the Schur complement. We will come back to
it later in the course.
