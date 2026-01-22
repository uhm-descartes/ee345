---
title: "Bayesian Formulation/Ridge Regression"
published: true
morea_id: reading-lr-ridge
morea_summary: "Class notes"
morea_type: reading
morea_labels:
---
\\( \newcommand{\w}{\bf w} \\)
\\( \newcommand{\E}{\mathbf E} \\)
\\( \newcommand{\cov}{\textbf{cov}} \\)

In linear regression, we have a real valued measurement \\(Y\\) of a
signal \\(\w\\) (potentially a vector) that we want to measure,
potentially corrupted by noise. Linear regression is ubiquitous as a
component of several algorithms, but a commonplace standalone (and
important) example is fMRI signals. We will assume that the
measurements are linear (\ie the signal \\(\w\\) is transformed by linear
operations, which is equivalent to multiplying by a matrix in
general). 

This is quite a vast topic in itself, and this module covers what is
known as Ridge Regression. The formulation we adopt here is
the "Bayesian" view.  You will contrast this with
the \emph{frequentist} approach, and it is recommended you familiarize
yourself with the frequentist (Maximum Likelihood) approach first.

We posit, as in the Maximum Likelihood case that the target \\(Y\\) are
linear measurements \\(X\\) of the unknown signal \\(W\\), written
compactly as $$ Y = XW + Z,$$ where specifically, \\(Y\\) is a vector of
the \\(n\\) targets, \\(X\\) is the \\(n\times p\\) measurement matrix, $W$
is the random vector with \\(p\\) coordinates that we want to measure,
and \\(Z\\) is a vector of discrepancies. Here again we assume \\(Z\\) is
a vector of \\(n\\) Gaussian random variables. But now we assume
something more, that \\(W\\) is a multivariate Gaussian as well,
independent of \\(Z\\). Therefore, \\(W\\), \\(Y\\) and \\(Z\\) are all
jointly Gaussian. Specifically, we assume
\\(W\sim \cN(\bf 0}, \Sigma)\\), \\(Z\sim \cN(0, \nu^2 I)\\) (and \\(W\\)
and \\(Z\\) are independent). We assume \\(W\\) has a non-degenerate pdf,
\ie \\(\Sigma\\) is invertible.

The best estimate of \\(W\\) from \\(Y\\) in the mean square sense,
namely $$ {\hat W} = \arg \min_{f(Y)} \E ||W - f(Y)||^2, $$ where
$\hat W$ is our estimate (which in turn in a function of the
measurement $Y$, so henceforth we will write it as ${\hat W}(Y)$). The minimizer is over any function of the
observations \\(Y\\), and from your basic probability/statistics class,
is given by
$$ \hat W(Y) = \E [W| Y]. $$ 

Of course, the conditional mean \\(\E [W|Y]\\) has a special form for
Gaussians, and we can reuse the insights from multivariate Gaussians.

\subsection{Gaussians and ridge regression}
\label{sec:org9f1eb22}
Find the answers to the (why?) questions in the Gaussian module or by elementary
manipulations.

Since \\(W\\) and \\(Y\\) are jointly Gaussian, we know therefore that \\(\E[W|Y]\\)
is a linear function of \\(Y\\) (why?). Furthermore since \\(\E W=\E Z={\bf 0}\\) by
assumption, we have \\(\E Y ={\bf 0}\\) by linearity of expectation (can you write out a full proof?). Therefore, 
$$ \E [ W| Y] = AY, $$
and the orthogonality
principle that says the error must be uncorrelated (``orthogonal'') to the signal,
$$ \E [ (W - AY)Y^T ] = {\bf 0}$$
yields,
$$A = \cov(W,Y) \cov(Y,Y)^{-1}$$
Now, show that 
$$\cov(W, Y) = (\E WW^T) X^T =  \Sigma X^T $$
and similarly
$$\cov (Y,Y) = X\Sigma Y^T + \nu^2 I .$$
Therefore,
$$A = \frac1{\nu^2}\Sigma X^T (\frac 1{\nu^2} X\Sigma X^T + I)^{-1}$$
$$ = \Sigma(I + \frac1{\nu^2}X^TX \Sigma )^{-1} \frac1{\nu^2}X^T$$
$$= (X^TX + \Sigma^{-1}\nu^2 )^{-1} X^T$$

