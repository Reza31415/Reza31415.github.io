---
title: Winsorize
date: 2024-04-25 17:47:12 +0100
toc: true
categories: [Mathematics, Statistics]
tags: [statistics, winsorize, outliers]
math: true
---

# Notes

The inverse of a square matrix $A$ with a non-zero determinant is
defined such that $AA^{- 1} = A^{- 1}A = I$. This is useful in the
context of the system of linear equations, that is to solve

$$
\begin{equation}
Ax = y \label{eq:d}
\end{equation}
$$

for unknown vector $x$. Let assume
$A \in \cnums^{m,n},\ x \in \cnums^{n},\ y \in \cnums^{m}$, then

if A is not a square matrix, $n \neq m$ , it does not have an inverse
and thus we cannot solve the unknown vector $x$. This in itself implies
that either the number of unknowns in the system of equations is more
than the number of equations, $n > m$ or there are more equations than
the number of unknowns in which case some of the equations are linearly
dependent, $m > n$.

It is still possible to obtain a solution.
dfg \eqref{eq:d}  .



$$
\begin{equation}
  LaTeX_math_expression
  \label{eq:label_name}
\end{equation}
$$

Can be referenced as \eqref{eq:label_name}.