Can you prove the last and the second to last equalities? They are very
useful, and form part of the series of equalities that go into the Matrix
Inversion Lemma. The second equality states for any \\(X\\) and \\(Y\\) such
that both \\(XY\\) and \\(YX\\) exist, and \\(I+XY\\) is invertible, we will have
that \\(I+YX\\) is also invertible and
$$ (I+YX)^{-1}Y= Y(1+XY)^{-1}. $$
The last equality is simple manipulations using \\((AB)^{-1} = B^{-1} A^{-1}\\) and
noting that \\(\Sigma\\) is invertible.

Therefore, our estimate of \\(W\\) in the Bayesian sense is
\begin{equation}
\label{eq:bayes} (X^TX + \nu^2\Sigma^{-1})^{-1} X^T Y, 
\end{equation}
which actually looks quite close to the OLS estimate of \\((X^TX)^{-1} X^T Y\\),
differing only by the \\(\nu^2\Sigma^{-1}\\) term within the inverse.

\paragraph{Regularization view}
To get a little more insight into this, let \\(\Sigma = \sigma^2 I\\). The
expression for the BAyesian estimate of \\(W\\) reduces to
$$ (X^TX + \frac{\nu^2}{\sigma^2}I )^{-1} X^T Y.$$

Now consider solving the following problem 

\begin{equation}
\label{eq:opt} 
\arg \min_{\x} ||Y- X\w||^2 + \frac{\nu^2}{\sigma^2} ||\w||^2. 
\end{equation}
We would take the gradient of the expression above with respect to \\(\x\\), and
this turns out to be 

$$ 2X^T (X\w - Y ) + \frac{\nu^2}{\sigma^2} 2\w. $$
Setting the gradient to \\(\bf 0\\) and rearranging we get
$$ (X^TX + \frac{\nu^2}{\sigma^2}I ) \w = X^T Y, $$
and solving for \\(\w\\) gives us the Bayesian optimal solution. You can verify that
the Hessian, 
$$ (X^TX + \frac{\nu^2}{\sigma^2} I )^T = (X^TX + \frac{\nu^2}{\sigma^2}I ) $$
is always positive definite, therefore the Bayesian optimal solution
\\((X^T X + \frac{\nu^2}{\sigma^2} I )^{-1} X^T Y\\) is a minima. It is
also the global minima because the objective being minimized is
\emph{convex} (over a convex domain) and we can have only one minimum.

Therefore, the Bayesian framework is equivalent to minimizing
Equation\textasciitilde{}\eqref{eq:opt}. Notice the objective we are minimizing is the
least squares loss (\\(||Y-X\w||^2\\)), but we add to it a term that
depends on the length squared of \\(\w\\), \ie \\(||\w||^2\\). 

If \\(\w_{b}\\) is the Bayes optimal solution, we must have
\begin{equation}
\label{eq:ineq} ||Y- X\w_b||^2 + \frac{\nu^2}{\sigma^2} ||\w_b||^2 
\le ||Y- X\w_{OLS}||^2 + \frac{\nu^2}{\sigma^2} ||\w_{OLS}||^2,
\end{equation}
because, of course, \\(\w_b\\) is the minima of~\eqref{eq:opt}. In fact, we usually have
$$ || Y - X\w_b ||^2 > || Y - X\w_{OLS}||^2 $$
but 
$$||\w_b||^2  < || \w_{OLS} ||^2,$$
while satisfying Equation\textasciitilde{}\eqref{eq:ineq}.

Therefore the Bayes optimal solution \\(\w_b\\) shrinks the OLS estimate. Estimates
like this, where we give preference to solutions that have some simplicity (here
by simplicity we mean smaller Euclidean length), are called \emph{regularized}
estimates. Here the term \\(||\w||^2\\) in the objective function of\textasciitilde{}\eqref{eq:opt}
is called the regularization penalty, and since this is the \\(\ell_2\\) norm of
\\(\w\\), this sort of regularization is called \\(\ell_2\\) regularization or Ridge
regression.

\paragraph{Problem} Show that the general Bayes optimal solution in Equation\textasciitilde{}\eqref{eq:bayes}
is the solution of the optimization problem

$$\arg \min_{\x} ||Y- X\w||^2 + \frac1{\nu^2} \w^T \Sigma^{-1} \w, $$
where \\(\Sigma\\) is symmetric and
positive definite).
\paragraph{Problem} Find answers to all the (why?) questions in the handout.

